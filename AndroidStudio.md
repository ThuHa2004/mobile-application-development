# BÀI TẬP LỚN MÔN HỌC: PHÁT TRIỂN ỨNG DỤNG TRÊN THIẾT BỊ DI ĐỘNG - TEE0419

---

## Họ tên: Trần Thị Thu Hà
## MSSV: K225480106009
## Lớp: K58KTP.01
## Dealine: 13/06/2026

---

# YÊU CẦU: 
Viết App sử dụng Android Studio: <br>
==> Tạo app1 sử dụng cơ chế Dữ liệu chuẩn bị trước trong Assets <br>
==> APP2 (android studio):  tạo app tương đương với Mit App inventor, app có 3 activity

---

# BÀI LÀM:

---

# I. LÝ THUYẾT

---

## 1. Tập tin Cấu trúc `AndroidManifest.xml` là gì?
`AndroidManifest.xml` là tập tin cấu hình trung tâm, đóng vai trò như "bản căn cước công dân" của một ứng dụng Android. Đây là tập tin bắt buộc phải có trong mọi dự án Android Studio. Hệ điều hành Android sẽ luôn đọc tập tin này đầu tiên trước khi khởi chạy ứng dụng để nắm được các thông tin cơ bản và cấu trúc phân cấp bảo mật.

**Các thông tin bắt buộc phải khai báo bao gồm:**
* **Tên package:** Định danh duy nhất cho ứng dụng trên toàn hệ thống và chợ ứng dụng Google Play.
* **Các thành phần (Components):** Khai báo toàn bộ các Activity, Service, Broadcast Receiver và Content Provider có trong ứng dụng.
* **Cấu hình hệ thống:** Phiên bản Android SDK hỗ trợ (minSdkVersion, targetSdkVersion), biểu tượng (icon) và chủ đề (Theme) của ứng dụng.
* **Hệ thống quyền (Permissions):** Các quyền truy cập tài nguyên phần cứng hoặc dữ liệu người dùng.

**Ví dụ khai báo quyền truy cập Internet:**
```xml
<uses-permission android:name="android.permission.INTERNET"/>
```

**Ví dụ khai báo Activity khởi chạy chính (Launcher Activity):**
```xml
<activity android:name=".MainActivity" android:exported="true">
    <intent-filter>
        <!-- MAIN: Xác định đây là Activity chính khi mở ứng dụng -->
        <action android:name="android.intent.action.MAIN"/>
        <!-- LAUNCHER: Cho phép Activity xuất hiện trên màn hình danh sách ứng dụng (App Drawer) -->
        <category android:name="android.intent.category.LAUNCHER"/>
    </intent-filter>
</activity>
```

---

## 2. Hệ thống Quyền (Permission) trong Android
Android sử dụng cơ chế bảo mật nghiêm ngặt dựa trên quyền truy cập để bảo vệ tối đa dữ liệu và quyền riêng tư của người dùng. Mọi ứng dụng muốn can thiệp vào các tài nguyên nằm ngoài phạm vi mặc định (như mạng, phần cứng, tệp tin) đều phải xin phép hệ thống.

| Chức năng phần cứng / dữ liệu | Tên Permission tương ứng |
| :--- | :--- |
| Truy cập mạng Internet toàn diện | `android.permission.INTERNET` |
| Sử dụng phần cứng máy ảnh | `android.permission.CAMERA` |
| Lấy vị trí chính xác thông qua GPS | `android.permission.ACCESS_FINE_LOCATION` |
| Đọc dữ liệu từ bộ nhớ lưu trữ ngoài | `android.permission.READ_EXTERNAL_STORAGE` |
| Thực hiện cuộc gọi điện thoại trực tiếp | `android.permission.CALL_PHONE` |

> **Mục đích:** Việc khai báo quyền minh bạch hóa hành vi của ứng dụng, giúp hệ điều hành giám sát tài nguyên và cho phép người dùng kiểm soát chặt chẽ những gì ứng dụng được phép làm trên thiết bị của họ.

---

