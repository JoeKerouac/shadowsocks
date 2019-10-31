# 说明
本vpn支持centos（centos7亲测可用）、Debian、Ubuntu
交互式使用方法：只需运行下列命令即可（运行过程中会让设置密码，如果不设置密码默认是qwer1234）
```
git clone https://github.com/JoeKerouac/shadowsocks
cd shadowsocks
chmod +x shadowsocks-go.sh
./shadowsocks-go.sh 2>&1 | tee shadowsocks-go.log
```

命令行参数式使用方法：
```
git clone https://github.com/JoeKerouac/shadowsocks
cd shadowsocks
./shadowsocks-go-withparam.sh install -p [password] -P [port] -c [cipher]
```
其中建议使用`-p`来替换默认密码，端口号和加密方式可以使用默认的，默认端口号10001，默认加密方式aes-256-cfb


文件清单：
- shadowsocks-go:启动脚本
- shadowsocks-go-debian:Debian启动脚本
- shadowsocks-go.sh:安装脚本
- shadowsocks-go-withparam.sh:安装脚本
- shadowsocks-server-linux32-1.2.1.gz:32位安装文件
- shadowsocks-server-linux64-1.2.1.gz:64位安装文件


# centos7环境一键初始化
使用下面的脚本可以在centos7环境一键安装初始化shadowsocks。
```
#!/bin/sh

cd /root
# 安装Git
yum install -y git
# 下载项目
git clone https://github.com/JoeKerouac/shadowsocks.git
# 切换目录
cd shadowsocks
# 安装，默认密码Qwer1234，端口1995，建议修改密码
sh shadowsocks-go-withparam.sh install -p Qwer1234 -P 1995 -c aes-256-cfb

# 防火墙打开
firewall-cmd --zone=public --add-port=1995/tcp
firewall-cmd --zone=public --add-port=1995/udp
```