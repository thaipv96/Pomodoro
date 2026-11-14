# 🍅 Pomodoro Timer

> Ứng dụng Pomodoro tối giản, không cần cài đặt, không cần tài khoản, không cần internet.

[![Single File](https://img.shields.io/badge/single--file-HTML-22c55e?style=flat-square)](pomodoro.html)
[![No Dependencies](https://img.shields.io/badge/dependencies-none-22c55e?style=flat-square)](#)
[![Offline Ready](https://img.shields.io/badge/offline-ready-22c55e?style=flat-square)](#)
[![License](https://img.shields.io/badge/license-MIT-blue?style=flat-square)](#-giấy-phép)

---

## 📖 Tổng quan

**Pomodoro Timer** là một ứng dụng quản lý thời gian theo phương pháp Pomodoro, được đóng gói gọn gàng, không cần máy chủ, không cần build, không phụ thuộc vào bất kỳ thư viện bên ngoài nào.

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