## 3. Vòng đời của Activity trong Android (Activity Lifecycle)
Mỗi Activity (màn hình ứng dụng) đều trải qua một chuỗi các trạng thái từ lúc được tạo ra cho đến khi bị hủy hoàn toàn. Hệ điều hành Android sẽ tự động gọi các phương thức callback tương ứng dưới đây khi trạng thái hiển thị của Activity thay đổi:

* **`onCreate()`:** Được gọi đầu tiên khi Activity bắt đầu khởi tạo cấu trúc. Phương thức này chỉ chạy duy nhất một lần trong một vòng đời để nạp giao diện, khởi tạo biến và ánh xạ phần tử.
* **`onStart()`:** Được gọi khi Activity bắt đầu hiển thị trên màn hình, người dùng đã có thể nhìn thấy giao diện nhưng chưa tương tác được.
* **`onResume()`:** Được gọi khi Activity đã hiển thị hoàn toàn và sẵn sàng nhận mọi tương tác (click, cuộn, nhập liệu) từ người dùng. Đây là trạng thái hoạt động chính của app.
* **`onPause()`:** Được gọi khi Activity chuẩn bị mất quyền tương tác một phần, ví dụ như khi có cuộc gọi đến, có một hộp thoại Dialog che khuất một phần màn hình. Lúc này app cần tạm dừng các tác vụ gây tốn tài nguyên.
* **`onStop()`:** Được gọi khi Activity bị che khuất hoàn toàn (khi người dùng bấm nút Home hoặc chuyển sang một màn hình hoàn toàn mới).
* **`onDestroy()`:** Được gọi khi Activity bị giải phóng hoàn toàn khỏi bộ nhớ hệ thống (khi người dùng bấm nút Back để thoát hẳn app hoặc hệ thống tự động giải phóng RAM).

---

## 4. Tại sao Android Studio tự động sinh sẵn hàm `onCreate()`?
Khi tạo một dự án mới hoặc một Activity mới, Android Studio luôn tự động sinh ra hàm `onCreate()`. Vai trò của hàm này tương tự như hàm `main()` trong các chương trình Java tiêu chuẩn. 

Vì hệ điều hành Android điều khiển việc khởi tạo các thành phần, nó cần một điểm kích hoạt cố định (Entry Point). Lập trình viên bắt buộc phải sử dụng `onCreate()` để liên kết file code Java với file giao diện XML thông qua câu lệnh `setContentView(R.layout.activity_main);`. Nếu không có hàm này, màn hình sẽ không có cấu trúc nền tảng và không thể hiển thị nội dung.

---

## 5. Cơ chế Kiểm tra Quyền trong Android (Runtime Permission)
Từ Android 6.0 (API 23) trở lên, đối với nhóm **Quyền nguy hiểm (Dangerous Permissions)** ảnh hưởng trực tiếp đến sự riêng tư của người dùng, việc khai báo trong `AndroidManifest.xml` là chưa đủ. Ứng dụng phải kiểm tra và xin quyền trực tiếp ngay khi đang chạy (Runtime).

**Ví dụ kiểm tra quyền sử dụng Camera:**
```java
if (ContextCompat.checkSelfPermission(this, Manifest.permission.CAMERA) 
        == PackageManager.PERMISSION_GRANTED) {
    // Ý nghĩa: Nếu quyền đã được cấp trước đó, ứng dụng thực hiện mở Camera ngay
    openCamera();
} else {
    // Ý nghĩa: Nếu chưa được cấp quyền, hiển thị hộp thoại yêu cầu người dùng cấp quyền
    ActivityCompat.requestPermissions(this, new String[]{Manifest.permission.CAMERA}, 1);
}
```

---

## 6. Giao diện Android và Thư mục Layout
Tất cả các tệp tin thiết kế giao diện đồ họa cho ứng dụng Android đều được quản lý tập trung trong thư mục: `res/layout/`. 

Giao diện được mô tả bằng cấu trúc ngôn ngữ định dạng XML. Mỗi file XML thường tương ứng với một màn hình Activity cụ thể và được đặt tên theo quy chuẩn viết thường cách nhau bởi dấu gạch dưới (Ví dụ: `activity_main.xml`).

