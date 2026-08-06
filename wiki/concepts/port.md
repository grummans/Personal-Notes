---
type: concept
topics: [networking, port, tcp, udp, transport-layer, rtsp]
status: raw
updated: 2026-08-06
---

# Port

## Tóm tắt

Port giúp một máy có một địa chỉ IP nhưng vẫn phân biệt được traffic của nhiều service khác nhau.

## Chi tiết

Port nằm ở Transport Layer. IP đưa packet tới đúng máy, còn [TCP](./tcp.md) hoặc [UDP](./udp.md) dùng port number trong header để chuyển dữ liệu tới đúng service trên máy đó.

Dải port từ `0` đến `65535`:

- `0-1023`: well-known ports cho service chuẩn.
- `1024-49151`: registered ports cho ứng dụng/service cụ thể.
- `49152-65535`: ephemeral ports, thường được máy tự chọn tạm thời cho outgoing connections.

Một số port thường gặp: SSH `22`, DNS `53`, HTTP `80`, HTTPS `443`, MySQL `3306`, PostgreSQL `5432`, Redis `6379`.

## Nguồn liên quan

- [Port source](../sources/personal-notes-networking-port.md)

## Quan hệ

- Thuộc [OSI Model](./osi-model.md) — vì port nằm ở Layer 4 Transport trong OSI.
- Được dùng bởi [TCP](./tcp.md) — vì TCP connection dùng port để phân biệt service đích trên cùng một IP.
- Được dùng bởi [UDP](./udp.md) — vì UDP datagram cũng dùng port để chuyển dữ liệu tới đúng process/service.
- Liên quan tới [DNS](./dns.md) — vì DNS thường dùng port `53`.
- Liên quan tới [Nginx configuration](./nginx-configuration.md) — vì Nginx `listen` và reverse proxy phụ thuộc vào port như `80`, `443` hoặc backend port.
- Liên quan tới [RTSP Server](../entities/rtsp-server.md) — liên kết chưa được xác nhận; RTSP là traffic service-level nên cần port để client/server phân biệt service, nhưng note chưa ghi port cụ thể.
