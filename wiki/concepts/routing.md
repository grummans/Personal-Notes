---
type: concept
topics: [networking, routing, ip, cidr, network-layer, vms]
status: raw
updated: 2026-08-06
---

# Routing

## Tóm tắt

Routing là quá trình chọn đường đi để chuyển packet từ source tới destination qua một hoặc nhiều network.

## Chi tiết

Routing thường được thực hiện bởi router, dựa trên routing table và routing protocol. Routing table chứa các rule cho biết destination range nào đi qua gateway nào và interface nào.

Dạng đọc phổ biến là `Destination via Next Hop dev Interface`, ví dụ default route qua gateway của mạng local, hoặc route tới network Docker bridge qua interface `docker0`.

## Nguồn liên quan

- [Routing source](../sources/personal-notes-networking-routing.md)

## Quan hệ

- Dựa trên [IP](./ip.md) — vì routing dùng địa chỉ IP/destination range để quyết định đường đi của packet.
- Liên quan tới [Subnetting](./subnetting.md) — vì routing table match route theo network range/CIDR.
- Thuộc [OSI Model](./osi-model.md) — vì routing là trách nhiệm của Network Layer.
- Liên quan tới [VPN](./vpn.md) — vì VPN tạo tunnel làm thay đổi đường đi logic của traffic tới private network.
- Liên quan tới [VMS streaming flow](./vms-streaming-flow.md) — vì nhiều server nhận và chuyển tiếp streaming flow qua các hop trong hệ thống.
- Liên quan tới [VMS benchmark](./vms-benchmark.md) — liên kết chưa được xác nhận; benchmark nói bottleneck NIC và input/output stream, nhưng chưa mô tả routing table cụ thể.
