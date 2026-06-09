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

## Cấu trúc của Screen1
```
Screen1
└── VerticalArrangement
    ├── Label1 (Tiêu đề)
    ├── Image1
    ├── Name
    ├── MSSV
    ├── Class
    ├── Label2 (Giới thiệu)
    ├── ButtonScreen2 (GIẢI TOÁN)
    └── ButtonScreen3 (XEM WEBSITE)
```

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

---

## Bước 2: Thiết kế giao diện (UI) cho Screen 1 (About Me)
### Đặt tiêu đề (Title) cho Screen 1: 
Tại cột bên phải kéo xuống bên dưới tìm thuộc tính **Title** và điền tên tiêu đề, tích chọn **Scrollable** để cho phép màn hình cuộn xuống. **AlignHorizontal** điền giá trị **Center** để căn giữa các thành phần trên màn hình. <br>

<img width="1534" height="777" alt="image" src="https://github.com/user-attachments/assets/60d25a9a-e693-4e67-81b8-b0aee4c47aea" /> <br>

<img width="1534" height="776" alt="image" src="https://github.com/user-attachments/assets/3230ff2e-787a-4d75-8c2f-3110284c0f49" /> <br>

### Tạo khung chứa giao diện bằng Vertical Arrangement: <br>

<img width="1534" height="780" alt="image" src="https://github.com/user-attachments/assets/8ed61ab2-9b61-4c72-8e0a-e62f46b841ef" /> <br>

Để tổ chức các thành phần giao diện một cách khoa học, thành phần Vertical Arrangement được sử dụng làm vùng chứa chính của Screen1. Thành phần này cho phép sắp xếp các đối tượng giao diện theo chiều dọc từ trên xuống dưới.

Việc sử dụng Vertical Arrangement giúp giao diện dễ quản lý hơn, đồng thời tạo sự nhất quán khi bổ sung thêm các thành phần như hình ảnh, nhãn hiển thị thông tin và các nút chức năng.

### Thêm tiêu đề bài cho bài viết

<img width="1227" height="581" alt="image" src="https://github.com/user-attachments/assets/341385e4-dbb4-460c-b43d-173f9a5a88bd" />


### Thêm ảnh đại diện

<img width="1227" height="608" alt="image" src="https://github.com/user-attachments/assets/4a334ec1-fdbe-4451-b4fc-d94fcf270546" /> <br>

<img width="1227" height="608" alt="image" src="https://github.com/user-attachments/assets/c59b5c6a-dc10-4583-86fc-38a2c1c100af" />

### Điền thông tin giới thiệu bản thân (About me)
Tạo Label **họ tên**: <br>
<img width="1227" height="609" alt="image" src="https://github.com/user-attachments/assets/69971b9e-228f-490e-a8f9-3f9fa8bca540" /> <br>

<img width="1227" height="608" alt="image" src="https://github.com/user-attachments/assets/55f238b4-f747-4262-9321-090c5835edf8" /> <br>

Tạo Label **:MSSV**: <br>

<img width="1918" height="972" alt="image" src="https://github.com/user-attachments/assets/a6d03863-febb-4b60-9d85-abdbf5b1d44a" /> <br>

Tạo label tên **lớp học**: <br>

<img width="1918" height="1030" alt="image" src="https://github.com/user-attachments/assets/fc7b9ebb-edb8-40ad-9864-55031958c561" /> <br>

<img width="1918" height="970" alt="image" src="https://github.com/user-attachments/assets/7c0f0bd6-45ed-4b39-8f5b-74692d09a3d7" />

### Thêm Button sang screen2 (giải toán) và screen3 (Viewer 1 trang web có sẵn)

<img width="1534" height="825" alt="image" src="https://github.com/user-attachments/assets/3002358b-52be-4018-a059-e7338f6d2b0c" /> <br>

<img width="1534" height="781" alt="image" src="https://github.com/user-attachments/assets/43f3aee0-a48c-4bad-b263-0ecee1125f46" />



---

# 4. Tạo các màn hình đích Screen2, Screen3

<img width="1534" height="822" alt="image" src="https://github.com/user-attachments/assets/9428cb89-fe5e-4db4-9136-02e39c5770b7" /> <br>

<img width="1534" height="785" alt="image" src="https://github.com/user-attachments/assets/88fab505-b9a1-4c92-ae56-402a017a2550" />


---

# Thiết kế và cấu hình Screen2 - Giải toán

Screen2 được sử dụng để xây dựng chức năng giải bài toán đơn giản trên thiết bị di động. Trong bài tập này, bài toán được lựa chọn là tính chỉ số BMI (Body Mass Index) dựa trên cân nặng và chiều cao của người dùng.

---

