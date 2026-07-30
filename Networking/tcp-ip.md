### TCP/IP

- In real world, internet use **TCP/IP** Protocol.

- Combine layer 5, 6, 7 of OSI to `Application` layer.

- Combine layer 1, 2 to `Network` layer.

```
+-------------------------------------------------------+

| 4. Application Layer                                  |
|    (HTTP, HTTPS, FTP, DNS, SMTP, SSH)                 |
+-------------------------------------------------------+
                           |
                           v
+-------------------------------------------------------+

| 3. Transport Layer                                    |
|    (TCP, UDP)                                         |
+-------------------------------------------------------+
                           |
                           v
+-------------------------------------------------------+

| 2. Internet Layer                                     |
|    (IP [IPv4/IPv6], ICMP, ARP)                        |
+-------------------------------------------------------+
                           |
                           v
+-------------------------------------------------------+

| 1. Network Access (Link) Layer                        |
|    (Ethernet, Wi-Fi, MAC, Physical Drivers)           |
+-------------------------------------------------------+
```
