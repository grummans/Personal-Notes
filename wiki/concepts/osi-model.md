---
type: concept
topics: [networking, osi, tcp-ip, protocol, port, routing]
status: raw
updated: 2026-08-03
---

# OSI Model

> Cập nhật lần cuối: 2026-08-03

## Tóm tắt

OSI Model là mô hình tham chiếu 7 tầng mô tả cách các hệ thống máy tính giao tiếp qua mạng. Mỗi tầng có một trách nhiệm riêng và chỉ làm việc với tầng ngay trên/ngay dưới nó.

## Chi tiết

7 tầng OSI từ trên xuống dưới:

- Layer 7 Application: request trực tiếp từ application, ví dụ HTTP/HTTPS, SSH, DNS, FTP, SMTP.
- Layer 6 Presentation: format dữ liệu và encryption, ví dụ JPEG, SSL/TLS, encryption.
- Layer 5 Session: mở, quản lý và đóng conversation/session, ví dụ RPC, NetBIOS.
- Layer 4 Transport: TCP, UDP, port và segment.
- Layer 3 Network: IP, routing, router và packet.
- Layer 2 Data Link: MAC, VLAN, switch và frame.
- Layer 1 Physical: thiết bị/môi trường vật lý như cable, Wi-Fi, hub và bit.

Mnemonic trong note: **All People Seem To Need Data Processing** tương ứng Application, Presentation, Session, Transport, Network, Data Link, Physical.

> Cập nhật 2026-08-03: phần so sánh TCP/IP không còn nằm trong source OSI hiện tại; nội dung đó được tách sang [TCP/IP](./tcp-ip.md).

## Nguồn liên quan

- [OSI model source](../sources/personal-notes-networking-osi-model.md)
- [Port source](../sources/personal-notes-networking-port.md)
- [Routing source](../sources/personal-notes-networking-routing.md)

## Quan hệ

- Liên quan tới [Nginx reverse proxy headers](./nginx-reverse-proxy-headers.md) — vì headers thuộc Application Layer còn TCP connection thuộc Transport Layer trong mô hình OSI.
- Liên quan tới [TCP/IP](./tcp-ip.md) — vì TCP/IP gộp một số layer của OSI thành mô hình 4 layer dùng trong thực tế.
- Bao gồm [Port](./port.md) ở Layer 4 — vì port thuộc Transport Layer để phân biệt service trên cùng host.
- Bao gồm [Routing](./routing.md) ở Layer 3 — vì routing chọn đường đi cho packet ở Network Layer.