**Ví dụ cấu trúc giao diện TextView đơn giản:**
```xml
<TextView
    android:id="@+id/txtHello"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="Xin chào" />
```

---

## 7. Kỹ thuật Hardcode và Giải pháp Tham chiếu Tài nguyên

## Bản chất của Hardcode
Hardcode là việc lập trình viên ghi trực tiếp các giá trị dữ liệu cụ thể (như văn bản hiển thị, mã màu, kích thước) vào ngay trong file code Java hoặc XML giao diện.
* **Ví dụ:** `android:text="Xin chào"` hoặc `txtView.setText("Xin chào");`
* **Nhược điểm:** Làm dự án cực kỳ khó bảo trì, khi cần sửa đổi nội dung văn bản sẽ phải đi tìm kiếm khắp các file để sửa, không có khả năng tái sử dụng và hoàn toàn không thể triển khai đa ngôn ngữ.

### Lưu trữ tài nguyên chuẩn trong `strings.xml`
Android khuyến khích tách rời dữ liệu hiển thị ra khỏi logic bằng cách lưu tập trung tất cả các chuỗi chữ vào file: `res/values/strings.xml`.
```xml
<resources>
    <string name="hello">Xin chào</string>
</resources>
```

### Cú pháp tham chiếu tài nguyên:
* **Trong file Layout XML:** `android:text="@string/hello"`
* **Trong file mã nguồn Java:**
  `txtHello.setText(R.string.hello);` hoặc `txtHello.setText(getString(R.string.hello));`

### Ưu điểm vượt trội:
1. **Dễ bảo trì:** Thay đổi nội dung tại một nơi duy nhất (`strings.xml`), toàn bộ ứng dụng tự động cập nhật.
2. **Tái sử dụng:** Một chuỗi văn bản có thể được gọi ra hiển thị ở nhiều màn hình khác nhau mà không cần viết lại.
3. **Chuẩn hóa đa ngôn ngữ:** Hạn chế tối đa lỗi chính tả và lỗi đồng bộ nội dung khi cập nhật phiên bản ứng dụng.

---

## 8. Cơ chế Hỗ trợ Tự động theo LOCATION, LANGUAGE và THEME
Khi ứng dụng sử dụng cơ chế tham chiếu tài nguyên, Hệ điều hành Android cung cấp khả năng tự động hóa cấu hình giao diện thông qua việc phân tách cấu trúc thư mục bằng các hậu tố đặc trưng (Qualifiers).

**Ví dụ tổ chức thư mục đa ngôn ngữ (Language):**
* `res/values/strings.xml` (Thư mục mặc định, ví dụ lưu tiếng Anh): `<string name="hello">Hello</string>`
* `res/values-vi/strings.xml` (Thư mục tài nguyên tiếng Việt): `<string name="hello">Xin chào</string>`
* `res/values-en/strings.xml` (Thư mục tài nguyên tiếng Anh chuẩn khu vực).

> **Cơ chế tự động của OS:** Khi người dùng thay đổi ngôn ngữ hệ thống trên điện thoại sang Tiếng Việt, Android OS sẽ tự động nhận diện vị trí và ngôn ngữ để trích xuất chính xác chuỗi chữ trong thư mục `values-vi`. Lập trình viên không cần viết thêm bất kỳ câu lệnh điều kiện `if/else` nào trong code logic. 

**Lợi ích thực tế:**
* Giúp ứng dụng thực hiện chiến lược Bản địa hóa (Localization) nhanh chóng.
* Nâng cao trải nghiệm người dùng theo xu hướng cá nhân hóa (như tự chuyển Light Mode / Dark Mode qua bộ lọc tài nguyên Theme).
* Tiết kiệm thời gian phát triển, không cần phải xây dựng nhiều phiên bản ứng dụng riêng biệt cho từng quốc gia.

---

## 9. Đối tượng chứa cấu trúc (Container)
Container thực chất là các lớp kế thừa từ `ViewGroup`, đóng vai trò làm khung chứa để gom nhóm và sắp xếp các đối tượng giao diện con (`View`) theo một quy luật hình học nhất định. Bố cục phổ biến và dễ sử dụng nhất là **`LinearLayout`** (Bố cục tuyến tính).

