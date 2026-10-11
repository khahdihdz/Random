# Random — Vòng quay may mắn

Website tiếng Việt quay số, bốc thăm tên và chọn phần tử ngẫu nhiên, với vòng quay hoạt ảnh được đồng bộ với kết quả thực tế.

## Tính năng

- Vòng quay nhiều màu, hiệu ứng tăng tốc và giảm tốc.
- **Kim chỉ dừng đúng vào phần tử thắng đầu tiên** được hiển thị ở kết quả.
- Quay số trong khoảng số nguyên, bốc thăm tên hoặc danh sách tùy chỉnh.
- Chọn nhiều kết quả, cho phép hoặc không cho phép trùng.
- Loại tên trùng và chọn theo trọng số.
- Dùng `crypto.getRandomValues()` cùng rejection sampling cho các lựa chọn ngẫu nhiên; `Math.random()` chỉ dùng để tạo hiệu ứng/vị trí hiển thị của vòng quay.
- Lịch sử cục bộ, giao diện sáng/tối, sao chép kết quả, xuất CSV và in.
- Responsive trên điện thoại, máy tính bảng và desktop.
- Không cần backend, API key hay dependency build.

## Sử dụng

1. Chọn **Quay số**, **Quay tên** hoặc **Danh sách**.
2. Nhập khoảng số hoặc dán danh sách, mỗi phần tử một dòng.
3. Chọn số lượng kết quả và các tùy chọn.
4. Nhấn **Bắt đầu quay**. Vòng quay dừng với phần tử thắng đầu tiên nằm ngay dưới kim.
5. Sao chép, xuất CSV hoặc in kết quả.

Khi chọn nhiều kết quả, kim được đồng bộ với **kết quả đầu tiên**; các kết quả còn lại hiển thị trong cùng khung kết quả. Nếu danh sách có hơn 12 phần tử, vòng quay hiển thị một tập đại diện và thay một lát bằng phần tử thắng đầu tiên để kim vẫn chỉ đúng kết quả.

### Trọng số

Bật **Quay theo trọng số** và nhập một trọng số cho mỗi dòng, theo thứ tự danh sách. Trọng số phải hữu hạn, không âm và ít nhất một trọng số phải lớn hơn 0. Nếu bật không trùng, phần tử đã chọn sẽ bị loại khỏi các lượt chọn tiếp theo.

## Chạy tại máy

Mở `index.html` trực tiếp hoặc chạy máy chủ HTTP:

```bash
python -m http.server 8000
```

Truy cập `http://localhost:8000`.

## Triển khai GitHub Pages

Workflow `.github/workflows/deploy.yml` tự chạy khi có commit lên nhánh `main`, hoặc có thể chạy thủ công trong tab **Actions**. Workflow xác thực HTML/JavaScript, sau đó triển khai lên GitHub Pages.

URL dự kiến: https://khahdihdz.github.io/Random/

Nếu trang chưa hiển thị, mở **Settings → Pages** và kiểm tra nguồn triển khai là **GitHub Actions**, sau đó xem kết quả workflow trong **Actions**.

## Quyền riêng tư và giới hạn

- Lịch sử được lưu trong `localStorage` trên trình duyệt hiện tại, không tự đồng bộ giữa các thiết bị.
- Kết quả ngẫu nhiên được tính trước khi hoạt ảnh chạy; vòng quay trình bày trực quan kết quả đó và không tự quyết định kết quả.
- Đây không phải hệ thống quay thưởng có kiểm toán độc lập; không nên dùng làm bằng chứng chống gian lận cho chương trình có giá trị pháp lý hoặc tài chính cao.

## Công nghệ

HTML, CSS và JavaScript thuần; GitHub Actions; GitHub Pages.

## Mã nguồn

https://github.com/khahdihdz/Random
