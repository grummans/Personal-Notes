---
type: concept
topics: [networking, dns, ip, protocol, application-layer]
status: raw
updated: 2026-08-03
---

# DNS

## Tóm tắt

DNS (Domain Name System) chuyển domain name thành địa chỉ IP để máy có thể kết nối tới đúng host.

## Chi tiết

Khi lookup một domain, máy thường hỏi resolver trước. Resolver hỏi root server để tìm TLD server phù hợp, TLD server trỏ tới authoritative server của domain, rồi authoritative server trả về record thật. Resolver có thể cache kết quả để lần lookup sau nhanh hơn.

Một số record thường gặp:

- `A`: trỏ name tới IPv4 address.
- `AAAA`: trỏ name tới IPv6 address.
- `CNAME`: alias từ name này sang name khác.
- `MX`: mail server xử lý email cho domain.
- `TXT`: text tự do, thường dùng cho verification.
- `NS`: name server authoritative cho domain.

## Nguồn liên quan

- [DNS source](../sources/personal-notes-networking-dns.md)

## Quan hệ

- Dựa trên [IP](./ip.md) — vì kết quả lookup thường là địa chỉ IP để client kết nối tới host.
- Là một [Protocol](./protocol.md) — vì DNS định nghĩa quy tắc phân giải tên miền thành record.
- Thuộc [TCP/IP](./tcp-ip.md) — vì DNS là ví dụ Application Layer trong mô hình TCP/IP.
- Liên quan tới [Port](./port.md) — vì DNS thường dùng port `53`.
