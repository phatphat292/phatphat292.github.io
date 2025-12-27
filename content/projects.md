---
title: "Đồ Án Đã Thực Hiện"
toc: false
comments: false
socialShare: false
tags: []
---

<style>
    /* Ẩn ngày tháng */
    .post-meta, 
    div[class*="meta"], span[class*="meta"],
    div[class*="date"], span[class*="date"] { 
        display: none !important; 
    }

    /* Container */
    .project-list {
        display: flex;
        flex-direction: column;
        gap: 40px;
        margin-top: 30px;
    }

    /* Thẻ đồ án */
    .project-card {
        background: #fff;
        border-radius: 15px;
        box-shadow: 0 5px 20px rgba(0,0,0,0.08);
        padding: 30px;
        border-left: 6px solid #007bff;
        transition: transform 0.3s ease;
    }

    .project-card:hover {
        transform: translateY(-5px);
        box-shadow: 0 10px 25px rgba(0,0,0,0.12);
    }

    .project-title {
        color: #2c3e50;
        margin-top: 0;
        font-size: 1.5em;
        display: flex;
        align-items: center;
        gap: 10px;
    }

    .tech-stack {
        display: flex;
        flex-wrap: wrap;
        gap: 10px;
        margin: 15px 0;
    }

    .tech-badge {
        background-color: #e3f2fd;
        color: #0d47a1;
        padding: 5px 12px;
        border-radius: 20px;
        font-size: 0.85em;
        font-weight: 600;
        border: 1px solid #bbdefb;
    }

    .project-desc {
        color: #555;
        line-height: 1.6;
        text-align: justify;
    }

    .btn-link {
        display: inline-block;
        margin-top: 15px;
        padding: 8px 18px;
        background-color: #333;
        color: #fff !important;
        text-decoration: none;
        border-radius: 5px;
        font-size: 0.9em;
    }
    .btn-link:hover {
        background-color: #000;
    }
</style>

<div class="project-list">
    <div class="project-card">
        <h3 class="project-title">🌐 Hệ thống Cân bằng tải (Load Balancer)</h3>      
        <div class="tech-stack">
            <span class="tech-badge">Nginx</span>
            <span class="tech-badge">Docker</span>
            <span class="tech-badge">Linux (Ubuntu)</span>
            <span class="tech-badge">Web Server</span>
        </div>
        <div class="project-desc">
            <p><strong>Mô tả:</strong> Xây dựng và triển khai hệ thống phân phối tải cho Web Server nhằm tối ưu hóa hiệu suất, tăng cường độ tin cậy và khả năng mở rộng của hệ thống mạng doanh nghiệp.</p>
            <p><strong>Chức năng chính:</strong></p>
            <ul style="margin-bottom: 0;">
                <li>Cấu hình <strong>Nginx</strong> làm Reverse Proxy và Load Balancer.</li>
                <li>Triển khai thuật toán phân phối <strong>Round Robin</strong> và <strong>Least Connections</strong>.</li>
                <li>Thiết lập cơ chế <strong>Health Check</strong> để tự động loại bỏ các server lỗi.</li>
                <li>Đóng gói hệ thống bằng <strong>Docker Container</strong> để dễ dàng triển khai.</li>
            </ul>
        </div>       
        <a href="https://github.com/phatphat292" target="_blank" class="btn-link">
            Xem Code trên GitHub
        </a>
    </div>

</div>