---
title: "So sánh TCP và UDP: Khi nào nên dùng giao thức nào?"
date: 2025-12-27
description: "Tại sao xem livestream lại dùng UDP còn gửi email lại bắt buộc phải dùng TCP? Phân tích ưu nhược điểm và ứng dụng thực tế của hai giao thức cốt lõi này."
tags: ["Networking", "Protocol", "NetworkLayer"]
categories: ["Kiến thức mạng"]
draft: false
image: "" # Bạn có thể thêm đường dẫn ảnh bìa nếu có
---

### 1. Giới thiệu chung
Trong tầng Giao vận (Transport Layer - Layer 4) của mô hình OSI, **TCP (Transmission Control Protocol)** và **UDP (User Datagram Protocol)** là hai giao thức phổ biến nhất chịu trách nhiệm vận chuyển dữ liệu giữa các thiết bị.

Tuy nhiên, cách chúng vận chuyển dữ liệu lại hoàn toàn trái ngược nhau. Nếu ví mạng Internet là hệ thống giao hàng, thì:
* **TCP** giống như dịch vụ **gửi thư bảo đảm**: Phải có chữ ký người nhận, nếu mất hàng thì gửi lại.
* **UDP** giống như dịch vụ **gửi thư thường (hoặc loa phát thanh)**: Cứ gửi đi nhanh nhất có thể, không quan tâm người nhận có nhận được hay không.

### 2. Chi tiết về TCP (Giao thức tin cậy)
TCP là giao thức hướng kết nối (**Connection-oriented**). Trước khi truyền dữ liệu, nó bắt buộc phải thiết lập một kết nối thông qua quá trình **"Bắt tay 3 bước" (3-way Handshake)**:
1.  **SYN:** Client gửi yêu cầu kết nối.
2.  **SYN-ACK:** Server đồng ý và gửi lại xác nhận.
3.  **ACK:** Client xác nhận lại lần cuối -> Kết nối được thiết lập.

**Đặc điểm nổi bật:**
* **Độ tin cậy cao:** Đảm bảo gói tin đến đúng thứ tự, không bị mất. Nếu mất, nó sẽ yêu cầu gửi lại (Retransmission).
* **Kiểm soát luồng (Flow Control):** Điều chỉnh tốc độ gửi để bên nhận không bị quá tải.
* **Tốc độ chậm hơn:** Do phải xử lý nhiều thủ tục kiểm tra lỗi và xác nhận.

### 3. Chi tiết về UDP (Giao thức không tin cậy)
UDP là giao thức phi kết nối (**Connectionless**). Nó hoạt động theo kiểu "Fire and Forget" (Bắn và Quên). Nó đóng gói dữ liệu và đẩy đi ngay lập tức mà không cần kiểm tra xem bên kia có sẵn sàng nhận hay không.

**Đặc điểm nổi bật:**
* **Tốc độ cực nhanh:** Không tốn thời gian bắt tay hay kiểm tra lỗi.
* **Header nhỏ gọn:** Header của UDP chỉ 8 bytes (so với 20 bytes của TCP), giúp tiết kiệm băng thông.
* **Không tin cậy:** Gói tin có thể bị mất, bị trùng lặp hoặc đến sai thứ tự mà không có cơ chế sửa lỗi.

### 4. Bảng so sánh tóm tắt

| Đặc điểm | TCP (Transmission Control Protocol) | UDP (User Datagram Protocol) |
| :--- | :--- | :--- |
| **Loại kết nối** | Hướng kết nối (Connection-oriented) | Phi kết nối (Connectionless) |
| **Độ tin cậy** | Cao (đảm bảo gửi thành công) | Thấp (có thể mất gói tin) |
| **Thứ tự** | Đảm bảo đúng thứ tự | Không đảm bảo thứ tự |
| **Tốc độ** | Chậm hơn | Rất nhanh |
| **Sửa lỗi** | Có (gửi lại gói tin lỗi) | Không |
| **Header Size** | 20 bytes | 8 bytes |

### 5. Khi nào dùng cái nào? (Ứng dụng thực tế)

* **Sử dụng TCP khi:** Bạn cần sự chính xác tuyệt đối và toàn vẹn dữ liệu.
    * *Ví dụ:* Duyệt web (HTTP/HTTPS), Gửi Email (SMTP), Truyền file (FTP), Chat văn bản (WhatsApp, Messenger).
* **Sử dụng UDP khi:** Bạn cần tốc độ thời gian thực và chấp nhận mất một chút dữ liệu (giật lag nhẹ) để đổi lấy sự mượt mà.
    * *Ví dụ:* Livestream, Gọi Video (VoIP, Zoom), Game Online (FPS, MOBA), DNS (Domain Name System).

### 6. Kết luận
Không có giao thức nào là "tốt nhất", chỉ có giao thức "phù hợp nhất" với mục đích sử dụng. Là một kỹ sư mạng hoặc lập trình viên, việc hiểu rõ sự đánh đổi (trade-off) giữa **Tốc độ (UDP)** và **Độ tin cậy (TCP)** là chìa khóa để thiết kế hệ thống hiệu quả.