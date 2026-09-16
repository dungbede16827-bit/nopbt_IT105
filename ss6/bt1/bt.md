# **PHẦN A — ACTIVITY DIAGRAM**

## **Bước 2: Hoàn thiện bảng Node – Swimlane**

| Loại Node | Tên Node / Tác vụ | Swimlane phụ trách |
| ----- | ----- | ----- |
| **Initial Node** | Bắt đầu | — |
| **Action** | Quét mã QR | **Khách hàng** |
| **Decision** | Kiểm tra số dư (Đủ / Không đủ) | **Hệ thống** |
| **Fork** | Tách 2 nhánh song song khi **Đủ số dư** | **Hệ thống** |
| **Action** | Nhả tiền | **Hệ thống** |
| **Action** | Gửi SMS báo biến động số dư | **Hệ thống** |
| **Join** | Gộp 2 nhánh song song | **Hệ thống** |
| **Final Node** | Kết thúc | — |

&nbsp;

### **Luồng hoạt động**

Bắt đầu

&nbsp;&nbsp;&nbsp;|

Khách hàng: Quét mã QR

&nbsp;&nbsp;&nbsp;|

Hệ thống: Kiểm tra số dư

&nbsp;&nbsp;&nbsp;|

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Đủ số dư?

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|            |

&nbsp;&nbsp;&nbsp;&nbsp;Có         Không

&nbsp;&nbsp;&nbsp;&nbsp;|            |

&nbsp;&nbsp;FORK      Hiển thị lỗi

&nbsp;&nbsp;/   \\           |

&nbsp;|      |       Kết thúc

Nhả   Gửi SMS

tiền  báo biến

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;động số dư

&nbsp;&nbsp;\\     /

&nbsp;&nbsp;&nbsp;JOIN

&nbsp;&nbsp;&nbsp;&nbsp;|

Kết thúc

Fork \-\> 2 Action \-\> Join

Còn khi Không đủ số dư, đi thẳng đến:

Hiển thị lỗi \-\> Final Node

&nbsp;

# **PHẦN B — USE CASE DIAGRAM**

## **Bước 5: Hoàn thiện bảng quan hệ**

Đề đã cho 4 Use Case:

1. Đăng nhập  
2. Rút tiền  
3. In hóa đơn giao dịch  
4. Rút tiền tiêu chuẩn  
5. Rút tiền nhanh

Thực tế là **5 Use Case**.

Bảng hoàn chỉnh:

| Use Case A | Use Case B | Quan hệ | Giải thích |
| ----- | ----- | ----- | ----- |
| **Rút tiền** | **Đăng nhập** | **`<<include>>`** | Rút tiền **bắt buộc phải đăng nhập/quét QR trước**, nên Rút tiền luôn bao gồm Đăng nhập |
| **Rút tiền** | **In hóa đơn giao dịch** | **`<<extend>>`** | In hóa đơn là chức năng **tùy chọn**, chỉ xảy ra khi khách hàng muốn in |
| **Rút tiền tiêu chuẩn** | **Rút tiền** | **Generalization** | Rút tiền tiêu chuẩn là một dạng/chuyên biệt của Rút tiền |
| **Rút tiền nhanh** | **Rút tiền** | **Generalization** | Rút tiền nhanh là một dạng/chuyên biệt của Rút tiền |

&nbsp;

&nbsp;

# **Bước 6 — Use Case Diagram hoàn chỉnh**

Bạn có thể vẽ chính xác theo bố cục này:

&nbsp;