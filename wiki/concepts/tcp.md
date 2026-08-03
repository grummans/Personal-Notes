---
type: concept
topics: [networking, tcp, tcp-ip, transport-layer, reliability, port]
status: raw
updated: 2026-08-03
---

# TCP

> Cập nhật lần cuối: 2026-08-03

## Tóm tắt

TCP (Transmission Control Protocol) là protocol connection-oriented: hai thiết bị bắt tay trước khi truyền dữ liệu và có cơ chế acknowledge/resend để hạn chế mất dữ liệu.

## Chi tiết

TCP chia dữ liệu thành nhiều packet nhỏ, đánh số chúng, rồi chờ bên nhận acknowledge từng packet. Nếu packet bị mất trong quá trình truyền, TCP gửi lại packet đó.

Kết quả là bên nhận có thể nhận đủ dữ liệu, không mất và không bị xáo trộn thứ tự. Trade-off là TCP có thêm overhead và độ trễ so với [UDP](./udp.md).

Trong mô hình [TCP/IP](./tcp-ip.md), TCP thuộc Transport Layer.

## Nguồn liên quan

- [TCP/UDP/IP source](../sources/personal-notes-networking-tcp-upd-ip.md)
- [TCP/IP source](../sources/personal-notes-networking-tcp-ip.md)
- [Port source](../sources/personal-notes-networking-port.md)
- [Connection-oriented source](../sources/personal-notes-networking-connection-oriented.md)

## Quan hệ

- So sánh với [UDP](./udp.md) — vì TCP ưu tiên reliability còn UDP ưu tiên gửi nhanh và connectionless.
- Chạy phía trên [IP](./ip.md) — vì TCP thuộc Transport Layer còn IP đưa packet tới destination ở Internet/Network Layer.
- Là một [Protocol](./protocol.md) — vì TCP là bộ quy tắc connection-oriented để hai thiết bị truyền dữ liệu.
- Là một phần của [TCP/IP](./tcp-ip.md) — vì TCP thuộc Transport Layer trong mô hình TCP/IP.
- Xem thêm [TCP vs UDP](../syntheses/tcp-vs-udp.md) — vì synthesis này tổng hợp trade-off giữa TCP và UDP.
- Được dùng bởi [Nginx architecture](./nginx-architecture.md) — vì flow Nginx mô tả client kết nối vào TCP port 80.
- Được dùng bởi [Nginx reverse proxy headers](./nginx-reverse-proxy-headers.md) — vì backend nhìn thấy TCP connection đến từ Nginx.
- Dùng [Port](./port.md) — vì TCP header có port để chuyển connection tới đúng service trên host.
- Là ví dụ của [Connection-Oriented](./connection-oriented.md) — vì TCP thiết lập connection trước khi truyền dữ liệu.
