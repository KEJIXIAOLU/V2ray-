# VPS一键搭建V2ray教程
## 准备工作
- 1、已经解析的域名，Win+R输入CMD 回车：键入ping 空格输入你的域名，检查一下是否可以ping通
- 2、一台境外VPS主流系统，例如：Debian/Ubuntu/CentOS
- 3、下载并安装FinalShell SSH工具

Windows版下载地址: http://www.hostbuf.com/downloads/finalshell_install.exe

macOS版下载地址: http://www.hostbuf.com/downloads/finalshell_install.pkg

 ### VPS服务器
Vultr注册链接：https://www.vultr.com/?ref=8941832-8H

VPS操作系统选择：Debian 10 x64


## V2Ray一键安装代码：


    bash <(curl -sL https://raw.githubusercontent.com/eujc/v2ray/main/xray.sh)



## 放行端口
### Debian/Ubuntu  放行端口
例如要放行80端口

    iptables -I INPUT -p tcp --dport 80 -j ACCEPT

然后保存放行规则

    iptables-save



### Centos  放行端口
例如要放行80端口

    firewall-cmd --zone=public --add-port=80/tcp --permanent

然后重启防火墙

    firewall-cmd --reload

### 查看防火墙规则

    iptables -L
    
    




