BÀI 1: PHÂN TÍCH VÀ KHẢO SÁT TOÀN DIỆN HỆ THỐNG PHÒNG KHÁM RIKKEICARE&nbsp;

&nbsp;

Bước 1: Nhận diện 5 thành phần HTTT và phân biệt Dữ liệu vs Thông tin&nbsp;

1\. Năm thành phần của hệ thống thông tin&nbsp;

&nbsp;

&nbsp;

| Thành phần HTTT | Ví dụ thực tế tại RikkeiCare | Vai trò cơ bản |
| ----- | ----- | ----- |
| **1\. Phần cứng (Hardware)** | Máy tính để bàn tại quầy lễ tân, máy chủ lưu trữ | Thiết bị vật lý để nhập liệu và xử lý |
| **2\. Phần mềm (Software)** | Phần mềm quản lý phòng khám RikkeiCare | Ứng dụng hỗ trợ nghiệp vụ khám chữa bệnh |
| **3\. Dữ liệu (Data)** | Danh sách bệnh nhân, hồ sơ bệnh án điện tử | Dữ liệu lưu trữ phục vụ chẩn đoán |
| **4\. Con người (People)** | **Bác sĩ, nhân viên tiếp tân** | Người trực tiếp sử dụng và vận hành hệ thống |
| **5\. Quy trình (Process)** | **Tiếp nhận bệnh nhân \-\> kiểm tra thông tin \-\> đăng ký khám \-\> phát số thứ tự** | Các bước tiếp nhận và phục vụ bệnh nhân |

&nbsp;

2\. Phân biệt Dữ liệu và Thông tin&nbsp;

&nbsp;

| STT | Nội dung dữ liệu tại phòng khám | Dữ liệu | Thông tin | Lý do phân loại |
| ----- | ----- | ----- | ----- | ----- |
| **1** | 38.5 | v |  | Số liệu thô, chưa có đơn vị và ngữ cảnh |
| **2** | Bệnh nhân Nguyễn Văn A, thân nhiệt 38.5 độ C, đo lúc 08:30 sáng |  | v | Đã có ngữ cảnh đầy đủ: Ai, chỉ số gì, khi nào |
| **3** | 1500000 | v |  | Chuỗi số thô, chưa có đơn vị tiền tệ hay mục đích |
| **4** | Tổng doanh thu tiền khám bệnh trong ngày là 15.000.000 VNĐ |  | v | Đã có ý nghĩa và ngữ cảnh về số tiền, nội dung và thời gian |
| **5** | BN001, Trần Thị B, 45, Nữ | v |  | Dữ liệu ban đầu về mã bệnh nhân, tên, tuổi và giới tính, chưa có phân tích |

&nbsp;

Bước 2: Khảo sát môi trường và xác định Stakeholders&nbsp;

## **1\. Phân loại môi trường**

| Yếu tố khảo sát tại phòng khám | Thuộc loại môi trường | Tầm ảnh hưởng đến hệ thống |
| ----- | ----- | ----- |
| Kỹ năng máy tính của y tá | **Môi trường Nội bộ** | Giao diện phần mềm cần đơn giản, dễ thao tác |
| Quy định bảo mật của Bộ Y tế | **Môi trường Bên ngoài** | Hệ thống bắt buộc phải tuân thủ quy chuẩn pháp lý |
| Hạ tầng mạng nội bộ phòng khám | **Môi trường Nội bộ** | Ảnh hưởng đến tốc độ vận hành phần mềm |
| **Ý kiến phản hồi từ bệnh nhân** | **Môi trường Bên ngoài** | Giúp phòng khám cải thiện chức năng và trải nghiệm người dùng |
| **Ứng dụng đặt khám từ đối thủ** | **Môi trường Bên ngoài** | Tạo áp lực cạnh tranh, yêu cầu hệ thống phải có chức năng tiện lợi và phù hợp nhu cầu |

&nbsp;

2\. Xác định Stakeholder&nbsp;

&nbsp;

&nbsp;

| Nhóm Stakeholder | Vai trò trong dự án | Mối quan tâm lớn nhất đối với phần mềm |
| ----- | ----- | ----- |
| **1\. Bác sĩ khám bệnh** | Người dùng chuyên môn | Tra cứu nhanh lịch sử bệnh án và kê đơn thuốc tiện lợi |
| **2\. Bệnh nhân** | Người thụ hưởng dịch vụ | Đặt lịch khám dễ dàng, không phải chờ đợi lâu |
| **3\. Nhân viên tiếp tân** | **Người dùng trực tiếp, thực hiện tiếp nhận và đăng ký khám cho bệnh nhân** | **Thao tác nhanh, dễ sử dụng, giảm thời gian nhập thông tin và xếp hàng cho bệnh nhân** |

