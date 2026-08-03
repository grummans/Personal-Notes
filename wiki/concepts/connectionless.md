---
type: concept
topics: [networking, udp, transport-layer, latency]
status: raw
updated: 2026-08-03
---

# Connectionless

## Tóm tắt

Connectionless là kiểu giao tiếp không yêu cầu thiết lập connection trước khi gửi dữ liệu.

## Chi tiết

Connectionless không bảo đảm delivery hoặc reliability ở chính tầng giao tiếp đó. Trade-off là dữ liệu có thể được gửi nhanh hơn vì không cần bước thiết lập kết nối trước.

## Nguồn liên quan

- [Connectionless source](../sources/personal-notes-networking-connectionless.md)

## Quan hệ

- Là tính chất của [UDP](./udp.md) — vì UDP gửi datagram mà không handshake trước.
- Đối lập với [Connection-Oriented](./connection-oriented.md) — vì connection-oriented yêu cầu connection trước khi truyền dữ liệu.
