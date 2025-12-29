---
title: "Giao thức HTTP và HTTPS hoạt động như thế nào?"
date: 2025-12-26
description: "Tại sao trình duyệt lại cảnh báo 'Not Secure' khi vào web cũ? Khám phá cơ chế mã hóa SSL/TLS và tầm quan trọng của HTTPS trong bảo mật."
tags: ["Security", "HTTP", "Web"]
categories: ["An toàn thông tin"]
draft: false
image: ""
---

### 1. HTTP là gì?
**HTTP (HyperText Transfer Protocol)** là giao thức truyền tải siêu văn bản, được sử dụng để truyền tải dữ liệu giữa Web Server và trình duyệt (Client).

Vấn đề lớn nhất của HTTP là dữ liệu được truyền đi dưới dạng **văn bản thuần (Plain Text)**.
* *Ví dụ:* Nếu bạn nhập mật khẩu là `123456` trên một trang HTTP, gói tin gửi đi sẽ chứa đúng chuỗi `123456`. Hacker đứng giữa (Man-in-the-Middle) có thể dễ dàng bắt gói tin và đọc được mật khẩu của bạn.

### 2. HTTPS là gì? Tại sao cần chữ "S"?
**HTTPS (HyperText Transfer Protocol Secure)** thực chất là HTTP được bọc thêm một lớp bảo mật gọi là **SSL/TLS (Secure Sockets Layer / Transport Layer Security)**.

Chữ **"S"** ở đây đại diện cho **Secure** (An toàn). Khi dùng HTTPS:
1.  **Mã hóa (Encryption):** Dữ liệu `123456` sẽ bị biến đổi thành một chuỗi ký tự vô nghĩa (ví dụ: `x8#mkL9@...`) trước khi gửi đi. Chỉ có Server nắm giữ chìa khóa giải mã mới đọc được.
2.  **Xác thực (Authentication):** Đảm bảo bạn đang kết nối đúng với server thật (ví dụ: đúng là `facebook.com` chứ không phải trang giả mạo) thông qua Chứng chỉ số (SSL Certificate).
3.  **Toàn vẹn dữ liệu (Integrity):** Đảm bảo dữ liệu không bị ai đó sửa đổi trên đường đi.

### 3. HTTPS hoạt động như thế nào? (SSL Handshake)
Quá trình thiết lập kết nối HTTPS diễn ra phức tạp hơn HTTP nhiều, gọi là **SSL Handshake**:

1.  **Client Hello:** Trình duyệt gửi yêu cầu kết nối an toàn và danh sách các thuật toán mã hóa nó hỗ trợ.
2.  **Server Hello:** Server chọn thuật toán mã hóa và gửi **Public Key** (Khóa công khai) kèm chứng chỉ SSL cho Client.
3.  **Key Exchange:** Client kiểm tra chứng chỉ. Nếu hợp lệ, Client tạo ra một **Session Key** (Khóa phiên), mã hóa nó bằng Public Key của Server rồi gửi lại cho Server.
4.  **Secure Connection:** Server dùng **Private Key** (Khóa bí mật) để giải mã và lấy Session Key. Từ lúc này, hai bên dùng Session Key này để mã hóa toàn bộ dữ liệu trao đổi.

### 4. Tại sao Website bắt buộc phải có HTTPS?
Ngày nay, HTTPS không còn là "lựa chọn" mà là "tiêu chuẩn bắt buộc":
* **Bảo mật thông tin:** Bảo vệ mật khẩu, thẻ tín dụng của người dùng.
* **SEO (Tối ưu hóa tìm kiếm):** Google ưu tiên xếp hạng các trang web có HTTPS cao hơn trang HTTP.
* **Uy tín (Trust):** Trình duyệt (Chrome, Edge) sẽ đánh dấu "Not Secure" (Không an toàn) nếu web không có HTTPS, làm người dùng sợ hãi và thoát trang.

### 5. Kết luận
HTTPS là tấm khiên bảo vệ internet hiện đại. Hiểu về cách nó hoạt động giúp bạn không chỉ bảo vệ bản thân khi lướt web mà còn biết cách triển khai bảo mật khi xây dựng ứng dụng web của riêng mình.