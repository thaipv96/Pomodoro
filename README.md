# Pomodoro

Ứng dụng Pomodoro độc lập giúp bạn tập trung vào một công việc tại một thời điểm, nghỉ ngơi đúng nhịp và theo dõi thời gian tập trung.

Giao diện được thiết kế theo hướng tối giản, lấy cảm hứng từ ngôn ngữ thiết kế Material của Google: rõ ràng, gọn gàng, dễ sử dụng và hạn chế các yếu tố gây xao nhãng.

> Đây là dự án độc lập, không phải sản phẩm chính thức hoặc được Google tài trợ.

## Tổng quan

- **Một tệp HTML duy nhất:** toàn bộ giao diện, CSS và JavaScript nằm trong `pomodoro.html`.
- **Không cần cài đặt:** mở tệp bằng trình duyệt hiện đại để sử dụng.
- **Hoạt động ngoại tuyến:** không sử dụng CDN, thư viện, font, hình ảnh hay API bên ngoài.
- **Lưu dữ liệu cục bộ:** công việc, lịch sử phiên, cài đặt và tùy chọn giao diện được lưu trong trình duyệt.
- **Song ngữ:** hỗ trợ Tiếng Việt và English.
- **Hai giao diện:** Sáng và Tối; mặc định là Tiếng Việt và giao diện Sáng.
- **Responsive:** bố cục thích ứng với máy tính, máy tính bảng và điện thoại.

## Tính năng

### 1. Bộ đếm Pomodoro

- Ba chế độ: **Tập trung (Focus)**, **Nghỉ ngắn (Short Break)** và **Nghỉ dài (Long Break)**.
- Thời lượng mặc định:

  | Chế độ | Thời lượng |
  |---|---:|
  | Tập trung | 25 phút |
  | Nghỉ ngắn | 5 phút |
  | Nghỉ dài | 15 phút |
  | Nghỉ dài sau | 4 phiên tập trung hoàn thành |

- Vòng tròn tiến trình và đồng hồ đếm ngược.
- Bắt đầu, tạm dừng, tiếp tục, đặt lại và bỏ qua phiên.
- Có thể chọn chế độ thủ công.
- Bộ đếm sử dụng mốc thời gian kết thúc (`Date.now()`), thay vì chỉ giảm một biến đếm theo từng giây, giúp đồng bộ thời gian khi tab bị đưa xuống nền hoặc trình duyệt tạm ngưng thực thi.
- Trạng thái phiên đang chạy được lưu để ứng dụng có thể đối soát khi mở lại.

### 2. Chu kỳ Pomodoro

Chu kỳ mặc định:

```text
Focus 1 → Short Break
Focus 2 → Short Break
Focus 3 → Short Break
Focus 4 → Long Break
                    ↓
                Chu kỳ mới
```

Chỉ phiên Focus hoàn thành mới được ghi nhận vào thống kê. Phiên nghỉ không làm tăng số phiên tập trung. Bỏ qua phiên không được tính là một phiên Focus hoàn thành.

Có thể điều chỉnh số phiên Focus trước khi nghỉ dài trong phần Cài đặt.

### 3. Quản lý công việc

- Thêm, sửa và xóa công việc.
- Đánh dấu hoàn thành hoặc mở lại công việc.
- Chọn công việc đang thực hiện ngay trên màn hình Timer.
- Đặt mục tiêu số phiên Pomodoro cho từng công việc.
- Theo dõi số phiên Focus đã hoàn thành theo từng công việc.
- Lịch sử phiên đã ghi nhận vẫn được giữ khi xóa công việc; tên công việc tại thời điểm hoàn thành được lưu trong bản ghi lịch sử.

### 4. Thống kê năng suất

Dữ liệu thống kê được tính từ các phiên Focus hoàn thành đã lưu, bao gồm:

- Số phiên tập trung hôm nay.
- Tổng thời gian tập trung hôm nay.
- Tổng số phiên và tổng thời gian tập trung.
- Biểu đồ thời gian tập trung trong 7 ngày gần nhất.
- Thời gian tập trung trung bình mỗi phiên.
- Số công việc đã hoàn thành.
- Ngày có thời gian tập trung cao nhất.
- Chuỗi ngày có ghi nhận phiên tập trung.
- Lịch sử các phiên Focus.

