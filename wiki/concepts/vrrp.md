---
type: concept
topics: [networking, vrrp, keepalived, high-availability, virtual-ip]
status: reviewed
updated: 2026-07-29
---

# VRRP

> Cập nhật lần cuối: 2026-07-29

## Tóm tắt

VRRP là Virtual Router Redundancy Protocol, một network protocol dùng để tạo virtual gateway, chia sẻ một IP duy nhất giữa nhiều router/node và tự động chuyển đổi khi có sự cố.

## Chi tiết

Trong ghi chú Keepalived, VRRP ban đầu được thiết kế cho router và được Keepalived áp dụng cho Linux để cung cấp high availability bằng Virtual IP.

Một node có thể ở trạng thái `MASTER`, `BACKUP` hoặc `FAULT`. MASTER gửi multicast advertisement liên tục. Nếu MASTER lỗi hoặc priority giảm, BACKUP có thể trở thành MASTER và nhận VIP.

## Nguồn liên quan

- [Keepalived VRRP source](../sources/personal-notes-linux-service-keepalived-vrrp.md)
- [Keepalived architecture source](../sources/personal-notes-linux-service-keepalived-architecture.md)

## Quan hệ

- Được dùng bởi [Keepalived](../entities/keepalived.md) — vì Keepalived áp dụng VRRP trên Linux để cung cấp high availability bằng Virtual IP.
- Là nền tảng của [Keepalived failover flow](./keepalived-failover-flow.md) — vì failover dựa trên trạng thái MASTER/BACKUP, Advertisement và priority của VRRP.
- Phụ thuộc vào [IP](./ip.md) — vì VRRP tạo/chia sẻ Virtual IP giữa nhiều router/node.
