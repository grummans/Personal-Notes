### Overall Nginx working flow

```
              Browser
                  │
                  ▼
          TCP Port 80
                  │
                  ▼
         Linux Kernel (epoll)
                  │
                  ▼
        Worker Process (Nginx)
                  │
      Parse HTTP / Match location
                  │
          Proxy to upstream
                  │
                  ▼
            Tomcat Server
                  │
      Spring → Service → DB
                  │
                  ▼
            HTTP Response
                  │
                  ▼
        Worker Process (Nginx)
                  │
                  ▼
               Browser
```

[Multi Worker Flow](/Linux/Service/Nginx/multi-worker-working-flow.md)
