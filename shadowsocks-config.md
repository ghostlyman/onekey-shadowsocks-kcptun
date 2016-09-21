##shadowsocks config-json in /etc/shadowsocks.json:
```bash
{
"server":"your_VPS_IP",
"server_port":8388,
"local_address":"127.0.0.1",
"local_port":1080,
"password":"MyPassword",
"timeout":300,
"method":"chacha20",
"fast_open": false
}
```
##manage shadowsocks:
```bash
/etc/init.d/shadowsocks {start|stop|restart|status}
OR
ssserver -c /etc/shadowsocks.json -d {start|stop|restart|status}
```
##Log path:  
```bash
/var/log/shadowsocks.log  
```
