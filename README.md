# debian-12

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
