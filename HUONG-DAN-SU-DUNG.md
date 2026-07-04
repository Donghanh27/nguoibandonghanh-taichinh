# Hướng dẫn sử dụng Landing Page — Master Coach Lê Huyền Dung

File chính: **`le-huyen-dung.html`** (đã nhúng sẵn 6 ảnh, chỉ cần 1 file này).

---

## 1. Cấu hình nhanh (mở file bằng Notepad / VS Code)

Tìm ở gần đầu file khối `window.LP_CONFIG = {` và điền các giá trị:

```js
window.LP_CONFIG = {
  phone: '0377266588',
  zalo:  '0377266588',
  email: 'huyendungmastercoach@gmail.com',
  leadEndpoint: '',   // Nơi nhận thông tin khách (xem mục 2)
  metaPixelId: '',    // Meta Pixel ID (xem mục 3)
  gaId: ''            // Google Analytics 4 ID (xem mục 3)
};
```

> Nếu để trống tất cả, trang vẫn chạy: nút "Đặt lịch" sẽ **mở email soạn sẵn**
> gửi về địa chỉ `email` ở trên, còn nút Zalo/Gọi vẫn hoạt động bình thường.

---

## 2. Cho form nhận khách tự động (khuyên dùng — Formspree, miễn phí, 2 phút)

1. Vào https://formspree.io → đăng ký free → **New form**.
2. Nhập email nhận lead (huyendungmastercoach@gmail.com) → Formspree cho 1 link
   dạng: `https://formspree.io/f/abcdwxyz`.
3. Dán link đó vào `leadEndpoint`. Xong. Từ giờ mỗi khách bấm "Đặt lịch",
   thông tin sẽ tự gửi về email của bạn (họ tên, SĐT/Zalo, nhu cầu, tình trạng).

*(Nâng cao: có thể thay bằng Google Apps Script Web App hoặc CRM — dán URL vào `leadEndpoint`.)*

---

## 3. Gắn quảng cáo (đo chuyển đổi)

- **Meta Pixel:** vào Trình quản lý sự kiện Facebook → lấy Pixel ID (dãy số) → dán vào `metaPixelId`.
- **Google Analytics 4:** tạo property GA4 → lấy mã `G-XXXXXXXXXX` → dán vào `gaId`.

Trang đã tự bắn sẵn 2 sự kiện quan trọng:
- `Lead`  — khi khách bấm gửi form đặt lịch.
- `Contact` — khi khách bấm nút Zalo hoặc gọi điện.

Dùng 2 sự kiện này để tối ưu quảng cáo Facebook (mục tiêu Khách hàng tiềm năng).

---

## 4. Đưa lên mạng để có link chạy quảng cáo

**Cách A — Netlify Drop (nhanh nhất, không cần tài khoản kỹ thuật):**
1. Vào https://app.netlify.com/drop
2. Kéo–thả file `le-huyen-dung.html` vào (nên đổi tên thành `index.html` trước để link gọn).
3. Nhận link dạng `https://ten-ngau-nhien.netlify.app` → dùng ngay để chạy ads.

**Cách B — GitHub Pages (miễn phí, ổn định):**
1. Vào repo trên GitHub → **Settings → Pages**.
2. Source: chọn branch (ví dụ `main` hoặc branch đang dùng) → Save.
3. Sau vài phút, trang truy cập tại:
   `https://<tên-tài-khoản>.github.io/nguoibandonghanh-taichinh/le-huyen-dung.html`

---

## 5. Checklist trước khi chạy quảng cáo

- [ ] Đã điền `leadEndpoint` (form nhận khách hoạt động)
- [ ] Đã gắn `metaPixelId` và `gaId`
- [ ] Kiểm tra trên **điện thoại** trước (phần lớn khách xem bằng mobile)
- [ ] Bấm thử nút "Đặt lịch", Zalo, Gọi ngay — đều đúng
- [ ] Đã có link online (Netlify/GitHub Pages)
- [ ] A/B test tiêu đề Hero và nút CTA trong 14 ngày đầu
