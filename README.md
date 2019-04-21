# graylog-bro-content-pack
BRO/Zeek IDS content pack contains pipeline rules, a stream, a dashboard displaying interesting activity, and a syslog tcp input to capture and index logs coming from a BRO/Zeek sensor. 

If you are using Security Onion or an older versin of BRO/Zeek, the log files might be different and not contain the same exact fields.

    See the full Description of BRO IDS Default Log files
    https://www.bro.org/sphinx/script-reference/log-files.html

    Working with BRO logs 
    https://www.bro.org/sphinx/logs/index.html#working-with-log-files

# Provided Content
A Dashboard: BRO IDS Information - Last 24 Hours  
A Stream: BRO IDS logs  
An Input: ids-tcp-input on port 15514  
Pipeline rules to get started with  
Rsyslog conf to get started with  
  > **00-bro.conf** should go in the /etc/rsyslog.d/ directory after editing the appropriate values for your setup
  > If selinux is enabled run **semanage port -a -t syslogd_port_t -p tcp 15514**

# Requirements
Graylog v2.2.0 or later because of the split pipeline function  
Rsyslog 8.x to use the replace() function if using rsyslog to ship logs  
Bro 2.5.3 to use the pipeline files out of the box  
  > editing pipeline configs will be required if using older versions of BRO  

Security Onion:  
If running with SO verify pipeline field values prior to sending data  

# Setup Steps

  1. Configure Graylog Input (Installed with Content pack)
  2. Configure Stream for Graylog (Installed with Content pack)
  3. Point BRO Sensor to Graylog (Manual Config on BRO sensor)
    - Configure rsyslog or syslog-ng to allow sending logs to a remote source  
  4. Configure Pipeline Rules (http://docs.graylog.org/en/2.4/pages/pipelines/usage.html#manage-rules)
  5. Configure Pipeline to process Rules (http://docs.graylog.org/en/2.4/pages/pipelines/usage.html#managing-pipelines)


        For a more detailed walk-through on setup for steps 1-3  
        http://alias454.com/send-security-onion-logs-to-a-centralized-graylog-server/
