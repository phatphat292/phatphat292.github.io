---
title: "Chi tiết: Hệ thống Cân bằng tải Load Balancer"
date: 2025-12-29
description: "Mô tả chi tiết kiến trúc, cấu hình và video demo hoạt động."
toc: true
# === BẠN CẦN THÊM 2 DÒNG NÀY ĐỂ HẾT LỖI ===
tags: ["System", "Nginx", "Project"]
categories: ["Đồ Án"]
# ==========================================
---

<style>
    img { border-radius: 10px; box-shadow: 0 4px 15px rgba(0,0,0,0.1); margin: 20px auto; display: block; max-width: 100%; }
    .video-wrapper { text-align: center; margin-top: 30px; background: #000; border-radius: 10px; padding: 5px; }
    /* Thêm chút khoảng cách cho tiêu đề */
    h2 { margin-top: 40px; border-bottom: 2px solid #007bff; padding-bottom: 10px; }
</style>

## 1. Mô hình Kiến trúc
Hệ thống được thiết kế theo mô hình **Reverse Proxy**, trong đó Nginx đứng vai trò trung gian tiếp nhận yêu cầu từ người dùng và phân phối xuống các Web Server phía sau.

Dưới đây là sơ đồ hoạt động của hệ thống:

![Sơ đồ hệ thống](/mohinh.png)

---

## 2. Nội dung thực hiện

Để xây dựng hệ thống này, tôi đã thực hiện các bước triển khai kỹ thuật sau:

### 2.1. Công nghệ sử dụng
* **Hệ điều hành:** Linux (Ubuntu) - Môi trường máy chủ ổn định.
* **Nginx:** Đóng vai trò là Load Balancer chính.

### 2.2. Các chức năng đã triển khai
1.  **Cân bằng tải (Load Balancing):** Sử dụng thuật toán **Round Robin** để chia đều traffic cho các node server, đảm bảo không server nào bị quá tải.
2.  **Health Check:** Hệ thống tự động kiểm tra trạng thái của các Web Server. Nếu một container bị lỗi hoặc tắt, Nginx sẽ tự động ngắt kết nối và chuyển hướng người dùng sang server khác đang hoạt động.


<div class="video-wrapper"> <video controls width="100%" style="border-radius: 8px;"> <source src="/demo.mp4" type="video/mp4"> Trình duyệt của bạn không hỗ trợ thẻ video. </video> </div>