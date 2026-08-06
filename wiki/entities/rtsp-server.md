---
type: entity
topics: [vms, rtsp, video-streaming, restream, server]
status: raw
updated: 2026-08-06
---

# RTSP Server

## Tóm tắt

RTSP Server trong ghi chú VMS nhận RTSP stream từ VMS Staging và restream thành nhiều streaming flow cho VMS Server.

## Chi tiết

Vai trò chính của RTSP Server là nhận luồng từ [VMS Staging](./vms-staging.md), sau đó clone hoặc restream `N` streaming flows tới [VMS Server](./vms-server.md).

## Nguồn liên quan

- [RTSP server source](../sources/personal-notes-vms-rtsp-server.md)
- [VMS system flow source](../sources/personal-notes-vms-vms-system-flow.md)

## Quan hệ

- Là một phần của [VMS](./vms.md) — vì RTSP server nằm giữa staging và VMS server trong flow.
- Nhận stream từ [VMS Staging](./vms-staging.md) — vì staging chuyển input stream sang RTSP server.
- Gửi stream tới [VMS Server](./vms-server.md) — vì VMS server nhận `N` flow từ RTSP server.
- Tham gia [VMS streaming flow](../concepts/vms-streaming-flow.md) — vì RTSP server thực hiện restream/clone trong chuỗi xử lý.
- Dùng [Port](../concepts/port.md) — liên kết chưa được xác nhận; RTSP là traffic service-level nên cần port để client/server phân biệt service, nhưng note chưa ghi port cụ thể.