* **Sắp xếp theo hàng dọc (`vertical`):** Các thành phần con sẽ tự động xếp chồng liên tiếp lên nhau từ trên xuống dưới.
```xml
<LinearLayout
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical">
    <!-- Các thành phần con nằm ở đây -->
</LinearLayout>
```
* **Sắp xếp theo hàng ngang (`horizontal`):** Các thành phần con sẽ tự động dàn hàng kề sát nhau từ trái qua phải.
```xml
<LinearLayout
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="horizontal">
    <!-- Các thành phần con nằm ở đây -->
</LinearLayout>
```

---

## 10. Thuộc tính Căn chỉnh Gravity
Thuộc tính `Gravity` được sử dụng để điều hướng và định vị vị trí hiển thị của các thành phần giao diện theo các trục không gian hình học.

* `android:gravity="center"`: Căn chỉnh đối tượng vào chính giữa không gian.
* `android:gravity="left"` hoặc `android:gravity="start"`: Căn chỉnh đối tượng về biên bên trái.
* `android:gravity="right"` hoặc `android:gravity="end"`: Căn chỉnh đối tượng về biên bên phải.

### Phân biệt rõ hai thuộc tính cốt lõi:
* **`android:gravity`:** Căn chỉnh nội dung nằm **bên trong** bản thân đối tượng đó (Ví dụ: Căn chữ nằm giữa lòng một Button).
* **`android:layout_gravity`:** Căn chỉnh **bản thân toàn bộ đối tượng đó** so với không gian của Layout cha bao quanh nó.

---

## 11. Cơ chế Tương tác giữa Mã nguồn Java và Layout XML
Mô hình phát triển của Android quản lý tách biệt giữa giao diện (XML) và xử lý logic (Java). Để code Java có thể can thiệp, đọc dữ liệu hoặc thay đổi thuộc tính của một phần tử trên UI, ta phải thực hiện cơ chế ánh xạ thông qua mã định danh ID.

**Quy trình thực hiện:**
```java
// 1. Khai báo đối tượng đại diện trong Java
TextView txtHello;

// 2. Sử dụng hàm findViewById để liên kết ánh xạ với ID bên XML giao diện
txtHello = findViewById(R.id.txtHello);

// 3. Tương tác thay đổi nội dung hiển thị chuẩn hóa dựa trên tham chiếu Strings
txtHello.setText(getString(R.string.hello));
```
> **Ý nghĩa:** Việc tuân thủ ánh xạ và nạp tài nguyên tham chiếu giúp giao diện ứng dụng biến đổi linh hoạt, luôn hiển thị chính xác theo ngôn ngữ và cấu hình thực tế của người dùng thiết bị mà không làm phá vỡ cấu trúc mã nguồn.

---

## 12. Xử lý Sự kiện (Event Handling) trong Android
Sự kiện (Event) là tất cả các hành vi tác động vật lý của người dùng lên trên màn hình ứng dụng (Ví dụ: Click Button, chạm màn hình, lướt danh sách, nhập văn bản). Để chạy một đoạn code xử lý khi xảy ra sự kiện click, thành phần giao diện bắt buộc phải được đặt thuộc tính `android:id` và được ánh xạ sang Java.

Ta có 2 phương pháp lập trình xử lý sự kiện click kinh điển:

### Cách 1: Sử dụng bộ lắng nghe sự kiện `OnClickListener` trong Java (Phổ biến nhất)
* **Mã nguồn xử lý:**
```java
Button btnTinh = findViewById(R.id.btnTinh);
btnTinh.setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View view) {
        // Thực thi các đoạn mã logic, tính toán tại đây khi người dùng CLICK
        showResult();
    }
});
```
* **Ưu điểm:** Tách biệt hoàn toàn mã hiển thị và mã logic, quản lý tập trung tại file code, bảo mật tốt, dễ dàng gỡ lỗi (debug) và áp dụng được cho mọi dự án lớn.

