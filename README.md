# ntpserver

The ntpd package is already installed by default on WAGO (linux based) controller, in order to work as a NTP client.

To enable the NTP server on a WAGO Controller you can use the following command : 

```shell
ntpd -l
```

You can see the NTP request by looking using the packet capture tool tcpdump 
```shell
tcpdump port 123
```

To start the daemon at the controller startup, download the ntpserver script in the repo in /etc/init.d/ntpserver

Give it execution permission :
```shell
chmod 750 /etc/init.d/ntpserver
```

Add a symlink in /etc/rc.d : 
```shell
ln -s /etc/init.d/ntpserver /etc/rc.d/S99_ntpserver
```
