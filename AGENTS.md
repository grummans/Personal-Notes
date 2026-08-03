# Second Brain — Agent Rules

Đây là repo second brain cá nhân, vận hành theo pattern LLM Wiki (Karpathy),
kết hợp mô hình Zettelkasten cho việc liên kết giữa các trang.

## Quy tắc bất biến

- `Personal-Notes/` = READ-ONLY đối với agent. Đây là note tay của con người.
  Nhiệm vụ của agent là ĐỌC để trích xuất thông tin, KHÔNG BAO GIỜ ghi, sửa,
  xóa, hay đổi tên file trong thư mục này, dưới bất kỳ lý do gì.
- `wiki/` = layer duy nhất agent được phép ghi/sửa. Toàn bộ output tổng hợp,
  liên kết, tóm tắt đều đi vào đây.

## Phân loại nội dung trong Personal-Notes/

- `Personal-Notes/` — note kỹ thuật, học tập, debug log. Đây là nguồn
  hợp lệ để index vào wiki/. Có thể có thư mục con theo chủ đề tuỳ ý
  (vd: `networking`, `docker`) — không ảnh hưởng tới cấu trúc
  phẳng của `wiki/concepts/` và `wiki/entities/`.
- `Personal-Notes/daily-notes/` — nhật ký cá nhân, cảm nghĩ, ghi chép hàng ngày
  không mang tính kỹ thuật. KHÔNG tổng hợp vào wiki/, KHÔNG trích xuất khái
  niệm/entity từ đây, KHÔNG tạo trang wiki/sources/ tương ứng.
  Nếu tôi yêu cầu "index file X" mà X nằm trong journal/, hỏi lại xác nhận
  trước khi thực hiện thay vì tự động xử lý.

## Cấu trúc wiki/

- `wiki/index.md` — bản đồ tổng, entrypoint đầu tiên khi trả lời câu hỏi
- `wiki/graph.md` — quan hệ có kiểu (typed relationship) giữa các trang,
  dùng để tìm liên kết chéo và phát hiện orphan mà
  không cần đọc lại toàn bộ nội dung từng trang
- `wiki/concepts/` — khái niệm/kỹ thuật (vd: VRRP, CATALINA_HOME, keepalived failover).
  Giữ CẤU TRÚC PHẲNG (flat) — không tạo thư mục con
  theo chủ đề dù số lượng file lớn. Trật tự đến từ
  `topics` trong frontmatter, link chéo, và graph.md.
- `wiki/entities/` — công cụ/công nghệ cụ thể (vd: Tomcat, Nginx, Pacemaker, NixOS).
  Cũng giữ cấu trúc phẳng như concepts/.
- `wiki/sources/` — mỗi file trong Personal-Notes/tech/ có 1 trang tóm tắt tương ứng
- `wiki/syntheses/` — bài tổng hợp lớn, so sánh, hoặc quyết định kiến trúc

## Metadata frontmatter cho mỗi trang concepts/ và entities/

Mọi trang trong `wiki/concepts/` và `wiki/entities/` bắt đầu bằng frontmatter:

```yaml
---
type: concept # concept | entity
topics: [docker, networking, tcp-ip]
status: raw # raw | reviewed
updated: YYYY-MM-DD
---
```

- `topics` là danh sách từ khoá tự do, không giới hạn số lượng, dùng để lọc
  nhanh các trang liên quan mà KHÔNG cần đọc nội dung đầy đủ — đây là cơ chế
  chính giúp bước "tìm liên kết chéo" không phải quét toàn bộ wiki mỗi lần.
- `status: raw` khi trang mới tạo/cập nhật tự động; đổi thành `reviewed` chỉ
  khi tôi xác nhận đã đọc và đồng ý với nội dung.

## Quy tắc liên kết (links)

KHÔNG dùng cú pháp `[[wikilink]]`. Neovim không hỗ trợ cú pháp này (không có
tag jump built-in cho wikilink).

Luôn dùng markdown link chuẩn với đường dẫn tương đối, để lệnh `gf` trong
Neovim nhảy tới file được:

```
[VRRP concept](../concepts/vrrp.md)
```

