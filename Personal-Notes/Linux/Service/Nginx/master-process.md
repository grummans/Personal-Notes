#### Master Process

- Take responsibility to manage all Nginx config.

- Master creates worker processes

E.g: `worker_processes 4;`

```
Master
   │
   ├── Worker 1
   ├── Worker 2
   ├── Worker 3
   └── Worker 4
```
