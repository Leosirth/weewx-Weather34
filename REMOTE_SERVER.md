To use a remote webserver(s) to display the Weather34 template the 
following are required to be setup: -

**RSYNC** 

Instructions for the use of rsync with WeeWX can be found at http://weewx.com/docs/usersguide.htm#config_RSYNC. If the machines are not on the same local network or you require secure communications, SSH keys need to be created for running weewx on both the remote webserver(s) and the weewx machine. This can sometimes be a tricky process to setup. An excellent tutorial can be found at https://www.digitalocean.com/community/tutorials/how-to-copy-files-with-rsync-over-ssh

**Webserver** 

In the weewx.conf file the webserver_address needs to be the ip address of the webserver(s) or a DNS name that a lookup can be done to get an IP address. This can be a comma separated list if there are more than one remote webserver.

**Open a Port**

Port 25252 needs to be open on the weewx machine and all the remote webserver machine(s) and any network device between these machines.

**Reverse Proxy**

If a reverse proxy is used in front of you weewx server and a routing has been setup for 25252 port (or what configured in weewx_port) you can set the weewxserver_reverseProxy property in the weewx.conf point to your reverse proxy in this format:

```
<reverseProxy_Host>:<reverseProxy_Port>
```

i.e.

```
weewxserver_reverseProxy = my-weewx-server-reverseProxy:80
```

Right now HTTPS protocol is NOT supported, please configure your reverse proxy to HTTP for this routing.

**Further Reading**

An excellent online guide by User Chris Alemany can be found at https://www.chrisalemany.ca/2021/02/24/installing-the-weather34-skin-on-weewx-with-remote-web-server-2021-edition/
