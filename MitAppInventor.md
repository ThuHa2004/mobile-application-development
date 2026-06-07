# BÀI TẬP MÔN: PHÁT TRIỂN ỨNG DỤNG TRÊN THIẾT BỊ DI ĐỘNG
---
## Họ tên: Trần Thị Thu Hà
## MSSV: K225480106009
## Lớp: K58KTP.01
### Dealine: 13/06/2026
---
# YÊU CẦU: 
1. Viết phần mềm trên công cụ Mit App inventor
   (tập trung vào quy trình tạo ra phần mềm)
   App có 3 screen:
   + about về bản thân+nút gọi sang 2 screen còn lại
   + giải 1 bài toán đơn giản
   + sử dụng webview: hiển thị 1 trang web có sẵn, hỗ trợ giao diện điện thoại
   mô tả: thanh công cụ có gì? kéo thả + thay đổi thuộc tính: làm ntn, để làm gì?
          block: mô tả bản chất việc kéo thả block ntn?
                 ưu điểm gì so với viết code? nhược điểm?
                 copy paste block ? (backpack)

---
# BÀI LÀM:
---
# 1. Mục tiêu 
Xây dựng một ứng dụng di động đa màn hình bằng nền tảng **MIT App Inventor** với các chức năng chính sau:
- **Screen 1 (Giới thiệu):** Hiển thị thông tin bản thân (About me) và chứa các nút điều hướng gọi sang 2 màn hình còn lại.
- **Screen 2 (Giải toán):** Chứa giao diện và logic để giải một bài toán đơn giản (ví dụ: tính tổng, giải phương trình,...).
- **Screen 3 (WebView):** Sử dụng component WebView để hiển thị một trang web có sẵn, hỗ trợ giao diện di động.

---

# 2. Giới thiệu công cụ MIT App Inventor
MIT App Inventor là nền tảng lập trình trực quan được phát triển bởi MIT cho phép người dùng xây dựng ứng dụng Android bằng cách kéo thả các thành phần giao diện và lập trình bằng các khối lệnh (Blocks).
## Ưu điểm: 
- Dễ học và dễ sử dụng.
- Không yêu cầu nhiều kiến thức lập trình.
- Phát triển ứng dụng nhanh.
- Hỗ trợ kiểm thử trực tiếp trên điện thoại.
## Nhược điểm: 
- Hạn chế khi xây dựng ứng dụng lớn.
- Khả năng tùy biến thấp hơn Android Studio.
- Hiệu năng không cao đối với các dự án phức tạp.

---

# 3. Xây dựng giao diện trang chủ - Screen 1 (giới thiệu bản thân)

## Bước 1: Khởi tạo dự án
Truy cập trang chủ MIT App Inventor, chọn **Create Apps** và đăng nhập bằng tài khoản Google. <br>

<img width="1534" height="822" alt="image" src="https://github.com/user-attachments/assets/25d8df3f-5acf-4f8d-8241-4ea98abdf7c8" /> <br>

<img width="1534" height="812" alt="image" src="https://github.com/user-attachments/assets/91ac4993-6231-41c3-a956-2aef123cdc50" /> <br> 

Giao diện ban đầu sẽ hiển thị chế độ **Designer** cho `Screen1` gồm các thành phần:
- **Palette** chứa các thành phần giao diện như: Button, Label, TextBox, Image, WebViewer
- **Viewer** là khu vực thiết kế giao diện ứng dụng.
- **Components** là danh sách các thành phần đã được thêm vào màn hình
- **Properties** cho phép thay đổi thuộc tính của các thành phần như: Text, Width, Height, Front Size, Background Color. <br>

<img width="1534" height="781" alt="image" src="https://github.com/user-attachments/assets/39c1d658-f23e-4a49-a5c4-6bbff12e8bcb" />


## Bước 2: Thiết kế giao diện (UI) cho Screen 1 (About Me)
### Đặt tiêu đề (Title) cho Screen 1: 
Tại cột bên phải kéo xuống bên dưới tìm thuộc tính **Title** và điền tên tiêu đề, tích chọn **Scrollable** để cho phép màn hình cuộn xuống. **AlignHorizontal** điền giá trị **Center** để căn giữa các thành phần trên màn hình. <br>

