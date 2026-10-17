# Kho cài LewdManhwa cho vBook (beta)

## Đưa lên GitHub

1. Tạo repository **public** với đúng tên `vbook-lewdmanhwa` và chọn branch `main`.
2. Giải nén ZIP hướng dẫn; upload **toàn bộ nội dung bên trong** (không upload file ZIP cha) vào gốc repository qua `Add file > Upload files`.
3. Mở `plugin.json` tại gốc repository; thay `hoang2401-arch` thành tên người dùng GitHub của bạn ở **cả hai chỗ** và commit. Nếu thay đổi tên repo / branch thì chỉnh URL tương ứng.
4. Xác minh mở được `https://raw.githubusercontent.com/hoang2401-arch/vbook-lewdmanhwa/main/plugin.json` và `https://raw.githubusercontent.com/hoang2401-arch/vbook-lewdmanhwa/main/lewdmanhwa/plugin.zip`.
5. Trong ứng dụng vBook, vào **Cài đặt > Kho tiện ích > Thêm kho** (các phiên bản khác có thể là Cá nhân > Phần mở rộng > dấu ba chấm > Quản lý extensions). Dán URL plugin.json của bước 4, làm mới, chọn LewdManhwa (Beta) và cài đặt.

**Chú ý**: URL `sandbox:/...` của ChatGPT không phải URL công khai để VBook tải. File trong repository là bản thử nghiệm chưa kiểm chứng hoạt động trong vBook. Nếu app có lựa chọn nhập file ZIP trực tiếp, có thể thử dùng `lewdmanhwa/plugin.zip` mà không cần tạo kho.
