# Python3 Supervisor 通用模板
### 使用配置
此文件夹需放到 ==/opt/supervisor== 目录下  
若改变目录需要同时修改 ==supervisord.conf==、==supervisord.service==、==conf==目录下的配置文件里面 /opt/supervisor 的路径
---
### 启动
```
supervisord  
说明：
1. $CWD/supervisord.conf 也就是当前目录（默认）  
2. $CWD/etc/supervisord.conf 也就当前目录下的etc目录  
3. /etc/supervisord.conf 的配置文件
```
```
supervisord -c /opt/supervisor/supervisord.conf #到指定路径下去找配置文件
```
### 查看状态
```
supervisorctl  
说明：
1. $CWD/supervisord.conf 也就是当前目录（默认）  
2. $CWD/etc/supervisord.conf 也就当前目录下的etc目录  
3. /etc/supervisord.conf 的配置文件
```
```
supervisorctl -c /opt/supervisor/supervisord.conf #到指定路径下去找配置文件
```
### supervisor 在 CentOS7 中开机启动  
```
1. 将 supervisord.service 放到 /usr/lib/systemd/system 目录下  
2. 运行 systemctl start supervisord 命令启动服务  

其他Linux系统开机启动参见： https://github.com/Supervisor/initscripts
```
### 目录说明

```
|-- conf                --> 需要监控的程序的配置文件的存放路径
    |-- test.conf       --> 需要监控的程序的配置文件（示例）
|-- log                 --> supervisor 日志的存放路径
    |-- supervisord.log --> supervisor 日志
|-- pid                 --> supervisor pid文件的存放路径
|-- run_log             --> 监控的程序的日志文件的存放路径
    |-- test.log        --> 监控的程序的日志文件（示例）
|-- sock                --> supervisor sock文件的存放路径
|-- supervisord.conf    --> supervisor 配置文件
|-- supervisord.service --> 此文件用于 centos7 注册服务
```
