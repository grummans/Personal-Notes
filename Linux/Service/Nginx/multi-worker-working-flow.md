```
                    Clients
                        │
                        ▼
                TCP Port 80
                        │
                        ▼
              Linux Kernel (epoll)
                        │
        ┌───────────────┼───────────────┐
        ▼               ▼               ▼
    Worker 1       Worker 2       Worker 3
        │               │               │
        └───────────────┼───────────────┘
                        ▼
                Upstream Servers
             (Tomcat, PHP, Node.js...)
```
