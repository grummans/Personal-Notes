---
type: entity
topics: [vms, rtsp, video-streaming, camera, staging]
status: raw
updated: 2026-08-06
---

# VMS Staging

## Tóm tắt

VMS Staging là lớp nhận stream từ camera trước khi phân phối tiếp tới các server phía sau trong hệ thống VMS.

## Chi tiết

Theo ghi chú, mỗi camera tạo một RTSP streaming flow. VMS Staging nhận các input stream này và gom chúng trước khi gửi sang [RTSP Server](./rtsp-server.md) để restream.

## Nguồn liên quan

- [VMS staging source](../sources/personal-notes-vms-vms-stagging.md)
- [VMS system flow source](../sources/personal-notes-vms-vms-system-flow.md)

## Quan hệ

- Là một phần của [VMS](./vms.md) — vì staging là lớp đầu vào nhận stream camera trong flow VMS.
- Gửi stream tới [RTSP Server](./rtsp-server.md) — vì RTSP server nhận RTSP stream từ VMS Staging.
- Tham gia [VMS streaming flow](../concepts/vms-streaming-flow.md) — vì flow đặt staging giữa camera và RTSP server.
