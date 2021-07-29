# Debian Network Reinstall Script

## 甲骨文云服务器（ARM）：重装 Debian


一键脚本：登录名：root，密码：passwd123456，可自行修改

``` bash
curl -fLO https://raw.githubusercontent.com/bohanyang/debi/master/debi.sh && chmod a+rx debi.sh && sudo ./debi.sh --architecture arm64 --user root --password passwd123456
```

执行后，重启，开始 DD Debian 10

```
sudo shutdown -r now
```

