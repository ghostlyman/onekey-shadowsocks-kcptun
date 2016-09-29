# onekey-shadowsocks-kcptun 
一键部署shadowsock（影梭）和KCPtun（网络加速工具）到你的VPS服务器.  
###[English version](https://github.com/Joehaivo/onekey-shadowsocks-kcptun/blob/master/README-en.md)
***********
###运行环境:
服务端: Linux CentOS 6+
客户端: Windows 7+  Android 5.0+  

##第一步：安装shadowsocks到服务器
```bash
wget --no-check-certificate https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks.sh  
chmod +x shadowsocks.sh  
./shadowsocks.sh 2>&1 | tee shadowsocks.log  
```
[更多信息](https://github.com/Joehaivo/onekey-shadowsocks-kcptun/blob/master/shadowsocks-server-config.md)  

##第二步：安装KCPtun到服务器
```bash
wget https://raw.githubusercontent.com/kuoruan/kcptun_installer/master/kcptun.sh  
chmod +x ./kcptun.sh  
./kcptun.sh  
```
[更多信息](https://github.com/Joehaivo/onekey-shadowsocks-kcptun/blob/master/kcptun-server-config.md)

##第三步：为你的shadowsocks程序添加chacha20加密方式（可选步骤）
```bash
yum install m2crypto gcc -y  
wget -N --no-check-certificate https://download.libsodium.org/libsodium/releases/libsodium-1.0.8.tar.gz  
tar zfvx libsodium-1.0.8.tar.gz  
cd libsodium-1.0.8  
./configure  
make && make install  
echo "include ld.so.conf.d/*.conf" > /etc/ld.so.conf  
echo "/lib" >> /etc/ld.so.conf  
echo "/usr/lib64" >> /etc/ld.so.conf  
echo "/usr/local/lib" >> /etc/ld.so.conf  
ldconfig  
```

脚本来源：[teddysun](https://github.com/teddysun)  [kuoruan](https://github.com/kuoruan)