Khi chưa có dữ liệu, ứng dụng hiển thị trạng thái trống thay vì tạo số liệu mẫu.

### 5. Âm thanh và thông báo

- Bật hoặc tắt âm thanh.
- Điều chỉnh âm lượng.
- Chọn một trong bốn kiểu âm báo: Digital Beep, Soft Bell, Classic Alarm và Gentle Chime.
- Nghe thử âm báo.
- Bật âm báo khi bắt đầu phiên (tùy chọn).
- Thông báo trong ứng dụng khi phiên kết thúc.
- Thông báo hệ thống qua Notification API nếu trình duyệt hỗ trợ và người dùng đã cấp quyền.
- Âm thanh được tạo bằng Web Audio API, không cần tệp âm thanh bên ngoài.

### 6. Cài đặt và tiện ích

- Điều chỉnh thời lượng Focus, nghỉ ngắn, nghỉ dài và số phiên trước nghỉ dài.
- Tùy chỉnh tự chuyển chế độ sau khi hoàn thành phiên.
- Tùy chỉnh tự bắt đầu phiên nghỉ và tự bắt đầu phiên Focus.
- Chuyển đổi giao diện Sáng/Tối.
- Chuyển đổi Tiếng Việt/English.
- Chế độ toàn màn hình.
- Tùy chọn giữ màn hình luôn bật bằng Screen Wake Lock API nếu trình duyệt hỗ trợ.
- Xuất dữ liệu ra JSON và nhập bản sao lưu JSON.
- Xóa dữ liệu ứng dụng với bước xác nhận.

## Cách sử dụng

### 1. Mở ứng dụng

1. Tải tệp `pomodoro.html` về thiết bị.
2. Mở tệp bằng trình duyệt hiện đại.
3. Ứng dụng mặc định mở ở màn hình Timer, giao diện Sáng và ngôn ngữ Tiếng Việt.

Không cần cài đặt phần mềm, máy chủ hay kết nối Internet.

### 2. Bắt đầu một phiên tập trung

1. Chọn chế độ **Tập trung**.
2. Nhấn nút bắt đầu ở giữa hai nút đặt lại và bỏ qua.
3. Nhấn nút chính một lần nữa để tạm dừng; nhấn tiếp để tiếp tục.
4. Dùng nút đặt lại để đưa phiên hiện tại về thời lượng đầy đủ.
5. Dùng nút bỏ qua để chuyển sang chế độ kế tiếp mà không ghi nhận phiên Focus hiện tại là hoàn thành.

Khi phiên kết thúc, ứng dụng ghi nhận kết quả, phát âm báo và hiển thị thông báo trong ứng dụng nếu tùy chọn này đang bật.

### 3. Gắn phiên tập trung với công việc

1. Nhấn dòng công việc bên dưới bộ đếm.
2. Chọn một công việc có sẵn, hoặc tạo công việc mới.
3. Bắt đầu phiên Focus. Khi phiên hoàn thành, kết quả sẽ được ghi nhận cho công việc đang chọn.

Bạn có thể quản lý danh sách, mục tiêu và trạng thái công việc trong mục **Công việc**.

### 4. Xem thống kê

Mở mục **Thống kê** để xem dữ liệu trong ngày, tổng thời gian tập trung, biểu đồ 7 ngày và lịch sử phiên Focus.

### 5. Tùy chỉnh ứng dụng

Trong mục **Cài đặt**, bạn có thể:

- Đổi thời lượng các chế độ và số phiên trước nghỉ dài.
- Bật/tắt tự chuyển chế độ, tự bắt đầu nghỉ hoặc tự bắt đầu Focus.
- Chọn âm báo và điều chỉnh âm lượng.
- Bật thông báo trong ứng dụng hoặc cấp quyền thông báo trình duyệt.
- Bật giữ màn hình luôn sáng nếu thiết bị hỗ trợ.
- Xuất hoặc nhập dữ liệu JSON.

