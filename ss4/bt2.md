# **BÀI 2: PHÂN TÍCH VÀ KHẢO SÁT TOÀN DIỆN HỆ THỐNG NGÂN HÀNG SỐ RIKKEIBANK**

## **Bước 1: Nhận diện 5 thành phần HTTT và phân biệt Dữ liệu vs Thông tin**

&nbsp;

### **1\. Năm thành phần HTTT**

| Thành phần HTTT | Ví dụ thực tế tại RikkeiBank | Vai trò cơ bản |
| ----- | ----- | ----- |
| **1\. Phần cứng (Hardware)** | Máy chủ xử lý giao dịch Core Banking, máy ATM/POS | Hạ tầng vật lý xử lý và giao tiếp tài chính |
| **2\. Phần mềm (Software)** | Ứng dụng RikkeiBank Mobile, hệ thống Internet Banking | Giao diện và logic thực hiện giao dịch số |
| **3\. Dữ liệu (Data)** | Số dư tài khoản, lịch sử biến động số dư | Dữ liệu tài chính cốt lõi |
| **4\. Con người (People)** | **Khách hàng cá nhân, nhân viên ngân hàng** | Tác nhân trực tiếp tương tác với hệ thống |
| **5\. Quy trình (Process)** | **Đăng nhập \-\> xác thực \-\> nhập thông tin người nhận \-\> nhập số tiền \-\> xác nhận \-\> OTP/sinh trắc học \-\> hoàn tất chuyển khoản** | Trình tự các bước xác thực và chuyển khoản |

&nbsp;

### **2\. Phân biệt Dữ liệu và Thông tin**

| STT | Nội dung dữ liệu tại RikkeiBank | Dữ liệu | Thông tin | Lý do phân loại |
| ----- | ----- | ----- | ----- | ----- |
| **1** | 50000000 | v |  | Chuỗi số thô, chưa rõ là tiền gửi, tiền vay hay hạn mức |
| **2** | Khách hàng Trần Văn C chuyển 5.000.000 VNĐ lúc 10:15 ngày 15/08 |  | v | Đầy đủ ngữ cảnh giao dịch: Ai, số tiền, thời gian |
| **3** | 0987654321 | v |  | Chuỗi số thô, có thể là số điện thoại hoặc số tài khoản |
| **4** | Tổng số dư tiết kiệm trực tuyến của chi nhánh đạt 200 tỷ VNĐ trong tháng 8 |  | v | **Dữ liệu đã được tổng hợp, có đơn vị, thời gian và ý nghĩa rõ ràng** |
| **5** | TK101, Nguyễn Thị D, Active, Gold | v |  | **Dữ liệu thô về tài khoản, khách hàng, trạng thái và hạng thành viên, chưa được phân tích** |

# **Bước 2: Khảo sát môi trường và xác định Stakeholders**

## **1\. Phân loại môi trường**

| Yếu tố khảo sát tại RikkeiBank | Thuộc loại môi trường | Tầm ảnh hưởng đến hệ thống |
| ----- | ----- | ----- |
| Năng lực bảo mật của đội ngũ IT | **Môi trường Nội bộ** | Quyết định khả năng phòng chống tấn công mạng |
| Thông tư an toàn thông tin Ngân hàng Nhà nước | **Môi trường Bên ngoài** | Quy định bắt buộc về xác thực sinh trắc học |
| Hệ thống đường truyền liên ngân hàng Napas | **Môi trường Bên ngoài** | Ảnh hưởng trực tiếp đến tốc độ chuyển tiền liên ngân hàng |
| **Thói quen sử dụng điện thoại của người cao tuổi** | **Môi trường Bên ngoài** | **Ảnh hưởng đến thiết kế giao diện, cần đơn giản, chữ dễ đọc và thao tác dễ dàng** |
| **Chính sách lãi suất của các ngân hàng đối thủ** | **Môi trường Bên ngoài** | **Tạo áp lực cạnh tranh, ảnh hưởng đến việc thiết kế chức năng gửi tiết kiệm và chính sách sản phẩm** |

## **2\. Xác định Stakeholders**

| Nhóm Stakeholder | Vai trò trong dự án | Mối quan tâm lớn nhất đối với phần mềm |
| ----- | ----- | ----- |
| **1\. Khách hàng cá nhân** | Người dùng dịch vụ cuối | Chuyển tiền nhanh chóng, an toàn, giao diện mượt mà |
| **2\. Chuyên viên An ninh mạng** | Giám sát bảo mật | Hệ thống chống rò rỉ mã OTP và mã hóa dữ liệu đầu cuối |
| **3\. Giao dịch viên tại quầy** | **Người dùng nghiệp vụ, hỗ trợ và xử lý giao dịch cho khách hàng** | **Tra cứu thông tin nhanh, nhập giao dịch chính xác và hệ thống hoạt động ổn định** |

