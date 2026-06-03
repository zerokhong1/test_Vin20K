Demo chủ đề 163: AI Nhận Diện & Hiểu Cảnh Quan Cho Robot Di Động (Scene Understanding)

# VLM-BlindSpot: Hệ Thống Định Hướng Robot Dựa Trên Ngữ Cảnh Đa Góc Nhìn Nhằm Giảm Thiểu Điểm Mù Không Gian

Dự án nghiên cứu và phát triển hệ thống định hướng thông minh cho robot di động (AMR/AGV) bằng cách kết hợp mô hình Thị giác - Ngôn ngữ (VLM) và hạ tầng Camera tổng giám sát trên cao.

---

## PHẦN 1: PRD (PRODUCT REQUIREMENT DOCUMENT)

### 1. Ý nghĩa & Mục tiêu sản phẩm (Product Vision)
Giải quyết hạn chế cốt lõi của các robot tự hành truyền thống: **Tầm nhìn cục bộ (Egocentric view)** dẫn đến việc hoàn toàn không thể phản ứng trước các mối nguy hiểm động bị che khuất sau vật cản (Occlusion). 

Hệ thống tận dụng hạ tầng Camera tổng (Allocentric view) phối hợp cùng mô hình Thị giác - Ngôn ngữ (VLM) để mang lại khả năng **hiểu ngữ cảnh và dự đoán hành vi chủ động**, đảm bảo tỷ lệ va chạm bằng 0 (Zero-collision) tại các góc khuất, ngã rẽ chữ L/T trong môi trường nhà kho và nhà thông minh.

### 2. Đối tượng người dùng & Môi trường áp dụng
* **Môi trường:** Nhà kho thông minh (Smart Warehouse), nhà máy tự động hóa (Smart Factory), hoặc không gian nhà thông minh (Smart Home) có thiết lập camera trần giám sát.
* **Đối tượng thụ hưởng:** Đội ngũ vận hành robot, các chuyên gia quản lý an toàn lao động trong nhà máy.

### 3. Các tính năng cốt lõi (Core Features - Bản MVP)
* **F01: Multi-Stream Data Aggregation:** Thu thập và đồng bộ hóa luồng video thời gian thực từ Camera robot và Camera tổng trên cao.
* **F02: Context-Aware Intent Prediction:** VLM phân tích hành vi của thực thể sống (đứa trẻ/thú cưng) phía sau vật cản vật lý thông qua camera tổng và đánh giá mức độ rủi ro lao ra khỏi góc khuất.
* **F03: Semantic Costmap Inflation:** Chuyển đổi đánh giá rủi ro dạng văn bản của VLM thành các thông số hình học (vùng nguy hiểm ảo) để can thiệp vào thuật toán định hướng của robot.
* **F04: Real-time Safe Navigation:** Robot tự động đánh lái, đi vòng rộng giữ khoảng cách an toàn với vật cản tĩnh có chứa mối nguy hiểm động phía sau thay vì đi sát mép vật cản.