## Mục tiêu: 
```
TÍNH CHỈ SỐ BMI

Nhập cân nặng (kg): [          ]

Nhập chiều cao (m): [          ]

[TÍNH BMI]

Kết quả BMI = ...

Phân loại:
Bình thường
```

---

## Cấu trúc của Screen2: 

```
Screen2
└── VA_BMI
    ├── lblBMI
    ├── HorizontalArrangement (Weight)
    │   ├── lblWeight
    │   └── TextWeight
    ├── HorizontalArrangement (Height)
    │   ├── lblHeight
    │   └── TextBox1
    ├── btnCalculate
    ├── lblResult
    └── lblPhanloai
```

<img width="1534" height="776" alt="image" src="https://github.com/user-attachments/assets/47fe6797-2d03-4b5a-8b73-61bb8cac76cd" /> <br>

<img width="1534" height="785" alt="image" src="https://github.com/user-attachments/assets/8bad8b61-94e9-437a-836e-20f4a0734af4" /> <br>

<img width="1534" height="777" alt="image" src="https://github.com/user-attachments/assets/2e4fcd0a-5098-4268-9c00-10da268494df" /> <br>

<img width="1918" height="967" alt="image" src="https://github.com/user-attachments/assets/312d24a6-319a-4014-b690-2efb2d9014d4" /> <br>

Nút tính toán: <br>

<img width="1534" height="780" alt="image" src="https://github.com/user-attachments/assets/d0f8e49f-d756-4d4f-aeba-b3808831b8ab" /> <br>

Nút hiển thị kết quả: <br>

<img width="1534" height="777" alt="image" src="https://github.com/user-attachments/assets/029bc620-7322-4f9d-b835-c555bf2215d6" /> <br>

## Lập trình logic cho Screen 2 (Tính BMI)
Tại màn hình **Screen2** chọn mục **Blocks**. 

### Bước 1: Sự kiện Click:
Ở cột bên trái, bấm vào **btnCaculate** -> Chọn khối `when Button1.Click do` kéo ra giữa. <br>

<img width="1534" height="772" alt="image" src="https://github.com/user-attachments/assets/9b81ddcd-5626-45ae-ade9-4b144a880e26" /> <br>

### Bước 2: Hiển thị kết quả:  
Kết quả sau khi tính toán xong sẽ được in ra Label tên `lblResult`.

Tại cột bên trái chọn `lblResult` trong Screen2 -> Kéo khối màu xanh lá cây đậm có chữ `set lblResult.Text to` ra màn hình cà lắp vào bên trong khối `when btnCalculate.Click do` <br>

<img width="1534" height="784" alt="image" src="https://github.com/user-attachments/assets/831c80da-50ea-40af-9035-eb488c71c997" /> <br>

<img width="1918" height="971" alt="image" src="https://github.com/user-attachments/assets/7b0993e9-3945-4300-b6c1-63024bf9bc03" />



### Bước 3: Lắp ráp công thức toán học và logic:
Công thức tính BMI là: **Cân nặng / (Chiều cao x Chiều cao)**. 

- Kéo lên trên cùng cột bên trái, bấm vào nhóm **Math** (màu xanh dương).

