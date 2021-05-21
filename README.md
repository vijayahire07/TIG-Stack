# TIG-Stack
This TIG stack is created for Syslog Analysis.
simply download the docker-compose file and fire up the TIG stack and your Syslog analysis server will be ready.

On rsyslog.conf forward all logs to TIG stack UDP port 6514.


after firing up Stack initial telegraf.conf file will be created in the current directory. edit the below configuration as below.

Note : Before firing docker-compose run below command to generate sample config.

docker run --rm telegraf telegraf config > telegraf.conf

[[inputs.syslog]]

server = "udp://:6514"
