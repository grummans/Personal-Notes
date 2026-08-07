### Request Flow

```
GET /api/users -> 192.168.1.10
```

- Flow:

```text
Client

↓

Switch

↓

eth0

↓

bond0

↓

Kernel TCP/IP

↓

Tomcat

↓

Spring Boot

↓

Response

↓

bond0

↓

eth0

↓

Switch

↓

Client
```

> Hmm, why not switch -> bond0 -> eth0 ?
>
> I just think bonding will cover all NIC and the request will work with bonding layer first then go to a NIC real (eth0) -> Maybe I'm wrong.
