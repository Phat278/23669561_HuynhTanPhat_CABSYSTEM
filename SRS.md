1. Mục tiêu MVP

Xây dựng phiên bản tối thiểu của CAB System trong thời gian 7 tuần, tập
trung vào quy trình cốt lõi:

Đăng ký/đăng nhập → Đặt xe → Tìm tài xế → Nhận chuyến → Thực hiện
chuyến → Tính cước → Thanh toán → Đánh giá.

MVP ưu tiên các chức năng cần thiết để hệ thống có thể vận hành một quy
trình đặt xe hoàn chỉnh. Các chức năng nâng cao sẽ được xem xét ở các
phiên bản sau.

2. Phạm vi MVP

2.1. Khách hàng

Đăng ký tài khoản.

Đăng nhập/đăng xuất.

Cập nhật thông tin cá nhân.

Nhập điểm đón và điểm đến.

Lựa chọn loại xe.

Gửi yêu cầu đặt xe.

Xem trạng thái tìm tài xế.

Xem thông tin tài xế đã nhận chuyến.

Theo dõi trạng thái chuyến đi.

Xem giá cước dự kiến và số tiền phải trả.

Thanh toán bằng tiền mặt hoặc thanh toán điện tử.

Xem lịch sử chuyến đi.

Đánh giá tài xế sau khi hoàn thành chuyến.

2.2. Tài xế

Đăng nhập.

Cập nhật thông tin cá nhân.

Cập nhật thông tin phương tiện.

Chuyển trạng thái sẵn sàng/không sẵn sàng nhận chuyến.

Nhận thông báo chuyến xe phù hợp.

Chấp nhận hoặc từ chối chuyến.

Cập nhật vị trí hiện tại.

Cập nhật trạng thái chuyến:

Đã đến điểm đón.

Đã đón khách.

Đang di chuyển.

Hoàn thành chuyến.

Xem lịch sử chuyến đã thực hiện.

2.3. Nhân viên vận hành

Đăng nhập hệ thống quản trị.

Quản lý thông tin khách hàng.

Quản lý tài xế.

Quản lý phương tiện.

Xem danh sách chuyến đi.

Xem các chuyến đang diễn ra.

Kiểm tra trạng thái tài xế.

Hỗ trợ xử lý các chuyến bị lỗi.

Tra cứu lịch sử giao dịch.

Phân quyền chức năng quản trị cơ bản.

2.4. Hệ thống

Tự động tìm tài xế phù hợp dựa trên:

Trạng thái sẵn sàng.

Vị trí gần khách hàng.

Loại xe phù hợp.

Nếu tài xế từ chối hoặc không phản hồi, tiếp tục tìm tài xế khác.

Thông báo khi không tìm được tài xế.

Tính cước sau khi chuyến hoàn thành.

Hỗ trợ thanh toán tiền mặt.

Tích hợp thanh toán điện tử thông qua nhà cung cấp bên ngoài.

Không lưu trực tiếp thông tin nhạy cảm của thẻ/tài khoản thanh toán.

Gửi thông báo về các sự kiện chính của chuyến đi.

Lưu lịch sử chuyến đi và giao dịch.

Ghi nhận các thao tác quản trị quan trọng.

3. Quy trình nghiệp vụ chính của MVP

Khách hàng đăng nhập
        ↓
Nhập điểm đón + điểm đến + loại xe
        ↓
Tạo yêu cầu đặt xe
        ↓
Hệ thống tìm tài xế phù hợp
        ↓
Tài xế nhận / từ chối / không phản hồi
        ↓
Nếu từ chối → tìm tài xế khác
        ↓
Tài xế nhận chuyến
        ↓
Tài xế đến điểm đón
        ↓
Đón khách
        ↓
Đang di chuyển
        ↓
Hoàn thành chuyến
        ↓
Hệ thống tính cước
        ↓
Thanh toán
        ↓
Khách hàng đánh giá tài xế
        ↓
Lưu lịch sử chuyến đi

4. Trạng thái chuyến đi trong MVP

Trạng thái              Mô tả

