# Quản lý Lịch hẹn - Appointment Management System

Đồ án thực hành môn học: **Triển khai và Quản trị Hệ thống Phần mềm**  
* **Sinh viên thực hiện**: Trần Ánh Phương  
* **Mã số sinh viên (MSSV)**: `dtc245200768`  
* **Lớp học phần / Chuyên ngành**: Công nghệ Thông tin - ICTU  

---

## 🏗️ 1. Tổng quan kiến trúc hệ thống
Hệ thống được xây dựng theo mô hình Microservices / Multi-container chạy trên nền tảng **Docker**, bao gồm các thành phần chính:
- **Nginx**: Đóng vai trò làm Reverse Proxy, tiếp nhận request ở cổng `80` và định tuyến vào ứng dụng.
- **Node.js App**: Ứng dụng quản lý lịch hẹn chính (`appointment-app`).
- **PostgreSQL (v16)**: Cơ sở dữ liệu quan hệ lưu trữ thông tin hệ thống (`appointment-db`).
- **pgAdmin**: Công cụ quản lý cơ sở dữ liệu trên nền web (`http://localhost:5050`).
- **Prometheus & cAdvisor & Postgres-Exporter**: Thu thập các chỉ số giám sát hiệu năng CPU, RAM và Database.
- **Grafana**: Giao diện trực quan hóa dữ liệu giám sát và quản lý biểu đồ (`http://localhost:3001`).
- **Loki & Promtail**: Hệ thống thu thập và gom log tập trung, hỗ trợ truy vấn bằng ngôn ngữ LogQL.

---

## 🚀 2. Hướng dẫn cài đặt và chạy hệ thống

### Yêu cầu hệ thống:
- Đã cài đặt **Docker** và **Docker Compose**.

### Các bước triển khai:
1. Clone repository về máy:
   ```bash
   git clone [https://github.com/dtc245200768-ui/dtc245200768-appointment.git](https://github.com/dtc245200768-ui/dtc245200768-appointment.git)
   cd dtc245200768-appointment