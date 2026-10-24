# Thiết kế giao diện — Trang CLB đọc sách cộng đồng (TEC-113)

> Tài liệu thiết kế (DESIGN.md) cho trang web CLB đọc sách cộng đồng.
> Repo: https://github.com/Muse-Soft/m-software-clb-doc-sach
> Epic: TEC-112 — "[Epic] Trang web CLB đọc sách cộng đồng" (từ yêu cầu web MSR-15).
>
> **Lưu ý về dữ liệu:** Dữ liệu thật chưa có nên mọi vị trí chưa có dữ liệu thật đều
> để placeholder rõ ràng dạng `[CẦN BỔ SUNG]`. Tuyệt đối KHÔNG tự bịa: tên CLB
> chính thức, địa điểm sinh hoạt cụ thể, danh sách sách thật + tóm tắt, liên hệ
> ban chủ nhiệm. Khi có dữ liệu thật, thay placeholder bằng nội dung thật mà không
> cần đổi bố cục.

## 1. Tinh thần thiết kế

- **Tông màu: giấy cũ + nâu trầm.** Nền như trang giấy cũ (kem ấm, không trắng
  chói), chữ và điểm nhấn nâu trầm, viền mảnh như gáy sách. Cảm giác ấm, yên
  tĩnh, hợp với không khí đọc sách — không dùng màu neon, không nền tối.
- **Chữ lớn, dễ đọc.** Chữ nội dung tối thiểu 18px trên máy tính, 17px trên điện
  thoại; tiêu đề lớn và rõ tầng bậc; giãn dòng rộng (1,7–1,8); đoạn văn ngắn,
  mỗi đoạn không quá 4–5 dòng.
- **Bố cục thoáng.** Một cột nội dung chính ở giữa, lề rộng, khoảng cách giữa các
  mục lớn; mỗi mục chỉ một ý chính; không nhồi nhiều cột, không banner rườm rà.
- **Đối tượng:** mọi lứa tuổi trong cộng đồng, kể cả người lớn tuổi đọc trên điện
  thoại — ưu tiên đọc được ngay, không cần phóng to.

## 2. Bảng màu và chữ

| Vai trò | Màu (mã) | Ghi chú |
|---|---|---|
| Nền giấy | `#F7F0E1` (kem giấy cũ) | Nền toàn trang |
| Nền thẻ | `#FFFDF6` (kem nhạt) | Thẻ mục, thẻ sách |
| Chữ chính | `#3E2A1E` (nâu trầm) | Tiêu đề, nội dung |
| Chữ phụ | `#7A5C44` (nâu nhạt) | Chú thích, ngày giờ phụ |
| Điểm nhấn | `#8B5E34` (nâu gỗ) | Nút, tiêu đề mục, gạch chân |
| Viền | `#D8C7A8` (be) | Viền thẻ, đường kẻ phân mục |
| Nút chính | Nền `#8B5E34`, chữ `#FFFDF6` | Nút "Đăng ký thành viên" |

- **Font chữ:** font có chân (serif) cho tiêu đề — gợi cảm giác sách in; font
  không chân (sans-serif) rõ nét cho nội dung. Nếu font web không có sẵn, dùng
  font hệ thống tương đương, vẫn giữ cỡ chữ và giãn dòng như trên.
- **Nút bấm:** cao tối thiểu 48px, chữ 18px, bo góc nhẹ — bấm dễ trên điện thoại.
- **Trạng thái:** nút khi rê chuột đậm hơn một nấc; không đổi màu đột ngột.

## 3. Bố cục tổng thể (từ trên xuống dưới)

1. **Đầu trang (header):** tên CLB (placeholder, xem mục 4.1) + dòng giới thiệu
   ngắn một câu + nút "Đăng ký thành viên" dẫn xuống mục đăng ký.
2. **Thanh điều hướng đơn giản:** Giới thiệu | Lịch sinh hoạt | Sách tiêu biểu |
   Đăng ký | Quy tắc | Liên hệ — dạng chữ, không menu phức tạp.
3. **Thân trang:** 6 mục theo đúng thứ tự ở mục 4, mỗi mục một khối riêng,
   tiêu đề mục lớn, có đường kẻ be phân cách.
4. **Cuối trang (footer):** nhắc lại tên CLB + địa điểm + liên hệ (đều là
   placeholder cho đến khi có dữ liệu thật) + dòng "Sinh hoạt tối thứ 5 hằng tuần".

- **Responsive (thích ứng màn hình):** một cột trên điện thoại; tối đa hai cột
  cho lưới sách tiêu biểu trên màn hình lớn; ảnh (nếu có) không vượt quá chiều
  rộng nội dung, luôn có mô tả thay thế bằng chữ.

## 4. Chi tiết từng mục

### 4.1. Giới thiệu CLB

- Tiêu đề: `[CẦN BỔ SUNG] — Tên CLB chính thức`.
- Một đoạn văn ngắn (3–5 câu): CLB là ai, sinh hoạt vì điều gì, ai có thể tham
  gia. Hiện để placeholder: `[CẦN BỔ SUNG] — Giới thiệu CLB (mục đích, đối
  tượng tham gia, hình thức sinh hoạt chung)`.
- 3 điểm nhấn ngắn dạng gạch đầu dòng: đọc cùng nhau, chia sẻ, cộng đồng mở
  (không cần số liệu thành viên khi chưa có dữ liệu thật).

