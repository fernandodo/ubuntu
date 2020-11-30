## Install Java JRE

[Install Oracle Java 15 via PPA in Ubuntu 20.04](http://ubuntuhandbook.org/index.php/2020/09/install-oracle-java-15-ubuntu-20-04-18-04-16-04/#comments)

```bash
sudo add-apt-repository ppa:linuxuprising/java

sudo apt update

sudo apt install oracle-java15-installer 
```
And after installed Oracle Java 15, check via `java --version` command.

## Install Eclipse

2 ways. 

### 1. Installing Eclipse using Snap [Easy]

Add CDT in marketplace.  or use command:

```bash
sudo snap install --classic eclipse
```



### 2. Install Eclipse Manually

1. download the installer from: https://www.eclipse.org/downloads/

2. extract:

   ```bash
   tar xfz ~/Downloads/eclipse-inst-linux64.tar.gz
   ```

3. Run installer

   ```
   ~/Downloads/eclipse-installer/eclipse-inst
   ```

4. (optional) create a desktop icon to launch the program.

```bash
nano ~/.local/share/applications/eclipse.desktop
```

Edit file:

```bash
[Desktop Entry]
Name=Eclipse Eclipse
Type=Application
Exec=/home/XXXXXX/eclipse/java-2020-03/eclipse/eclipse
Terminal=false
Icon=/home/XXXXXX/eclipse/java-2020-03/eclipse/icon.xpm
Comment=Eclipse Integrated Development Environment
NoDisplay=false
Categories=Development;IDE;
Name[en]=Eclipse
```

Make it executable

```bash
chmod +x ~/.local/share/applications/eclipse.desktop
```



## Reference:

[How to Install Eclipse IDE on Ubuntu 20.04 | 18.04](https://websiteforstudents.com/how-to-install-eclipse-ide-on-ubuntu-20-04-18-04/)