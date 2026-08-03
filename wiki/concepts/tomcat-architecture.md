---
type: concept
topics: [tomcat, java, web-server, application-server, architecture]
status: reviewed
updated: 2026-07-29
---

# Tomcat Architecture

> Cập nhật lần cuối: 2026-07-29

## Tóm tắt

Tomcat xử lý Java web application thông qua các lớp Server, Service, Connector, Engine, Host, Context và Servlet/Filter/Listener.

## Chi tiết

Luồng tổng quát trong ghi chú:

```text
Client
-> Load Balancer / Nginx
-> Tomcat Connector
-> Tomcat Engine
-> Virtual Host
-> Web Application Context
-> Servlet / Spring MVC / Business Logic
-> Database / Redis / External Service
```

Cấu trúc component:

```text
Server
└── Service
    ├── Connector
    └── Engine
        └── Host
            └── Context
                └── Servlet / Filter / Listener
```

## Nguồn liên quan

- [Tomcat introduce source](../sources/personal-notes-linux-service-tomcat-introduce.md)
- [Tomcat architecture source](../sources/personal-notes-linux-service-tomcat-architecture.md)

## Quan hệ

- Là kiến trúc của [Tomcat](../entities/tomcat.md) — vì trang này mô tả Server, Service, Connector, Engine, Host, Context và Servlet/Filter/Listener.
- Liên quan tới [Nginx](../entities/nginx.md) — vì flow ghi chú đặt Tomcat phía sau Load Balancer/Nginx.
- Liên quan tới [Nginx configuration](./nginx-configuration.md) — vì cấu hình reverse proxy của Nginx định tuyến request vào Tomcat Connector.
- Liên quan tới [Nginx reverse proxy headers](./nginx-reverse-proxy-headers.md) — vì Tomcat/backend cần proxy headers để hiểu host gốc, IP client thật và protocol ban đầu.
