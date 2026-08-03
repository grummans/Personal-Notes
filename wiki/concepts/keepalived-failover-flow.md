---
type: concept
topics: [keepalived, vrrp, high-availability, failover, virtual-ip]
status: reviewed
updated: 2026-07-29
---

# Keepalived Failover Flow

> Cập nhật lần cuối: 2026-07-29

## Tóm tắt

Keepalived failover dựa trên trạng thái MASTER/BACKUP, VRRP Advertisement, health check và priority để quyết định node nào giữ Virtual IP.

## Chi tiết

Flow chính trong ghi chú:

```text
MASTER giữ VIP
-> gửi Advertisement
-> health check OK thì tiếp tục MASTER
-> health check FAIL thì giảm priority
-> BACKUP so sánh priority
-> nếu BACKUP cao hơn thì BACKUP trở thành MASTER
-> gán VIP cho BACKUP
-> gửi Gratuitous ARP
-> client tiếp tục truy cập VIP
```

Trong `keepalived.conf`, các khối quan trọng gồm `global_defs`, `vrrp_script`, `vrrp_instance` và `virtual_server`.

## Nguồn liên quan

- [Keepalived working flow source](../sources/personal-notes-linux-service-keepalived-working-flow.md)
- [Keepalived configuration source](../sources/personal-notes-linux-service-keepalived-how-to-config.md)

## Quan hệ

- Là flow failover của [Keepalived](../entities/keepalived.md) — vì trang này mô tả cách Keepalived chuyển VIP giữa MASTER/BACKUP.
- Phụ thuộc vào [VRRP](./vrrp.md) — vì failover dùng VRRP Advertisement, priority và trạng thái MASTER/BACKUP.
- Phụ thuộc vào [IP](./ip.md) — vì failover gán Virtual IP cho BACKUP để client tiếp tục truy cập qua VIP.
- Liên quan tới [Nginx](../entities/nginx.md) — liên kết chưa được xác nhận; cả hai có thể cùng nằm trên availability/load-balancing path nhưng wiki chưa có source nối trực tiếp.
