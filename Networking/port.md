### Port

- A single server has an unique IP address. But, that server is running many services (tomcat, nginx, docker,... ).

- **Ports** are how keeps their traffic apart, so a website's request not get delivered to the database.

### Port numbers

- From 0 - 65535, split into 3 groups:
  - 0-1023: **well-known ports**. Usually for standard services.
  - 1024-49151: **Registered ports**. Used by specific applications and custom service.
  - 49152-65535: **Ephemeral ports**. temp ports that computer pick automatically for outgoing connections.

- Some default service ports:

| Port   | Service     |
| ------ | ----------- |
| 22     | SSH         |
| 25/587 | SMTP(email) |
| 53     | DNS         |
| 80     | HTTP        |
| 443    | HTTPS       |
| 3306   | MySQL       |
| 5432   | PostgreSQL  |
| 6379   | Redis       |

### Port location in OSI Model

- In **Layer 4 (Transport Layer)** in the OSI-Model.

> Why port located in layer 4?
>
> Layer 3 (IP) gets the packet to the right machine using its IP address -> TCP or UDP (Layer 4) looks at the **port number** in the packet's header to decide which service on that machine should receive it.

#### IP Address + Port like building + apartment number -> Pinpoint an exact destination.
