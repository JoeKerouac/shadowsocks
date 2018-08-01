本vpn支持centos（centos7亲测可用）、Debian、Ubuntu
使用方法：只需运行下列命令即可（运行过程中会让设置密码，如果不设置密码默认是qwer1234）
```
git clone https://github.com/JoeKerouac/shadowsocks
cd shadowsocks
chmod +x shadowsocks-go.sh
./shadowsocks-go.sh 2>&1 | tee shadowsocks-go.log
```

文件清单：
- shadowsocks-go:启动脚本
- shadowsocks-go-debian:Debian启动脚本
- shadowsocks-go.sh:安装脚本
- shadowsocks-server-linux32-1.2.1.gz:32位安装文件
- shadowsocks-server-linux64-1.2.1.gz:64位安装文件