session和log： ~/.aria2/aria2.session 和 ~/.aria2/aria2.log
## My config file
配置文件： ~/.aria2/aria2.conf 
```bash
# place under ${HOME}/.aria2/

# Daemonize, rpc and session save.
# The daemon is launched by the rpc query and
# stops when all downloads are completed.

## 文件保存相关 ##
dir=/home/feluxa/Downloads
file-allocation=trunc
continue=true

## 下载连接相关 ##
max-concurrent-downloads=10
max-connection-per-server=10
min-split-size=10M
split=5
disable-ipv6=true

## 进度保存相关 ##
save-session=/home/feluxa/.aria2/session
input-file=/home/feluxa/.aria2/session
save-session-interval=60

## RPC相关设置 ##
enable-rpc=true
pause=false
rpc-allow-origin-all=true
rpc-listen-all=true
rpc-save-upload-metadata=true
rpc-secure=false

## BT/PT下载相关 ##
listen-port=51413
enable-dht=true
bt-enable-lpd=true
enable-peer-exchange=false
user-agent=Transmission/2.92
seed-ratio=1.0
seed-time=30
bt-save-metadata=true

#下载完成后删除.ara2的同名文件
on-download-complete = rm -f "$3.aria2" 
# on-download-complete=exit
```
## 启动服务
-D 以Daemon的方式启动 `# aria2c -D`
将次命令放入startup application就可以开机运行
查看是否运行`# ss -tulpn | grep aria2c`

## 浏览器集成
### firefox
(Aria2 Download Manager Integration)[https://addons.mozilla.org/en-US/firefox/addon/aria2-integration/]


[1]: http://ivo-wang.github.io/2019/04/18/%E5%85%B3%E4%BA%8Earia2%E6%9C%80%E5%AE%8C%E6%95%B4%E7%9A%84%E4%B8%80%E7%AF%87/	"关于aria2最完整的一篇"
[2]: https://kzpu.com/archives/3620.html	"删除aria2下载完成后生成的.aria2后缀文件"

