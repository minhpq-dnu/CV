# Portfolio cá nhân – Phạm Quang Minh

## 1. Tên dự án

**Portfolio cá nhân của Phạm Quang Minh** – trang giới thiệu bản thân, kỹ năng, các dự án và thông tin liên hệ.

## 2. Mô tả

Đây là website portfolio tĩnh giới thiệu Phạm Quang Minh, định hướng Frontend Developer và sở thích về xe độ, chụp ảnh, chỉnh sửa video/ảnh. Giao diện được thiết kế responsive theo hướng mobile-first, hiển thị trên điện thoại, máy tính bảng và máy tính.

Trang web chỉ gồm HTML và CSS thuần. Không cần cài thư viện, chạy backend hay biên dịch mã nguồn.

## 3. Chức năng

- Hiển thị phần giới thiệu, ảnh đại diện và các nút điều hướng.
- Trình bày các kỹ năng dưới dạng thẻ.
- Giới thiệu các dự án và liên kết mạng xã hội.
- Cung cấp thông tin liên hệ qua email, TikTok và Facebook.
- Điều hướng đến các phần trên trang và quay lại đầu trang.
- Tự điều chỉnh bố cục theo kích thước màn hình.

## 4. Công nghệ sử dụng

- **HTML5:** cấu trúc và nội dung trang.
- **CSS3:** giao diện, responsive, Flexbox và CSS Grid.
- **Không sử dụng JavaScript, framework hoặc thư viện bên ngoài.**
- **Không cần Node.js, npm hay cơ sở dữ liệu.**

## 5. Yêu cầu

- Trình duyệt hiện đại như Google Chrome, Microsoft Edge, Firefox hoặc Safari.
- Để mở trực tiếp: không cần cài thêm phần mềm.
- Để chạy máy chủ cục bộ: Python 3 (tùy chọn; có thể dùng máy chủ tĩnh khác).
- Để chạy bằng Docker: Docker Engine hoặc Docker Desktop đang hoạt động.
- Giữ nguyên cấu trúc thư mục và tên tệp ảnh để các đường dẫn trong trang hoạt động chính xác.

## 6. Cấu trúc dự án

```text
KT A2.1/
├── index.html
├── README.md
└── assets/
    ├── css/
    │   └── styles.css
    └── img/
        ├── dinoco.jpg
        ├── fb.png
        ├── minh.jpg
        ├── tik.jpg
        └── zin.jpg
```

## 7. Cài đặt

Không cần cài đặt thư viện hoặc chạy lệnh build. Tải/chép toàn bộ thư mục dự án về máy, sau đó:

1. Kiểm tra `index.html` và thư mục `assets/` nằm cùng cấp như cấu trúc trên.
2. Mở `index.html` bằng trình duyệt để xem nhanh; hoặc làm theo hướng dẫn chạy máy chủ bên dưới.

## 8. Cấu hình và tùy chỉnh

- **Nội dung trang:** chỉnh sửa các phần tử HTML trong `index.html`.
- **Màu sắc, kiểu chữ, khoảng cách và bố cục:** chỉnh sửa biến CSS ở đầu `assets/css/styles.css` và các quy tắc tương ứng.
- **Ảnh:** thay ảnh trong `assets/img/`; nếu đổi tên tệp, cập nhật đường dẫn `src` trong `index.html`.
- **Thông tin liên hệ và liên kết:** cập nhật địa chỉ email, URL TikTok/Facebook và các liên kết dự án trong `index.html`.
- Các thẻ dự án đang dùng `href="#"` là liên kết mẫu; hãy thay bằng URL thật khi có.

Không có tệp cấu hình môi trường, khóa bí mật hoặc dịch vụ backend cần thiết.

## 9. Chạy thử

### Mở trực tiếp

Mở tệp `index.html` bằng trình duyệt. Cách này phù hợp để xem trang cơ bản; một số tính năng trình duyệt có thể hoạt động ổn định hơn khi truy cập qua máy chủ HTTP cục bộ.

### Windows

Mở PowerShell tại thư mục dự án. Có thể mở PowerShell từ thanh địa chỉ của File Explorer bằng cách nhập `powershell`, hoặc chuyển đến thư mục dự án bằng `cd`. Sau đó chạy:

```powershell
py -m http.server 8000
```

Nếu lệnh `py` không có, thử:

```powershell
python -m http.server 8000
```

Mở <http://localhost:8000> trong trình duyệt. Dừng máy chủ bằng `Ctrl+C`.

### macOS

Mở Terminal, chuyển đến thư mục dự án bằng `cd` (có thể kéo thư mục dự án vào cửa sổ Terminal để điền đường dẫn), rồi chạy:

```bash
python3 -m http.server 8000
```

Mở <http://localhost:8000> trong trình duyệt. Dừng máy chủ bằng `Control+C`.

### Linux

Mở Terminal, chuyển đến thư mục dự án bằng `cd`, rồi chạy:

```bash
python3 -m http.server 8000
```

Mở <http://localhost:8000> trong trình duyệt. Dừng máy chủ bằng `Ctrl+C`.

Nếu cổng `8000` đang được sử dụng, thay `8000` trong lệnh bằng một cổng khác, ví dụ `8081`, rồi mở địa chỉ tương ứng.

## 10. Chạy bằng Docker

Docker phục vụ các tệp tĩnh bằng Nginx; không cần tạo image riêng hoặc cài dependency cho dự án.

### macOS và Linux

Chạy lệnh sau trong Terminal tại thư mục dự án:

```bash
docker run --rm --name portfolio-minh -p 8080:80 \
  --mount "type=bind,source=$(pwd),target=/usr/share/nginx/html,readonly" \
  nginx:alpine
```

### Windows PowerShell

Chạy lệnh sau trong PowerShell tại thư mục dự án:

```powershell
docker run --rm --name portfolio-minh -p 8080:80 `
  --mount "type=bind,source=$($PWD.Path),target=/usr/share/nginx/html,readonly" `
  nginx:alpine
```

Sau khi container khởi động, mở <http://localhost:8080>. Dừng container bằng `Ctrl+C`; tùy chọn `--rm` sẽ tự xóa container sau khi dừng.

## 11. Thông tin liên hệ

- **Email:** [Game1k1ne@gmail.com](mailto:Game1k1ne@gmail.com)
- **TikTok:** [@zindivis.08](https://www.tiktok.com/@zindivis.08)
- **Facebook:** [Quang Minh](https://www.facebook.com/yeuemtamthuii)

---

© 2026 Phạm Quang Minh