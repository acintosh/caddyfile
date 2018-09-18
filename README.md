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

2. Copy service file.
```
cd /opt/caddy
sudo cp ./caddy.service /etc/systemd/system/
```

3. Add user
```
sudo useradd caddy -s /sbin/nologin -r
```

4. Set permission.
```
sudo chmod 600 ./Caddyfile
sudo chmod 600 ./start.sh
sudo chown caddy ./Caddyfile
sudo chown caddy ./start.sh
sudo setcap 'cap_net_bind_service=+ep' $(which caddy)
```

5. Setting systemd
```
sudo systemctl daemon-reload
sudo systemctl start caddy.service
sudo systemctl enable caddy.service
systemctl status caddy.service
```
