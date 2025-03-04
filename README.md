# BlogAniRu_BE
Backend services Blog AniRu.

## Document ver.1

mô tả:<br>
Trang blog AniRu chuyên đăng các bài viết về anime, cho phép người dùng bình luận, thả cảm xúc, trả lời bình luận của người khác và tham gia các vòng vote cho nhân vật yêu thích. Blog còn tích hợp API MyAnimeList để cung cấp thông tin các bộ anime.

---

## 1. Thu Thập Yêu Cầu & Phân Tích

### 1.1. Họp Khởi Đầu & Phỏng Vấn Stakeholders
- **Xác định đối tượng người dùng:**
  - **Admin/Chủ blog:** Quản lý bài viết, vòng vote, bình luận, cập nhật thông tin nhân vật.
  - **Người dùng đăng ký:** Đăng nhập, bình luận, thả cảm xúc, tham gia vote.
  - **Khách (không đăng nhập):** Xem bài viết và thông tin cơ bản, đăng ký để tương tác sâu hơn.

### 1.2. Thu Thập Yêu Cầu Chức Năng
- **Blog & Bài Viết:**
  - CRUD bài viết (tạo, đọc, cập nhật, xóa).
  - Hỗ trợ định dạng (Markdown, Rich Text (nếu có) ).
- **Bình Luận & Cảm Xúc:**
  - Cho phép bình luận và trả lời bình luận.
  - Thả cảm xúc (like, love, haha, …).
- **Hệ Thống Vote:**
  - Tạo và quản lý vòng vote theo mùa.
  - Người dùng vote cho nhân vật yêu thích theo đợt vote.
- **Quản Lý Thông Tin Nhân Vật:**
  - Lưu trữ và hiển thị thông tin chi tiết của nhân vật anime.
  - Cho phép admin cập nhật thông tin.
- **Tích Hợp API MyAnimeList:**
  - Kết nối với API để lấy thông tin các bộ anime.
  - Xử lý dữ liệu và hiển thị.

### 1.3. Yêu Cầu Phi Chức Năng
- **Bảo mật:** Xác thực, phân quyền, bảo vệ API.
- **Hiệu năng:** Tối ưu truy vấn, đồng bộ dữ liệu vote.
- **Khả năng mở rộng:** gắn thẻ bài viết, người dùng đăng ký có thể viết bài trên blog, thích hợp api nhân vật cho chủ blog lấy thông tin nhanh, tạo API public cung cấp api cho các bên thứ 3.
- **Tính ổn định:** Backup, logging.
- **Responsive Design:** Tương thích trên mobile, tablet và desktop.

### 1.4. Tài Liệu & Use Case
- **Use Case Diagram:** Mô phỏng tương tác chính giữa các đối tượng.


- **User Stories:** Định nghĩa kịch bản sử dụng chi tiết.


- **Yêu cầu kỹ thuật:** Bảo mật, đồng bộ, tích hợp API.


---

## 2. Thiết Kế Kiến Trúc Hệ Thống

### 2.1. Lựa Chọn Stack Công Nghệ
- **Frontend:**
  - JavaScript Framework: `Angular`.
  - CSS Framework: `CSS`, `Bootstrap`, `SCSS`.
- **Backend:**
  - Ngôn ngữ: `C#`, `Java`.
  - API: `RESTful` hoặc `GraphQL`.
  - Framework: `Spring Boot MVC` hoặc `ASP.NET (MVC)`
- **Cơ Sở Dữ Liệu:**
  - SQL:  `Microsoft SQL Server`.
  - NoSQL: `Mongodb`.
- **Tích hợp API bên ngoài:**  
  - Kết nối với MyAnimeList theo chuẩn REST, và tuân thủ quy định của bên cung cấp API đặc ra.

### 2.2. Kiến Trúc Hệ Thống
- **3-Tier Architecture:**
  - **Presentation Layer (Frontend):** Giao diện người dùng.
  - **Application Layer (Backend):** Xử lý nghiệp vụ và API.
  - **Data Layer (Database):** Lưu trữ dữ liệu.
- **Microservices:**
  - chia nhỏ các module dựa trên 6 module chính: <br>
        
        - bài viết
        - bình luận
        - vote
        - nhân vật
        - tích hợp API ngoài
        - tài khoản

