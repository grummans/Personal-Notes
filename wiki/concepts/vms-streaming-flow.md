---
type: concept
topics: [vms, rtsp, video-streaming, camera, network-flow]
status: raw
updated: 2026-08-06
---

# VMS streaming flow

## Tóm tắt

VMS streaming flow mô tả đường đi của luồng camera RTSP từ camera tới staging, RTSP server, VMS server, VMS client và màn hình hiển thị.

## Chi tiết

Chuỗi flow trong ghi chú:

- Camera tạo original RTSP stream.
- [VMS Staging](../entities/vms-staging.md) thu thập input stream.
- [RTSP Server](../entities/rtsp-server.md) nhận và restream/clone thành nhiều RTSP stream flow.
- [VMS Server](../entities/vms-server.md) nhận nhiều flow, quản lý camera/user/permission và phân phối dữ liệu.
- [VMS Client](../entities/vms-client.md) nhận dữ liệu để hiển thị monitor.

## Nguồn liên quan

- [VMS system flow source](../sources/personal-notes-vms-vms-system-flow.md)
- [VMS staging source](../sources/personal-notes-vms-vms-stagging.md)
- [RTSP server source](../sources/personal-notes-vms-rtsp-server.md)
- [VMS server source](../sources/personal-notes-vms-vms-server.md)
- [VMS client source](../sources/personal-notes-vms-vms-client.md)

## Quan hệ

- Thuộc [VMS](../entities/vms.md) — vì flow này mô tả pipeline chính của hệ thống VMS.
- Bắt đầu tại [VMS Staging](../entities/vms-staging.md) sau camera — vì staging thu input stream trước khi phân phối.
- Dùng [RTSP Server](../entities/rtsp-server.md) — vì RTSP server restream/clone flow cho VMS server.
- Đi qua [VMS Server](../entities/vms-server.md) — vì server nhận flow và phân phối dữ liệu cho client.
- Kết thúc ở [VMS Client](../entities/vms-client.md) — vì client hiển thị camera stream.
- Liên quan tới [IP](./ip.md) — vì các luồng RTSP đi giữa camera/server/client qua network addressing.
- Liên quan tới [Routing](./routing.md) — vì nhiều server nhận và chuyển tiếp streaming flow qua các hop trong hệ thống.