- Đường dẫn luôn tương đối so với vị trí file hiện tại (không dùng đường dẫn
  tuyệt đối).
- Text hiển thị trong `[...]` nên là tên khái niệm/entity, rõ ràng, không viết
  tắt khó hiểu.
- Khi link tới file trong `wiki/sources/` trỏ ngược về `Personal-Notes/tech/`,
  vẫn dùng path tương đối, ví dụ:
  `[Nguồn: keepalived-vrrp-notes](../../Personal-Notes/tech/2026-07-29-vrrp.md)`.

## Quy trình khi có note mới (chỉ áp dụng cho Personal-Notes/tech/)

Khi tôi yêu cầu "index file X" hoặc "cập nhật wiki từ Personal-Notes/tech/X":

1. Đọc file X, xác định:
   - Khái niệm chính được đề cập
   - Công cụ/công nghệ cụ thể (entity)
   - Claim/kết luận quan trọng
   - Có mâu thuẫn gì với nội dung đã có trong wiki/ không?
2. Tạo hoặc cập nhật (không ghi đè hoàn toàn) các trang liên quan trong
   `wiki/concepts/` và `wiki/entities/`, kèm frontmatter `topics` phù hợp.
3. Tạo 1 trang trong `wiki/sources/` tóm tắt file X, link ngược về file gốc
   bằng markdown link tương đối.
4. Nếu phát hiện mâu thuẫn với nội dung cũ: KHÔNG xóa nội dung cũ, thêm dòng
   `> Cập nhật YYYY-MM-DD: <mô tả mâu thuẫn/thay đổi>` ngay dưới đoạn liên quan.
5. Tìm liên kết chéo (bắt buộc — xem mục "Tìm liên kết chéo" bên dưới) cho
   mọi trang vừa tạo/cập nhật ở bước 2.
6. Cập nhật `wiki/index.md` và `wiki/graph.md` để phản ánh trang mới/đã sửa,
   dùng markdown link tương đối.

## Tìm liên kết chéo (Zettelkasten — bắt buộc sau mỗi lần tạo/cập nhật trang)

wiki/concepts/ và wiki/entities/ vận hành theo mô hình Zettelkasten: liên kết
đến từ NGUYÊN LÝ NỀN TẢNG chung, không chỉ từ việc 2 trang cùng nguồn hoặc
cùng "chủ đề bề mặt" (vd: cùng nằm trong domain "Network"). Một note về
Docker bridge network và một note về VRRP đều đáng được liên kết nếu cả hai
cùng dựa trên cơ chế Linux networking/iptables bên dưới, dù một cái thuộc
"Docker" và cái kia thuộc "HA infrastructure".

Để tránh phải đọc-hiểu toàn bộ wiki mỗi lần (chi phí tăng theo số trang),
việc tìm ứng viên liên kết đi qua 2 bước: lọc rẻ bằng `topics`, rồi mới đọc
kỹ tập đã lọc:

1. Xác định `topics` của trang vừa tạo/cập nhật.
2. Lọc nhanh: chỉ đọc frontmatter (không đọc toàn bộ nội dung) của các trang
   khác trong `wiki/concepts/` và `wiki/entities/` có ít nhất 1 `topics`
   trùng, HOẶC được nhắc tên trực tiếp trong nội dung trang vừa tạo.
3. Với tập đã lọc, đọc kỹ để xác nhận có nên link không — không suy luận
   liên quan chỉ từ việc trùng topic (topic trùng chỉ là gợi ý để đọc kỹ,
   không phải điều kiện đủ để tự động link).
