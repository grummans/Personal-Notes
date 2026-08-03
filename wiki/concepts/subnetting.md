---
type: concept
topics: [networking, ip, subnetting, cidr, routing]
status: raw
updated: 2026-08-03
---

# Subnetting

## Tóm tắt

Subnetting là cách chia một network lớn thành các subnet nhỏ hơn bằng cách mượn bit từ phần host của địa chỉ IP.

## Chi tiết

Với IPv4, địa chỉ có 32 bit và thường được nhìn như hai phần: Network ID xác định network, Host ID xác định thiết bị trong network đó. Subnetting thay đổi ranh giới giữa hai phần này để tạo thêm nhiều network con.

CIDR notation biểu diễn kích thước network bằng dạng `IP/prefix`, ví dụ `192.168.1.10/24`. Số địa chỉ trong subnet IPv4 có thể tính bằng `2^(32 - prefix)`, nên `192.168.1.0/24` có 256 địa chỉ.

Các private network phổ biến gồm `10.0.0.0/8`, `172.16.0.0/12` và `192.168.0.0/16`.

## Nguồn liên quan

- [Subnetting source](../sources/personal-notes-networking-subnetting.md)

## Quan hệ

- Dựa trên [IP](./ip.md) — vì subnetting chia không gian địa chỉ IPv4 thành Network ID và Host ID.
- Liên quan tới [Routing](./routing.md) — vì routing table thường match packet theo destination range/CIDR để chọn gateway hoặc interface.
