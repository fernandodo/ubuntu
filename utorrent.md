# [How to Install uTorrent in Ubuntu 20.04](https://www.linuxbabe.com/ubuntu/install-utorrent-ubuntu-20-04)

Once downloaded, change working directory to the directory where  uTorrent server file is downloaded. Then run the following command to  extract the `tar.gz` file to `/opt/` directory.

```bash
sudo tar xvf utserver.tar.gz -C /opt/
```

Next, install required dependencies by executing the following commands.

```bash
sudo apt install libssl-dev
wget http://archive.ubuntu.com/ubuntu/pool/main/o/openssl1.0/libssl1.0.0_1.0.2n-1ubuntu5.3_amd64.deb

sudo apt install ./libssl1.0.0_1.0.2n-1ubuntu5.3_amd64.deb
```

After the dependencies are installed, create a symbolic link.

```bash
sudo ln -s /opt/utorrent-server-alpha-v3_3/utserver /usr/bin/utserver
```

Use the following command to start uTorrent server. By default, uTorrent server listens on `0.0.0.0:8080`. If there’s another service also listens on port 8080, you should  temporarily stop that service. uTorrent will also use port 10000 and  6881. The `-daemon` option will make uTorrent server run in the background.

```bash
utserver -settingspath /opt/utorrent-server-alpha-v3_3/ -daemon
```

You can now visit the uTorrent web UI in your browser by typing in the following text in the web browser address bar.

```bash
your-server-ip:8080/gui
```

If you are installing uTorrent on your local computer, then replace `your-server-ip` with `localhost`.

```bash
localhost:8080/gui
```

后面不想学了. 因为试试效果不好.