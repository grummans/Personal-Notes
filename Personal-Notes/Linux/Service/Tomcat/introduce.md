### Tomcat

- Open-source web server.
- Running Java web app.

#### Location

```
Client
   │
   ▼
Load Balancer / Nginx
   │ HTTP/HTTPS
   ▼
Tomcat Connector
   │
   ▼
Tomcat Engine
   │
   ▼
Virtual Host
   │
   ▼
Web Application Context
   │
   ▼
Servlet / Spring MVC / Business Logic
   │
   ▼
Database / Redis / External Service
```

[Architecture](/Linux/Service/Tomcat/architecture.md)
