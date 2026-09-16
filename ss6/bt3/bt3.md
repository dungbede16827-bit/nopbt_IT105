# **PHẦN A — ACTIVITY DIAGRAM**

## **Bước 2: Hoàn thiện bảng Node – Swimlane**

| Loại Node | Tên Node / Tác vụ | Swimlane phụ trách |
| ----- | ----- | ----- |
| **Initial Node** | Bắt đầu | — |
| **Action** | Đặt lịch khám | **Bệnh nhân** |
| **Decision** | Kiểm tra khung giờ (Còn trống / Hết chỗ) | **Lễ tân** |
| **Fork** | Tách 2 nhánh song song khi **Còn trống** | **Lễ tân** |
| **Action** | Xác nhận lịch khám | **Lễ tân** |
| **Action** | Gửi SMS nhắc lịch | **Lễ tân** |
| **Join** | Gộp 2 nhánh song song | **Lễ tân** |
| **Action** | Báo chọn khung giờ khác | **Lễ tân** |
| **Final Node** | Kết thúc | — |

&nbsp;

## **Bước 3: Luồng Activity Diagram**

### **Trường hợp còn trống**

Bắt đầu

&nbsp;&nbsp;&nbsp;|

Bệnh nhân: Đặt lịch khám

&nbsp;&nbsp;&nbsp;|

Lễ tân: Kiểm tra khung giờ

&nbsp;&nbsp;&nbsp;|

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Còn trống?

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Có

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;FORK

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/   \\

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|     |

Xác nhận    Gửi SMS

lịch khám   nhắc lịch

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\\     /

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;JOIN

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Kết thúc

&nbsp;

### **Trường hợp hết chỗ**

Kiểm tra khung giờ

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Còn trống?

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;│

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Hết chỗ

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|

Báo chọn khung giờ khác

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Kết thúc

# **Sơ đồ Activity hoàn chỉnh**

Có **2 Swimlane**:

* **Bệnh nhân**  
* **Lễ tân**

# **PHẦN B — USE CASE DIAGRAM**

## **Bước 5: Hoàn thiện bảng quan hệ**

Có **5 Use Case**:

1. Đăng nhập  
2. Đặt lịch khám  
3. Chọn bác sĩ chỉ định  
4. Đặt lịch khám thường  
5. Đặt lịch khám ưu tiên

| Use Case A | Use Case B | Quan hệ | Giải thích logic |
| ----- | ----- | ----- | ----- |
| **Đặt lịch khám** | **Đăng nhập** | `<<include>>` | Phải đăng nhập trước khi đặt lịch khám, đây là chức năng **bắt buộc** |
| **Chọn bác sĩ chỉ định** | **Đặt lịch khám** | `<<extend>>` | Chọn bác sĩ chỉ định là chức năng **tùy chọn**, bệnh nhân có thể chọn hoặc không |
| **Đặt lịch khám thường** | **Đặt lịch khám** | **Generalization** | Đặt lịch khám thường là một dạng chuyên biệt của Đặt lịch khám |
| **Đặt lịch khám ưu tiên** | **Đặt lịch khám** | **Generalization** | Đặt lịch khám ưu tiên là một dạng chuyên biệt của Đặt lịch khám |

&nbsp;

# **1\. `<<include>>` — Đăng nhập**

Đề nói:

> Bệnh nhân **phải Đăng nhập trước khi Đặt lịch khám**.

Vì vậy:

Đặt lịch khám ──────\<\<include\>\>──────Đăng nhập

&nbsp;

# **2\. `<<extend>>` — Chọn bác sĩ chỉ định**

Đề nói:

> Bệnh nhân **có thể tùy chọn** Chọn bác sĩ chỉ định.

Vì vậy:

Chọn bác sĩ chỉ định ──────\<\<extend\>\>────── Đặt lịch khám

&nbsp;

# **3\. Generalization — Đặt lịch khám thường**

Đề nói:

> Đặt lịch khám thường là một dạng của Đặt lịch khám.

Vẽ:

Đặt lịch khám thường ───────── Đặt lịch khám

Mũi tên là **tam giác rỗng** và hướng về **Use Case cha**.

&nbsp;

# **4\. Generalization — Đặt lịch khám ưu tiên**

Tương tự:

Đặt lịch khám ưu tiên ──────── Đặt lịch khám

Có nghĩa:

> Đặt lịch khám ưu tiên là một dạng chuyên biệt của Đặt lịch khám.

&nbsp;

# **Bước 6 — Use Case Diagram hoàn chỉnh**

## **Actor**

Bệnh nhân

## **System Boundary**

Hệ thống RikkeiCare

## **Các Use Case**

(Đăng nhập)

(Đặt lịch khám)

(Chọn bác sĩ chỉ định)

(Đặt lịch khám thường)

(Đặt lịch khám ưu tiên)

&nbsp;