---
type: concept
topics: [vms, benchmark, video-streaming, nic, bandwidth, failover]
status: raw
updated: 2026-08-06
---

# VMS benchmark

## Tóm tắt

VMS benchmark trong ghi chú dùng số camera flow tăng dần để tìm giới hạn chịu tải của server và bottleneck mạng.

## Chi tiết

Quy trình benchmark bắt đầu với 200 camera flow, kiểm tra performance server, rồi tăng lên 250, 300, 400 và tiếp tục cho tới khi failover. Với hệ thống Vivas VMS, ghi chú nêu failover point khoảng 350 camera.

Bottleneck được ghi nhận là NIC: càng nhiều camera thì bandwidth tiêu thụ càng cao, khiến NIC 1Gbps trở thành điểm nghẽn. Các hướng xử lý gồm nâng NIC lên 2.5Gbps/5Gbps/10Gbps, mở rộng card mạng kèm bonding để tách input/output stream, hoặc tối ưu stream bằng cách giảm bitrate và dùng main/sub-stream phù hợp.

## Nguồn liên quan

- [VMS benchmark source](../sources/personal-notes-vms-benchmark-vms.md)

## Quan hệ

- Đo giới hạn của [VMS](../entities/vms.md) — vì benchmark tăng số camera flow để tìm điểm failover của hệ thống.
- Đo [VMS Server](../entities/vms-server.md) — vì ghi chú kiểm tra performance server khi nhận nhiều camera flow.
- Liên quan tới [VMS streaming flow](./vms-streaming-flow.md) — vì số camera flow trong benchmark chính là lượng stream đi qua pipeline VMS.
- Liên quan tới [IP](./ip.md) — vì bandwidth camera flow phụ thuộc vào traffic đi qua network stack.
- Liên quan tới [Routing](./routing.md) — liên kết chưa được xác nhận; benchmark nói bottleneck NIC và input/output stream, nhưng chưa mô tả routing table cụ thể.
