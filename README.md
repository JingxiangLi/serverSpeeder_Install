-----------------------------   
#\#  serverSpeeder Install  \#                           
-----------------------------      
----------------------------- 
#Debian 7  3.2.0-4   
安装
```
wget --no-check-certificate -O appex.sh https://raw.githubusercontent.com/0oVicero0/serverSpeeser_Install/master/appex.sh && chmod +x appex.sh && bash appex.sh install
```    
卸载    
```
wget --no-check-certificate -O appex.sh https://raw.githubusercontent.com/0oVicero0/serverSpeeser_Install/master/appex.sh && chmod +x appex.sh && bash appex.sh unstall
```  
----------------------------- 
Nginx反代 (锐速检测许可证,嫌麻烦可不设置)
```
echo "$yourIP dl.serverspeeder.com" > /etc/hosts
```
```
	server {
		listen 80;
		server_name dl.serverspeeder.com;
		location /  {
			proxy_pass http://serverspeeder.azurewebsites.net;
		}
	}
```
----------------------------- 
-----------------------------
部分用法说明(制作一键脚本,或手动安装)
-----------------------------
具体用哪个内核看(搜索)这个文件
```
https://github.com/0oVicero0/serverSpeeder_kernel/blob/master/serverSpeeder.txt
```
改内核文件名字
下载链接是下面这样的(变量$1,$2,$3,$4,$5,$6)  
```
https://raw.githubusercontent.com/0oVicero0/serverSpeeder_kernel/master/$1/$2/$3/$4/$5/$6
```
下载后文件名改成这样  ```acce-$5-[$1_$2_$3]```
如果不改名字,可能会触发某个BUG(Debian下会触发,别的系统没用过,不清楚。)
许可证的话在这里生成: ```http://serverspeeder.azurewebsites.net/```
需要填写你网卡的MAC地址,点击OK就可以了.
也可以直接在服务器上运行下面这句:
```
wget http://serverspeeder.azurewebsites.net/lic?mac=$(ifconfig |grep -B1 "$(wget -qO- ipv4.icanhazip.com)" |awk '/HWaddr/{ print $5 }')
```
Azure 东南亚机房,大佬们别搞我啊！
