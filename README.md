# sshuttle for YOSEMITE 10.10
```
$ mkdir -p /usr/local/libexec; cd /usr/local/libexec
$ git clone git://github.com/apenwarr/sshuttle.git
$ ln -s /usr/local/libexec/sshuttle/sshuttle /usr/local/bin
```
here is command 
```
sshuttle --dns -r username@example.com 0/0
```
These are the aliases I use to make setting up and tearing down the tunnel easier:
```
alias tunnel='sshuttle --dns --daemon --pidfile=/tmp/sshuttle.pid -r username@example.com 0/0'
alias tunnelx='[[ -f /tmp/sshuttle.pid ]] && kill $(cat /tmp/sshuttle.pid) && echo "Disconnected."'
```
