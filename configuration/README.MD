# API Gateway Configuration
API Gateway has some configuration to meet your goals, in this article we just provide basic configuration for setting platform resource from JVM API Gateway and API Gateway Data Store.

## API Gateway JVM Setting
API Gateway JVM setting locate in this file:
```
<SoftwareAGInstallDir>/profiles/IS_<instance_name>/configuration/custom_wrapper.conf
```

to update the jvm init and max, can be done using vi or nano command.
using this command:
```
vi custom_wrapper.conf 
or 
nano custom_wrapper.conf 
```

update two line below with value you want it, in this example I will give 1GB on init memory and maxmemory:
```
wrapper.java.initmemory=1024
wrapper.java.maxmemory=1024
```

anw, software ag recomendation to give same value in this jvm config (init and max).


## API Gateway Data Store JVM Setting
API Gateway Data Store jvm setting locate in this file:
```
<SoftwareAGInstallDir>/InternalDataStore/config/jvm.options
```
the default init and max is 2GB if your computer memory is very small, you can adjust that to 512m.

to update the jvm init and max, can be done using vi or nano command.
using this command:
```
vi jvm.options 
or 
nano jvm.options 
```

update two line below with value you want it, in this example I will give 512m on init memory and maxmemory:
```
-Xms512m
-Xmx512m
```

