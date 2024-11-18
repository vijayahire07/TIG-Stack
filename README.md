# TIG-Stack
This TIG stack is created for Syslog Analysis.
simply download the docker-compose file and fire up the TIG stack and your Syslog analysis server will be ready.




after firing up Stack initial telegraf.conf file will be created in the current directory. edit the below configuration as below.

Note : Before firing docker-compose up -d run below command to generate sample config.
```buildoutcfg
mkdir -p /volumes/influxdb
```
fire up the docker containers by running below command.
```
docker-compose up -d
```
add datasourse using influxdb. 
use HTTP URL as : "http://influxdb:8086"
database name   : telegraf


Finally import Dashboard 12433 on grafana .



create new config file on rsyslog server path should be based on the linux flavour you are using.
On rsyslog.conf forward all logs to TIG stack UDP port 6514.

vim /etc/rsyslog.d/70-TIG-stack.conf
```buildoutcfg
*.*;sshd,auth,crond.*,authpriv.none             @(o)xx.xx.xx.xx:6514;RSYSLOG_SyslogProtocol23Format
```