4. Nếu xác nhận nên link: thêm link 2 chiều vào mục `## Quan hệ` của cả 2
   trang, kèm 1 câu ngắn giải thích LÝ DO liên kết (không chỉ link trơ —
   phải nói rõ kiểu "vì cả hai đều dùng iptables để NAT giữa các
   container/node"), VÀ thêm 1 dòng tương ứng vào `wiki/graph.md` theo định
   dạng:
   ```
   <Trang A> -> <loại quan hệ: uses|depends_on|part_of|related_to> -> <Trang B>
   ```
5. Nếu không chắc chắn mức độ liên quan, vẫn thêm link nhưng ghi chú
   "liên kết chưa được xác nhận" để tôi tự đánh giá sau — không tự loại bỏ
   ứng viên chỉ vì không chắc.

## Batch audit (khi tôi yêu cầu "audit ..." hoặc "tìm liên kết còn thiếu")

KHÔNG quét toàn bộ wiki/ mỗi lần trừ khi tôi yêu cầu rõ "audit toàn bộ".
Mặc định audit theo đúng phạm vi được chỉ định, ví dụ:

- Theo thư mục nguồn: "audit Personal-Notes/tech/networking"
- Theo thay đổi: "audit các note đã sửa từ lần index gần nhất"
- Theo orphan: "audit concept orphan" — tìm các trang trong concepts/ hoặc
  entities/ KHÔNG xuất hiện trong bất kỳ dòng quan hệ nào ở `wiki/graph.md`
- Theo cặp còn thiếu liên kết: "tìm liên kết còn thiếu trong wiki" — nhóm
  các trang theo `topics` trùng nhau trước (rẻ), chỉ so khớp cặp-với-cặp
  (đắt hơn) trong phạm vi từng nhóm, không so mù toàn bộ wiki

Với mọi loại audit: liệt kê danh sách phát hiện được (orphan, cặp nên liên
kết, mâu thuẫn...) kèm lý do cụ thể, CHỜ tôi xác nhận trước khi sửa hàng loạt
— không tự động thêm/xoá link hay nội dung trên diện rộng.

## Quy trình tạo trang trong syntheses/

Khác với concepts/ và entities/ (tự động cập nhật mỗi khi index nguồn mới),
syntheses/ CHỈ được tạo/cập nhật khi tôi yêu cầu rõ ràng, ví dụ:
"tổng hợp so sánh X và Y", "viết synthesis về...", "tóm tắt quyết định về...".

Khi được yêu cầu:

1. Tìm và đọc các trang concepts/, entities/, sources/ liên quan tới chủ đề.
2. Tổng hợp thành 1 trang mới trong syntheses/, có cấu trúc:
   - Bối cảnh/câu hỏi đặt ra
   - Các phương án/khía cạnh được so sánh (dẫn link tới concepts/entities liên quan)
   - Nhận định tổng hợp (nêu rõ đây là bản nháp tổng hợp, không phải quyết định cuối)
3. KHÔNG tự ý đưa ra kết luận "nên chọn X" thay tôi — chỉ trình bày dữ kiện
   và trade-off một cách khách quan, để tôi tự quyết định.
4. Link từ syntheses/ page về lại các concepts/entities/sources liên quan,
   và ngược lại có thể thêm link "Xem thêm: [synthesis liên quan]" ở cuối
   trang concept nếu phù hợp.

## Quy trình khi trả lời câu hỏi

1. Luôn đọc `wiki/index.md` trước tiên để định vị.
2. Chỉ mở các trang liên quan trong `wiki/`, tránh quét toàn bộ `Personal-Notes/`
   trừ khi wiki chưa có thông tin cần thiết.
3. Trả lời kèm trích dẫn markdown link tới trang wiki cụ thể (không chỉ nói suông).
4. Nếu thông tin không có trong wiki lẫn Personal-Notes/tech/, nói rõ là chưa
   có dữ liệu, không suy đoán.

## Format chuẩn cho 1 trang wiki

```
---
type: concept
topics: [tag1, tag2]
status: raw
updated: YYYY-MM-DD
---

# <Tên khái niệm/entity>

## Tóm tắt

...

## Chi tiết

...

## Nguồn liên quan
- [Tên nguồn](../../Personal-Notes/tech/ten-file.md)

## Quan hệ
- Liên quan tới [TCP/IP](./tcp-ip.md) — vì cùng dùng chung tầng Transport
- Được dùng bởi [Docker bridge network](./docker-bridge-network.md)
```

## Format wiki/graph.md

```
# Graph — quan hệ giữa các trang

Docker bridge network -> uses -> Linux bridge
Docker port publishing -> depends_on -> NAT
TCP -> part_of -> TCP/IP Transport Layer
```
