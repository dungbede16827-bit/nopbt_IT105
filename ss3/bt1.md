# **BÀI LÀM – KHO DƯỢC RIKKEICARE**

## **Phần 1\. Bóc tách 3 lỗi sai nghiệp vụ**

### **Lỗi 1 – Phân loại môi trường**

**Nhận định sai:**

> “Thông tư quản lý thuốc gây nghiện của Bộ Y tế là Môi trường Nội bộ của RikkeiCare.”

**Nguyên nhân sai:**  
Thông tư và quy định của Bộ Y tế là yếu tố bên ngoài tổ chức, RikkeiCare không thể trực tiếp kiểm soát hay thay đổi.

**Hậu quả nếu không sửa:**  
Hệ thống có thể được thiết kế không đúng quy định pháp luật, dẫn đến vi phạm quy định quản lý thuốc và bị xử phạt.

**Nhớ:**Luật, thông tư, quy định Nhà nước → Môi trường bên ngoài.

### **Lỗi 2 – Đánh giá sai quy trình AS-IS**

**Nhận định sai:**

> “Kho dược vận hành hoàn hảo... dược sĩ luôn nhớ chính xác hạn dùng...”

**Nguyên nhân sai:**  
Nhận định chỉ dựa vào giả định/chủ quan của nhân viên, không phản ánh đúng thực tế hiện trường; thực tế đã có khiếu nại bệnh nhân nhận thuốc quá hạn.

**Hậu quả nếu không sửa:**  
Bỏ qua rủi ro xuất thuốc hết hạn, có thể gây ảnh hưởng đến sức khỏe bệnh nhân và uy tín bệnh viện.

**Nhớ:**Khảo sát AS-IS phải dựa trên thực tế, không dựa vào suy đoán.

### **Lỗi 3 – Phân loại FR/NFR**

**Nhận định sai:**

> “Hệ thống phải có chức năng tự động khóa các lô thuốc hết hạn là Yêu cầu Phi chức năng.”

**Nguyên nhân sai:**  
“Tự động khóa lô thuốc hết hạn” là một hành động/chức năng cụ thể mà hệ thống phải thực hiện nên đây là FR.

**Hậu quả nếu không sửa:**  
Đội phát triển có thể hiểu sai yêu cầu và không xây dựng đúng chức năng kiểm soát thuốc hết hạn, làm tăng nguy cơ xuất nhầm thuốc.

**Nhớ:**Có hành động như khóa, thêm, sửa, xóa, tìm kiếm, xác nhận → thường là FR.

# **Phần 2\. Hoàn thiện bảng**

&nbsp;

| Yếu tố khảo sát | Thuộc loại môi trường | Tác động trực tiếp đến phần mềm |
| ----- | ----- | ----- |
| Kỹ năng vi tính & thói quen ghi sổ của Dược sĩ | Môi trường Nội bộ | Cần giao diện tối giản, hỗ trợ quét mã vạch |
| Thông tư & Chế tài xử phạt của Bộ Y tế | Môi trường Bên ngoài | Bắt buộc khóa tự động thuốc hết hạn, lưu audit log |
| Hạ tầng máy chủ và mạng LAN nội bộ bệnh viện | Môi trường Nội bộ | Hệ thống phải kiểm soát xuất thuốc hết hạn; với thuốc RESTRICTED phải yêu cầu xác nhận kép từ Dược sĩ Trưởng khoa Dược trước khi xuất kho. |

### **Điểm bẫy RESTRICTED**

Thuốc RESTRICTED (hướng thần, gây nghiện) không được phép để một nhân viên tự ý xuất kho.

Luồng đúng:

> Nhân viên tạo yêu cầu xuất thuốc  
> &nbsp;  
>  Hệ thống kiểm tra thuốc \= RESTRICTED  
> &nbsp;  
>  Yêu cầu xác nhận  
> &nbsp;  
>  Dược sĩ Trưởng khoa Dược xác nhận  
> &nbsp;  
>  Đủ xác nhận  cho phép xuất kho

Có thể gọi cơ chế này là:

> Dual-Authorization \= Xác nhận kép

# **Phần 3\. Viết FR và NFR**

## **1\. Yêu cầu chức năng – FR**

> **FR:** Hệ thống phải tự động khóa các lô thuốc đã hết hạn sử dụng và không cho phép xuất kho.

Đây là FR vì hệ thống phải thực hiện một hành động cụ thể: kiểm tra và khóa lô thuốc.

Có thể viết thêm FR cho bẫy RESTRICTED:

> **FR:** Khi xuất thuốc thuộc nhóm RESTRICTED, hệ thống phải yêu cầu xác nhận kép, trong đó có xác nhận của Dược sĩ Trưởng khoa Dược trước khi cho phép xuất kho.

## **2\. Yêu cầu phi chức năng – NFR**

> **NFR:** Hệ thống phải đảm bảo 95% các thao tác tra cứu thông tin thuốc có thời gian phản hồi không quá 2 giây trong điều kiện có tối đa 500 người dùng đồng thời.

Đây là NFR vì nó quy định về hiệu năng/chất lượng hoạt động của hệ thống và có chỉ số đo lường cụ thể.

# **Chốt bài để đi vấn đáp**

### **Câu 1: Thông tư Bộ Y tế thuộc môi trường nào?**

> Môi trường bên ngoài, vì đây là yếu tố pháp luật bên ngoài tổ chức và RikkeiCare không thể kiểm soát trực tiếp.

### **Câu 2: Tại sao “khóa thuốc hết hạn” là FR?**

> Vì đây là một chức năng cụ thể mà hệ thống phải thực hiện, tức là hệ thống phải kiểm tra và khóa lô thuốc hết hạn.

### **Câu 3: RESTRICTED phải xử lý thế nào?**

> Thuốc RESTRICTED không được để một nhân viên tự xuất kho mà phải có Dual-Authorization, tức là xác nhận kép, trong đó có Dược sĩ Trưởng khoa Dược.

### **Câu 4: FR và NFR khác nhau thế nào?**

> FR trả lời hệ thống phải làm gì, còn NFR trả lời hệ thống phải hoạt động như thế nào, ví dụ nhanh, bảo m\`		ật, ổn định và chịu tải.

### **Câu 5: Sai lầm lớn nhất của khảo sát AS-IS là gì?**

> Không được giả định quy trình đang hoàn hảo. System Analyst phải dựa vào hiện trạng thực tế, bằng chứng và các vấn đề thực tế đã xảy ra để xác định yêu cầu và rủi ro.

&nbsp;

&nbsp;