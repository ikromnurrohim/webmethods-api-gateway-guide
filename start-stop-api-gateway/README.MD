# API Gateway Administration

### Before you begin
Elasticsearch does several checks before starting up, Software AG recommends that you review the bootstrap checks and important system configuration settings before starting the data store. In particular, you may need to adjust these settings:

- Check the settings for the system-wide maximum number of file descriptors (kernel parameter fs.file-max) by executing the command sysctl -a | fgrep fs.file-max . If the value is less than 65536, log on as the root user and increase the value by executing sysctl -w fs.file-max=200000 or echo "fs.file-max=65536" >> /etc/sysctl.conf, then activate the new value by executing sysctl -p 

- Check the data store user settings for the maximum number of open file descriptors by executing the commands ulimit -Hn and ulimit -Sn, where -Hn is the hard limit and -Sn is the soft limit. If the value is less than 65536, log on as the data store user and increase the value to at least 65536 by executing ulimit -n 65536. To permanently save this setting for the user, execute the following:
```
echo "user_name soft nofile 65536" >> /etc/security/limits.conf
echo "user_name hard nofile 65536" >> /etc/security/limits.conf
```

- Check the setting for the system-wide maximum map count (kernel parametervm.max_map_count) by executing the command sysctl -a | fgrepvm.max_map_count. If the value is less than 262144, log on as the rootuser and increase the value to at least 262144 by executing sysctl -wvm.max_map_count=262144 or echo " vm.max_map_count=262144" >> /etc/sysctl.conf, then activate the new value by executing sysctl -p.

- Check the data store user settings for the maximum number of processes by executing the command ulimit -u. If the value is less than 4096, log on as the data store user and increase the value to at least 4096 by executing ulimit -n 4096. To permanently save this setting for the user, execute the following:
```
echo "user_name soft nproc 4096" >> /etc/security/limits.conf
echo "user_name hard nproc 4096" >> /etc/security/limits.conf
```

### Starting API Gateway
To starting, stoping and restarting go to the directory:
```
<SoftwareAGInstallDir>/profiles/IS_<instance_name>/bin/
```

For starting:
```
sh startup.sh
```

For stoping:
```
sh shutdown.sh
```

For restarting:
```
sh restart.sh
```

If you wanna see the log API Gateway for starting, stoping or restarting <br>
Go to directory
```
<SoftwareAGInstallDir>/IntegrationServer/instances/<instance_name>/logs/
```

To see with updated log, you can use this command
```
tail -f server.log 
```

To read whole the file use this command 
```
cat server.log 
```