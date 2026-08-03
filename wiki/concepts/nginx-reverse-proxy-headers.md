---
type: concept
topics: [nginx, reverse-proxy, headers, http, tomcat]
status: reviewed
updated: 2026-07-29
---

# Nginx Reverse Proxy Headers

> Cập nhật lần cuối: 2026-07-29

## Tóm tắt

Khi Nginx đứng trước backend như Tomcat, cần set các proxy header để backend biết host gốc, IP client thật và protocol ban đầu.

## Chi tiết

Các header phổ biến:

```nginx
proxy_set_header Host $host;
proxy_set_header X-Real-IP $remote_addr;
proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
proxy_set_header X-Forwarded-Proto $scheme;
```

Nếu không set header, backend chỉ thấy TCP connection đến từ Nginx, ví dụ remote IP là IP của Nginx và protocol có thể là HTTP dù client ban đầu dùng HTTPS.

`Host $host` giữ host/virtual host mà client truy cập. `X-Real-IP $remote_addr` truyền IP của thiết bị kết nối trực tiếp tới Nginx. `X-Forwarded-For` lưu chuỗi IP khi request đi qua nhiều proxy layer. `X-Forwarded-Proto $scheme` giúp backend biết protocol gốc như HTTPS.

## Nguồn liên quan

- [Nginx headers source](../sources/personal-notes-linux-service-nginx-hearder-nginx.md)

## Quan hệ

- Được cấu hình trong [Nginx](../entities/nginx.md) — vì Nginx reverse proxy set các header trước khi chuyển request tới backend.
- Liên quan tới [Tomcat](../entities/tomcat.md) — vì Tomcat/backend cần các header này để biết host gốc, IP client thật và protocol ban đầu.
- Phụ thuộc vào [TCP](./tcp.md) — vì backend chỉ thấy TCP connection đến từ Nginx trong reverse proxy flow.
- Liên quan tới [OSI Model](./osi-model.md) — vì trang này đặt HTTP/HTTPS/proxy headers ở Application Layer và TCP connection ở Transport Layer.
- Liên quan tới [Tomcat architecture](./tomcat-architecture.md) — vì proxy headers giúp Tomcat/backend hiểu host gốc, IP client thật và protocol ban đầu.
