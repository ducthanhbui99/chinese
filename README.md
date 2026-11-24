# Hán Nôm · Mỗi ngày một chữ

Website tĩnh, không backend, không tài khoản, chạy bằng HTML/CSS/JavaScript. 52 mục khởi đầu (44 chữ Hán phồn thể và 8 chữ Nôm), được biên soạn riêng cho học tập. Không phải bản sao toàn bộ từ điển; phần giải thích là bản diễn giải ngắn và cần đối chiếu với nguồn khi nghiên cứu chuyên sâu. Một số tự dạng Nôm cần thiết bị có font CJK Extension B (ví dụ HanaMinB).

## Mở trên máy
Mở `index.html` trong trình duyệt, giữ `app.js` và `vocabulary.js` trong cùng thư mục.

## Đưa lên GitHub Pages
1. Tạo repository public `chinese` trên tài khoản `ducthanhbui99`, khởi tạo README.
2. Upload `index.html`, `app.js`, `vocabulary.js` và README (ở gốc repository).
3. Settings → Pages → Build and deployment → Deploy from a branch → `main` → `/ (root)` → Save.
4. Khi GitHub báo triển khai thành công, truy cập https://ducthanhbui99.github.io/chinese/.

## Kho từ vựng
`vocabulary.js` chứa mảng `window.VOCABULARY`, mỗi mục gồm:
- `id`: ID duy nhất, ví dụ `han-休`.
- `script`: `Hán` hoặc `Nôm`.
- `char`, `reading`, `meaning`: chữ, âm đọc Hán Việt/Nôm, nghĩa đáp án.
- `construction`, `components`, `explanation`, `example`: phép cấu tạo, các thành phần, diễn giải, ví dụ.
- `sources`: danh sách liên kết tham khảo (`label`, `url`).

Thêm mục vào mảng, giữ cú pháp JSON/JavaScript, dùng ID duy nhất và nghĩa đáp án ngắn, rõ. Mỗi nhóm phải có ít nhất bốn nghĩa khác nhau. Các câu hỏi được xáo ngẫu nhiên không lặp trong một vòng; đáp án sai lấy từ cùng nhóm đã chọn. Các cách giải thích chưa thống nhất được chú thích. Không nhập hàng loạt nội dung từ website khác nếu chưa xác định quyền sử dụng.

## Nguồn tra cứu
- CUHK – https://humanum.arts.cuhk.edu.hk/Lexis/lexi-mf/ : văn tự học và hình thể cổ.
- Thi Viện – https://hvdic.thivien.net/ : âm Hán Việt, nghĩa.
- Hội Bảo tồn Di sản chữ Nôm – https://www.nomfoundation.org/ : tự điển và văn bản Nôm.
- Viện Nghiên cứu Hán Nôm – https://hannom.vass.gov.vn/ : nghiên cứu cấu tạo và cách dùng chữ Nôm.

Tiến độ quiz được lưu bằng localStorage trong trình duyệt, không đồng bộ giữa các thiết bị.
