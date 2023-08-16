# TIG-Stack
This TIG stack is created for Syslog Analysis.
simply download the docker-compose file and fire up the TIG stack and your Syslog analysis server will be ready.

On rsyslog.conf forward all logs to TIG stack UDP port 6514.

create new config file on rsyslog server path should be based on the linux flavour you are using.

/etc/rsyslog.d/70-TIG-stack.conf
```buildoutcfg
*.*             @(o)xx.xx.xx.xx:6514;RSYSLOG_SyslogProtocol23Format
```


after firing up Stack initial telegraf.conf file will be created in the current directory. edit the below configuration as below.

Note : Before firing docker-compose up -d run below command to generate sample config.
```buildoutcfg
mkdir -p /volumes/influxdb
```
fire up the docker containers by running below command.
```
docker-compose up -d
```
Finally import Dashboard 12433 on grafana .
