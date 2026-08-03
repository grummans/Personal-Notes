# TCP vs UDP

> Cập nhật lần cuối: 2026-08-03

## Bối cảnh/câu hỏi đặt ra

Trong mô hình [TCP/IP](../concepts/tcp-ip.md), [TCP](../concepts/tcp.md) và [UDP](../concepts/udp.md) đều nằm ở Transport Layer. Cả hai đều phục vụ việc truyền dữ liệu giữa các chương trình qua mạng, nhưng khác nhau ở cách đánh đổi giữa độ tin cậy, tốc độ, độ trễ và overhead.

Trang này là bản nháp tổng hợp từ các note hiện có, không phải quyết định cuối cho mọi hệ thống.

## Các phương án/khía cạnh được so sánh

### TCP

[TCP](../concepts/tcp.md) là protocol connection-oriented. Hai thiết bị handshake trước khi gửi dữ liệu, dữ liệu được chia thành packet nhỏ, đánh số, chờ acknowledge và resend khi packet bị mất.

Điểm mạnh của TCP là đảm bảo dữ liệu đến đủ, đúng thứ tự và không bị xáo trộn theo mô tả trong note. Trade-off là có thêm overhead và độ trễ vì cần handshake, acknowledge và resend.

TCP phù hợp với các ứng dụng nơi tính đúng/đủ của dữ liệu quan trọng hơn độ trễ thấp tuyệt đối. Theo wiki hiện có, các note chưa gán cụ thể từng application protocol như HTTP/HTTPS/SSH sang TCP, nên phần ứng dụng ở đây chỉ nêu theo tiêu chí kỹ thuật: dữ liệu cần đầy đủ, đúng thứ tự, và có thể chấp nhận thêm overhead.

### UDP

[UDP](../concepts/udp.md) là protocol connectionless. UDP không handshake, không acknowledge; nó chỉ address dữ liệu rồi gửi đi.

Điểm mạnh của UDP là nhanh và ít overhead hơn TCP. Trade-off là không guaranteed delivery: dữ liệu có thể mất, thiếu hoặc không đến theo cách application mong muốn nếu không có cơ chế bổ sung ở tầng trên.

UDP phù hợp với các ứng dụng ưu tiên tốc độ/độ trễ thấp hoặc có thể chấp nhận mất một phần dữ liệu. Wiki hiện có chưa có note riêng về các ứng dụng cụ thể chạy trên UDP, nên phần ứng dụng ở đây chỉ nêu theo tiêu chí kỹ thuật: gửi nhanh, ít bước, không cần guarantee mặc định ở Transport Layer.

## Bảng so sánh nhanh

| Khía cạnh             | TCP                   | UDP                                    |
| --------------------- | --------------------- | -------------------------------------- |
| Kiểu kết nối          | Connection-oriented   | Connectionless                         |
| Handshake             | Có                    | Không                                  |
| Acknowledge           | Có                    | Không                                  |
| Resend khi mất packet | Có                    | Không mặc định                         |
| Đảm bảo thứ tự        | Có theo cơ chế TCP    | Không mặc định                         |
| Overhead              | Cao hơn               | Thấp hơn                               |
| Độ trễ                | Thường cao hơn        | Thường thấp hơn                        |
| Phù hợp khi           | Cần đúng, đủ, ổn định | Cần nhanh, realtime, chấp nhận mất mát |

## Nhận định tổng hợp

TCP và UDP không phải quan hệ tốt/xấu tuyệt đối. Chúng phục vụ hai nhóm trade-off khác nhau trong Transport Layer của [TCP/IP](../concepts/tcp-ip.md).

TCP ưu tiên reliability: dữ liệu cần đến đủ và đúng thứ tự, đổi lại phải trả giá bằng handshake, acknowledge, resend và overhead. UDP ưu tiên tốc độ và đơn giản: gửi nhanh, ít bước, nhưng không tự đảm bảo delivery.

Trong thực tế, lựa chọn phụ thuộc vào yêu cầu của application. Nếu mất một packet làm hỏng nghiệp vụ hoặc dữ liệu cần chính xác, TCP nghiêng về trade-off phù hợp hơn. Nếu độ trễ thấp quan trọng hơn và application có thể tự xử lý mất mát hoặc chấp nhận mất mát, UDP nghiêng về trade-off phù hợp hơn.

## Nguồn liên quan

- [TCP](../concepts/tcp.md)
- [UDP](../concepts/udp.md)
- [TCP/IP](../concepts/tcp-ip.md)
- [IP](../concepts/ip.md)
- [TCP/UDP/IP source](../sources/personal-notes-networking-tcp-upd-ip.md)
- [TCP/IP source](../sources/personal-notes-networking-tcp-ip.md)
