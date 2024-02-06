# debian-12

debian 11 upgrade 12
``
https://www.cyberciti.biz/faq/update-upgrade-debian-11-to-debian-12-bookworm/
``

bbr
```
https://wiki.crowncloud.net/?How_to_enable_BBR_on_Debian_12#How+to+Enable+BBR+on+Debian+12
```


docker
```
https://docs.docker.com/engine/install/debian/
```


```
apt install python3-setuptools -y
apt install python3-dev -y
apt install build-essential -y
apt install python3-psutil
apt install vnstat -y
```

```
mkdir /opt/serverstatus
cd /opt/serverstatus


```


```
[Unit]
Description=Server Status
After=rc-local.service
After=network.target

[Service]
Type=simple
User=root
Group=root
WorkingDirectory=/opt/serverstatus
ExecStart=/usr/bin/python3 /opt/serverstatus/client-psutil.py SERVER=status.starbuckss.xyz USER=xxx PASSWORD=xxx
ExecReload=/bin/kill -HUP $MAINPID
StandardOutput=syslog
StandardError=syslog
Restart=always

[Install]
WantedBy=multi-user.target
```


```
apt install chrony -y
vi /etc/chrony/chrony.conf
systemctl restart chrony.service
systemctl status chrony.service
systemctl enable chrony.service
```
