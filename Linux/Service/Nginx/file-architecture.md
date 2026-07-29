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

#### sites-available

- Save all virtual hosts.

E.g:

```
sites-available/

example.com

api.local

blog.conf

harbor.conf
```

#### sites-enabled

- Symbolink to active sites.

> Why we have to separate 2 folders?

Assuming we have 10 sites, but only want to run 3 sites, we just create symlink to 3 sites.

#### snippets

- Save common configurations.

#### modules-available

- Save installed modules.

#### modules-enabled

- Similar to `sites-enabled`.

#### `Web Root` folder

- If Nginx serves statis web, it will get data from `root /var/www/html`

[Log](/Linux/Service/Nginx/log.md)

[Cache](/Linux/Service/Nginx/cache.md)
