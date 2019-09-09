# telegraf-configs
snippets of telegraf configuration for monitoring various things

### cisco-csr-1000v-restconf.conf
Uses telegraf's [inputs.http](https://github.com/influxdata/telegraf/tree/master/plugins/inputs/http) plugin to query the CSR 1000V RESTCONF HTTPS API and return the hostname of device. This is used as a basic check to make sure RESTCONF is running and returning data after authentication.

```
$ telegraf --config cisco-csr-1000v-restconf.conf --input-filter http --test
2019-09-09T16:10:45Z I! Starting Telegraf 1.11.2
> cisco_restconf,host=myserver.mydomain.com,url=https://10.0.1.250/restconf/data/Cisco-IOS-XE-native:native/hostname Cisco-IOS-XE-native:hostname="CSR1000V-TEST1" 1568045446000000000
> cisco_restconf,host=myserver.mydomain.com,url=https://10.0.1.251/restconf/data/Cisco-IOS-XE-native:native/hostname Cisco-IOS-XE-native:hostname="CSR1000V-TEST2" 1568045446000000000
> cisco_restconf,host=myserver.mydomain.com,url=https://10.0.1.252/restconf/data/Cisco-IOS-XE-native:native/hostname Cisco-IOS-XE-native:hostname="CSR1000V-TEST3" 1568045446000000000
> cisco_restconf,host=myserver.mydomain.com,url=https://10.0.1.253/restconf/data/Cisco-IOS-XE-native:native/hostname Cisco-IOS-XE-native:hostname="CSR1000V-TEST4" 1568045446000000000
```
