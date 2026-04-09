# BẢNG PHÂN CÔNG NHIỆM VỤ DỰ ÁN: HỆ THỐNG "EDU-PATH"

| STT | Vai trò                    | Thành viên | Nhiệm vụ chi tiết | File phụ trách chính                                                |
| :-- |:---------------------------| :--- | :--- |:--------------------------------------------------------------------|
| **01** | **Nhóm trưởng (Leader)**   | **[Tên 01]** | **Cấu hình dự án:** Setup Gradle, Spring MVC, Thymeleaf, cấu hình ViewResolver, khởi tạo Git Repo. | `WebConfig.java`, `WebAppInitializer.java`, phân tích DA, phân công |
| **02** | **Frontend (Layout)**      | [Tên 02] | **Xây dựng khung Layout:** Tạo Header, Footer, Navbar; cấu hình `Thymeleaf Layout Dialect`. | `main-layout.html`, `base-style.css`                                |
| **03** | **Frontend (List)**        | [Tên 03] | **Giao diện danh sách:** Thiết kế Grid/Table hiển thị khóa học, thanh Search và các bộ lọc Level/Price. | `course/list.html`                                                  |
| **04** | **Frontend (Detail/Form)** | [Tên 04] | **Giao diện chi tiết & Form:** Thiết kế trang xem lộ trình và Form chỉnh sửa (binding dữ liệu `th:object`). | `detail.html`, `edit.html`                                          |
| **05** | **Backend (Model)**        | [Tên 05] | **Thiết kế dữ liệu:** Xây dựng Class `Course` và tạo **Mock Data** (List tĩnh ít nhất 5 khóa học). | `Course.java`, `CourseRepository.java`                              |
| **06** | **Backend (Service)**      | [Tên 06] | **Logic nghiệp vụ:** Viết các hàm Search, Filter theo Level/Price và xử lý logic check `isFull` (hết chỗ). | `CourseService.java`                                                |
| **07** | **Controller (Read)**      | [Tên 07] | **Điều phối hiển thị:** Xử lý `@GetMapping` cho danh sách, tìm kiếm và chi tiết qua `@PathVariable`. | `CourseController.java`                                             |
| **08** | **Controller (Write)**     | [Tên 08] | **Điều phối hành động:** Xử lý `@PostMapping` cho Edit (PRG Pattern) và xóa khóa học. | `CourseController.java`                                             |
| **09** | **Logic & Validation**     | [Tên 09] | **Ràng buộc nghiệp vụ:** Kiểm tra điều kiện xóa (studentCount = 0) và format tiền tệ VNĐ bằng `#numbers`. | `CourseController.java`, `list.html`                                |
| **10** | **Bootstrap**              | [Tên 10] | **Hoàn thiện UI/UX:** Sử dụng **Bootstrap Alerts** cho thông báo thành công/lỗi, **Badges** cho trạng thái "Hết chỗ", tối ưu Responsive . | tất cả file html                                                    |

---

## QUY TRÌNH PHỐI HỢP (WORKFLOW)

1.  **Giai đoạn 1 (Setup):** Nhóm trưởng (01) và Model (05) hoàn thành cấu hình dự án và dữ liệu mẫu.
2.  **Giai đoạn 2 (Giao diện):** Nhóm Layout (02) gửi file `main-layout.html` để nhóm 03 và 04 nhúng nội dung.
3.  **Giai đoạn 3 (Logic):** Nhóm Service (06) và Controller (07, 08) kết nối dữ liệu từ Repository lên các trang HTML.
4.  **Giai đoạn 4 (Kiểm thử):** Nhóm 09 và 10 kiểm tra toàn bộ luồng PRG Pattern, thông báo lỗi và căn chỉnh CSS cuối cùng.

---

## Cấu Trúc Dự Án

```
Session06MiniProject/
├── src/
│   ├── main/
│   │   ├── java/org/example/minipj
│   │   │   ├── config/
│   │   │   │   ├── WebConfig.java              # Cấu hình Spring MVC & Thymeleaf
│   │   │   │   └── WebAppInitializer.java       # Khởi tạo ứng dụng web
│   │   │   ├── controller/
│   │   │   │   └── CourseController.java       # Controller xử lý request
│   │   │   ├── model/
│   │   │   │   └── Course.java                 # Model Course
│   │   │   ├── repository/
│   │   │   │   └── CourseRepository.java       # Repository & Mock Data
│   │   │   └── service/
│   │   │       └── CourseService.java          # Service layer
│   │   ├── resources/
│   │   └── webapp/
│   │       └── WEB-INF/
│   │           ├── templates/
│   │           │   ├── layout/
│   │           │   │   └── main-layout.html   # Layout chính
│   │           │   └── course/
│   │           │       ├── list.html           # Danh sách khóa học
│   │           │       ├── detail.html         # Chi tiết khóa học
│   │           │       └── edit.html           # Form chỉnh sửa
│   │           └── web.xml                    # Cấu hình web
│   └── test/
│       ├── java/
│       └── resources/
├── gradle/
│   └── wrapper/
│       ├── gradle-wrapper.jar
│       └── gradle-wrapper.properties
├── build.gradle                    # Cấu hình Gradle
├── settings.gradle                 # Cài đặt Gradle
├── gradlew                         # Gradle wrapper (Unix)
├── gradlew.bat                     # Gradle wrapper (Windows)
├── .gitignore                      # Git ignore file
├── srs.txt                         # Tài liệu đặc tả yêu cầu
└── README.md                       # Tài liệu dự án này
```
