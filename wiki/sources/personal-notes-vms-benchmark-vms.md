# Source: VMS benchmark

> Cập nhật lần cuối: 2026-08-06

## Tóm tắt

Ghi chú mô tả benchmark VMS bằng cách tăng số camera flow từ 200 lên 250, 300, 400 và cao hơn cho tới failover. Với Vivas VMS, failover point khoảng 350 camera. Bottleneck chính là NIC 1Gbps do bandwidth tăng theo số camera; hướng xử lý gồm nâng NIC, thêm NIC kèm bonding để tách input/output stream, hoặc giảm bitrate/main-sub stream.

## Nguồn gốc

- [Nguồn: Personal-Notes/VMS/benchmark-vms.md](../../Personal-Notes/VMS/benchmark-vms.md)

## Liên kết

- [VMS](../entities/vms.md)
- [VMS Server](../entities/vms-server.md)
- [VMS benchmark](../concepts/vms-benchmark.md)
- [VMS streaming flow](../concepts/vms-streaming-flow.md)
