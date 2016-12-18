# graylog-bro-content-pack
BRO IDS content pack contains pipeline rules, a stream, a dashboard displaying interesting activity, and a syslog tcp input to capture and index BRO logs coming from a Security Onion sensor. 

If you are not using Security Onion, the log files might be different and not contain the same exact fields. Also, if you are using an older version of Security Onion, these setting may not match either.

    See the full Description of BRO IDS Default Log files
    https://www.bro.org/sphinx/script-reference/log-files.html

    Working with BRO logs
    https://www.bro.org/sphinx/logs/index.html#working-with-log-files

# Provided Content
A Dashboard: BRO IDS Information - Last 24 Hours
A Stream: BRO IDS logs
An Input: ids-tcp-input on port 15514
And some pipeline rules to get started with

# Requirements
You must be running Graylog v2.2.0 or later because of the split pipeline function  
Bro 2.4.1 running on Security Onion  
Security Onion v14.04.x.x  

# Setup Steps
Configure Security Onion instance with SYSLOG-NG sending logs to a remote destination.

 1. Configure Graylog Input (Installed with Content pack)
 2. Configure Stream for Graylog (Installed with Content pack)
 3. Point Security Onion Sensor to Graylog (Manual Config on SO sensor)
 4. Configure Pipeline Rules (http://docs.graylog.org/en/2.1/pages/pipelines/usage.html#manage-rules)
 5. Configure Pipeline to process Rules (http://docs.graylog.org/en/2.1/pages/pipelines/usage.html#managing-pipelines)


        For a more detailed walk-through on setup for steps 1-3
        http://alias454.com/send-security-onion-logs-to-a-centralized-graylog-server/
