# AI LOG – BUỔI 7, TIẾT 3

> Điền vào `[ ... ]`, tích `[x]` vào lựa chọn phù hợp. Ghi đúng việc đã làm; chưa kiểm tra thì ghi “Chưa kiểm tra”. Không cần chép toàn bộ cuộc trò chuyện AI.

## Thông tin sinh viên

- Họ và tên: [ Phạm Bình Minh]
- Mã sinh viên – Lớp: [ CNTT 20-02 ]
- Ngày thực hiện: [ 30 ]
- Link repository: [ https://github.com/pm247208-lgtm/K20_Portfolio_CNTT-20-02.git ]
- URL website: [ https://pm247208-lgtm.github.io/K20_Portfolio_CNTT-20-02/ ]
- Tình huống: [x] Website của tôi  [ ] Repo luyện của giảng viên

## 1. Nhận định của tôi trước khi hỏi AI

- Trang/thao tác gặp lỗi: [ Trang Đăng nhập - bấm nút "Login" không phản hồi ]
- Mong muốn và hiện tượng thực tế: [ Mong muốn: Chuyển hướng sang trang Dashboard sau khi nhập đúng thông tin. Hiện tượng thực tế: Màn hình đứng yên, không báo lỗi trên giao diện]
- Dữ kiện đã kiểm tra (cấu trúc tệp, Request URL, Status…): [ F12 Console báo lỗi 500 Internal Server Error, Request URL: /api/login, Status: 500 ]
- Tôi nghi nguyên nhân là: [ Chưa kết nối được cơ sở dữ liệu hoặc sai thông tin truy vấn SQL trong hàm loginController ]
- Vì sao tôi nhận định như vậy: [ Vì backend trả về Status Code 500 và log terminal báo "Connection timeout to DB" ]

## 2. Tôi hỏi AI và nhận được gợi ý

- Nguồn: [x] Công cụ AI: [ gemini ]  [ ] Phản hồi mẫu của giảng viên
- Câu hỏi/prompt tôi đã gửi (hoặc tình huống của phản hồi mẫu):

  [ "Tôi bị lỗi 500 khi gọi API login trong Node.js/Express, đây là đoạn code router và controller của tôi: [dán code]. Hãy giúp tôi tìm nguyên nhân và cách sửa."]

- Gợi ý chính của AI:

  [ AI hướng dẫn kiểm tra lại kết nối cơ sở dữ liệu, thêm khối try...catch vào hàm xử lý bất đồng bộ (async/await), và sửa lại cú pháp câu lệnh SQL trong file controllers/authController.js ]

## 3. Quyết định của tôi

- [x] Chấp nhận gợi ý
- [ ] Chỉnh sửa gợi ý rồi áp dụng
- [ ] Bác bỏ gợi ý

- Tôi quyết định làm gì: [ Thêm khối try...catch và bổ sung file .env để cấu hình lại thông số kết nối database theo gợi ý của AI ]
- Lý do, dựa trên dữ kiện nào: [ Dựa trên thông báo lỗi 500 và log terminal, việc thiếu cấu hình biến môi trường kết nối database chính là nguyên nhân gốc rễ ]

## 4. Thực hiện và kiểm chứng

- Tệp/vị trí đã sửa (không sửa thì ghi rõ): [ controllers/authController.js và file .env ]
- Nội dung thay đổi hoặc cách xử lý khác: [ Thêm khối try-catch bọc hàm kết nối database và bổ sung biến DB_HOST, DB_USER vào file cấu hình ]
- Commit của bản sửa, nếu có: [ git commit -m "fix: fix database connection error 500 in login"]
- Bản sửa đã deploy: [x] Có  [ ] Chưa  [ ] Không phát sinh bản sửa

| Nội dung kiểm tra | Trước xử lý | Sau xử lý/thử lại |
| --- | --- |---|
|Request URL và Status của tài nguyên liên quan| [/api/login - Status: 500 Internal Server Error] | [/api/login - Status: 200 OK] |
| Giao diện/chức năng trên URL website | [ /api/login - Status: 200 OK ] | [ Đăng nhập thành công, chuyển hướng sang trang Dashboard ] |

- Cách thử lại và kết quả thực tế: [ Nhập lại tài khoản mật khẩu trên giao diện website, bấm Đăng nhập -> Website chuyển hướng mượt mà, F12 Network báo trạng thái 200 ]
- Căn cứ để đối chiếu (URL tệp, commit, đường dẫn ảnh chụp hoặc dữ kiện quan sát): [ Ảnh chụp màn hình kết quả Network tab thành công / Link commit GitHub ]

## 5. Kết luận

- [x] Đã xử lý được  [ ] Xử lý được một phần  [ ] Chưa xử lý được
- Điều tôi rút ra hoặc việc cần làm tiếp: [ Cần chú ý kiểm tra kỹ file cấu hình môi trường (.env) trước khi chạy ứng dụng và luôn bọc các hàm bất đồng bộ trong khối try...catch để bắt lỗi chuẩn xác hơn ]

---

*Tệp là minh chứng MC2 để nhận định mức đạt của tiết học; không tính điểm MC2 riêng. Nếu có tình huống khác, sao chép mục 1–5 để ghi thêm.*
