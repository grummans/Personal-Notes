---
type: concept
topics: [nginx, event-loop, non-blocking-io, epoll, web-server]
status: reviewed
updated: 2026-07-29
---

# Nginx Event Loop

> Cập nhật lần cuối: 2026-07-29

## Tóm tắt

Event loop là cơ chế giúp worker Nginx xử lý nhiều socket mà không cần block theo từng request.

## Chi tiết

Theo ghi chú, event loop chạy vòng lặp liên tục: kiểm tra socket, nếu có dữ liệu thì xử lý request, rồi chuyển sang socket khác. Kết hợp với non-blocking I/O và kernel event notification như `epoll`, worker có thể phục vụ nhiều kết nối đồng thời.

Pseudo-flow:

```c
while (true) {
    check_socket;
    process_request;
    move_to_another_socket;
}
```

## Nguồn liên quan

- [Nginx event loop source](../sources/personal-notes-linux-service-nginx-event-loop.md)
- [Nginx worker process source](../sources/personal-notes-linux-service-nginx-worker-process.md)

## Quan hệ

- Là một phần của [Nginx architecture](./nginx-architecture.md) — vì event loop là cơ chế worker dùng để xử lý nhiều socket không blocking.
- Được dùng bởi [Nginx](../entities/nginx.md) — vì Nginx worker dựa vào event loop để phục vụ nhiều kết nối đồng thời.
