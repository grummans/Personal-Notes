---
type: entity
topics: [vms, rtsp, video-streaming, camera, monitoring]
status: raw
updated: 2026-08-06
---

# VMS

## Tóm tắt

VMS (Video Management System) trong ghi chú hiện có là hệ thống nhận luồng camera qua RTSP, phân phối qua các lớp staging/RTSP server/VMS server, rồi hiển thị trên VMS client.

## Chi tiết

Luồng tổng quát: camera tạo original RTSP stream, [VMS Staging](./vms-staging.md) thu thập input stream, gửi sang [RTSP Server](./rtsp-server.md), RTSP server clone hoặc restream thành nhiều luồng, [VMS Server](./vms-server.md) nhận các luồng đó và phân phối cho [VMS Client](./vms-client.md) để live view.

Ghi chú benchmark cho hệ thống Vivas VMS nêu ngưỡng failover khoảng 350 camera flow, với NIC 1Gbps là bottleneck chính khi số camera tăng.

## Nguồn liên quan

- [VMS system flow source](../sources/personal-notes-vms-vms-system-flow.md)
- [VMS server source](../sources/personal-notes-vms-vms-server.md)
- [VMS client source](../sources/personal-notes-vms-vms-client.md)
- [VMS benchmark source](../sources/personal-notes-vms-benchmark-vms.md)

## Quan hệ

- Bao gồm [VMS streaming flow](../concepts/vms-streaming-flow.md) — vì flow mô tả chuỗi camera, staging, RTSP server, VMS server và client của hệ thống.
- Bao gồm [VMS Staging](./vms-staging.md) — vì staging nhận stream camera đầu vào trước khi chuyển tiếp.
- Bao gồm [RTSP Server](./rtsp-server.md) — vì RTSP server restream/clone luồng cho VMS server.
- Bao gồm [VMS Server](./vms-server.md) — vì server trung tâm nhận luồng từ các RTSP server và phân phối cho client.
- Bao gồm [VMS Client](./vms-client.md) — vì client dùng để live view camera stream.
- Liên quan tới [VMS benchmark](../concepts/vms-benchmark.md) — vì benchmark đo giới hạn camera flow và bottleneck của VMS.
