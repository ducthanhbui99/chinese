# Nguồn dữ liệu · 24/11/2026

## Quy mô thực tế
{
  "total": 32854,
  "metadata": 25631,
  "han": 11942,
  "nom": 11690,
  "both": 1999,
  "unclassified": 7223,
  "withReading": 8300,
  "withDefinition": 20958,
  "nomRead": 4511,
  "kai": 768,
  "curated": 52,
  "extra": 465,
  "quiz": 517,
  "batches": 10
}

## Dữ liệu & giấy phép
- Kai Hanzi / binhbuithithanh: https://github.com/binhbuithithanh/hanzi-sino-vietnamese — CC BY 4.0 (https://creativecommons.org/licenses/by/4.0/). Bản chuyển đổi từ data/characters.json: loại bỏ mục trùng, chọn mặt chữ phồn thể, giữ nghĩa và âm Hán Việt; mẹo nhớ và các thành phần chỉ nhập cho tự dạng không đổi, không gán phép Lục thư. Giữ LICENSE và NOTICE trong data/licenses. Tác giả: Kai Hanzi. Mẹo nhớ không phải bằng chứng từ nguyên.
- Unicode Consortium, Unihan 12.1.0, qua dahlia/unihan-json: https://github.com/dahlia/unihan-json/tree/gh-pages/12.1.0 — các trường kVietnamese, kDefinition, kIRG_VSource, kTraditionalVariant. Unicode License; xem data/licenses/Unicode.txt và https://www.unicode.org/license.txt. Nghĩa gốc tiếng Anh không dịch tự động. kVietnamese không phân biệt đầy đủ âm Hán Việt/Nôm, kIRG_VSource không đồng nghĩa với chữ Nôm.
- Nôm Na Việt: https://github.com/nomnaviet/nomnaviet-contrib/blob/main/classifications/character-classifications.csv — chỉ dùng tự dạng, mã Unicode, nhãn danh mục han/nom/both, số nét và bộ thủ (metadata, không nhập các mã phân loại A1–G2 hoặc ghi chú từ Tự Điển Chữ Nôm Dẫn Giải; các trường Unicode theo Unicode License). Xem https://github.com/nomnaviet/nomnaviet-contrib/blob/main/NOTICE.md. Nhãn danh mục không khẳng định chữ chỉ được dùng duy nhất theo một hệ chữ.
- 52 mục biên soạn ban đầu trong vocabulary.js được giữ nguyên, có nguồn tham khảo từng mục.
- Các nguồn tra cứu bổ sung (không sao chép toàn văn): CUHK, Thi Viện, Hội Bảo tồn Di sản chữ Nôm, Viện Nghiên cứu Hán Nôm, Make Me a Hanzi, Nôm Na Việt. 

## Schema catalog
Mỗi hàng: [char, type, strokes, radical, vietnameseReadings, englishDefinition, traditionalVariants, vietnameseIRGSource, kaiMeaningVi, kaiSinoViet, kaiLevel, kaiOriginal].
Hợp nhất theo tự dạng Unicode, không phải số từ ghép hay số nghĩa. Tự dạng chưa phân loại và biến thể có thể nằm trong kho, nhưng không tự động vào quiz nghĩa. Phần học âm Nôm chỉ dùng chữ được danh mục đánh dấu nom và có kVietnamese; không gọi đó là nghĩa, không suy diễn phép tạo chữ. Một số chữ hiếm cần font hỗ trợ CJK mở rộng.

## Mở rộng 24/11/2026
- Make Me a Hanzi, Shaunak Kishore và các nguồn upstream Unihan/CJKlib: https://github.com/skishore/makemeahanzi/tree/bddc96d41bef78427ed0e034e9f7e31d71fd1b92. Dữ liệu dictionary.txt: https://github.com/skishore/makemeahanzi/blob/bddc96d41bef78427ed0e034e9f7e31d71fd1b92/dictionary.txt. LGPL-3.0-or-later; giữ COPYING và LGPL trong data/licenses; văn bản GPLv3 dẫn chiếu trong LGPL: https://www.gnu.org/licenses/gpl-3.0.txt. Chuyển đổi các trường character, decomposition, radical, pinyin, definition, etymology thành hàng JSON [char,IDS,radical,pinyin,definition,etymology]; lọc Unicode Unified_Ideograph, chia mỗi 1.800 hàng. Không dùng graphics.txt. Dữ liệu JSON chịu cùng giấy phép LGPL-3.0-or-later, bản nguồn gốc tại liên kết commit ở trên. 9.574 bản ghi upstream, 9.565 chữ thống nhất nhập, 9.506 IDS khác ？ (có thể chứa thành phần chưa xác định), 9.030 gợi ý từ nguyên. Thêm 61 chữ không trùng vào danh mục, nhãn Hán theo nguồn chữ Trung Quốc, không khẳng định không có cách dùng Nôm. Không sửa dữ liệu gốc hay tự động thêm quiz. Tổng kho 32.915 tự dạng khi tải thành công.
- Bộ thủ: thứ tự Khang Hy U+2F00–U+2FD5, chuyển sang tự dạng tương thích NFKC; tên Hán Việt và nghĩa ngắn biên soạn, biến thể chọn lọc; đối chiếu https://www.unicode.org/charts/nameslist/n_2F00.html và https://www.chuhannom.com/214bothu.php. Không suy ra nghĩa phù từ bộ tra cứu; 阝 không tự động quy về 阜 hoặc 邑. Số chữ theo bộ chỉ tính chữ có metadata phù hợp, không phải tổng số chữ chứa thành phần đó.
- Từ ghép: 175 mục biên soạn, nghĩa ngắn và yếu tố cấu thành để học; không phải bản trích xuất từ điển. Nguồn đối chiếu: https://hvdic.thivien.net/ và https://en.wiktionary.org/. Chưa kiểm chứng ngữ liệu đầy đủ, một số từ là cách đọc Hán Việt của từ tiếng Hán, không phải từ phổ dụng tiếng Việt. Không suy diễn nghĩa toàn từ chỉ bằng cách cộng nghĩa từng chữ.