### 4.2. Lịch sinh hoạt tháng

- Quy tắc cố định, hiển thị nổi bật ở đầu mục: **sinh hoạt tối thứ 5 hằng tuần**.
- Bảng lịch tháng hiện tại, mỗi buổi một hàng: ngày (thứ 5) | sách đang đọc |
  người dẫn buổi sinh hoạt.
- Dữ liệu thật chưa có — toàn bộ hàng trong bảng là placeholder:
  `[CẦN BỔ SUNG] — Sách đang đọc`, `[CẦN BỔ SUNG] — Người dẫn buổi sinh hoạt`.
  Không điền tên sách hay tên người thật nào khi chưa được xác nhận.
- Ghi chú dưới bảng: lịch có thể đổi theo thông báo của ban chủ nhiệm; xem mục
  liên hệ khi cần xác nhận buổi gần nhất.

### 4.3. Sách tiêu biểu kèm tóm tắt ngắn

- Lưới thẻ sách: mỗi thẻ gồm bìa sách (placeholder hình chữ nhật tông giấy cũ,
  ghi tên sách khi có), tên sách, tác giả, và tóm tắt ngắn 2–3 câu.
- Số thẻ hiển thị: 3–6 cuốn, tùy dữ liệu thật có được.
- Hiện tại toàn bộ là placeholder: `[CẦN BỔ SUNG] — Danh sách sách thật + tóm
  tắt ngắn từng cuốn`. Không tự chọn sách hay tự viết tóm tắt thay dữ liệu thật.
- Thẻ nào chưa có sách thật thì không hiển thị ra trang thật — chỉ giữ khung mẫu
  trong tài liệu này để Dev dựng theo.

### 4.4. Đăng ký thành viên mới

- Form đăng ký **chỉ thu thập hiển thị, chưa nối backend**: các trường họ tên,
  số điện thoại hoặc email, và một ô "Bạn muốn đọc thể loại nào?" (không bắt
  buộc). Nút "Gửi đăng ký".
- Hành vi khi bấm Gửi (tạm thời, vì chưa có backend): hiện thông báo trên trang
  "Đã ghi nhận thông tin. Ban chủ nhiệm sẽ liên hệ lại." — dữ liệu KHÔNG được
  gửi đi đâu, KHÔNG lưu ở đâu cho đến khi có backend thật. Ghi rõ trạng thái này
  ngay dưới form để người dùng không hiểu lầm là đã đăng ký thành công thật.
- Không thu thập thông tin nhạy cảm (địa chỉ nhà, số giấy tờ, tài khoản).

### 4.5. Quy tắc sinh hoạt

- Danh sách ngắn, dễ nhớ (6–8 quy tắc, mỗi quy tắc một dòng), ví dụ khung:
  đúng giờ (tối thứ 5), tôn trọng người đang phát biểu, giữ sách chung cẩn thận,
  đăng ký trước khi dẫn buổi sinh hoạt.
- Nội dung quy tắc cụ thể do ban chủ nhiệm xác nhận — nếu ban chủ nhiệm chưa
  chốt, giữ khung trên và ghi `[CẦN BỔ SUNG] — Quy tắc sinh hoạt chính thức
  do ban chủ nhiệm xác nhận`.
- Trình bày dạng danh sách đánh số, chữ lớn, không dùng thuật ngữ khó hiểu.

### 4.6. Địa điểm và liên hệ ban chủ nhiệm

- Địa điểm sinh hoạt: `[CẦN BỔ SUNG] — Địa điểm sinh hoạt cụ thể (tên địa điểm,
  địa chỉ, hướng dẫn đến nơi)`.
- Liên hệ ban chủ nhiệm: `[CẦN BỔ SUNG] — Liên hệ ban chủ nhiệm (người liên hệ,
  số điện thoại/email, giờ liên hệ)`.
- Thêm dòng thời gian cố định: sinh hoạt tối thứ 5 hằng tuần (đã có trong mục
  lịch sinh hoạt).
- Không hiển thị số điện thoại hay email cá nhân nào chưa được xác nhận.

## 5. Trạng thái trống và lỗi (để Dev dựng đúng)

- Chưa có dữ liệu thật: hiển thị đúng dòng `[CẦN BỔ SUNG]` như tài liệu này, kèm
  câu "Nội dung đang được ban chủ nhiệm cập nhật." — không để trang trống trơn,
  không tự điền nội dung giả.
- Form chưa nối backend: hiện rõ trạng thái "chưa nối backend" dưới form (mục 4.4).
- Lỗi tải trang: thông báo ngắn bằng chữ, không dùng mã lỗi kỹ thuật.

## 6. Bàn giao cho Dev

- Dev dựng trang theo đúng thứ tự 6 mục ở mục 4, bảng màu và cỡ chữ ở mục 2,
  bố cục một cột thoáng ở mục 3.
- Mọi placeholder `[CẦN BỔ SUNG]` giữ nguyên cho đến khi PO/ban chủ nhiệm cung cấp
  dữ liệu thật — Dev không tự thay bằng nội dung tự nghĩ.
- Kiểm chứng sau khi dựng: đọc thử toàn trang trên điện thoại (chữ không phải
  phóng to mới đọc được), kiểm tra đủ 6 mục, kiểm tra form chỉ hiển thị thông
  báo mà không gửi dữ liệu đi đâu.
