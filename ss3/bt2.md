## **Phần 1 – Thanh lọc danh sách Stakeholder**

| Đối tượng | Phân loại | Giải thích |
| ----- | ----- | ----- |
| Bác sĩ điều trị trực tiếp | Stakeholder | Là người trực tiếp sử dụng EHR và chịu ảnh hưởng bởi hệ thống. |
| Máy chủ cơ sở dữ liệu Oracle | Thực thể kỹ thuật | Là phần cứng/hệ thống kỹ thuật, không phải con người hay tổ chức. |
| Ban Giám đốc Bệnh viện RikkeiCare | Stakeholder | Có quyền quyết định, quản lý và chịu trách nhiệm về dự án. |
| Bệnh nhân và Thân nhân người bệnh | Stakeholder | Là đối tượng được phục vụ và chịu ảnh hưởng trực tiếp từ hệ thống EHR. |
| Thanh tra Pháp chế & Bảo mật Y tế (Bộ Y tế) | Stakeholder | Có vai trò kiểm tra, giám sát việc tuân thủ pháp luật và bảo mật dữ liệu y tế. |

Kết luận: Có 4 nhóm Stakeholder thực thụ và 1 thực thể kỹ thuật cần loại bỏ là Máy chủ cơ sở dữ liệu Oracle.

## **Phần 2 – Ma trận Stakeholder 4 ô**

| Nhóm chiến lược | Tiêu chí | Stakeholder | Hành động tương tác chủ chốt |
| ----- | ----- | ----- | ----- |
| Quản lý chặt chẽ (Manage Closely) | Quyền lực Cao \- Quan tâm Cao | Ban Giám đốc Bệnh viện | Báo cáo tiến độ trực tiếp, tham gia mọi quyết định lớn |
| Giữ hài lòng (Keep Satisfied) | Quyền lực Cao \- Quan tâm Thấp | Thanh tra Pháp chế & Bảo mật Y tế (Bộ Y tế) | Đảm bảo tuân thủ pháp luật, cung cấp báo cáo và thông tin khi cần |
| Giữ thông tin (Keep Informed) | Quyền lực Thấp \- Quan tâm Cao | Bác sĩ điều trị trực tiếp | Cập nhật thường xuyên, lấy ý kiến về quy trình sử dụng và quyền truy cập |
| Giám sát tối thiểu (Monitor) | Quyền lực Thấp \- Quan tâm Thấp | Bệnh nhân và Thân nhân | Thông báo định kỳ qua email/app, không cần họp riêng |

### **Giải thích ngắn**

* Ban Giám đốc: quyền lực và mức độ quan tâm đều cao phải quản lý chặt chẽ.  
* Thanh tra Pháp chế & Bảo mật: có quyền lực kiểm tra và yêu cầu tuân thủ nhưng không tham gia sử dụng hệ thống hằng ngày  giữ hài lòng.  
* Bác sĩ: sử dụng EHR thường xuyên, rất quan tâm đến tính tiện lợi và quyền truy cập nhưng quyền quyết định cấp tổ chức thấp hơn Ban Giám đốc  giữ thông tin.  
* Bệnh nhân/thân nhân: trong phạm vi quản trị dự án, quyền lực thấp và không tham gia quản lý dự án thường xuyên  giám sát tối thiểu.

&nbsp;

## **Phần 3 – Giải quyết xung đột Bác sĩ và Pháp chế**

Giải pháp: Thiết kế cơ chế phân quyền theo vai trò và Consent: bác sĩ chỉ được xem thông tin nhạy cảm sau khi bệnh nhân xác nhận bằng mã xác thực; riêng trường hợp cấp cứu, bệnh nhân hôn mê không thể xác nhận, hệ thống cho phép Emergency Override để bác sĩ được truy cập thông tin cần thiết, đồng thời ghi vết đầy đủ vào nhật ký kiểm toán (Audit Log) để phục vụ kiểm tra sau này.

&nbsp;