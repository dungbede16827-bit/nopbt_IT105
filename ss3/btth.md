# **BÀI LÀM – PHÂN TÍCH YÊU CẦU HỆ THỐNG QUICKBITE**

## **Nhiệm vụ 1\. Phân tích môi trường hệ thống và Stakeholders**

### **1.1. Ba nhóm môi trường hoạt động**

| Môi trường | Mô tả | Ảnh hưởng đến QuickBite |
| ----- | ----- | ----- |
| **Môi trường kinh doanh** | 15 chi nhánh Cơm Tấm Sài Gòn, quy trình nhận đơn, chế biến, giao hàng, thanh toán | Hệ thống phải hỗ trợ quản lý món ăn, đơn hàng, doanh thu và giao hàng |
| **Môi trường kỹ thuật** | Mobile App, POS, Internet, GPS, bản đồ, máy chủ, cơ sở dữ liệu, thanh toán online | Hệ thống phải hoạt động ổn định, nhanh và kết nối được với các dịch vụ cần thiết |
| **Môi trường con người** | Khách hàng, chủ nhà hàng, nhân viên bếp, tài xế, quản trị viên | Mỗi nhóm có nhu cầu và cách sử dụng hệ thống khác nhau |

### **1.2. Stakeholders**

| Stakeholder | Nguồn thu thập yêu cầu phù hợp | Nhu cầu cốt lõi |
| ----- | ----- | ----- |
| **Khách hàng** | Nguồn con người, nguồn thị trường/đối thủ | Tìm món, đặt món, thanh toán, theo dõi đơn |
| **Chủ nhà hàng** | Nguồn con người, tài liệu, hệ thống hiện tại | Quản lý menu, nhận đơn, theo dõi doanh thu |
| **Tài xế** | Nguồn con người, hệ thống hiện tại, thị trường/đối thủ | Nhận đơn, xem đường đi, cập nhật trạng thái, đối soát thu nhập |
| **Quản trị viên** | Nguồn tài liệu, hệ thống hiện tại, nguồn thị trường | Quản lý người dùng, nhà hàng, tài xế và giám sát toàn hệ thống |

**Mẹo nhớ:** Stakeholder là **những người có liên quan hoặc chịu ảnh hưởng bởi hệ thống**.

&nbsp;

# **Nhiệm vụ 2\. Lựa chọn kỹ thuật thu thập yêu cầu**

| Tình huống | Kỹ thuật phù hợp | Lý do |
| ----- | ----- | ----- |
| Tìm hiểu danh mục món và giá từ hóa đơn giấy cũ | **Phân tích tài liệu** | Hóa đơn là tài liệu có sẵn, có thể lấy thông tin trực tiếp từ đó |
| Tìm hiểu phối hợp giữa đầu bếp và nhân viên soạn đồ | **Quan sát thực tế** | Cần nhìn trực tiếp quy trình đang diễn ra để hiểu chính xác |
| Tìm hiểu trăn trở về doanh thu của chủ nhà hàng | **Phỏng vấn chuyên sâu** | Chủ nhà hàng có nhiều kinh nghiệm và vấn đề cần trao đổi chi tiết |
| Thu thập ý kiến về cước phí của 1.000 tài xế | **Khảo sát diện rộng** | Số lượng người lớn và phân bố rộng nên khảo sát giúp thu thập dữ liệu nhanh |

### **Tại sao không dùng phỏng vấn chuyên sâu với 1.000 tài xế?**

Vì phỏng vấn chuyên sâu tốn nhiều thời gian, nhân lực và chi phí. Nếu phỏng vấn từng người thì rất khó thực hiện với 1.000 tài xế.

Thay vào đó, khảo sát diện rộng bằng bảng hỏi giúp thu thập ý kiến của nhiều người trong thời gian ngắn và dễ tổng hợp, thống kê.

&nbsp;

# **Nhiệm vụ 3\. Phân loại FR và NFR**

### **FR – Functional Requirement**

Là yêu cầu chức năng, nói về hệ thống phải làm được gì.

### **NFR – Non-Functional Requirement**

Là **yêu cầu phi chức năng**, nói về **hệ thống phải hoạt động như thế nào**, ví dụ tốc độ, bảo mật, khả năng chịu tải.

| Yêu cầu | Loại | Giải thích |
| ----- | ----- | ----- |
| Khách hàng gõ từ khóa để tìm kiếm món ăn | **FR** | Đây là một chức năng của hệ thống |
| Hiển thị kết quả tìm kiếm dưới 1.5 giây | **NFR** | Quy định về hiệu năng |
| Chủ nhà hàng xác nhận tiếp nhận đơn trên POS | **FR** | Đây là chức năng |
| Chịu tải 10.000 người dùng cùng lúc | **NFR** | Quy định về khả năng chịu tải |
| Thanh toán thẻ được mã hóa an toàn | **NFR** | Quy định về bảo mật |
| Tài xế bật/tắt chế độ sẵn sàng nhận đơn | **FR** | Đây là chức năng |

### **NFR và chỉ số đo lường**

Có thể chuẩn hóa thành:

**1\. Hiệu năng**

> Hệ thống phải trả về kết quả tìm kiếm trong ≤ 1,5 giây đối với ít nhất 95% số lượt tìm kiếm.

**2\. Khả năng chịu tải**

> Hệ thống phải hỗ trợ ít nhất 10.000 người dùng truy cập đồng thời mà không làm hệ thống ngừng hoạt động.

**3\. Bảo mật**

> Dữ liệu giao dịch thanh toán phải được truyền qua kết nối HTTPS sử dụng TLS 1.2 trở lên.

# **Nhiệm vụ 4\. Xây dựng User Story**

Công thức:

> **Là một \[Vai trò\], Tôi muốn \[Hành động\], Để \[Giá trị/Mục tiêu\].**

##  **Nhóm Khách hàng**

User Story 1:

> Là một Khách hàng, tôi muốn tìm kiếm món ăn bằng từ khóa, để có thể nhanh chóng tìm được món mình muốn đặt.

User Story 2:

> Là một Khách hàng, tôi muốn thanh toán đơn hàng trực tuyến, để có thể hoàn tất việc đặt món một cách thuận tiện.

&nbsp;

## **Nhóm Chủ nhà hàng**

User Story 3:

> Là một Chủ nhà hàng, tôi muốn xác nhận tiếp nhận đơn hàng trên màn hình POS, để nhà hàng có thể bắt đầu chuẩn bị món cho khách.

User Story 4:

> Là một Chủ nhà hàng, tôi muốn quản lý danh sách món ăn và giá bán, để đảm bảo thông tin menu luôn chính xác.

&nbsp;

##  **Nhóm Tài xế**

User Story 5:

> Là một Tài xế, tôi muốn bật/tắt chế độ sẵn sàng nhận đơn, để chủ động quyết định thời điểm mình muốn nhận đơn giao hàng.

User Story 6:

> Là một Tài xế, tôi muốn xem thông tin và vị trí giao hàng trên bản đồ, để có thể tìm đường và giao đơn cho khách đúng địa điểm.

&nbsp;

Điều này giúp:

* SA hiểu đúng nhu cầu.  
* Developer biết mình đang xây dựng chức năng để làm gì.  
* Tester biết mục tiêu cần kiểm tra.  
* Khách hàng dễ hiểu tài liệu hơn.  
* Tránh xây dựng chức năng có nhưng không mang lại giá trị thực tế.

&nbsp;