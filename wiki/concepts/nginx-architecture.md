---
type: concept
topics: [nginx, web-server, reverse-proxy, event-driven, architecture]
status: reviewed
updated: 2026-07-29
---

# Nginx Architecture

> Cập nhật lần cuối: 2026-07-29

## Tóm tắt

Nginx dùng mô hình event-driven, asynchronous và non-blocking I/O. Kiến trúc chính gồm master process sinh worker process; worker xử lý request thông qua event loop và cơ chế kernel như `epoll`.

## Chi tiết

Master process quản lý cấu hình Nginx và tạo các worker process, ví dụ `worker_processes 4;` tạo 4 worker. Worker process chịu trách nhiệm xử lý HTTP request.

Worker được ghi chú là single-thread, nhưng có thể xử lý rất nhiều request nhờ event loop: khi socket có dữ liệu thì worker xử lý request, sau đó chuyển sang socket khác thay vì block theo từng connection.

Trong multi-worker flow, client kết nối vào TCP port 80, Linux kernel dùng `epoll`, rồi phân phối kết nối tới nhiều worker. Các worker sau đó proxy tới upstream server như Tomcat, PHP hoặc Node.js.

## Nguồn liên quan

- [Nginx architecture source](../sources/personal-notes-linux-service-nginx-architecture.md)
- [Nginx master process source](../sources/personal-notes-linux-service-nginx-master-process.md)
- [Nginx worker process source](../sources/personal-notes-linux-service-nginx-worker-process.md)
- [Nginx multi-worker flow source](../sources/personal-notes-linux-service-nginx-multi-worker-working-flow.md)

## Quan hệ

- Là kiến trúc của [Nginx](../entities/nginx.md) — vì trang này mô tả master process, worker process và cách Nginx xử lý request.
- Sử dụng [Nginx event loop](./nginx-event-loop.md) — vì worker xử lý nhiều socket thông qua event loop và non-blocking I/O.
- Phụ thuộc vào [TCP](./tcp.md) — vì client kết nối vào TCP port 80 trước khi Linux kernel phân phối connection tới worker.
- Phụ thuộc vào [IP](./ip.md) — vì request phải được định tuyến qua network stack tới đúng destination trước khi Nginx xử lý.
- Liên quan tới [Nginx configuration](./nginx-configuration.md) — vì các tham số như `worker_processes`, `server`, `location` và `upstream` điều khiển cách kiến trúc Nginx vận hành.
