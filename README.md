# prometheus-grafana
### 使用prometheus+grafana实现服务监控（并可以集成springboot）


* 参考连接： 
* 案例一：https://www.linuxidc.com/Linux/2017-06/144972.htm   实现再mysql服务的监控（本案例我已在虚拟机进行搭建学习)
* grafana dashboard 的配置：https://www.jianshu.com/p/82abd86ef447
* 案例2：https://myblog.qinxuewu.club/index.php/archives/38.html

#### 案例一：

* 在各自安装目录下启动：
* 启动prometheus：nohup ./prometheus -config.file=prometheus.yml&
* 登录prometheus: http://192.168.2.31:9090/
* 启动客户端：nohup ./node_exporter &
* 启动MySQL监控客户端： nohup ./mysqld_exporter --config.my-cnf=".my.cnf" &

![image](https://www.linuxidc.com/upload/2017_06/170619163967335.png)

* 安装后启动grafana： 
```
[root@sun /]#  systemctl start grafana-server
[root@sun /]# ps aux |grep grafana
grafana    4153  1.6  0.9 351008 17840 ?        Ssl  14:05   0:00 /usr/sbin/grafana-server --config=/etc/grafana/grafana.ini --pidfile= cfg:default.paths.logs=/var/log/grafana cfg:default.paths.data=/var/lib/grafana cfg:default.paths.plugins=/var/lib/grafana/plugins
root       4169  0.0  0.0 112720   984 pts/0    S+   14:05   0:00 grep --color=auto grafana
```
* 登录grafana: http://192.168.2.31:3000