&nbsp;

# **Bước 3: Lựa chọn kỹ thuật thu thập yêu cầu**

## **1\. Chọn kỹ thuật phù hợp**

| STT | Tình huống khảo sát thực tế | Kỹ thuật phù hợp nhất | Lý do lựa chọn ngắn gọn |
| ----- | ----- | ----- | ----- |
| **1** | Tìm hiểu mục tiêu chiến lược và ngân sách từ Giám đốc phòng khám | **Phỏng vấn (Interview)** | Số lượng người ít, cần trao đổi sâu và chi tiết |
| **2** | Thu thập ý kiến từ hơn 1.000 bệnh nhân về sự tiện lợi khi đặt lịch hẹn | **Bảng câu hỏi / Khảo sát (Survey)** | Số lượng người dùng lớn, thu thập nhanh số liệu định lượng |
| **3** | Xem thực tế quy trình tiếp đón và phát số thứ tự tại quầy tiếp tân | **Quan sát (Observation)** | **Giúp BA thấy trực tiếp quy trình thực tế và phát hiện các vấn đề mà người dùng có thể không nói ra** |
| **4** | Nắm rõ quy định về biểu mẫu phiếu khám bệnh và danh mục thuốc | **Nghiên cứu tài liệu (Document Analysis)** | Biểu mẫu và quy chế là tài liệu có sẵn, chuẩn pháp lý |
| **5** | Tìm hiểu mong muốn sắp xếp ca trực của đội ngũ 20 y tá | **Phỏng vấn nhóm (Group Interview)** | **Có thể trao đổi cùng nhiều y tá để thu thập và so sánh nhu cầu, ý kiến về việc sắp xếp ca trực** |

2\. Câu hỏi phỏng vấn mở dành cho Bác sĩ&nbsp;

**“Thầy/Cô đang gặp những khó khăn lớn nhất nào khi tra cứu hồ sơ bệnh án, nhập kết quả chẩn đoán và kê đơn thuốc cho bệnh nhân bằng hệ thống hiện tại?”**

**Bước 4: Phân loại Yêu cầu Chức năng và Phi chức năng**&nbsp;

&nbsp;

| STT | Phát biểu yêu cầu | Phân loại | Mã định danh đề xuất | Câu hỏi cốt lõi giải thích |
| ----- | ----- | ----- | ----- | ----- |
| **1** | **Bệnh nhân có thể đặt lịch khám theo bác sĩ trên website** | **FR** | **FR-01** | **Đây là hành động/tính năng hệ thống LÀM GÌ** |
| **2** | **Thời gian tải trang hiển thị lịch khám không quá 2 giây** | **NFR** | **NFR-01** | **Tiêu chuẩn hiệu năng: hệ thống chạy TỐT NHƯ THẾ NÀO** |
| **3** | **Mật khẩu tài khoản phải được mã hóa bảo mật khi lưu trữ** | **NFR** | **NFR-02** | **Tiêu chuẩn an toàn: bảo mật TỐT NHƯ THẾ NÀO** |
| **4** | **Bác sĩ có thể nhập kết quả chẩn đoán và kê đơn thuốc điện tử** | **FR** | **FR-02** | **Đây là chức năng hệ thống LÀM GÌ** |
| **5** | **Hệ thống phải hoạt động liên tục và ổn định 24/7** | **NFR** | **NFR-03** | **Đây là yêu cầu về tính sẵn sàng và độ ổn định của hệ thống** |

&nbsp;

&nbsp;

# **Bước 5: Đặc tả User Story**

User Story có **3 thành phần chính**:

> **Là ai \-\> Muốn làm gì \-\> Để làm gì**:

| Thành phần User Story | User Story dành cho Bác sĩ |
| ----- | ----- |
| **Là một (Vai trò \- Who):** | Bác sĩ khám bệnh |
| **Tôi muốn (Hành động \- What):** | Xem danh sách bệnh nhân đã đăng ký khám trong ngày |
| **Để (Lợi ích \- Why):** | **Chủ động nắm được lịch khám, chuẩn bị trước thông tin và khám bệnh cho bệnh nhân hiệu quả hơn** |

### **Viết thành câu hoàn chỉnh:**

**“Là một bác sĩ khám bệnh, tôi muốn xem danh sách bệnh nhân đã đăng ký khám trong ngày, để chủ động nắm được lịch khám và chuẩn bị trước thông tin phục vụ việc khám bệnh hiệu quả hơn.”**

&nbsp;