<img width="1533" height="781" alt="image" src="https://github.com/user-attachments/assets/8c8c7d53-72ce-4ec7-aaf2-c5be2e3dc262" /> <br>

<img width="1533" height="780" alt="image" src="https://github.com/user-attachments/assets/c3aac9af-6145-4cc9-966b-3fddcb493a3a" /> <br>

### Tạo khung chứa giao diện bằng Vertical Arrangement: <br>

<img width="1533" height="776" alt="image" src="https://github.com/user-attachments/assets/aacb5022-ced7-45a9-8e34-0246bbf4e259" /> <br>

Để tổ chức các thành phần giao diện một cách khoa học, thành phần Vertical Arrangement được sử dụng làm vùng chứa chính của Screen1. Thành phần này cho phép sắp xếp các đối tượng giao diện theo chiều dọc từ trên xuống dưới.

Việc sử dụng Vertical Arrangement giúp giao diện dễ quản lý hơn, đồng thời tạo sự nhất quán khi bổ sung thêm các thành phần như hình ảnh, nhãn hiển thị thông tin và các nút chức năng.

### Điền thông tin giới thiệu bản thân (About me)



















- Ở cột **Palette** (bên trái), trong nhóm *User Interface*, kéo một **Label** và thả vào vùng màn hình điện thoại (Viewer).
- Sang cột **Properties** (bên phải), sửa thuộc tính `Text` của Label thành thông tin cá nhân. Căn giữa chữ bằng `TextAlignment` và chỉnh `FontSize` cho phù hợp. <br>
<img width="1529" height="777" alt="image" src="https://github.com/user-attachments/assets/adcc92b4-dd91-4051-971e-b6115dedf5ae" />

- Kéo tiếp hai **Button** từ Palette thả vào phía dưới Label.
- Bấm vào Button 1, sửa thuộc tính `Text` thành *"Chuyển sang Giải Toán"*.
- Bấm vào Button 2, sửa thuộc tính `Text` thành *"Chuyển sang Xem Web"*.

> **[Chèn hình ảnh 2: Ảnh chụp màn hình Designer sau khi đã kéo thả xong Label và các Button, kèm theo cột Properties đang được chỉnh sửa]**

### Bước 3: Tạo các màn hình đích (Screen2, Screen3)
- Trên thanh công cụ trên cùng, nhấn nút **Add Screen**.
- Nhập tên `Screen2` và nhấn OK.
- Lặp lại thao tác trên để tiếp tục tạo `Screen3`.
- Dùng menu danh sách màn hình thả xuống ở thanh công cụ để chọn quay lại `Screen1`.

> **[Chèn hình ảnh 3: Ảnh chụp menu thả xuống cho thấy dự án đã tạo đủ 3 màn hình: Screen1, Screen2, Screen3]**

### Bước 4: Lập trình khối lệnh (Blocks) chuyển trang cho Screen 1
- Chuyển từ chế độ Designer sang chế độ **Blocks** (nhấn nút ở góc trên bên phải).
- Bấm vào **Button1** ở cột danh sách bên trái, kéo khối sự kiện `when Button1.Click do` ra không gian làm việc.
- Mở nhóm lệnh **Control** (màu cam), kéo khối `open another screen screenName` ghép vào trong thân khối Click.
- Mở nhóm lệnh **Text** (màu hồng), kéo khối chuỗi trống ` " " ` ghép vào sau khối control và gõ chính xác chữ `Screen2`.
- Làm tương tự cho **Button2**, nhưng nhập tên màn hình đích là `Screen3`.

> **[Chèn hình ảnh 4: Ảnh chụp vùng làm việc Blocks hiển thị rõ 2 khối lệnh hoàn chỉnh của Button1 và Button2]**

### Bước 5: Chạy thử ứng dụng (Testing)
- Trên thanh menu, chọn **Connect** -> **AI Companion**.
- Dùng ứng dụng MIT AI2 Companion trên điện thoại quét mã QR hiển thị trên màn hình máy tính.
- Kiểm tra chức năng: Bấm vào các nút trên điện thoại xem ứng dụng có chuyển sang màn hình mới thành công hay không.

> **[Chèn hình ảnh 5: Ảnh chụp cửa sổ mã QR kết nối AI Companion HOẶC ảnh chụp màn hình điện thoại đang hiển thị App thực tế]**




