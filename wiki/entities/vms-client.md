---
type: entity
topics: [vms, client, video-streaming, camera, monitoring]
status: raw
updated: 2026-08-06
---

# VMS Client

## Tóm tắt

VMS Client là ứng dụng phía người dùng để live view camera streaming flow trong hệ thống VMS.

## Chi tiết

Client đứng ở cuối flow: [VMS Server](./vms-server.md) phân phối streaming data cho client, rồi client hiển thị lên màn hình giám sát.

## Nguồn liên quan

- [VMS client source](../sources/personal-notes-vms-vms-client.md)
- [VMS system flow source](../sources/personal-notes-vms-vms-system-flow.md)

## Quan hệ

- Là một phần của [VMS](./vms.md) — vì client là nơi người dùng xem camera stream.
- Nhận dữ liệu từ [VMS Server](./vms-server.md) — vì server phân phối streaming data cho client.
- Tham gia [VMS streaming flow](../concepts/vms-streaming-flow.md) — vì client là điểm cuối hiển thị monitor trong flow.
