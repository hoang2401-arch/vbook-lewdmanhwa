# Góc Truyện Tranh Vui 30 — VBook extension v1 (Beta)

Source: https://goctruyentranhvui30.com/

## Đã đối chiếu thực tế
- Home: `/trang-chu`.
- Danh sách / tìm kiếm: `/danh-sach` (phần kết quả cần JavaScript).
- Truyện: `/truyen/<slug>`.
- Chương: `/truyen/<slug>/chuong-<number>`.
- Danh sách ở trang truyện có thể chỉ hiển thị 20 chương, trong khi menu trang đọc có các URL chương đầy đủ hơn (đã kiểm tra các trang mẫu).
- Trang đọc chương được client render; bộ kiểm tra HTML không thấy toàn bộ ảnh. **Chưa test được thực tế trong VBook**.

## Các script
- `src/home.js`, `homecontent.js`: tab khám phá và danh sách truyện.
- `src/genre.js`: 6 category có mã lọc đã đối chiếu qua liên kết nguồn.
- `src/search.js`: thử điều khiển thanh tìm kiếm bằng browser engine. Cần kiểm thử trong vBook.
- `src/detail.js`: chi tiết truyện, ảnh bìa.
- `src/toc.js`: lấy danh sách chương từ trang truyện và từ menu chương trên trang đọc (tránh mất 20+ chương).
- `src/chap.js`: mở trang bằng browser, giữ ảnh qua nhiều đợt cuộn/lazy-load. Nếu chưa xác nhận đã cuộn tới cuối chương, trả lỗi thay vì tự coi là hết chương.
- `src/common.js`: các hàm tiện ích; tránh dùng `parent()`/`selectFirst()` trên đối tượng jsoup của vBook.

## Cách cài vào GitHub hiện tại của bạn
Repo: https://github.com/hoang2401-arch/vbook-lewdmanhwa

**Đừng upload ZIP “goc-vbook-github-add-to-existing-v1.zip” nguyên khối.** Hãy giải nén, sau đó:
1. Thay file `plugin.json` ở thư mục gốc bằng file registry đi kèm; registry giữ lại entry LewdManhwa v12 và thêm Góc Truyện Tranh Vui 30 v1.
2. Tạo folder `goctruyentranhvui30` trong repo bằng cách `Add file > Create new file`, nhập `goctruyentranhvui30/.gitkeep`, Commit.
3. Trong folder đó, `Add file > Upload files`: upload `plugin.zip` và `icon.png` từ bản đã giải nén. Commit.
4. VBook: cập nhật kho bằng URL hiện có: `https://raw.githubusercontent.com/hoang2401-arch/vbook-lewdmanhwa/main/plugin.json`. Refresh → cài Goc Truyen Tranh Vui 30 (Beta).

**Quan trọng:** Registry lấy từ GitHub vào thời điểm tạo gói có LewdManhwa v12. Nếu sau này bạn nâng version LewdManhwa hoặc thêm plugin khác, không thay đè bằng registry cũ; chỉ thêm entry mới vào registry mới nhất.

## Kiểm thử đề xuất
1. Home → có truyện và ảnh bìa?
2. Search: `Mèo Mập Béo Bự`.
3. Detail và TOC: `Mèo Mập Béo Bự` → có >20 chương và Chương 1?
4. Chapter: chọn Chương 1 và đọc đến cuối; kiểm tra số ảnh đủ so với website gốc.

Log prefix: `GocTruyen v1:`. Nếu HTML/API của site đổi hoặc vBook không hỗ trợ browser action, gửi log cùng đường dẫn chương cụ thể. Đây là prototype, chưa có xác nhận hoạt động thực tế trên điện thoại.

Chỉ đọc từ nguồn và với nội dung bạn có quyền truy cập; tuân thủ điều khoản website và bản quyền.
