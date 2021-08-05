# Debian Network Reinstall Script

## 甲骨文云服务器（ARM）：重装 Debian


一键脚本：登录名：root，密码：passwd123456，可自行修改

``` bash
curl -fLO https://raw.githubusercontent.com/veip007/debi/master/debi.sh && chmod a+rx debi.sh && sudo ./debi.sh --architecture arm64 --user root --password passwd123456
```

执行后，重启，开始 DD Debian 10

```
sudo shutdown -r now
```

## 更新内核至5.10  

1、添加 back­ports 源

可能需要的依赖：
```bash 
apt install sudo lsb-release -y
```


``` bash
echo "deb http://deb.debian.org/debian $(lsb_release -sc)-backports main" | tee /etc/apt/sources.list.d/backports.list
```
2.更新
```
apt update
```
3.执行内核升级命令
```bash
apt -t $(lsb_release -sc)-backports install linux-image-$(dpkg --print-architecture) linux-headers-$(dpkg --print-architecture) --install-recommends -y
```
4.安装完重启，执行 uname -r 命令，现在已经是5.10了。
