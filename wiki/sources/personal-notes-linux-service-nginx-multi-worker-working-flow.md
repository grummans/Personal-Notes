# Source: Nginx Multi-Worker Working Flow

> Cập nhật lần cuối: 2026-07-29

## Tóm tắt

Ghi chú mô tả nhiều client đi vào TCP port 80, Linux kernel dùng `epoll`, sau đó nhiều worker Nginx xử lý và chuyển tiếp tới upstream servers như Tomcat, PHP hoặc Node.js.

## Nguồn gốc

- [Nguồn: Personal-Notes/Linux/Service/Nginx/multi-worker-working-flow.md](../../Personal-Notes/Linux/Service/Nginx/multi-worker-working-flow.md)

## Liên kết

- [Nginx architecture](../concepts/nginx-architecture.md)
- [Nginx](../entities/nginx.md)
