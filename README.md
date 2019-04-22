# graylog-bro-content-pack
BRO/Zeek IDS content pack contains pipeline rules, a stream, a dashboard displaying interesting activity, and a syslog tcp input to capture and index logs coming from a BRO/Zeek sensor. 

If you are using Security Onion or an older versin of BRO/Zeek, the log files might be different and not contain the same exact fields.

    See the full Description of Zeek IDS Default Log files
    https://www.zeek.org/sphinx/script-reference/log-files.html

    Working with Zeek logs 
    https://www.zeek.org/sphinx/logs/index.html#working-with-log-files

## Releases
Content for older versions of Graylog https://github.com/alias454/graylog-bro-content-pack/releases

# Provided Content
A Dashboard: BRO/Zeek IDS Information - Last 24 Hours  
A Stream: BRO/Zeek IDS logs  
An Input: ids-tcp-input (default port 13514)  
Pipeline rules to get started with  
Rsyslog conf to get started with  
  > **00-bro.conf** should go in the /etc/rsyslog.d/ directory after editing the appropriate values for your setup
  > If selinux is enabled run **semanage port -a -t syslogd_port_t -p tcp 15514**

# Requirements
Graylog v3.x.x or later for new content pack handling features  
Rsyslog 8.x to use the replace() function if using rsyslog to ship logs  
BRO/Zeek 2.6.x to use the pipeline files out of the box  
  > editing pipeline configs will be required if using older versions of BRO  

Security Onion:  
If running with SO, verify pipeline field values prior to sending data  

# Setup Steps

  1. Configure Graylog Input (Installed with Content pack)
  2. Configure Stream for Graylog (Installed with Content pack)
  3. Configure Pipeline Rules Processing (Installed with Content pack)
  4. Point BRO/Zeek Sensor to Graylog (Manual Config on sensor)
    - Configure rsyslog or syslog-ng to allow sending logs to a remote source  

## Additional Setup Information
    Manual pipeline rule setup  
    http://docs.graylog.org/en/3.0/pages/pipelines/usage.html#configuration  

    For a more detailed walk-through on setup for steps 1-3  
    http://alias454.com/send-security-onion-logs-to-a-centralized-graylog-server/
