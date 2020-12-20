# [How to setup FTP server on Ubuntu 20.04 Focal Fossa Linux](https://linuxconfig.org/how-to-setup-ftp-server-on-ubuntu-20-04-focal-fossa-linux)

## install VSFTPD
```bash
$ sudo apt-get install vsftpd
```

## Configure FSFTPD server

1. keep a backup copy of the original config  file

```bash
$ sudo mv /etc/vsftpd.conf /etc/vsftpd.conf_orig
```

2. Create a new VSFTPD configuration file using nano

```bash
$ sudo nano /etc/vsftpd.conf
```

3. Copy the following base configuration into your file. 

   ```bash
   listen=NO
   listen_ipv6=YES
   anonymous_enable=NO
   local_enable=YES
   write_enable=YES
   local_umask=022
   dirmessage_enable=YES
   use_localtime=YES
   xferlog_enable=YES
   connect_from_port_20=YES
   chroot_local_user=YES
   secure_chroot_dir=/var/run/vsftpd/empty
   pam_service_name=vsftpd
   rsa_cert_file=/etc/ssl/certs/ssl-cert-snakeoil.pem
   rsa_private_key_file=/etc/ssl/private/ssl-cert-snakeoil.key
   ssl_enable=Yes
   pasv_enable=Yes
   pasv_min_port=10000
   pasv_max_port=10100
   allow_writeable_chroot=YES
   ```

   save changes and close the file.

4. Ubuntu's built-in firewall will block FTP traffic by default, but the  following command will create an exception in UFW to allow the traffic:

```bash
$ sudo ufw allow from any to any port 20,21,10000:10100 proto tcp
```

5. With the configuration file saved and the firewall rules updated, restart VSFTPD to apply the new changes:

```bash
$ sudo systemctl restart vsftpd
```

## Create an FTP user

**We can use the same account as administrator, but it is not safe.**

1. Use this first command to create a new account, and the second command to set a password for the account:

```bash
$ sudo useradd -m ftpuser
$ sudo passwd ftpuser
```

2. In order to verify that everything's working properly, you should store at least one file in `ftpuser`'s home directory. This file should be visible when we login to FTP in the next steps.

```bash
$ sudo bash -c "echo FTP TESTING > /home/ftpuser/FTP-TEST"
```

