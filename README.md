# Báo cáo kiểm thử hiệu năng bằng JMeter

## Thông tin sinh viên

- Họ tên: Hoàng Thị Duyên

- MSSV: BIT220045

- Website được kiểm thử: https://vnexpress.net

## Mô tả kịch bản kiểm thử

1. **Kịch bản 1: Cơ bản**

- Số lượng người dùng: [10 + (45 % 10)] = 15

- Hành vi: Gửi yêu cầu GET đến trang chủ: https://vnexpress.net

- Loop Count: 5

2. **Kịch bản 2: Tải nặng**

- Số lượng người dùng: [50 + (45 % 20)] = 55

- Ramp-up Period: 30 giây

- Hành vi: Gửi yêu cầu GET đến trang chủ: https://vnexpress.net và trang: https://vnexpress.net/bat-dong-san

3. **Kịch bản 3: Tùy chỉnh**

- Số lượng người dùng: [20 + (45 % 15)] = 20

- Thời gian chạy: 60 giây

- Hành vi: Gửi yêu cầu GET đến 2trang: https://vnexpress.net/thoi-su và https://vnexpress.net/kinh-doanh

## Kết quả kiểm thử

- **Kịch bản 1**:

- Response Time trung bình: 276 ms

- Throughput: 30.53 yêu cầu/giây

- Error Rate: 0.00%

- **Kịch bản 2**:

- Response Time trung bình: 2124 ms

- Throughput: 24.91 yêu cầu/giây

- Error Rate: 0.38%

- **Kịch bản 3**:

- Response Time trung bình: 818 ms

- Throughput: 24.23 yêu cầu/giây

- Error Rate: 0.07 %

## Nhận xét
 ### 1. Về thời gian phản hồi (Response Time)

- Kịch bản 1: 276 ms – rất tốt, phản hồi nhanh và phù hợp với tiêu chuẩn web phổ thông.

- Kịch bản 2: 2124 ms – khá cao, có thể gây chậm trễ trong trải nghiệm người dùng nếu thao tác quan trọng.

- Kịch bản 3: 818 ms – mức trung bình khá, vẫn trong ngưỡng chấp nhận được cho các tác vụ phức tạp.

#### Nhận định:
- Thời gian phản hồi có dao động đáng kể giữa các kịch bản. Điều này cho thấy hiệu năng chưa hoàn toàn ổn định và có thể phụ thuộc vào loại tác vụ hoặc lượng tải tại thời điểm kiểm thử.

### 2. Về thông lượng (Throughput)
- Kịch bản 1: 30.53 yêu cầu/giây

- Kịch bản 2: 24.91 yêu cầu/giây

- Kịch bản 3: 24.23 yêu cầu/giây

#### Nhận định:
- Throughput nhìn chung ổn định, cho thấy hệ thống có khả năng xử lý lượng yêu cầu tương đối đều, mặc dù có thể bị giới hạn bởi tài nguyên máy chủ hoặc độ phức tạp của request.

### 3. Về Tỷ lệ lỗi (Error Rate)
- Kịch bản 1: 0.00% – hoàn hảo

- Kịch bản 2: 0.38% – chấp nhận được

- Kịch bản 3: 0.07% – rất thấp

#### Nhận định:
- Tỷ lệ lỗi rất thấp hoặc không có lỗi, cho thấy hệ thống xử lý ổn định và không gặp lỗi nghiêm trọng dưới tải kiểm thử.
Kết luận chung
- Website có khả năng chịu tải tốt trong điều kiện kiểm thử hiện tại.

- Thời gian phản hồi chưa thực sự ổn định, có lúc cao bất thường (> 2s), cần xem xét tối ưu thêm ở backend hoặc database nếu muốn nâng cao trải nghiệm.

- Hệ thống không gặp lỗi nghiêm trọng, đảm bảo tính ổn định cao dưới tải vừa phải.