#### Worker Process

- Take responsibility to process HTTP request.

```
Browser
    │
    ▼
Worker
    │
    ▼
Tomcat
```

- Worker is a **single thread**

> Why a thread can hundred thousands request?
>
> - [Event Loop](/Linux/Service/Nginx/event-loop.md)
