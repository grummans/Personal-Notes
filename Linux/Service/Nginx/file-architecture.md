### Config folder

```
/etc/nginx/
├── nginx.conf
├── mime.types
├── fastcgi.conf
├── fastcgi_params
├── proxy_params
├── scgi_params
├── uwsgi_params
├── conf.d/
├── modules-available/
├── modules-enabled/
├── sites-available/
├── sites-enabled/
└── snippets/
```

#### nginx.conf

`/etc/nginx/nginx.conf`

- Nginx read this file when start.

```
nginx
    │
    ▼
nginx.conf
    │
    ├── include mime.types
    ├── include conf.d/*
    ├── include sites-enabled/*
    └── ...
```