### Cách 2: Sử dụng thuộc tính gán nhãn `android:onClick` trực tiếp từ XML
* **Khai báo trong file Layout XML:**
```xml
<Button
    android:id="@+id/btnTinh"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:onClick="xuLyNut"/>
```
* **Khai báo phương thức xử lý tương ứng trong file code Java:**
```java
public void xuLyNut(View view) {
    // Thực thi đoạn mã logic tại đây khi xảy ra sự kiện click
    showResult();
}
```
* **Ưu điểm:** Khai báo nhanh gọn, giảm thiểu dung lượng code Java, trực quan, phù hợp với các ứng dụng quy mô nhỏ hoặc các bài thực hành tính toán đơn giản.

---

## 13. Thư mục Đặc biệt `Assets`
Thư mục `Assets` là một không gian lưu trữ đặc biệt nằm trong cấu trúc thư mục của dự án Android Studio tại đường dẫn: `app/src/main/assets`.

**Bản chất và đặc điểm:**
* Cho phép lưu trữ các tệp tin thô nguyên bản chưa qua biên dịch (như `.txt`, `.json`, `.html`, `.pdf`, các file dữ liệu SQLite, video, âm thanh).
* Toàn bộ dữ liệu nằm trong thư mục này sẽ giữ nguyên cấu trúc phân cấp cây thư mục do lập trình viên tự tạo, không bị hệ thống tự động biên dịch và không sinh ra mã định danh quản lý trong file `R.java`.
* Khi thực hiện quá trình đóng gói ứng dụng (Compile), toàn bộ nội dung trong thư mục Assets sẽ được đóng gói đi kèm theo ứng dụng và nằm trọn vẹn bên trong tệp tin cài đặt APK.

---

## 14. Phương thức Truy cập Dữ liệu trong Assets
Để tương tác với các tệp tin nằm trong thư mục `assets`, ứng dụng sử dụng lớp quản lý hệ thống mang tên `AssetManager` kết hợp luồng đọc byte dữ liệu `InputStream`.

**Ví dụ cú pháp đọc tệp dữ liệu văn bản thô:**
```java
InputStream is = getAssets().open("data.txt");
```

**Ví dụ cú pháp đọc tệp dữ liệu có cấu trúc định dạng JSON:**
```java
InputStream is = getAssets().open("data.json");
```
Thông qua luồng byte này, lập trình viên có thể chuyển đổi mảng byte sang chuỗi `String` chuẩn định dạng UTF-8 để phân tích cấu trúc dữ liệu và hiển thị lên màn hình ứng dụng bất cứ lúc nào.

---

## 15. Lợi ích vượt trội và Ứng dụng thực tế của cơ chế Assets Offline

### Lợi ích cốt lõi:
* **Tính độc lập cao (Offline):** Dữ liệu được đóng gói cứng đi kèm bên trong app nên ứng dụng hoạt động hoàn toàn ngoại tuyến mà không cần kết nối mạng Internet.
* **Tốc độ truy xuất tối đa:** Do đọc tệp từ bộ nhớ cục bộ của thiết bị, dữ liệu hiển thị lên màn hình gần như ngay lập tức, loại bỏ hoàn toàn thời gian trễ phản hồi mạng.
* **Tiết kiệm chi phí vận hành:** Lập trình viên không cần thuê máy chủ (Server) hay xây dựng hệ thống cơ sở dữ liệu trên cloud để lưu trữ dữ liệu tĩnh.

### Ứng dụng thực tế:
Cơ chế Assets cực kỳ phù hợp để xây dựng các loại ứng dụng như: Ứng dụng học tập offline, Từ điển tra cứu thuật ngữ, Ứng dụng đọc truyện chữ (Sách điện tử E-book), Cẩm nang hướng dẫn du lịch hoặc Danh sách tổng hợp công thức toán học/mật mã học bỏ túi.

---

# II. TẠO APP1: sử dụng cơ chế Dữ liệu chuẩn bị trước trong Assets

---

## APP - Cẩm nang du lịch Việt Nam offline

---

