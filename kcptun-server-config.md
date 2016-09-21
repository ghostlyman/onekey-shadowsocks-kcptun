##kcptun configuration file in /usr/share/kcptun/server-config.json(sample):  
```bash
{
	"listen": ":29900",
	"target": "YourVPSIP:YourShadowsocksPort",
	"crypt": "aes",
	"mode": "fast",
	"mtu": 1350,
	"sndwnd": 1024,
	"rcvwnd": 1024,
	"datashard": 10,
	"parityshard": 3,
	"dscp": 0,
	"nocomp": false
}
```
##manage kcptun:  
```bash
supervisorctl {restart|start|stop} kcptun
```
##Log path:  
```bash
/var/log/kcptun.log 
```
