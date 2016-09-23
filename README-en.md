# onekey-shadowsocks-kcptun
An easy way to implement shadowsocks service and kcptun service for your VPS.  
***********
###Operating environment:
Server: Linux CentOS 7  
Client: Windows 7/8/10  Android 5.0+  

##Step 1: Install shadowsocks service to server.  
```bash
wget --no-check-certificate https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks.sh  
chmod +x shadowsocks.sh  
./shadowsocks.sh 2>&1 | tee shadowsocks.log  
```
[More information](https://github.com/Joehaivo/onekey-shadowsocks-kcptun/blob/master/shadowsocks-server-config.md)  

##Step 2: Install kcptun service to server.  
```bash
wget https://raw.githubusercontent.com/kuoruan/kcptun_installer/master/kcptun.sh  
chmod +x ./kcptun.sh  
./kcptun.sh  
```
[More information](https://github.com/Joehaivo/onekey-shadowsocks-kcptun/blob/master/kcptun-server-config.md)

##Step 3: Install chacha20 encryption for shadowsocks service.  
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

