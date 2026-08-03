---
type: entity
topics: [nginx, web-server, reverse-proxy, load-balancing, http-cache]
status: reviewed
updated: 2026-07-29
---

# Nginx

> Cập nhật lần cuối: 2026-07-29

## Tóm tắt

Nginx là web server open-source, reverse proxy, load balancer và HTTP cache. Ghi chú hiện có nhấn mạnh kiến trúc event-driven, asynchronous, non-blocking I/O và mô hình master/worker để xử lý nhiều kết nối.

## Chi tiết

Nginx có master process quản lý cấu hình và sinh worker process. Worker process xử lý HTTP request, thường chạy single-thread và dựa vào event loop cùng cơ chế kernel như `epoll`, `kqueue` hoặc `select` để phục vụ nhiều kết nối.

Trong luồng reverse proxy, request từ browser đi tới cổng TCP, qua Linux kernel, vào worker process, được parse/match `server` và `location`, sau đó proxy tới upstream như Tomcat.

Các thư mục quan trọng gồm `/etc/nginx/` cho cấu hình, `/var/log/nginx/` cho log và `/var/cache/nginx/` cho `proxy_cache`.

## Nguồn liên quan

- [Nginx introduce](../sources/personal-notes-linux-service-nginx-introduce.md)
- [Nginx architecture](../sources/personal-notes-linux-service-nginx-architecture.md)
- [Nginx file architecture](../sources/personal-notes-linux-service-nginx-file-architecture.md)
- [Nginx working flow](../sources/personal-notes-linux-service-nginx-working-flow.md)

## Quan hệ

- Có kiến trúc được mô tả ở [Nginx architecture](../concepts/nginx-architecture.md) — vì trang đó giải thích master/worker, event-driven và reverse proxy flow của Nginx.
- Sử dụng [Nginx event loop](../concepts/nginx-event-loop.md) — vì worker dùng event loop và non-blocking I/O để xử lý nhiều connection.
- Được cấu hình bởi [Nginx configuration](../concepts/nginx-configuration.md) — vì `nginx.conf` và các block cấu hình điều khiển hành vi Nginx.
- Sử dụng [Nginx reverse proxy headers](../concepts/nginx-reverse-proxy-headers.md) — vì khi đứng trước backend, Nginx cần truyền host/IP/protocol gốc qua proxy headers.
- Liên quan tới [Tomcat](./tomcat.md) — vì Tomcat thường đứng sau Nginx trong flow reverse proxy/load balancer.
- Liên quan tới [Keepalived](./keepalived.md) — liên kết chưa được xác nhận; Keepalived cung cấp HA/VIP còn Nginx có vai trò reverse proxy/load balancer.
- Liên quan tới [Keepalived failover flow](../concepts/keepalived-failover-flow.md) — liên kết chưa được xác nhận; cả hai có thể cùng nằm trên availability/load-balancing path nhưng wiki chưa có source nối trực tiếp.
