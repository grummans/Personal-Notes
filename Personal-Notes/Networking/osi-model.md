### OSI model architecture

- Each layer has one job.
- Only works with the layer above and blow it.

### Layer 7 - Application

- Request directly (HTTPS, SSH,...)

### Layer 6 - Presentation

- Format and encrypt.

### Layer 5 - Session

- Open/Manage/Close conversation.

### Layer 4 - Transport

- TCP, UDP, Port

### Layer 3 - Network

- IP, Routing,...

### Layer 2 - Data Link

- MAC, VLAN, Switch,...

### Layer 1 - Physical

- Physical device: Cable, Wifi,...

> Key to remember
>
> **A**ll **P**eople **S**eem **T**o **N**eed **D**ata **P**rocessing.

- Diagram

```
+-------------------------------------------------------+

| 7. Application Layer    | HTTP, DNS, FTP, SMTP        |
+-------------------------------------------------------+

| 6. Presentation Layer   | JPEG, SSL/TLS, Encryption   |
+-------------------------------------------------------+

| 5. Session Layer        | RPC, NetBIOS, Sessions      |
+-------------------------------------------------------+

| 4. Transport Layer      | TCP, UDP, Segments          |
+-------------------------------------------------------+

| 3. Network Layer        | IP, Routers, Packets        |
+-------------------------------------------------------+

| 2. Data Link Layer      | MAC, Switches, Frames       |
+-------------------------------------------------------+

| 1. Physical Layer       | Cables, Hubs, Bits          |
+-------------------------------------------------------+
```
