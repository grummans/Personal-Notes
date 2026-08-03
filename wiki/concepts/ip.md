---
type: concept
topics: [networking, ip, tcp-ip, network-layer, routing, subnetting, dns, vpn]
status: raw
updated: 2026-08-03
---

# IP

> Cập nhật lần cuối: 2026-08-03

## Tóm tắt

IP (Internet Protocol) hoạt động ở Network Layer và dùng địa chỉ IP để đưa packet tới đúng đích.

## Chi tiết

Mỗi thiết bị có một địa chỉ IP riêng. IP sử dụng địa chỉ này để chuyển packet từ máy này sang máy khác, bảo đảm packet được gửi tới đúng destination ở tầng mạng.

Trong mô hình [TCP/IP](./tcp-ip.md), IP nằm ở Internet Layer, cùng nhóm với các cơ chế như IPv4/IPv6, ICMP và ARP theo note TCP/IP.

## Nguồn liên quan

- [TCP/UDP/IP source](../sources/personal-notes-networking-tcp-upd-ip.md)
- [TCP/IP source](../sources/personal-notes-networking-tcp-ip.md)
- [Subnetting source](../sources/personal-notes-networking-subnetting.md)
- [Routing source](../sources/personal-notes-networking-routing.md)
- [DNS source](../sources/personal-notes-networking-dns.md)
- [VPN source](../sources/personal-notes-networking-vpn.md)

## Quan hệ

- Là một [Protocol](./protocol.md) — vì IP là bộ quy tắc dùng địa chỉ IP để đưa packet tới đúng destination.
- Là một phần của [TCP/IP](./tcp-ip.md) — vì IP nằm ở Internet Layer trong mô hình TCP/IP.
- Liên quan tới [OSI Model](./osi-model.md) — vì IP tương ứng với Network Layer trong OSI.
- Được dùng bởi [Nginx architecture](./nginx-architecture.md) — vì request cần IP/network stack để tới đúng destination trước khi worker xử lý.
- Được dùng bởi [VRRP](./vrrp.md) — vì VRRP chia sẻ một Virtual IP giữa nhiều router/node.
- Được dùng bởi [Keepalived failover flow](./keepalived-failover-flow.md) — vì failover gán Virtual IP cho node BACKUP để client tiếp tục truy cập.
- Là nền tảng của [Subnetting](./subnetting.md) — vì subnetting chia không gian địa chỉ IPv4 thành network/host và các subnet nhỏ hơn.
- Được dùng bởi [Routing](./routing.md) — vì routing chọn next hop dựa trên destination IP/range.
- Được phân giải bởi [DNS](./dns.md) — vì DNS chuyển domain name thành địa chỉ IP.
- Liên quan tới [VPN](./vpn.md) — vì VPN tunnel vẫn cần IP để endpoint và traffic được định tuyến.
