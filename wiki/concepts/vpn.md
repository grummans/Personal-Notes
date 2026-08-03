---
type: concept
topics: [networking, vpn, tunneling, encryption, routing]
status: raw
updated: 2026-08-03
---

# VPN

## Tóm tắt

VPN (Virtual Private Network) cho phép dùng Internet như thể đang kết nối trực tiếp vào một private network, bằng cách bọc traffic trong tunnel được mã hóa.

## Chi tiết

VPN hữu ích khi máy đang ở mạng public nhưng cần truy cập tài nguyên như trong private network. Ý chính trong note là VPN wrap traffic trong encrypted tunnel để tạo kết nối logic tới private network.

## Nguồn liên quan

- [VPN source](../sources/personal-notes-networking-vpn.md)

## Quan hệ

- Liên quan tới [Routing](./routing.md) — vì VPN tunnel ảnh hưởng đường đi logic của packet giữa client và private network.
- Liên quan tới [IP](./ip.md) — vì traffic bên trong/ngoài tunnel vẫn cần địa chỉ IP để đi tới endpoint phù hợp.