## Mô tả bài toán 
Hiện nay, nhu cầu tìm hiểu các địa điểm du lịch tại Việt Nam ngày càng phổ biến. Tuy nhiên, việc tra cứu thông tin thường phụ thuộc vào kết nối Internet. Trong một số trường hợp người dùng không có mạng hoặc muốn tra cứu nhanh thông tin cơ bản thì việc sử dụng các website trực tuyến trở nên bất tiện.

Để giải quyết vấn đề này, ứng dụng "Cẩm nang du lịch Việt Nam Offline" được xây dựng nhằm cung cấp thông tin về các địa điểm du lịch nổi tiếng tại Việt Nam dưới hình thức dữ liệu được chuẩn bị sẵn và lưu trữ trực tiếp trong ứng dụng. Người dùng có thể xem thông tin địa điểm du lịch mọi lúc mà không cần kết nối Internet.

---

## Dữ liệu sử dụng

Ứng dụng sử dụng dữ liệu được chuẩn bị trước và lưu trong thư mục Assets dưới dạng tệp JSON.

Mỗi địa điểm du lịch bao gồm các thông tin:

Mã địa điểm.
Tên địa điểm.
Tỉnh/Thành phố.
Mô tả ngắn.
Hình ảnh minh họa.

Ví dụ:
```
{
  "id": 1,
  "name": "Đà Lạt",
  "city": "Lâm Đồng",
  "description": "Thành phố ngàn hoa nổi tiếng với khí hậu mát mẻ.",
  "image": "dalat"
}
```

---

## Thuật toán xử lý dữ liệu

Ứng dụng sử dụng thuật toán tìm kiếm tuyến tính (Linear Search).

Khi người dùng nhập từ khóa tìm kiếm, chương trình sẽ lần lượt duyệt qua danh sách địa điểm du lịch và so sánh tên địa điểm với từ khóa được nhập. Các địa điểm phù hợp sẽ được hiển thị trên màn hình.

Thuật toán này phù hợp vì số lượng dữ liệu nhỏ và dễ triển khai.

---

## Đối tượng hiển thị dữ liệu

Dữ liệu được hiển thị bằng `RecyclerView` kết hợp với `CardView` để hiển thị cấu trúc danh sách. `RecyclerView` giúp tái sử dụng các ô hiển thị (ViewHolders) đã cuộn khỏi màn hình, giúp ứng dụng vận hành mượt mà, không bị giật lag kể cả trên các thiết bị cấu hình yếu.

Mỗi phần tử trong RecyclerView sẽ hiển thị:

Hình ảnh địa điểm.
Tên địa điểm.
Tỉnh/Thành phố.
Mô tả ngắn.

RecyclerView giúp hiển thị danh sách dữ liệu hiệu quả, dễ mở rộng và phù hợp với các ứng dụng Android hiện đại.

---

## Giải pháp thực hiện

Ứng dụng được xây dựng bằng Android Studio sử dụng ngôn ngữ Java.

Quy trình hoạt động:

Đọc dữ liệu từ tệp JSON trong thư mục Assets.
Chuyển dữ liệu JSON thành các đối tượng Java.
Hiển thị dữ liệu bằng RecyclerView.
Cho phép người dùng tìm kiếm địa điểm theo tên.
Cập nhật danh sách kết quả sau khi tìm kiếm.

Ứng dụng hoạt động hoàn toàn offline, không yêu cầu kết nối Internet và đáp ứng đầy đủ yêu cầu sử dụng dữ liệu chuẩn bị trước trong Assets.

---

## Cấu trúc project: 
```
app
│
├─ manifests
│   └─ AndroidManifest.xml
│
├─ kotlin+java
|   └─com.example.camnangdulichvietnam
│       └─MainActivity.java
│       └─TravelAdapter.java
|       └─TravelPlace.java
|
├─ assets
|   └─travel_places.json
|
├─ res
│   ├─ layout
│   │   └─ activity_main.xml
│   │   └─ item_travel.xml
│   └─ drawable
|       └─ img_dalat.jpg
|       └─ img_hoian.jpg
|       └─ img_halong.jpg
│
└─ Gradle Scripts
```

---

# CÁC BƯỚC THỰC HIỆN

---

## Bước 1: Khởi tạo project trên Android Studio

