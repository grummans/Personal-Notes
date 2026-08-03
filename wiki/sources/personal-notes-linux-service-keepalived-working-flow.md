# Source: Keepalived Working Flow

> Cập nhật lần cuối: 2026-07-29

## Tóm tắt

Ghi chú mô tả failover flow: MASTER giữ VIP và gửi Advertisement; nếu health check fail thì giảm priority; BACKUP so sánh priority và có thể trở thành MASTER, assign VIP, gửi Gratuitous ARP để client tiếp tục truy cập VIP.

## Nguồn gốc

- [Nguồn: Personal-Notes/Linux/Service/Keepalived/working-flow.md](../../Personal-Notes/Linux/Service/Keepalived/working-flow.md)

## Liên kết

- [Keepalived](../entities/keepalived.md)
- [Keepalived failover flow](../concepts/keepalived-failover-flow.md)
- [VRRP](../concepts/vrrp.md)
