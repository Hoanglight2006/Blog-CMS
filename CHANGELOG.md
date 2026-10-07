# Changelog

## [Unreleased]
### Todo (Commit 3)
- Setup Loki + Promtail gom log tập trung.
- Truy vấn log Nginx bằng LogQL.
- Hoàn thiện tài liệu báo cáo.

---

## [1.1.0] - 2026-10-07
### Added (Commit 2)
- Tích hợp Prometheus server thu thập dữ liệu định kỳ mỗi 15 giây (`prometheus.yml`).
- Bổ sung cAdvisor thu thập metrics tài nguyên container (CPU, RAM, Network).
- Bổ sung mysqld-exporter thu thập metrics trạng thái và truy vấn MySQL (sử dụng cờ `--mysqld.address` và biến `MYSQLD_EXPORTER_PASSWORD`).
- Tích hợp Grafana tự động kết nối Data Source Prometheus qua cơ chế provisioning.
- Mở rộng phân vùng mạng `monitor_net` bảo đảm cô lập dịch vụ giám sát.
- Xây dựng bộ kịch bản kiểm thử tự động 15 ca test (`scripts/test-system.ps1`, `scripts/test-system.sh`) bao gồm kiểm thử an ninh, phân vùng mạng, test biên, mã lỗi 404 và sức khỏe hệ thống giám sát đạt 100% PASS.

---

## [1.0.0] - 2026-10-07
### Added (Commit 1)
- Setup WordPress, MySQL 8.0 và phpMyAdmin chạy bằng Docker Compose.
- Tách 2 mạng riêng `frontend_net` và `backend_net` để ẩn cổng database.
- Cấu hình Nginx reverse proxy với HTTPS cổng 443 và tự động chuyển hướng từ cổng 80.
- Thêm script tự tạo SSL certificate nội bộ (`generate-ssl.ps1`, `generate-ssl.sh`).
- Cấu hình các HTTP security headers cho Nginx (`X-Frame-Options`, `nosniff`, `HSTS`...).
- Thiết lập file `.env` quản lý mật khẩu và tài khoản an toàn.
