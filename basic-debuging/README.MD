# Basic Debuging API Gateway
If you are new to install and config API Gateway, maybe you want to know how to check API Gateway is up and running, or it's API Gateway up and running but you can't access it.


### Check Availability Port 
using this command:
```
netstat -ntlp
```


### Are API Gateway UP and Running ?
to know the API gateway up and running, first you can check the available port,
if the result showing the port of the api gateway and also the integration server which is port 9072, and also 5555 it's mean the api gateway up and runing. 


### Are API Gateway Data Store UP and Running ?
api gateway is store the data in the API Gateway Data Store which have default port 9240, so if that port is not avaliable, then startup the API Gateway Data Store:
```
cd <SoftwareAGInstallDir>/InternalDataStore/bin/
sh startup.sh 
```
after the startup is done, then check again the port 9240 to makesure that Data Store is up and running.

### The API Gateway and API Gateway Data Store Up and Running but can Access it through Browser.
First check the firewall status using this command:
```
sudo systemctl status firewalld
```
if the firewall is active(running) then check are API Gateway and Data Store port is registered on firewall or not, using this command
```
sudo firewall-cmd --list-port
```
the result of above command is to see which port are allowed to access from outside, if there are not available port API Gateway and Data Store in the result, register that port using this command:
```
sudo firewall-cmd --add-port=5555/tcp --zone=public --permanent
sudo firewall-cmd --add-port=9072/tcp --zone=public --permanent
sudo firewall-cmd --add-port=9240/tcp --zone=public --permanent
```
5555 is port Integration Server,
9072 is port API Gateway UI,
9240 is port API Gateway Data Store. <br>

after registering that port, we need to reload the firewall using this command:
```
sudo firewall-cmd --reload
```

then try to access API Gateway UI through Browser.


### API Gateway Has Started but can't UP.
If you are runnig API Gateway from ```<SoftwareAGInstallDir>/profiles/IS_<instance_name>/bin/``` but you have been check the server.log, the server not up. \
for this situation, first shutdown your API Gateway after that run command 
```ls -la``` in this directory ```<SoftwareAGInstallDir>/profiles/IS_<instance_name>/bin/``` \
if the the results available file within named **.lock** and **wrapper.anchor** then remove both file, after that startup again the API Gateway.