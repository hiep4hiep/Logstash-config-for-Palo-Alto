# Logstash-config-for-Palo-Alto
Logstash config file to get log from Palo Alto Networks Firewall &amp; Traps &amp; Cortex XDR
Put this file into /etc/logstash/conf.d/

This will pre-process every Palo Alto Networks log including: NGFW, Traps, Cortex XDR from XDR Data Lake.

After installing,  it will open 4 log receivers:
- Syslog TCP/UDP 5514 to get log from NGFW
- Syslog TCP/UDP 5515 to get log from Traps ESM
- TCP Syslog SSL 5519 to get log from Cortex Data Lake
- TCP Syslog SSL 6514 to get log from Cortex Data Lake (backup, if you need to separate log from  difference Cortex instances)

Following filter rule will pre-process and index these logs to different index repo on ElasticSearch. 

Enjoy correlating and searching for your Palo Alto Networks platform logs!
