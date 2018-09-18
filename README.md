# Caddyfile

## Usage
0. Install caddy
```
curl https://getcaddy.com | bash -s personal
```

1. Clone
```
sudo git clone https://github.com/acintosh/caddyfile /opt/caddy
```

1. Copy service file.
```
cd /opt/caddy
sudo cp ./caddy.service /etc/systemd/system/
```

1. Add user
```
sudo useradd caddy -s /sbin/nologin -r
```

1. Set permission. #! You need to replace $(which caddy)
```
sudo chmod 600 ./Caddyfile
sudo chmod 600 ./start.sh
sudo chown caddy ./Caddyfile
sudo chown caddy ./start.sh
sudo setcap 'cap_net_bind_service=+ep' $(which caddy)
```

1. Setting systemd
```
sudo systemctl daemon-reload
sudo systemctl start caddy.service
sudo systemctl enable caddy.service
systemctl status caddy.service
```