- **Sơ đồ Kiến Trúc:**
  - Component Diagram, Deployment Diagram.
  - Sơ đồ luồng dữ liệu giữa các module và MyAnimeList API.

---

## 3. Thiết Kế Giao Diện Người Dùng (UI/UX)

### 3.1. Wireframe & Prototype
- **Wireframe:**

---
---

- **Prototype:**
  - Sử dụng Figma, Adobe PS, hoặc Sketch để tạo mẫu tương tác.

---
---

- **Responsive Design:**  
  - Thiết kế tương thích cho desktop, tablet và mobile.

---
---

### 3.2. UX/UI Style Guide
- **Phong cách thiết kế:**  
  
  - Màu sắc, typography, iconography phù hợp với chủ đề anime.
  - phong cách hiện đại, tối giản, chia lưới, màu sắc chủ đạo Rusty red,  Cherry blossom pink

- **Flow người dùng:**  
  - Tối ưu quy trình đăng nhập, đăng bài, bình luận và tham gia vote.

---

## 4. Thiết Kế Cơ Sở Dữ Liệu

### 4.1. Xác Định Các Thực Thể Chính


### 4.2. ER Diagram


---

## 5. Thiết Kế API và Tích Hợp

### 5.1. API Nội Bộ

### 5.2. Thiết Kế Endpoint và Tài Liệu API
- **Endpoint:**

- **Documentation:**  
  - Sử dụng Swagger, Postman.

---

## 6. Kiến Trúc Phần Mềm & Phân Chia Module

### 6.1. Module Chính
- **Module Blog:** 
Quản lý bài viết, định dạng nội dung.
- **Module Bình Luận & Cảm Xúc:** 
Xử lý bình luận, phản hồi và cảm xúc.
- **Module Vote:** 
Quản lý vòng vote theo mùa.
- **Module Nhân Vật:** 
Quản lý thông tin chi tiết nhân vật.
- **Module Tích Hợp API:** 
Giao tiếp với MyAnimeList, xử lý dữ liệu.
- **Module Quản Trị:** 
Giao diện admin cho quản lý tổng thể.
-  **Module Tài khoản:**
Quản lý phân quyền người dùng.

### 6.2. Thiết Kế Lớp & Flow Nghiệp Vụ
- **Flow nghiệp vụ:**
  - Quy trình đăng bài:

  - Quy trình bình luận:

  - Quy trình vote nhân vật:

  - Quy trình mở vote:

  - Quy trình công bố kế quả vote:

- **Mô hình:**  
  - MVC: Tách biệt rõ ràng giữa logic nghiệp vụ, giao diện và dữ liệu.

---

## 7. Lập Kế Hoạch Phát Triển & Quản Lý Dự Án
### 7.2. Quản Lý Source Code và Code Review
- **Git:**  
  - Tạo repository, quy trình commit, chia brand.

---

## 8. Kiểm Thử & Đảm Bảo Chất Lượng

### 8.1. Kiểm Thử Đơn Vị & Tích Hợp
- **Unit Test:**  
  - Viết test cho chức năng backend và frontend.

- **Integration Test:**  
  - Kiểm tra tương tác giữa các module (API, DB).

### 8.2. Đánh Giá Hiệu Năng
- **Load Test:**  
  - Đảm bảo hệ thống đáp ứng tốt dưới tải cao.
---

## 9. Triển Khai & Vận Hành

### 9.1. Hạ Tầng & Hosting

- **Lựa chọn Hosting:** Somee.

- **Cấu hình Server:**  

### 9.2. Deploy
- **Quy trình Deploy:**  

- **Backup & Recovery:** 

### 9.3. backup & Logging

---

## 10. Tài Liệu & Hỗ Trợ Bảo Trì

### 10.1. Tài Liệu Hệ Thống
- **Documentation:**  
  - Tài liệu thiết kế hệ thống, kiến trúc, API và hướng dẫn sử dụng.
  - README, hướng dẫn cài đặt.

### 10.2. Hỗ Trợ Bảo Trì
---

*Ghi chú: Các phần chi tiết có thể được mở rộng dựa trên feedback và đội ngũ phát triển.*