- Mở Android Studio. Chọn `New Project` -> `Empty Views Activity` -> Nhấn Next. <br>

<img width="1227" height="673" alt="image" src="https://github.com/user-attachments/assets/d347b083-70a1-4e3e-9b81-9e72f0ff45de" /> <br>

- Sau đó điền:
```
Name: CamNangDuLichVietNam
Package Name: com.example.camnangdulich
Language: Java
Minimum SDK: API 24
```
- Nhấn Finish <br>

<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/dc64064c-2af5-4ae6-8976-9299efaea680" />

---

## Bước 2: Tạo thư mục Assets và file dữ liệu JSON địa điểm

### Tạo thư mục Assets
Mặc định dự án mới sẽ không có thư mục này vì vậy ta phải tạo nó. Tại cột danh sách thư mục bên trái: 
- Nhấp chuột phải vào thư mục **app**
- Chọn **New** -> **Directory** -> **Assets Folder** -> **Finish**.
Sau khi nhấn `Finish` dưới thư mục `main` sẽ xuất hiện một thư mục tên là `Assets` <br>

<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/100d0559-387c-49e4-a329-e76550afb821" /> <br>

<img width="1534" height="822" alt="image" src="https://github.com/user-attachments/assets/f28a8eb8-b4c6-40a4-afca-f70ee99b99cc" /> <br>

<img width="1227" height="608" alt="image" src="https://github.com/user-attachments/assets/8d0e388a-1748-47b2-b9d3-aff6a929ba33" /> <br>

### Tạo file dữ liệu `travel_places.json`
- Nhấp chuột phải vào thư mục **Assets** vừa tạo -> **New** -> **File**
- Đặt tên cho file là: `travel_places.json` <br>

<img width="1534" height="862" alt="image" src="https://github.com/user-attachments/assets/d29021d7-e4d8-4cd1-b1e2-4d39764847dd" /> <br>

<img width="1227" height="608" alt="image" src="https://github.com/user-attachments/assets/811d2026-71ee-46ef-88a5-f4fe7ae10169" /> <br>

- Viết file json vừa tạo: <br>

<img width="1918" height="1021" alt="image" src="https://github.com/user-attachments/assets/c7423f46-c66f-4e9c-91a6-46aaa612d1db" />

### Thêm ảnh vào app

Tải ảnh trên google hoặc chụp ảnh từ ccamera sau đó đổi tên 3 ảnh lần thành `img_dalat.jpg`, `img_halong.jpg`, `img_hoian.jpg`. 
- Copy 3 file ảnh vừa lưu về.
- Tìm thư mục `app` -> `res` -> `drawable`. Dán ảnh vào trong `drawable`

<img width="1534" height="681" alt="image" src="https://github.com/user-attachments/assets/0ba02731-4841-4822-bbdf-6f167e949b63" /> <br>

---

## Bước 3: Thiết kế giao diện XML (Layout)

### Màn hình chính file `activity_main.xml`

Mở file `activity_main.xml` và chuyển sang chế độ xem **Code** sau đó sửa lại file `activity_main.xml` <br>

<img width="1534" height="814" alt="image" src="https://github.com/user-attachments/assets/e8fd9012-494f-444b-b1e7-fcddb4d7c318" /> <br>

<img width="1534" height="796" alt="image" src="https://github.com/user-attachments/assets/5eb081e1-ee7c-4364-b881-8563830eb578" /> <br>

Sau khi chuyển sang chế độ code, cấu hình lại file `activity_main.xml`: <br>

<img width="1534" height="813" alt="image" src="https://github.com/user-attachments/assets/14acc75a-0ab8-4c89-b7c9-a63bddfb6c49" /> <br>

### Thiết kế ô hiển thị file `item_travel.xml`
Click chuột phải vào thư mục **Layout** -> **New** -> **Layout Resource File**. Đặt tên file là `item_travel` sau đó mở file này ra và viết code thiết kế khung dạng thẻ vào. <br>

<img width="1534" height="862" alt="image" src="https://github.com/user-attachments/assets/a734e499-d9d0-4082-85a8-fb84992365a6" /> <br>

