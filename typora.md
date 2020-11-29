
## Installation instructions for different flavours of Linux.

1. Debian/Ubuntu
```bash

# or use
# sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys BA300B7755AFCFAE
wget -qO - https://typora.io/linux/public-key.asc | sudo apt-key add -

# add Typora's repository
sudo add-apt-repository 'deb https://typora.io/linux ./'
sudo apt-get update

# install typora
sudo apt-get install typora
```
2. Mint
```bash
# or use
# sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys BA300B7755AFCFAE
wget -qO - https://typora.io/linux/public-key.asc | sudo apt-key add -

# add Typora's repository
echo -e "\ndeb https://typora.io/linux ./" | sudo tee -a /etc/apt/sources.list
sudo apt-get update

# install typora
sudo apt-get install typora
```

[1]: https://support.typora.io/Typora-on-Linux/	"" Install typora on Linux ""

