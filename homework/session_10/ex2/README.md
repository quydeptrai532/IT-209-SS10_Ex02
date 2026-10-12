
# Bài 2: Single-stage Dockerfile

## Giới thiệu
Ứng dụng REST API sử dụng Node.js và Express, được đóng gói bằng Docker Single-stage.

## Dockerfile
- FROM: Chọn Node.js 18 Alpine.
- WORKDIR: Thiết lập thư mục /app.
- COPY: Sao chép mã nguồn.
- RUN: Cài đặt Express.
- ENV: Thiết lập PORT=3000.
- EXPOSE: Khai báo cổng 3000.
- CMD: Khởi động server.js.

## Build Image
```bash
docker build -t hw-backend:v1 .
```

## Chạy Container
```bash
docker run -d --name app-single-stage -p 8080:3000 hw-backend:v1
```

## Kiểm tra
```bash
docker ps
docker logs app-single-stage
curl -i http://localhost:8080/
```

Kết quả: HTTP 200 OK và JSON trả về thành công.

## Kết luận
Ứng dụng được đóng gói và triển khai thành công bằng Docker Single-stage.

