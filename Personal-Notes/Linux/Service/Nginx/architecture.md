### Overall Nginx Architecture

`Nginx` using **Event-driven** + **Asynchronous** + **Non-blocking I/O**

```
                    Client
                       │
      ┌────────────────┴────────────────┐
      │                                 │
   Request 1                        Request 2
      │                                 │
      └──────────────┬──────────────────┘
                     │
              MASTER PROCESS
                     │
     ┌───────────────┼──────────────────┐
     │               │                  │
     │ spawn         │ spawn            │
     ▼               ▼                  ▼
  WORKER 1        WORKER 2          WORKER 3
     │               │                  │
     └───────────────┼──────────────────┘
                     │
                Event Loop
                     │
            epoll / kqueue / select
                     │
          Thousands of connections
```

[Working flow](/Linux/Service/Nginx/working-flow.md)
