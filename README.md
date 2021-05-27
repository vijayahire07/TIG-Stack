# TIG-Stack
This TIG stack is created for Syslog Analysis.
simply download the docker-compose file and fire up the TIG stack and your Syslog analysis server will be ready.

On rsyslog.conf forward all logs to TIG stack UDP port 6514.

*.*             @(o)xx.xx.xx.xx:6514;RSYSLOG_SyslogProtocol23Format

after firing up Stack initial telegraf.conf file will be created in the current directory. edit the below configuration as below.

Note : Before firing docker-compose run below command to generate sample config.

mkdir -p /volumes/influxdb

docker run --rm telegraf telegraf config > telegraf.conf

on the telegraf.conf uncomment these lines to receive logs from log server.
[[inputs.syslog]]

server = "udp://:6514"

Finally import Dashboard 12433 on grafana .
