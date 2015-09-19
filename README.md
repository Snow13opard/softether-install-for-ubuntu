# softether-install-for-ubuntu

## Coming soon.
## Currently working on
First install lynx on your server:
```
apt-get install lynx -y
```
Download SoftEther with these commands:
```
cd ~/
```
```
wget https://raw.githubusercontent.com/Snow13opard/softether-install-for-ubuntu/master/softetherupdatelynx
```
```
lynx -cmd_script=softetherupdatelynx http://www.softether-download.com/files/softether/
```
Install and Configure SoftEther
```
tar xzvf softether* && mv softether* /tmp
```
```
apt-get install build-essential -y
```
```
cd vpnserver
```
```
make
```
```
cd ..
```
```
sudo cp -r vpnserver /usr/local
```
```
cd /usr/local/vpnserver/
```
And then change the files permission in order to protect them:
```
chmod 600 *
chmod 700 vpnserver
chmod 700 vpncmd
```

sudo apt-get install supervisor

sudo service supervisor start

sudo nano /etc/supervisor/conf.d/softether.conf
```
[program:softether]
command = /usr/local/vpnserver/vpnserver start
stopsignal = stop
user = root
autostart = true
autorestart = true
stdout_logfile = /var/log/supervisor/softether.log
stderr_logfile = /var/log/supervisor/softether_err.log
```
Save the file.

sudo supervisorctl reload
