# **PHẦN A — ACTIVITY DIAGRAM**

## **Bước 2: Hoàn thiện bảng Node – Swimlane**

| Loại Node | Tên Node / Tác vụ | Swimlane phụ trách |
| ----- | ----- | ----- |
| **Initial Node** | Bắt đầu | — |
| **Action** | Đặt đơn hàng | **Khách hàng** |
| **Decision** | Kiểm tra tồn kho (Còn hàng / Hết hàng) | **Bộ phận Kho** |
| **Fork** | Tách 2 nhánh song song khi **Còn hàng** | **Bộ phận Kho** |
| **Action** | Đóng gói đơn hàng | **Bộ phận Kho** |
| **Action** | Gửi thông báo xuất kho cho Khách hàng | **Bộ phận Kho** |
| **Join** | Gộp 2 nhánh song song | **Bộ phận Kho** |
| **Action** | Báo hoàn tiền | **Bộ phận Kho** |
| **Final Node** | Kết thúc | — |

&nbsp;

# **Bước 3 — Activity Diagram hoàn chỉnh**

Có **2 Swimlane**:

* &nbsp;**Khách hàng**  
* &nbsp;**Bộ phận Kho**

&nbsp;

# **PHẦN B — USE CASE DIAGRAM**

## **Bước 5: Hoàn thiện bảng quan hệ**

Có tổng cộng **5 Use Case**:

1. Đăng nhập  
2. Đặt đơn hàng  
3. Giao hàng hoả tốc  
4. Đặt đơn hàng lẻ  
5. Đặt đơn hàng sỉ

Bảng hoàn chỉnh:

| Use Case A | Use Case B | Quan hệ | Giải thích logic |
| ----- | ----- | ----- | ----- |
| **Đặt đơn hàng** | **Đăng nhập** | `<<include>>` | Phải đăng nhập trước khi đặt đơn hàng, đây là chức năng **bắt buộc** |
| **Đặt đơn hàng** | **Giao hàng hoả tốc** | `<<extend>>` | Giao hàng hoả tốc là chức năng **tùy chọn**, khách hàng có thể yêu cầu hoặc không |
| **Đặt đơn hàng lẻ** | **Đặt đơn hàng** | **Generalization** | Đặt đơn hàng lẻ là một dạng chuyên biệt của Đặt đơn hàng |
| **Đặt đơn hàng sỉ** | **Đặt đơn hàng** | **Generalization** | Đặt đơn hàng sỉ là một dạng chuyên biệt của Đặt đơn hàng |

# **1\. Quan hệ `<<include>>`**

Đề nói:

> Khách hàng **phải Đăng nhập trước khi Đặt đơn hàng**.

Vì vậy:

Đặt đơn hàng ──────\<\<include\>\>────── Đăng nhập

# **2\. Quan hệ `<<extend>>`**

Đề nói:

> Khách hàng **có thể tùy chọn** yêu cầu Giao hàng hoả tốc.

Vì vậy:

Giao hàng hoả tốc ──────\<\<extend\>\>──────► Đặt đơn hàng

&nbsp;

# **3\. Generalization — Đặt đơn hàng lẻ**

Đề nói:

> Đặt đơn hàng có 2 hình thức: Đặt đơn hàng lẻ và Đặt đơn hàng sỉ.

&nbsp;

# **4\. Generalization — Đặt đơn hàng sỉ**

Tương tự:

Đặt đơn hàng sỉ ──────── Đặt đơn hàng

Có nghĩa:

> Đặt đơn hàng sỉ **là một dạng của** Đặt đơn hàng.

&nbsp;

# **Bước 6 — Use Case Diagram hoàn chỉnh**

## **Các thành phần**

### **Actor**

Khách hàng

### **System Boundary**

Hệ thống RikkeiLogistics

### **Use Case**

(Đăng nhập)

(Đặt đơn hàng)

(Giao hàng hoả tốc)

(Đặt đơn hàng lẻ)

(Đặt đơn hàng sỉ)

&nbsp;