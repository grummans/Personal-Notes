# Source: Nginx Working Flow

> Cập nhật lần cuối: 2026-07-29

## Tóm tắt

Ghi chú mô tả request đi từ browser tới TCP port 80, qua Linux kernel `epoll`, vào Nginx worker process, match HTTP/location, proxy tới upstream Tomcat, rồi response quay lại browser.

## Nguồn gốc

- [Nguồn: Personal-Notes/Linux/Service/Nginx/working-flow.md](../../Personal-Notes/Linux/Service/Nginx/working-flow.md)

## Liên kết

- [Nginx architecture](../concepts/nginx-architecture.md)
- [Nginx](../entities/nginx.md)
- [Tomcat](../entities/tomcat.md)
