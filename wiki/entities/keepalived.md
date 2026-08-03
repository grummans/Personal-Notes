---
type: entity
topics: [keepalived, vrrp, high-availability, load-balancing, virtual-ip]
status: reviewed
updated: 2026-07-29
---

# Keepalived

> Cập nhật lần cuối: 2026-07-29

## Tóm tắt

Keepalived là ứng dụng open-source chạy trên Linux để cung cấp high availability và load balancing. Ghi chú hiện có tập trung vào việc Keepalived dùng VRRP để chia sẻ một Virtual IP giữa các node.

## Chi tiết

Các thành phần chính gồm VRRP Engine, Health Check và Notify. VRRP Engine xử lý election master; health check có thể dùng `check_script`; notify có thể gọi script như `notify.sh`.

Node trong cụm có các trạng thái `MASTER`, `BACKUP` và `FAULT`. MASTER gửi VRRP Advertisement liên tục. Khi health check fail hoặc priority thay đổi, BACKUP so sánh priority và có thể trở thành MASTER, gán VIP rồi gửi Gratuitous ARP để client tiếp tục truy cập qua VIP.

File cấu hình chính là `/etc/keepalived/keepalived.conf`; binary thường ở `/usr/sbin/keepalived`; service systemd ở `/lib/systemd/system/keepalived.service`.

## Nguồn liên quan

- [Keepalived introduce](../sources/personal-notes-linux-service-keepalived-introduce.md)
- [Keepalived architecture](../sources/personal-notes-linux-service-keepalived-architecture.md)
- [Keepalived working flow](../sources/personal-notes-linux-service-keepalived-working-flow.md)
- [Keepalived file architecture](../sources/personal-notes-linux-service-keepalived-file-architecture.md)

## Quan hệ

- Sử dụng [VRRP](../concepts/vrrp.md) — vì Keepalived dùng VRRP để chia sẻ Virtual IP giữa các node.
- Có failover flow được mô tả ở [Keepalived failover flow](../concepts/keepalived-failover-flow.md) — vì flow đó mô tả cách Keepalived chuyển VIP từ MASTER sang BACKUP.
- Liên quan tới [Nginx](./nginx.md) — liên kết chưa được xác nhận; cả hai cùng xuất hiện trong ngữ cảnh availability/load-balancing nhưng wiki chưa có source nối trực tiếp Keepalived với Nginx.