<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/5c0f3499-6290-4d7d-b9ed-8f66fc889624" />

---

## Bước 4: Viết mã nguồn cấu trúc logic (java)

### Tạo dữ liệu mẫu (TravelPlace.java)
- Trong thư mục `kotlin+java`, nhấp chuột phải vào thư mục `com.example.camnangdulichvietnam` (dòng đầu tiên) -> Chọn `New` -> Chọn `Java Class`. <br>

<img width="1534" height="816" alt="image" src="https://github.com/user-attachments/assets/631a46c5-3fbc-4fae-adad-93915f391534" /> <br>

- Đặt tên file là `TravelPlace` -> `Enter`
- Xóa hết code tự sinh bên trong đi và viết lại code chuẩn package vào <br>

<img width="1534" height="816" alt="image" src="https://github.com/user-attachments/assets/17344bd9-a95c-46fa-a4ec-76cddebeae3c" />

### Tạo bộ nạp dữ liệu lên màn hình (TravelAdapter.java)
Tạo tiếp một Class Java tên là `TravelAdapter` trong thư mục `com.example.camnangdulichvietnam`. File này đóng vai trò cầu nối, lấy dữ liệu từ file JSON đổ vào file giao diện item_travel.xml. <br>

<img width="1918" height="1025" alt="image" src="https://github.com/user-attachments/assets/232ba60a-269a-407f-9f08-a3bcc44cda31" />

### Cập nhật mã nguồn file `MainActivity.java`
Mở file `MainActivity.java` có sẵn ra và cập nhật lại toàn bộ code để thực hiện việc: Đọc file JSON từ `Assets` -> Chạy thuật toán tìm kiếm tuyến tính <br>

<img width="1521" height="824" alt="image" src="https://github.com/user-attachments/assets/3f701cc3-5e12-4b63-8021-1c45bb415d5d" />

---

## Bước 5: Chạy kiểm thử

Bấm vào nút tam giác màu xanh lá cây (Run app) hoặc nhấn tổ hợp phím Shift + F10.

Đợi một lát máy ảo sẽ khởi động lên, tự động cài đặt app và hiển thị danh sách du lịch hoạt động Offline hoàn toàn!

<img width="901" height="971" alt="image" src="https://github.com/user-attachments/assets/e58c956e-3ff3-4663-af0f-08c3490cb043" /> <br>

<img width="912" height="1015" alt="image" src="https://github.com/user-attachments/assets/1db77aa6-41bd-4a55-bf73-f933ed3368b4" />


---


# III. TẠO APP2

---

## Bước 1: Tạo project mới

<img width="1227" height="669" alt="image" src="https://github.com/user-attachments/assets/0d273c66-2992-4f84-a0a9-cd3c0d1784d7" />

### Cấp quyền Internet trong `AndroidManifest.xml` 
Mở file `AndroidManifest.xml` và dán dòng lệnh sau nằm trên thẻ `<application>`

```
<uses-permission android:name="android.permission.INTERNET" />
```

<img width="1534" height="820" alt="image" src="https://github.com/user-attachments/assets/e574ff50-8e65-46aa-8821-d98f9db1dc5c" />


## Bước 2: Tạo các màn hình (Activity)
Mặc định dự án chỉ có sẵn 1 màn hình chính (`MainActivity`). Vì vậy cần tạo thêm 2 màn hình nữa:

- `MainActivity` sẽ đóng vai trò là `Activity 1 (About)`.

- Tạo thêm `MathActivity` đóng vai trò là `Activity 2 (Giải toán)`.

- Tạo thêm `WebActivity` đóng vai trò là `Activity 3 (WebView)`

### Cách tạo: 

- Nhấp chuột phải vào thư mục gói code Java (ví dụ: `com.example.app2`) -> Chọn `New` -> `Activity` -> Chọn `Empty Views Activity`.
- Ô `Activity Name` gõ chữ: `MathActivity` -> Bấm `Finish`.
- Làm lại y hệt bước trên, tạo một `Activity` nữa tên là: `WebActivity` -> Bấm `Finish`. <br>







