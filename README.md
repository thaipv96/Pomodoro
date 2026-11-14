# 🍅 Pomodoro Timer

> Ứng dụng Pomodoro tối giản, hoạt động offline, chạy trực tiếp trên trình duyệt — không cần cài đặt, không cần tài khoản, không cần internet.

[![Single File](https://img.shields.io/badge/single--file-HTML-22c55e?style=flat-square)](pomodoro.html)
[![No Dependencies](https://img.shields.io/badge/dependencies-none-22c55e?style=flat-square)](#)
[![Offline Ready](https://img.shields.io/badge/offline-ready-22c55e?style=flat-square)](#)
[![License](https://img.shields.io/badge/license-MIT-blue?style=flat-square)](#-giấy-phép)

---

## 📖 Tổng quan

**Pomodoro Timer** là một ứng dụng quản lý thời gian theo phương pháp Pomodoro, được đóng gói gọn gàng trong **một file HTML duy nhất**. Chỉ cần mở file bằng trình duyệt hiện đại là có thể sử dụng ngay — không cần máy chủ, không cần build, không phụ thuộc vào bất kỳ thư viện bên ngoài nào.

Ứng dụng được thiết kế theo phong cách **tối giản – tinh tế – tập trung**, với hai giao diện sáng/tối, hai ngôn ngữ (Tiếng Việt / English), và toàn bộ dữ liệu được lưu trữ cục bộ trong trình duyệt của bạn.

### Điểm nổi bật

- 🪶 **Một file duy nhất** — `pomodoro.html`
- 🔌 **Hoàn toàn offline** — không gọi API, không tải tài nguyên từ CDN
- 🎨 **Hai giao diện** — Sáng / Tối (mặc định: Sáng)
- 🌐 **Hai ngôn ngữ** — Tiếng Việt / English (mặc định: Tiếng Việt)
- 📱 **Responsive** — hiển thị đẹp trên desktop, tablet và smartphone, không có cuộn ngang/dọc
- ⏱️ **Đồng hồ chính xác** — dùng timestamp tuyệt đối, không bị lệch khi chuyển tab hay khóa máy
- 💾 **Lưu dữ liệu tự động** — qua `localStorage`
- 🔊 **Âm thanh & thông báo** — tổng hợp âm thanh bằng Web Audio API, hỗ trợ Notification API
- ⌨️ **Phím tắt** đầy đủ cho người dùng thành thạo

---

## ✨ Chức năng

### ⏱️ Đồng hồ Pomodoro

- Ba chế độ: **Tập trung (Focus)**, **Nghỉ ngắn (Short Break)**, **Nghỉ dài (Long Break)**
- Chu kỳ mặc định: **25 → 5 → 25 → 5 → 25 → 5 → 25 → 15** (phút)
- Vòng tròn tiến trình trực quan, đổi màu theo chế độ:
  - Focus → cam
  - Short Break → xanh lá
  - Long Break → xanh dương
- Hiển thị **chấm chu kỳ** — biết đang ở phiên thứ mấy trước giờ nghỉ dài
- Đồng hồ **không bị lệch** kể cả khi chuyển tab, khóa màn hình, hay đóng trình duyệt (dùng timestamp tuyệt đối)

### ✅ Quản lý công việc

- Tạo, sửa, xóa công việc
- Đánh dấu hoàn thành / mở lại
- Đặt **mục tiêu số phiên** cho mỗi công việc (ví dụ: 4 phiên)
- Theo dõi tiến độ bằng thanh tiến trình
- **Chọn công việc đang làm** — phiên focus hoàn thành sẽ tự cộng vào công việc đó
- Công việc đã xóa vẫn giữ lịch sử phiên trong thống kê

### 📊 Thống kê

- **Hôm nay**: số phiên, tổng thời gian tập trung, số việc hoàn thành, thời lượng trung bình, số chu kỳ
- **7 ngày qua**: biểu đồ cột trực quan + tổng tuần + trung bình ngày
- **Toàn thời gian**: tổng số phiên, tổng thời gian, ngày năng suất nhất, ngày tập trung dài nhất, chuỗi ngày liên tiếp (streak)

### ⚙️ Cài đặt

- **Timer**: thời lượng Focus / Nghỉ ngắn / Nghỉ dài, số phiên trước nghỉ dài, tự động bắt đầu
- **Âm thanh**: bật/tắt, 4 kiểu âm (Bíp / Chuông / Báo thức / Du dương), âm lượng, nghe thử
- **Thông báo**: thông báo trình duyệt, thông báo trong app, giữ màn hình sáng (Screen Wake Lock)
- **Dữ liệu**: xuất/nhập JSON, xóa toàn bộ dữ liệu

### 🌗 Giao diện & Ngôn ngữ

- Nút chuyển **Sáng / Tối** ở góc trên bên phải
- Nút chuyển **VI / EN** ngay cạnh nút giao diện
- Toàn bộ nội dung (bao gồm thông báo, modal, tooltip) đều được dịch

### 🔊 Thông báo & Âm thanh

- Âm thanh được **tổng hợp trực tiếp bằng Web Audio API** — không cần file MP3/WAV
- Thông báo hệ thống qua **Notification API** (yêu cầu cấp quyền)
- Thông báo trong ứng dụng (toast) luôn hoạt động như phương án dự phòng

### 💾 Dữ liệu

- Tự động lưu sau mỗi thay đổi quan trọng
- Phục hồi chính xác sau khi đóng/mở lại trình duyệt
- Nếu phiên đã hết trong lúc trang đóng → tự động ghi nhận đúng **một lần**, không nhân đôi
- Xuất bản sao lưu dạng JSON, nhập lại khi cần

---

## ⌨️ Phím tắt

| Phím | Chức năng |
|:---:|-----------|
| <kbd>Space</kbd> | Bắt đầu / Tạm dừng / Tiếp tục |
| <kbd>R</kbd> | Đặt lại đồng hồ |
| <kbd>N</kbd> | Bỏ qua phiên hiện tại |
| <kbd>F</kbd> | Bật / tắt toàn màn hình |
| <kbd>S</kbd> | Mở Cài đặt |
| <kbd>Esc</kbd> | Đóng hộp thoại / thoát toàn màn hình |

> ⚠️ Phím tắt **không hoạt động** khi bạn đang gõ trong ô nhập liệu, và không ghi đè phím tắt hệ thống của trình duyệt (Ctrl/Cmd/Alt).

---

## 🚀 Cách sử dụng

### Bước 1 — Tải file

Tải file `pomodoro.html` từ repository này về máy:

```bash
# Nếu dùng Git
git clone https://github.com/<your-username>/<your-repo>.git

# Hoặc chỉ cần tải trực tiếp file pomodoro.html
```

### Bước 2 — Mở bằng trình duyệt

- **Trên desktop**: nhấp đúp vào file `pomodoro.html`
- **Trên mobile**: mở file bằng trình duyệt (Chrome, Safari, Firefox, Edge…)

Không cần cài đặt gì thêm. Ứng dụng sẽ chạy ngay.

### Bước 3 — Sử dụng hằng ngày

1. **Thêm công việc** — vào tab **Việc**, nhấn **+ Thêm**
2. **Chọn công việc đang làm** — nhấn vào dòng công việc (hoặc dùng nút trên tab Đồng hồ)
3. **Bắt đầu phiên tập trung** — nhấn **Bắt đầu** (hoặc <kbd>Space</kbd>)
4. **Nghỉ khi hết giờ** — ứng dụng tự chuyển sang chế độ nghỉ phù hợp
5. **Xem tiến độ** — vào tab **Thống kê** để xem thành tích
6. **Tùy chỉnh** — vào tab **Cài đặt** để đổi thời lượng, âm thanh, ngôn ngữ…

### 💡 Mẹo sử dụng hiệu quả

- **Bật thông báo trình duyệt** trong Cài đặt để không bỏ lỡ khi hết giờ
- **Bật "Giữ màn hình sáng"** khi làm việc trên laptop để màn hình không tự tắt
- **Xuất JSON định kỳ** để sao lưu dữ liệu (dữ liệu chỉ lưu trong trình duyệt, có thể mất nếu xóa cache)
- **Dùng phím tắt** để thao tác nhanh hơn khi đang tập trung
- **Thêm vào màn hình chính** (Add to Home Screen) trên điện thoại để mở như một ứng dụng

### 🌐 Tương thích trình duyệt

| Trình duyệt | Hỗ trợ |
|---|---|
| Chrome / Edge (phiên bản mới) | ✅ Đầy đủ |
| Firefox | ✅ Đầy đủ |
| Safari (macOS / iOS) | ✅ Đầy đủ (một số giới hạn về Screen Wake Lock) |
| Trình duyệt cũ / IE | ❌ Không hỗ trợ |

> Một số tính năng như **Screen Wake Lock** hoặc **Notification** có thể không khả dụng trên tất cả thiết bị — ứng dụng sẽ tự động chuyển sang phương án dự phòng.

---

## 🔒 Quyền riêng tư & Dữ liệu

- **Không có máy chủ**, không thu thập dữ liệu, không theo dõi
- Toàn bộ dữ liệu (công việc, phiên, cài đặt) được lưu trong `localStorage` của trình duyệt
- Dữ liệu **chỉ tồn tại trên thiết bị của bạn** — xóa cache trình duyệt sẽ xóa dữ liệu
- Nên **xuất JSON định kỳ** để sao lưu

---

## 📁 Cấu trúc dự án

```
.
└── pomodoro.html    # Toàn bộ ứng dụng trong một file duy nhất
```

---

## 🛠 Công nghệ sử dụng

- **HTML5** — semantic markup
- **CSS3** — custom properties, flexbox, grid, responsive design
- **Vanilla JavaScript (ES6+)** — không framework, không thư viện
- **Web Audio API** — tổng hợp âm thanh
- **Notification API** — thông báo hệ thống
- **Screen Wake Lock API** — giữ màn hình sáng
- **Fullscreen API** — chế độ toàn màn hình
- **LocalStorage** — lưu dữ liệu cục bộ

---

## 🤝 Đóng góp

Nếu bạn muốn đóng góp:

1. Fork repository
2. Tạo nhánh mới: `git checkout -b feature/ten-tinh-nang`
3. Commit thay đổi: `git commit -m "Thêm tính năng X"`
4. Push: `git push origin feature/ten-tinh-nang`
5. Mở Pull Request

---

## 📄 Giấy phép

Dự án được phát hành theo giấy phép **MIT**. Bạn có thể tự do sử dụng, sửa đổi và phân phối.

---

## 🙏 Ghi công

- Phương pháp **Pomodoro** được phát triển bởi [Francesco Cirillo](https://en.wikipedia.org/wiki/Pomodoro_Technique)
- Biểu tượng sử dụng inline SVG, không phụ thuộc thư viện icon bên ngoài

---

<div align="center">

**Made with ❤️ for focused people**

⭐ Nếu bạn thấy hữu ích, hãy tặng repo một ngôi sao!

</div>
