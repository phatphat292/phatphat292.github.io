---
title: "Đồ Án Đã Thực Hiện"
toc: false
comments: false
socialShare: false
# Đã xóa phần menu ở đây để không bị hiện 2 lần
---

<style>
    /* Ẩn các thành phần thừa */
    .post-meta, .meta, .date { display: none !important; }

    /* CSS cho Card */
    .project-card {
        background: #fff;
        border-radius: 15px;
        box-shadow: 0 5px 20px rgba(0,0,0,0.08);
        padding: 30px;
        border-left: 6px solid #007bff;
        margin-top: 30px;
        transition: transform 0.3s ease;
    }
    .project-card:hover { transform: translateY(-5px); }
    
    .project-title { 
        color: #2c3e50; 
        font-size: 1.5em; 
        margin-top: 0; 
        font-weight: bold;
    }
    
    .tech-stack { margin: 15px 0; }
    
    .tech-badge { 
        background: #e3f2fd; 
        color: #0d47a1; 
        padding: 5px 12px; 
        border-radius: 20px; 
        font-size: 0.85em; 
        margin-right: 5px; 
        border: 1px solid #bbdefb; 
        display: inline-block;
        margin-bottom: 5px;
    }
    
    /* CSS Nút bấm (Đã sửa lại cho chắc chắn hiện chữ) */
    .btn-container {
        display: flex;
        gap: 15px;
        margin-top: 25px;
        flex-wrap: wrap;
    }
    
    .btn-link {
        display: inline-flex;
        align-items: center;
        justify-content: center;
        padding: 10px 20px;
        color: #fff !important; /* Bắt buộc chữ màu trắng */
        text-decoration: none !important;
        border-radius: 6px;
        font-weight: bold;
        font-size: 0.95em;
        transition: opacity 0.3s;
        border: none;
    }
    
    .btn-link:hover { opacity: 0.9; }
    
    /* Màu nút */
    .btn-blue { background-color: #007bff; }
    .btn-dark { background-color: #333; }
</style>

<div class="project-card">
    <h3 class="project-title">🌐 Hệ thống Cân bằng tải (Load Balancer)</h3>        
    <div class="tech-stack">
        <span class="tech-badge">Nginx</span>
        <span class="tech-badge">Docker</span>
        <span class="tech-badge">Ubuntu</span>
        <span class="tech-badge">Web Server</span>
    </div>
    <p style="color: #555; line-height: 1.6; text-align: justify;">
        Xây dựng và triển khai hệ thống phân phối tải cho Web Server nhằm tối ưu hóa hiệu suất, tăng cường độ tin cậy và khả năng mở rộng của hệ thống mạng doanh nghiệp.
    </p>   
    <div class="btn-container">            
        <a href="/posts/he-thong-load-balancer" class="btn-link btn-blue">
            Xem Chi Tiết & Demo
        </a>
        <a href="https://github.com/phatphat292" target="_blank" class="btn-link btn-dark">
            GitHub
        </a>
    </div>
</div>