&nbsp;

# **Bước 3: Lựa chọn kỹ thuật thu thập yêu cầu**

## **1\. Chọn kỹ thuật phù hợp**

| STT | Tình huống khảo sát tại RikkeiBank | Kỹ thuật phù hợp nhất | Lý do lựa chọn ngắn gọn |
| ----- | ----- | ----- | ----- |
| **1** | Khảo sát nhu cầu giao dịch của 50.000 khách hàng trẻ Gen Z | **Bảng câu hỏi / Khảo sát (Survey)** | Quy mô người dùng cực lớn, thu thập nhanh số liệu định lượng |
| **2** | Làm rõ quy định đối soát và hạn mức chuyển khoản với Giám đốc rủi ro | **Phỏng vấn (Interview)** | Chuyên gia cấp cao, cần trao đổi sâu về chính sách nghiệp vụ |
| **3** | Xem thực tế thao tác nhập lệnh chuyển tiền quốc tế của giao dịch viên | **Quan sát (Observation)** | **Giúp BA trực tiếp thấy các bước thao tác thực tế và phát hiện vấn đề trong quy trình** |
| **4** | Đọc các văn bản hướng dẫn tiêu chuẩn bảo mật thanh toán PCI-DSS | **Nghiên cứu tài liệu (Document Analysis)** | Tiêu chuẩn quốc tế dạng văn bản quy chuẩn có sẵn |
| **5** | Lấy ý kiến đóng góp của nhóm 15 chuyên viên chăm sóc khách hàng VIP | **Phỏng vấn nhóm (Group Interview)** | **Có thể thu thập nhiều ý kiến cùng lúc và trao đổi trực tiếp về nhu cầu của khách hàng VIP** |

## **2\. Câu hỏi trắc nghiệm khảo sát khách hàng**

**Câu hỏi:**  
 "Khi chuyển tiền trên ứng dụng RikkeiBank, yếu tố nào quan trọng nhất với bạn?"

**A.** Tốc độ chuyển tiền nhanh

**B.** Tính bảo mật và an toàn

**C.** Giao diện đơn giản, dễ sử dụng

**D.** Phí chuyển tiền thấp

&nbsp;

# **Bước 4: Phân loại Yêu cầu Chức năng và Phi chức năng**

| STT | Phát biểu yêu cầu | Phân loại | Mã định danh đề xuất | Câu hỏi cốt lõi giải thích |
| ----- | ----- | ----- | ----- | ----- |
| **1** | Khách hàng có thể quét mã QR để thanh toán hóa đơn | **FR** | **FR-01** | Hành động hệ thống cung cấp (**LÀM GÌ**) |
| **2** | Giao dịch chuyển tiền phải hoàn tất trong vòng dưới 3 giây | **NFR** | **NFR-01** | Tiêu chuẩn tốc độ xử lý (**TỐT NHƯ THẾ NÀO**) |
| **3** | Mọi giao dịch trên 10 triệu VNĐ bắt buộc xác thực sinh trắc học khuôn mặt | **NFR** | **NFR-02** | Tiêu chuẩn an ninh và bảo mật (**TỐT NHƯ THẾ NÀO**) |
| **4** | Khách hàng có thể mở sổ tiết kiệm trực tuyến ngay trên ứng dụng | **FR** | **FR-02** | **Đây là một chức năng mà hệ thống phải cung cấp cho khách hàng** |
| **5** | Hệ thống Core Banking chịu tải được 10.000 giao dịch đồng thời mỗi giây | **NFR** | **NFR-03** | **Đây là yêu cầu về hiệu năng và khả năng chịu tải của hệ thống** |

&nbsp;

&nbsp;

&nbsp;

# **Bước 5: Đặc tả User Story**

User Story gồm 3 phần:

> **Who \-\> What \-\> Why**  
>  **Là ai \-\> Muốn làm gì \-\> Để làm gì**

| Thành phần User Story | User Story dành cho Khách hàng |
| ----- | ----- |
| **Là một (Vai trò \- Who):** | Khách hàng sử dụng ứng dụng RikkeiBank |
| **Tôi muốn (Hành động \- What):** | Lưu danh bạ người thụ hưởng thường xuyên chuyển tiền |
| **Để (Lợi ích \- Why):** | **Tiết kiệm thời gian, không phải nhập lại thông tin người nhận mỗi lần chuyển tiền** |

### **User Story hoàn chỉnh**

&nbsp;

**Là một khách hàng sử dụng ứng dụng RikkeiBank, tôi muốn lưu danh bạ những người thụ hưởng thường xuyên chuyển tiền, để tiết kiệm thời gian và không phải nhập lại thông tin người nhận mỗi lần chuyển tiền.**

&nbsp;