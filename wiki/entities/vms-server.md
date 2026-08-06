---
type: entity
topics: [vms, rtsp, video-streaming, server, camera]
status: raw
updated: 2026-08-06
---

# VMS Server

## Tóm tắt

VMS Server là server trung tâm nhận các RTSP stream flow từ nhiều RTSP server và phân phối dữ liệu streaming cho client xem camera.

## Chi tiết

Trong flow VMS, [RTSP Server](./rtsp-server.md) restream nhiều luồng tới VMS Server. VMS Server nhận các luồng này, quản lý camera, user, permission theo sơ đồ hệ thống, rồi phục vụ [VMS Client](./vms-client.md) để live view.

## Nguồn liên quan

- [VMS server source](../sources/personal-notes-vms-vms-server.md)
- [VMS system flow source](../sources/personal-notes-vms-vms-system-flow.md)
- [VMS benchmark source](../sources/personal-notes-vms-benchmark-vms.md)

## Quan hệ

- Là một phần của [VMS](./vms.md) — vì VMS server là server trung tâm trong hệ thống.
- Nhận stream từ [RTSP Server](./rtsp-server.md) — vì RTSP server clone/restream nhiều flow tới VMS server.
- Phục vụ [VMS Client](./vms-client.md) — vì client nhận dữ liệu từ VMS server để xem camera.
- Tham gia [VMS streaming flow](../concepts/vms-streaming-flow.md) — vì flow đặt VMS server trước VMS client.
- Bị giới hạn bởi [VMS benchmark](../concepts/vms-benchmark.md) — vì benchmark đo số camera flow mà server chịu được trước failover.
