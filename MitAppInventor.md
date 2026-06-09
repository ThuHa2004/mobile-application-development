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

























---

## Tạo liên kết đến Screen2 và Sceen3
### Bước 1: Quay về Screen1 mở tab Blocks ở góc trên bên phải

<img width="1534" height="773" alt="image" src="https://github.com/user-attachments/assets/fef51939-438a-4fe4-8efc-ee56c786bf77" />

### Bước 2: Tạo liên kết sang Screen2
- Tại cột bên trái chọn `ButtonScreen2`
- Kéo block `when ButtonScreen2.Click do` ra vùng làm việc. Tiếp theo chọn `Built-in`→ `Control`,  kéo xuống bên dưới chọn block `open another screen screenName`  <br>

<img width="1534" height="824" alt="image" src="https://github.com/user-attachments/assets/c2055e50-370f-4429-b809-1081d5267198" /> <br>

<img width="1534" height="780" alt="image" src="https://github.com/user-attachments/assets/af794d7d-3768-4898-aa52-6c65242f5720" /> <br>

- Tiếp theo chọn `Built-in` -> `Text`. Kéo block `" "` vào ô `screenName` nhập `Screen2` <br>

<img width="1534" height="772" alt="image" src="https://github.com/user-attachments/assets/133adf8b-3c0d-4052-9482-0891d0b903ea" /> <br>

=> Kết quả sẽ được:
```
when ButtonScreen2.Click
do  open another screen screenName "Screen2"
```
<img width="1534" height="780" alt="image" src="https://github.com/user-attachments/assets/92c8a0db-51b5-46ab-b026-23b936950852" />

### Bước 3: Tạo liên kết sang Screen3

<img width="1534" height="777" alt="image" src="https://github.com/user-attachments/assets/a1825702-2bac-4505-bcf1-d67020fda6e3" /> <br>

<img width="1534" height="776" alt="image" src="https://github.com/user-attachments/assets/0b7d432c-8ec5-4719-840c-464adec579d9" /> <br>

<img width="1534" height="776" alt="image" src="https://github.com/user-attachments/assets/9cb4f5bc-8b3b-4d93-9ee4-a6a7e5382199" />










---






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