Thay đổi thời lượng được áp dụng cho phiên mới; phiên đang chạy không bị thay đổi âm thầm.

### 6. Đổi ngôn ngữ và giao diện

Sử dụng hai nút ở góc trên bên phải:

- **EN / VI:** chuyển giữa Tiếng Việt và English.
- **Biểu tượng mặt trăng / mặt trời:** chuyển giữa giao diện Sáng và Tối.

Ứng dụng lưu lựa chọn để sử dụng lại ở lần mở tiếp theo.

## Phím tắt

| Phím | Chức năng |
|---|---|
| `Space` | Bắt đầu / Tạm dừng / Tiếp tục |
| `R` | Đặt lại phiên hiện tại |
| `N` | Bỏ qua phiên hiện tại |
| `F` | Bật / Tắt toàn màn hình |
| `S` | Mở mục Cài đặt |
| `Esc` | Đóng hộp thoại hoặc thông báo hoàn thành |

Phím tắt không được kích hoạt khi con trỏ đang nhập liệu trong ô input, textarea hoặc phần tử có thể chỉnh sửa.

Có thể mở bảng phím tắt bằng nút biểu tượng bàn phím trên thanh công cụ.

## Dữ liệu và quyền riêng tư

- Dữ liệu được lưu cục bộ trong LocalStorage của trình duyệt.
- Ứng dụng không có tài khoản, máy chủ hay cơ chế đồng bộ dữ liệu lên dịch vụ bên ngoài.
- Dữ liệu không tự động đồng bộ giữa các trình duyệt hoặc thiết bị.
- Dùng **Xuất JSON** để tạo bản sao lưu và **Nhập JSON** để khôi phục trên cùng hoặc thiết bị khác.
- Xóa dữ liệu trang web, hồ sơ trình duyệt hoặc dữ liệu trình duyệt có thể làm mất dữ liệu chưa sao lưu.

## Lưu ý về trình duyệt

Một số tiện ích phụ thuộc API và quyền của trình duyệt:

- Notification API cần trình duyệt hỗ trợ và người dùng cấp quyền.
- Screen Wake Lock chỉ hoạt động trên các trình duyệt/thiết bị tương thích.
- Fullscreen API có thể bị giới hạn tùy trình duyệt và cách mở trang.
- Web Audio có thể chỉ phát sau thao tác tương tác đầu tiên của người dùng.
- Bộ đếm có thể khôi phục và đối soát thời gian khi người dùng quay lại ứng dụng, nhưng một trang HTML độc lập không thể bảo đảm JavaScript hoặc âm thanh tiếp tục chạy sau khi trình duyệt hay tab bị đóng hoàn toàn.
- Hành vi lưu trữ LocalStorage khi mở trực tiếp bằng `file://` có thể khác nhau giữa các trình duyệt. Nếu dữ liệu không được giữ ổn định, hãy chạy ứng dụng qua GitHub Pages hoặc một máy chủ tĩnh và xuất bản sao lưu định kỳ.

## Đưa dự án lên GitHub

Đặt hai tệp sau trong thư mục gốc của repository:

```text
your-repository/
├── README.md
└── pomodoro.html
```

Sau đó commit và push lên GitHub. Người dùng có thể tải `pomodoro.html` trực tiếp từ repository.

Nếu muốn mở ứng dụng bằng một địa chỉ web, có thể bật GitHub Pages cho repository và truy cập đường dẫn đến `pomodoro.html` trên trang GitHub Pages tương ứng.

## Công nghệ

- HTML5
- CSS3
- Vanilla JavaScript (ES6+)
- Inline SVG
- Web Audio API
- Notification API
- Fullscreen API
- Screen Wake Lock API
- LocalStorage

Không sử dụng framework, thư viện JavaScript, CSS framework, CDN, font hoặc tài nguyên bên ngoài.

---

**Pomodoro** — Tập trung vào một việc, hoàn thành từng phiên, tiến bộ từng ngày.
