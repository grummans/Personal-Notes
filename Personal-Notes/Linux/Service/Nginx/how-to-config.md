### Overview

Diagram

```
                 nginx.conf
                      │
        ┌─────────────┴─────────────┐
        │                           │
     events {}                  http {}
                                     │
          ┌──────────────────────────┴─────────────────────────┐
          │                    │                │              │
      include mime.types   include conf.d  include sites-enabled
                                                    │
                                               server {}
                                                    │
                                           location {}
                                                    │
                                  root / proxy_pass / fastcgi_pass
```

#### Global Configuration

- Effect to nginx process.

| Params             | Meaning                  |
| ------------------ | ------------------------ |
| `user`             | User runs Worker Process |
| `worker_processes` | Number of Worker Process |
| `pid`              | File save PID of Master  |
| `error_log`        | File error log           |
| `load_module`      | Load dynamic module      |

E.g: `worker_processes auto;`

-> Auto create number of workers = cores of CPU

#### server{}

- A `server` = a `Virtual Host`

```nginx
server {

    listen 80;

    server_name example.com;

}
```

#### location{}

- Decide to process each URL.

```
location / {

}
```

- A request after matching `server{}` will be compared to a suitable `location{}`.

E.g: `location /api`

Browser -> `GET /api/user` -> Response

#### upstream{}

- Use for `Reverse Proxy` or `Load Balancer`

```nginx
upstream tomcat_cluster {

    server 192.168.1.10:8080;

    server 192.168.1.20:8080;

}

location / {

    proxy_pass http://tomcat_cluster;

}

```

Request -> Nginx -> Tomcat1 / Tomcat2

