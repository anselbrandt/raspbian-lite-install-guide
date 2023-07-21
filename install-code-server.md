# Install Code Server

https://coder.com/docs/code-server/latest/install

```
curl -fsSL https://code-server.dev/install.sh | sh
```

```
sudo systemctl enable --now code-server@$USER
```

Modify config.yaml

`.config/code-server/config.yaml`

```
bind-addr: 127.0.0.1:8080
auth: password
password: 0c6ac14042a8f28f4e5d308d
cert: false
```

Change to:
```
bind-addr: 0.0.0.0:8080
auth: none
password: <your-password>
cert: false
```