REQUESTED             Khách hàng vừa tạo yêu cầu
SEARCHING_DRIVER      Hệ thống đang tìm tài xế
DRIVER_ASSIGNED       Đã có tài xế nhận chuyến
DRIVER_ARRIVING       Tài xế đang đến điểm đón
DRIVER_ARRIVED        Tài xế đã đến điểm đón
PASSENGER_PICKED_UP   Tài xế đã đón khách
IN_PROGRESS           Chuyến đang thực hiện
COMPLETED             Chuyến đã hoàn thành
CANCELLED             Chuyến bị hủy
NO_DRIVER             Không tìm được tài xế

5. Thanh toán trong MVP

MVP hỗ trợ hai phương thức:

Tiền mặt

Khách hàng thanh toán trực tiếp cho tài xế.

Hệ thống ghi nhận trạng thái thanh toán.

Thanh toán điện tử

CAB System gửi yêu cầu đến nhà cung cấp thanh toán bên ngoài.

Hệ thống chỉ lưu kết quả giao dịch và mã giao dịch cần thiết.

Không lưu thông tin nhạy cảm của thẻ hoặc tài khoản thanh toán.

Nếu thanh toán thất bại, thông báo cho khách hàng và cho phép xử
lý lại theo chính sách được xác định.

6. Thông báo trong MVP

Các thông báo chính:

Yêu cầu đặt xe được tiếp nhận.

Hệ thống đang tìm tài xế.

Tài xế đã nhận chuyến.

Tài xế đã đến điểm đón.

Chuyến đi hoàn thành.

Thanh toán thành công/thất bại.

Tài xế nhận được chuyến mới.

Chuyến đang thực hiện có thay đổi quan trọng.

Thiết kế chức năng thông báo theo hướng có thể bổ sung thêm các kênh như
SMS, Email hoặc Push Notification trong tương lai.

7. Yêu cầu phi chức năng chính của MVP

Hiệu năng

Hệ thống đáp ứng được lượng người dùng đồng thời theo quy mô được
thống nhất trong giai đoạn phân tích.

Chức năng tìm tài xế và đặt xe phải phản hồi nhanh trong điều kiện
vận hành bình thường.

Bảo mật

Người dùng phải xác thực trước khi sử dụng chức năng yêu cầu tài
khoản.

Phân quyền đối với các chức năng quản trị.

Bảo vệ thông tin cá nhân, phương tiện, vị trí và giao dịch.

Ghi log các thao tác quan trọng.

Khả năng mở rộng

Có thể mở rộng số lượng khách hàng và tài xế.

Các thành phần thanh toán và thông báo có thể thay đổi hoặc mở rộng
độc lập.

Có thể bổ sung loại dịch vụ mới trong tương lai.

Độ tin cậy

Lỗi ở thanh toán hoặc thông báo không được làm dừng toàn bộ chức
năng đặt xe.

Có cơ chế xử lý lỗi và thử lại đối với các dịch vụ bên ngoài.

8. Ngoài phạm vi MVP

Các nội dung sau chưa cần triển khai đầy đủ trong MVP và cần được làm rõ
trước khi phát triển:

Công thức tính cước chi tiết.

Thuật toán và trọng số ưu tiên tài xế.

Thời gian tài xế phải phản hồi.

Chính sách hủy chuyến và phí hủy.

Chi tiết xử lý khi mất kết nối mạng.

Thời gian lưu trữ dữ liệu.

Nhiều loại dịch vụ nâng cao.

Nhiều nhà cung cấp thanh toán.

Hệ thống thông báo đa kênh nâng cao.

Báo cáo phân tích nâng cao.

Các thuật toán tối ưu tài xế và dự đoán ETA nâng cao.

9. Tiêu chí hoàn thành MVP

MVP được xem là đạt yêu cầu khi có thể thực hiện thành công một chuyến
xe hoàn chỉnh:

Khách hàng tạo được yêu cầu đặt xe.

Hệ thống tìm được tài xế phù hợp.

Tài xế có thể nhận chuyến.

Khách hàng theo dõi được trạng thái chuyến.

Tài xế cập nhật được trạng thái chuyến.

Chuyến xe có thể hoàn thành.

Hệ thống tính được số tiền phải trả.

Khách hàng có thể thanh toán.

Khách hàng có thể đánh giá tài xế.

Hệ thống lưu được lịch sử chuyến đi.

Nhân viên vận hành có thể theo dõi và hỗ trợ xử lý chuyến.
