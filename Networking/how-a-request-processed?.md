### A break down to understand the way a request processed.

- When user type url `https://example.com/api/user`, what is exactly going on behind the scenes?

### Application Layer

- Browser create

```
GET /api/user HTTP/1.1

Host: example.com

User-Agent: Firefox

Accept: */*
```

### Transport

- HTTP must run on TCP -> TCP create segment.

```
TCP Header

Source Port: 52341

Destination Port: 443

Sequece Number

ACK

Flags

Window
```
