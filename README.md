# Hán Nôm · Mỗi ngày một chữ

Website GitHub Pages: https://ducthanhbui99.github.io/chinese/

- 32.854 tự dạng tra cứu, 517 mục quiz nghĩa (52 biên soạn + 465 mẹo nhớ Kai Hanzi), 4.511 chữ luyện âm Nôm theo danh mục và Unihan.
- Kho dữ liệu chia thành các file JSON tải khi mở kho tra cứu hoặc luyện âm; quiz nghĩa hoạt động độc lập.
- Tìm theo chữ, âm, nghĩa, bộ thủ và Unicode source. Kết quả giới hạn theo trang. Hán/Nôm có thể dùng chung tự dạng.
- Nguồn, schema, giới hạn và giấy phép: [data/SOURCES.md](data/SOURCES.md).

## Chạy local
Dùng máy chủ tĩnh: python -m http.server 8000 rồi mở http://localhost:8000/. GitHub Pages: main / root, .nojekyll. Dữ liệu và mã nguồn cập nhật trực tiếp qua GitHub. Tiến độ lưu localStorage, riêng giữa quiz nghĩa và luyện âm.

## Ôn chữ sai
Trả lời sai tự động thêm mục vào danh sách ôn tập trên thiết bị. Chọn **Ôn chữ sai** để luyện các mục sai thuộc nhóm đang chọn; trả lời đúng sẽ bỏ mục đó khỏi danh sách. Quiz nghĩa và luyện âm Nôm có danh sách riêng. Các câu trả lời trong chế độ ôn vẫn được tính vào thống kê hiện có. Lịch sử trước khi có tính năng không thể khôi phục theo từng chữ. Không cần đăng nhập; dữ liệu không đồng bộ giữa thiết bị.
