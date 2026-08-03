---
type: concept
topics: [nginx, configuration, reverse-proxy, load-balancing, filesystem, port]
status: raw
updated: 2026-08-03
---

# Nginx Configuration

> Cập nhật lần cuối: 2026-07-29

## Tóm tắt

Nginx cấu hình từ `nginx.conf`, thường chia thành global config, `events {}`, `http {}`, `server {}`, `location {}` và `upstream {}`.

## Chi tiết

Global configuration ảnh hưởng tới process Nginx. Một số tham số chính gồm `user`, `worker_processes`, `pid`, `error_log` và `load_module`. Ví dụ `worker_processes auto;` tạo số worker theo số core CPU.

Trong `http {}`, Nginx có thể include `mime.types`, `conf.d` hoặc `sites-enabled`. Một `server {}` tương ứng virtual host. Sau khi request match `server {}`, Nginx tiếp tục match `location {}` để quyết định xử lý từng URL.

`upstream {}` dùng cho reverse proxy hoặc load balancer. Ví dụ một `upstream tomcat_cluster` có thể chứa nhiều Tomcat server và được dùng bởi `proxy_pass http://tomcat_cluster;`.

Filesystem thường gặp:

```text
/etc/nginx/nginx.conf
/etc/nginx/sites-available/
/etc/nginx/sites-enabled/
/etc/nginx/snippets/
/var/log/nginx/
/var/cache/nginx/
```

## Nguồn liên quan

- [Nginx configuration source](../sources/personal-notes-linux-service-nginx-how-to-config.md)
- [Nginx file architecture source](../sources/personal-notes-linux-service-nginx-file-architecture.md)
- [Nginx log source](../sources/personal-notes-linux-service-nginx-log.md)
- [Nginx cache source](../sources/personal-notes-linux-service-nginx-cache.md)

## Quan hệ

- Cấu hình cho [Nginx](../entities/nginx.md) — vì `nginx.conf` và các block `http`, `server`, `location`, `upstream` quyết định hành vi runtime của Nginx.
- Liên quan tới [Nginx reverse proxy headers](./nginx-reverse-proxy-headers.md) — vì proxy headers thường được khai báo trong cấu hình reverse proxy của Nginx.
- Liên quan tới [Nginx architecture](./nginx-architecture.md) — vì cấu hình `worker_processes`, `http`, `server`, `location` và `upstream` điều khiển cách kiến trúc Nginx vận hành.
- Liên quan tới [Tomcat](../entities/tomcat.md) — vì `upstream tomcat_cluster` và `proxy_pass` nối Nginx tới backend Tomcat.
- Liên quan tới [Tomcat architecture](./tomcat-architecture.md) — vì reverse proxy định tuyến request vào Tomcat Connector trong flow Tomcat.
- Liên quan tới [Port](./port.md) — vì `listen`, HTTP/HTTPS và backend upstream đều dựa trên port để nhận/chuyển request tới đúng service.
