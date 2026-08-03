---
type: concept
topics: [networking, udp, tcp-ip, transport-layer, latency, port]
status: raw
updated: 2026-08-03
---

# UDP

> Cập nhật lần cuối: 2026-08-03

## Tóm tắt

UDP (User Datagram Protocol) là protocol connectionless: không handshake, không acknowledge, gửi dữ liệu nhanh nhưng không bảo đảm delivery.

## Chi tiết

UDP định nghĩa một cách gửi dữ liệu khác với [TCP](./tcp.md): nó chỉ address dữ liệu rồi gửi đi. Vì không có handshake và không chờ acknowledge, UDP rất nhanh.

Trade-off là UDP không bảo đảm dữ liệu đến nơi đầy đủ hoặc đúng như mong muốn.

Trong mô hình [TCP/IP](./tcp-ip.md), UDP thuộc Transport Layer.

## Nguồn liên quan

- [TCP/UDP/IP source](../sources/personal-notes-networking-tcp-upd-ip.md)
- [TCP/IP source](../sources/personal-notes-networking-tcp-ip.md)
- [Port source](../sources/personal-notes-networking-port.md)
- [Connectionless source](../sources/personal-notes-networking-connectionless.md)

## Quan hệ

- So sánh với [TCP](./tcp.md) — vì UDP connectionless, không handshake/acknowledge, trái với TCP connection-oriented.
- Chạy phía trên [IP](./ip.md) — vì UDP thuộc Transport Layer còn IP đưa packet tới destination ở Internet/Network Layer.
- Là một [Protocol](./protocol.md) — vì UDP là bộ quy tắc connectionless để gửi datagram.
- Là một phần của [TCP/IP](./tcp-ip.md) — vì UDP thuộc Transport Layer trong mô hình TCP/IP.
- Xem thêm [TCP vs UDP](../syntheses/tcp-vs-udp.md) — vì synthesis này tổng hợp trade-off giữa TCP và UDP.
- Dùng [Port](./port.md) — vì UDP header có port để chuyển datagram tới đúng service trên host.
- Là ví dụ của [Connectionless](./connectionless.md) — vì UDP không cần handshake trước khi gửi datagram.
