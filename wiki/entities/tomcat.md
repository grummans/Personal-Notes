---
type: entity
topics: [tomcat, java, web-server, application-server, servlet]
status: reviewed
updated: 2026-07-29
---

# Tomcat

> Cập nhật lần cuối: 2026-07-29

## Tóm tắt

Tomcat là open-source web server/application server dùng để chạy Java web application.

## Chi tiết

Trong mô hình ghi chú, Tomcat thường đứng sau load balancer hoặc Nginx. Request đi qua Tomcat Connector, vào Engine, Virtual Host, Web Application Context, rồi tới Servlet/Spring MVC/business logic và các dependency như Database, Redis hoặc external service.

Kiến trúc Tomcat được ghi theo chuỗi: `Server -> Service -> Connector + Engine -> Host -> Context -> Servlet / Filter / Listener`.

## Nguồn liên quan

[Tomcat introduce](../sources/personal-notes-linux-service-tomcat-introduce.md)
[Tomcat architecture](../sources/personal-notes-linux-service-tomcat-architecture.md)

## Quan hệ

- Có kiến trúc được mô tả ở [Tomcat architecture](../concepts/tomcat-architecture.md) — vì trang đó giải thích Server, Service, Connector, Engine, Host và Context của Tomcat.
- Liên quan tới [Nginx](./nginx.md) — vì Tomcat thường đứng sau Nginx/load balancer trong flow request.
- Liên quan tới [Nginx configuration](../concepts/nginx-configuration.md) — vì cấu hình `upstream`/`proxy_pass` có thể định tuyến request từ Nginx tới Tomcat.
