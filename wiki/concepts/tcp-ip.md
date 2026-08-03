---
type: concept
topics: [networking, tcp-ip, osi, protocol, transport-layer, dns]
status: raw
updated: 2026-08-03
---

# TCP/IP

> Cập nhật lần cuối: 2026-08-03

## Tóm tắt

TCP/IP là protocol model được Internet dùng trong thực tế. Mô hình này gom một số tầng của [OSI Model](./osi-model.md) thành 4 layer: Application, Transport, Internet và Network Access.

## Chi tiết

Mapping chính trong note:

- Layer 4 Application: gộp layer 5, 6, 7 của OSI; nơi các chương trình như browser/mail client hoạt động, ví dụ HTTP, HTTPS, FTP, DNS, SMTP, SSH.
- Layer 3 Transport: gồm [TCP](./tcp.md) và [UDP](./udp.md); chia dữ liệu thành packet, reassemble và đảm bảo không mất/trùng/sai thứ tự theo cách của transport protocol.
- Layer 2 Internet: gồm [IP](./ip.md), IPv4/IPv6, ICMP, ARP; route và forward packet giữa các network khác nhau.
- Layer 1 Network Access (Link): gộp layer 1, 2 của OSI; di chuyển dữ liệu giữa thiết bị trên cùng physical network, ví dụ Ethernet, Wi-Fi, MAC và physical drivers.

## Nguồn liên quan

- [TCP/IP source](../sources/personal-notes-networking-tcp-ip.md)
- [OSI model source](../sources/personal-notes-networking-osi-model.md)
- [TCP/UDP/IP source](../sources/personal-notes-networking-tcp-upd-ip.md)
- [DNS source](../sources/personal-notes-networking-dns.md)

## Quan hệ

- Liên quan tới [OSI Model](./osi-model.md) — vì TCP/IP mapping gộp các layer OSI thành Application, Transport, Internet và Network Access.
- Dựa trên [Protocol](./protocol.md) — vì TCP/IP là mô hình gồm các protocol dùng chung quy tắc giao tiếp.
- Bao gồm [TCP](./tcp.md) — vì TCP nằm ở Transport Layer trong mô hình TCP/IP.
- Bao gồm [UDP](./udp.md) — vì UDP nằm ở Transport Layer trong mô hình TCP/IP.
- Bao gồm [IP](./ip.md) — vì IP nằm ở Internet Layer trong mô hình TCP/IP.
- Xem thêm [TCP vs UDP](../syntheses/tcp-vs-udp.md) — vì synthesis này so sánh hai protocol Transport Layer trong TCP/IP.
- Bao gồm [DNS](./dns.md) ở Application Layer — vì DNS là protocol ứng dụng dùng để phân giải domain name thành địa chỉ IP.
