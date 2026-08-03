# Source: Nginx Architecture

> Cập nhật lần cuối: 2026-07-29

## Tóm tắt

Ghi chú mô tả Nginx dùng event-driven, asynchronous, non-blocking I/O. Master process sinh nhiều worker process; worker dùng event loop và cơ chế như `epoll`, `kqueue`, `select` để xử lý nhiều connection.

## Nguồn gốc

- [Nguồn: Personal-Notes/Linux/Service/Nginx/architecture.md](../../Personal-Notes/Linux/Service/Nginx/architecture.md)

## Liên kết

- [Nginx](../entities/nginx.md)
- [Nginx architecture](../concepts/nginx-architecture.md)