- Tìm khối có dấu chia **/**, kéo nó gắn vào cái đuôi còn trống của khối `set lblResult.Text to`. <br>

<img width="1534" height="778" alt="image" src="https://github.com/user-attachments/assets/be217cb9-f863-47f1-b640-39036e1c8a61" /> <br>

<img width="1918" height="915" alt="image" src="https://github.com/user-attachments/assets/d3266ec9-1254-43e6-b24e-a5f787f1081e" /> <br>

- Click vào chữ `TextWeight` ở cột bên trái -> Chọn khối `TextWeight.Text` -> Kéo ra và gắn vào ô trống bên trái dấu `/` của phép chia. <br>

<img width="1534" height="774" alt="image" src="https://github.com/user-attachments/assets/3c493de3-87df-4f58-ad6e-dd3bb82c1714" /> <br>


- Vào lại nhóm **Math** lấy khối nhân `x` và gắn vào ô trống thứ hai bên phải dấu chia `/` để tạo phép nhân mẫu số <br>

<img width="1534" height="750" alt="image" src="https://github.com/user-attachments/assets/a91ecd50-72e6-43dc-8ece-83e1f86ed92d" /> <br>

#### Chiều cao x Chiều cao: 
Nhấn vào chữ `TextHeight` ở cột bên trái, tìm khối `TextHeight.Text` -> Kéo vào ô trống đầu tiên của khối `x`. Tiếp tục lấy thêm một khối `TextHeight.Text` nữa gắn vào ô trống thứ hai của khối nhấn `x`. <br>

<img width="1534" height="788" alt="image" src="https://github.com/user-attachments/assets/ed02db83-95ff-497f-9fa6-50f98f71e189" /> <br>


#### Tạo biến toàn cục để lưu giá trị BMI: 
Tìm nhóm `Variables`, kéo khối `initialize global name to` (màu cam) ra màn hình -> Nhấn vào chữ `name` và đổi tên thành `BMI_Value`.
Vào nhóm **Math** kéo hối số `0` ghép vào đuôi khối màu cam này. Ý nghĩa của phần này là khởi tạo một biến tên là BMI_Value với giá trị ban đầu bằng 0. <br>

<img width="1534" height="777" alt="image" src="https://github.com/user-attachments/assets/6f0d1ce3-0961-4695-aaf7-3c01a5978ff4" /> <br>

<img width="1534" height="776" alt="image" src="https://github.com/user-attachments/assets/37f4abbf-d301-461e-9398-22d090cc98ab" /> <br>

#### Gán công thức toán học vào biến:
Vào nhóm Variables, kéo khối set global BMI_Value to thả vào ngay dòng đầu tiên bên trong lòng khối màu nâu Click.

Kéo cả cụm phép tính toán học (phép chia và phép nhân chiều cao, cân nặng) đang gắn ở chữ `set lblResult.Text to`-> Chuyển nó sang gắn vào đuôi của khối `set global BMI_Value to`.

Tiếp theo, dòng `set lblResult.Text to` lúc này đang bị trống phần đuôi. Vào `Variables`, lấy khối `get global BMI_Value` gắn vào chỗ trống đó.
(Ý nghĩa: Khi bấm nút -> Tính toán công thức và cất vào biến BMI_Value -> Sau đó lấy biến BMI_Value in ra màn hình ở dòng lblResult). <br>

<img width="1918" height="985" alt="image" src="https://github.com/user-attachments/assets/9122065f-3e70-46fc-bf3c-997c7c617ea0" /> <br>

#### Lập trình Logic Phân loại (If - Else):
Phân loại chuẩn của WHO: Dưới 18.5 là Gầy; Dưới 25 là Bình thường; Dưới 30 là Thừa cân; Còn lại là Béo phì.
1. Vào nhóm Control (màu cam nhạt), kéo khối `if then` thả vào ngay dưới khối `set lblResult.Text to`

2. Mở rộng `if-Else`: Bấm vào hình bánh răng màu xanh dương nhỏ xíu trên khối if đó. Một hộp nhỏ hiện ra.

3. Kéo 2 cái khối `else if` và 1 khối `else` ở bên trái, thả vào lồng bên dưới chữ `if` ở bên phải. Xong thì bấm lại hình bánh răng để đóng hộp. Lúc này khối lệnh đã có 4 nhánh. <br>

<img width="1918" height="955" alt="image" src="https://github.com/user-attachments/assets/d05b5df2-ecd7-410f-86ab-63b94e707298" /> <br>

<img width="1918" height="977" alt="image" src="https://github.com/user-attachments/assets/478acd02-d41d-4d1d-9e44-fa6432a9e99b" />


---

# Thiết kế và lập trình Screen 3 (WebView - Xem Website).

Tại giao diện thiết kế Screen3. Tại cột **Palette** bên trái màn hình chọn mục **USer Interface**. 
Kéo xuống bên dưới -> Nhấn giữ chuột vào **WebViewer** kéo vào màn hình điện thoại ở giữa <br>

<img width="1534" height="828" alt="image" src="https://github.com/user-attachments/assets/39719d67-765a-48e7-8176-484f245b49e0" /> <br>

Tại cột **Properties** bên phải, tìm **HomeUrl**, copy và dán một địa chỉ trang web bất kỳ có hỗ trợ giao diện di động vào đây. 
Tìm dòng `IgnoreSslErrors` (Bỏ qua lỗi bảo mật SSL): Đánh dấu tích vào ô vuông này. Việc này cực kỳ quan trọng để đảm bảo điện thoại có thể load được trang web mượt mà mà không bị hệ thống chặn lại. <br>

<img width="1534" height="778" alt="image" src="https://github.com/user-attachments/assets/73d4a8f7-56d4-468a-b469-382701648c1e" /> <br>

---

# 5. Chạy thử ứng dụng

## Kết nối điện thoại với máy tính (Dùng MIT AI2 Companion)
- Trên điện thoại tải ứng dụng tên **MIT AI2 Companion**. Kết nối điện thoại và máy tính vào cùng một mạng wi-Fi
- Trên máy tính click vào `Connect` -> Chọn `AI Companion` -> Hiển thị một mã `QR Code`. Mở ứng dụng MIT AI2 trên điện thoại -> `Scan QR code` để quét mã QR trên máy tính.<br>

<img width="1534" height="862" alt="image" src="https://github.com/user-attachments/assets/ed0dea73-cf57-4b06-8a4a-a4c2052eb35a" /> <br>

<img width="1528" height="765" alt="image" src="https://github.com/user-attachments/assets/cdb7c47e-f456-4efe-b0d6-3e288d7a894d" /> <br>

## Chạy thử chức năng của ứng dụng

<img width="2054" height="1540" alt="image" src="https://github.com/user-attachments/assets/94c3e80f-9fff-41af-a663-4a7a70df74d5" /> <br>

<img width="2054" height="1540" alt="image" src="https://github.com/user-attachments/assets/d1c90a41-4a06-4401-844a-4e4071c338ed" /> <br>

<img width="2054" height="1540" alt="image" src="https://github.com/user-attachments/assets/6005f00b-e3d1-462e-b676-32abf1749c76" />

---

# 6. Bản chất của việc kéo thả khối lệnh (Blocks Panel)
Sau khi hoàn thành phần giao diện, chuyển sang không gian **Blocks** để xây dựng phần "Não" (Logic điều khiển và xử lý thuật toán) cho ứng dụng.

* **Bản chất thao tác:** Lập trình khối là phương thức lập trình trực quan (Visual Programming). Thay vì phải gõ từng dòng ký tự dòng lệnh tuần tự (Text-based), người lập trình chọn các khối hình học đại diện cho các cấu trúc dữ liệu, vòng lặp, câu lệnh điều kiện, biến số, hàm chức năng và thực hiện thao tác lắp ráp chúng lại với nhau. Các khối lệnh được thiết kế các khớp nối vật lý dựa trên tư duy logic nghiêm ngặt; nếu hai khối lệnh không đồng nhất về mặt logic hoặc sai lệch kiểu dữ liệu, các khớp nối sẽ từ chối liên kết về mặt cơ học.
* **Ưu điểm so với viết code truyền thống:**
    * **Loại bỏ hoàn toàn lỗi cú pháp (Syntax Error):** Lập trình viên không còn phải đối mặt với các lỗi phổ biến như thiếu dấu chấm phẩy `;`, sai dấu ngoặc nhọn `{}`, viết sai chính tả từ khóa hệ thống.
    * **Trực quan, dễ tiếp cận:** Các nhóm khối được phân tách rõ ràng bằng các màu sắc đặc trưng (Toán học màu xanh dương, Văn bản màu hồng, Cấu trúc điều khiển màu cam, Biến số màu cam đậm) giúp người học nhanh chóng nắm bắt luồng đi của dữ liệu.
    * **Tập trung vào tư duy giải thuật:** Giúp lập trình viên dồn toàn bộ sự tập trung vào cấu trúc logic của bài toán (luồng đi của thuật toán tính BMI, luồng phân nhánh If-Else) thay vì bị phân tâm bởi việc học thuộc lòng cú pháp của một ngôn ngữ lập trình cụ thể.
* **Nhược điểm:**
    * **Khó quản lý mã nguồn lớn:** Khi ứng dụng mở rộng tính năng với hàng ngàn khối lệnh, màn hình Blocks sẽ trở nên cực kỳ phức tạp, rối mắt giống một mạng nhện, gây khó khăn cho công tác bảo trì, gỡ lỗi (Debug).
    * **Tốc độ thao tác chậm:** Việc dùng chuột tìm kiếm và kéo rê thả khối lệnh tốn nhiều thời gian hơn đáng kể so với việc gõ phím tốc độ cao của một coder chuyên nghiệp trên môi trường văn bản.
    * **Hạn chế tính năng chuyên sâu:** Không thể can thiệp sâu vào các kiến trúc phần cứng hệ thống phức tạp hoặc tối ưu hóa hiệu năng tài nguyên RAM/CPU theo ý muốn.
* **Cơ chế Sao chép - Dán khối lệnh thông qua tính năng Balo (Backpack):**
    * **Khái niệm:** Biểu tượng chiếc balo (`Backpack`) nằm ở góc trên cùng bên phải của không gian Blocks đóng vai trò như một bộ nhớ đệm (Clipboard) toàn cục của dự án.
    * **Cách thức vận hành:** Khi lập trình viên xây dựng được một cụm khối lệnh chuẩn (Ví dụ: Cụm lệnh click chuyển đổi màn hình hoặc cụm xử lý chuỗi văn bản) và muốn tái sử dụng ở các màn hình khác, chỉ cần dùng chuột kéo toàn bộ cụm khối đó thả vào biểu tượng Balo. Khi chuyển sang màn hình mới (`Screen2` hoặc `Screen3`), người lập trình chỉ cần nhấp chuột mở Balo ra, chọn cụm khối lệnh đó và kéo ngược ra không gian làm việc. Đây chính là cơ chế **Copy - Paste** phiên bản lập trình kéo thả trực quan, giúp tăng năng suất phát triển phần mềm cực kỳ hiệu quả.

