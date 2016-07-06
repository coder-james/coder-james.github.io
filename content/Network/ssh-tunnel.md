---
title: "ssh tunnel"
date: 2016-07-02 09:04
---

####SSH SOCKS5代理
#####访问内网机器

- 机器A 端口port1  
  内网主机，即要访问的主机
- 机器B 端口port2  
  跳板主机，即双网卡机器，可访问内网和外网
- 机器C 端口port3  
  请求主机
  
#####建立SOCKS5代理
在机器C上建立SOCKS5代理

`ssh -N -f -D 127.0.0.1:port3  [user]@[机器B IP] -p [port2]`

期间可能需要输入[user]登录密码验证

#####使用SOCKS5代理
######Chrome SwitchySharp插件

设置如下：

![alt text](../attach/chromescreenshot.png) 

于是通过chrome浏览器就可以访问内网服务器了。