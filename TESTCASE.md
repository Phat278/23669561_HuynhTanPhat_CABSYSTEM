# CAB System – Test Cases

**Tổng số:** 7 scenario × 20 Test Case = **140 Test Case**

**Quy tắc mỗi scenario:** 4 Positive + 4 Negative + 4 Boundary + 4 Null/Rỗng + 4 Sai form/Format.

## Đăng ký_Đăng nhập

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
| --- | --- | --- | --- | --- | --- | --- | --- |
| TC-AUTH-001 | Đăng ký/đăng nhập | Positive – Đăng ký tài khoản mới với thông tin hợp lệ | Người dùng chưa có tài khoản | 1. Mở Đăng ký<br>2. Nhập thông tin hợp lệ<br>3. Nhấn Đăng ký | Username: user01<br>Password: Password@123 | Tài khoản được tạo thành công | High |
| TC-AUTH-002 | Đăng ký/đăng nhập | Positive – Đăng nhập bằng tài khoản hợp lệ | Tài khoản đã đăng ký và Active | 1. Mở Login<br>2. Nhập username<br>3. Nhập password<br>4. Nhấn Login | user01 / Password@123 | Đăng nhập thành công và được xác thực | High |
| TC-AUTH-003 | Đăng ký/đăng nhập | Positive – Đăng xuất sau khi đăng nhập | Người dùng đã đăng nhập | 1. Đăng nhập<br>2. Nhấn Đăng xuất | Tài khoản hợp lệ | Người dùng được đăng xuất và không còn phiên xác thực | Medium |
| TC-AUTH-004 | Đăng ký/đăng nhập | Positive – Đăng nhập lại sau khi đăng xuất | Tài khoản tồn tại | 1. Đăng nhập<br>2. Đăng xuất<br>3. Đăng nhập lại | user01 / Password@123 | Đăng nhập lại thành công | High |
| TC-AUTH-005 | Đăng ký/đăng nhập | Negative – Username không tồn tại | Hệ thống hoạt động | 1. Mở Login<br>2. Nhập username không tồn tại<br>3. Nhập password<br>4. Login | unknown01 / Password@123 | Đăng nhập thất bại; không tạo phiên xác thực | High |
| TC-AUTH-006 | Đăng ký/đăng nhập | Negative – Password không đúng | Tài khoản tồn tại | 1. Nhập username đúng<br>2. Nhập password sai<br>3. Login | user01 / Wrong@123 | Đăng nhập thất bại; hiển thị lỗi phù hợp | High |
| TC-AUTH-007 | Đăng ký/đăng nhập | Negative – Đăng ký username đã tồn tại | user01 đã tồn tại | 1. Mở Đăng ký<br>2. Nhập username đã tồn tại<br>3. Nhập thông tin còn lại<br>4. Đăng ký | Username: user01 | Hệ thống từ chối đăng ký trùng tài khoản | High |
| TC-AUTH-008 | Đăng ký/đăng nhập | Negative – Truy cập chức năng yêu cầu tài khoản khi chưa đăng nhập | Người dùng chưa xác thực | 1. Không Login<br>2. Truy cập chức năng yêu cầu tài khoản | Token/session: không tồn tại | Hệ thống yêu cầu đăng nhập/xác thực | High |
| TC-AUTH-009 | Đăng ký/đăng nhập | Boundary – Username tại giới hạn độ dài cho phép | Quy tắc độ dài được hệ thống cấu hình | 1. Nhập username đúng giới hạn<br>2. Nhập password hợp lệ<br>3. Đăng ký | Username có độ dài đúng giới hạn | Hệ thống chấp nhận username tại giới hạn | Medium |
| TC-AUTH-010 | Đăng ký/đăng nhập | Boundary – Username vượt giới hạn độ dài | Quy tắc độ dài được hệ thống cấu hình | 1. Nhập username vượt giới hạn<br>2. Nhập các thông tin khác<br>3. Đăng ký | Username dài hơn giới hạn | Hệ thống từ chối dữ liệu vượt giới hạn | Medium |
| TC-AUTH-011 | Đăng ký/đăng nhập | Boundary – Password tại giới hạn cho phép | Quy tắc password được cấu hình | 1. Nhập password đúng giới hạn<br>2. Đăng ký/đăng nhập | Password tại giới hạn | Hệ thống chấp nhận password hợp lệ tại giới hạn | Medium |
| TC-AUTH-012 | Đăng ký/đăng nhập | Boundary – Password vượt giới hạn | Quy tắc password được cấu hình | 1. Nhập password vượt giới hạn<br>2. Gửi request | Password vượt giới hạn | Hệ thống từ chối password vượt giới hạn | Medium |
| TC-AUTH-013 | Đăng ký/đăng nhập | Rỗng – Username để trống | Đang ở Login | 1. Để trống username<br>2. Nhập password<br>3. Login | Username: empty<br>Password: Password@123 | Không cho đăng nhập; yêu cầu nhập username | High |
| TC-AUTH-014 | Đăng ký/đăng nhập | Rỗng – Password để trống | Đang ở Login | 1. Nhập username<br>2. Để trống password<br>3. Login | Username: user01<br>Password: empty | Không cho đăng nhập; yêu cầu nhập password | High |
| TC-AUTH-015 | Đăng ký/đăng nhập | Rỗng – Username và password đều trống | Đang ở Login | 1. Không nhập username<br>2. Không nhập password<br>3. Login | Username: empty<br>Password: empty | Không cho đăng nhập; hiển thị validation tương ứng | High |
| TC-AUTH-016 | Đăng ký/đăng nhập | Rỗng – Thiếu trường bắt buộc khi đăng ký | Đang ở màn hình đăng ký | 1. Bỏ trống một trường bắt buộc<br>2. Nhấn Đăng ký | Một hoặc nhiều trường: empty | Hệ thống không tạo tài khoản và yêu cầu bổ sung dữ liệu | High |
| TC-AUTH-017 | Đăng ký/đăng nhập | Sai format – Username chứa ký tự không hợp lệ | Đang ở Login/Đăng ký | 1. Nhập username sai định dạng<br>2. Nhập password<br>3. Gửi | Username: user@@@ | Hệ thống từ chối username sai format | Medium |
| TC-AUTH-018 | Đăng ký/đăng nhập | Sai format – Password không đáp ứng format yêu cầu | Quy tắc password đã được cấu hình | 1. Nhập username<br>2. Nhập password sai format<br>3. Gửi | Password: 123 | Hệ thống từ chối password không đúng format/rule | Medium |
| TC-AUTH-019 | Đăng ký/đăng nhập | Sai format – Username chứa khoảng trắng/ký tự không phù hợp | Đang ở màn hình đăng ký | 1. Nhập username có dữ liệu không đúng format<br>2. Nhập password<br>3. Đăng ký | Username: user 01@@ | Hệ thống từ chối username và hiển thị validation | Medium |
| TC-AUTH-020 | Đăng ký/đăng nhập | Sai format – Dữ liệu request đăng nhập không đúng kiểu | API Login đang hoạt động | 1. Gửi request Login<br>2. Truyền username/password sai kiểu dữ liệu | Username: 12345 thay vì chuỗi<br>Password: sai kiểu | API từ chối request và trả lỗi validation; không tạo authentication | High |

## Đặt xe

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
| --- | --- | --- | --- | --- | --- | --- | --- |
| TC-BOOK-001 | Đặt xe | Positive – Đặt xe với điểm đón, điểm đến và loại xe hợp lệ | Khách hàng đã đăng nhập | 1. Nhập điểm đón<br>2. Nhập điểm đến<br>3. Chọn loại xe<br>4. Gửi yêu cầu | Điểm đón: IUH<br>Điểm đến: Sân bay Tân Sơn Nhất<br>Loại xe: hợp lệ | Yêu cầu đặt xe được tạo; trạng thái REQUESTED | High |
| TC-BOOK-002 | Đặt xe | Positive – Đặt xe với tuyến đường hợp lệ khác | Khách hàng đã đăng nhập | 1. Nhập điểm đón<br>2. Nhập điểm đến<br>3. Chọn loại xe<br>4. Xác nhận | Điểm đón/đến hợp lệ; loại xe hợp lệ | Yêu cầu được ghi nhận và chuyển sang bước tìm tài xế | High |
| TC-BOOK-003 | Đặt xe | Positive – Chọn đúng loại xe có trong danh mục | Khách hàng đã đăng nhập | 1. Nhập địa điểm<br>2. Mở danh sách loại xe<br>3. Chọn loại xe hợp lệ<br>4. Đặt xe | Loại xe thuộc danh mục hệ thống | Yêu cầu đặt xe được tạo thành công | Medium |
| TC-BOOK-004 | Đặt xe | Positive – Gửi yêu cầu đặt xe sau khi kiểm tra thông tin | Khách hàng đã đăng nhập | 1. Nhập đủ thông tin<br>2. Kiểm tra lại<br>3. Xác nhận đặt xe | Thông tin chuyến hợp lệ | Hệ thống tạo đúng một yêu cầu đặt xe | High |
| TC-BOOK-005 | Đặt xe | Negative – Đặt xe khi chưa đăng nhập | Người dùng chưa xác thực | 1. Truy cập chức năng đặt xe<br>2. Nhập thông tin<br>3. Gửi yêu cầu | Không có token/session | Hệ thống yêu cầu đăng nhập; không tạo chuyến | High |
| TC-BOOK-006 | Đặt xe | Negative – Điểm đến không hợp lệ/không thể xác định | Khách hàng đã đăng nhập | 1. Nhập điểm đón hợp lệ<br>2. Nhập điểm đến không tồn tại<br>3. Gửi | Điểm đến: địa chỉ không xác định | Không tạo yêu cầu; hiển thị lỗi điểm đến | High |
| TC-BOOK-007 | Đặt xe | Negative – Loại xe không thuộc danh mục | Khách hàng đã đăng nhập | 1. Nhập điểm đón/đến<br>2. Gửi loại xe không hợp lệ | VehicleType: UNKNOWN | Hệ thống từ chối yêu cầu | Medium |
| TC-BOOK-008 | Đặt xe | Negative – Gửi lại cùng yêu cầu đặt xe nhiều lần | Khách hàng đã gửi yêu cầu | 1. Gửi yêu cầu đặt xe<br>2. Gửi lại cùng request | Cùng thông tin chuyến | Hệ thống không tạo bản ghi chuyến trùng ngoài quy tắc hệ thống | High |
| TC-BOOK-009 | Đặt xe | Boundary – Điểm đón/đến ở giới hạn dữ liệu được phép | Khách hàng đã đăng nhập | 1. Nhập địa điểm tại giới hạn hệ thống<br>2. Gửi yêu cầu | Địa điểm tại giới hạn cho phép | Yêu cầu được xử lý nếu dữ liệu vẫn hợp lệ | Medium |
| TC-BOOK-010 | Đặt xe | Boundary – Độ dài địa chỉ tại giới hạn | Khách hàng đã đăng nhập | 1. Nhập địa chỉ có độ dài đúng giới hạn<br>2. Gửi | Địa chỉ đúng giới hạn | Hệ thống chấp nhận dữ liệu tại giới hạn | Medium |
| TC-BOOK-011 | Đặt xe | Boundary – Địa chỉ vượt giới hạn | Khách hàng đã đăng nhập | 1. Nhập địa chỉ vượt giới hạn<br>2. Gửi | Địa chỉ dài hơn giới hạn | Hệ thống từ chối hoặc validation theo rule | Medium |
| TC-BOOK-012 | Đặt xe | Boundary – Chọn loại xe ở biên danh mục | Khách hàng đã đăng nhập | 1. Mở danh mục<br>2. Chọn phần tử đầu/cuối danh mục<br>3. Đặt xe | Loại xe hợp lệ ở biên danh mục | Hệ thống xử lý đúng loại xe được chọn | Low |
| TC-BOOK-013 | Đặt xe | Rỗng – Điểm đón để trống | Khách hàng đã đăng nhập | 1. Để trống điểm đón<br>2. Nhập điểm đến<br>3. Gửi | Điểm đón: empty | Không tạo yêu cầu; yêu cầu nhập điểm đón | High |
| TC-BOOK-014 | Đặt xe | Rỗng – Điểm đến để trống | Khách hàng đã đăng nhập | 1. Nhập điểm đón<br>2. Để trống điểm đến<br>3. Gửi | Điểm đến: empty | Không tạo yêu cầu; yêu cầu nhập điểm đến | High |
| TC-BOOK-015 | Đặt xe | Rỗng – Không chọn loại xe | Khách hàng đã đăng nhập | 1. Nhập điểm đón/đến<br>2. Không chọn loại xe<br>3. Gửi | VehicleType: empty | Không tạo yêu cầu; yêu cầu chọn loại xe | High |
| TC-BOOK-016 | Đặt xe | Rỗng – Tất cả thông tin đặt xe đều trống | Khách hàng đã đăng nhập | 1. Không nhập điểm đón<br>2. Không nhập điểm đến<br>3. Không chọn xe<br>4. Gửi | Tất cả: empty | Hệ thống không tạo chuyến và hiển thị validation | High |
| TC-BOOK-017 | Đặt xe | Sai format – Tọa độ/vị trí sai định dạng | Khách hàng đã đăng nhập | 1. Gửi dữ liệu vị trí sai kiểu/format<br>2. Xác nhận | Location: @@@### | API/UI từ chối dữ liệu vị trí | High |
| TC-BOOK-018 | Đặt xe | Sai format – Loại xe sai kiểu dữ liệu | Khách hàng đã đăng nhập | 1. Gửi request với vehicleType sai kiểu | VehicleType: 12345 nếu yêu cầu chuỗi | API trả validation; không tạo chuyến | High |
| TC-BOOK-019 | Đặt xe | Sai format – Request thiếu cấu trúc bắt buộc | Khách hàng đã đăng nhập | 1. Gửi request không đúng schema | JSON thiếu trường/field sai tên | API từ chối request và trả lỗi validation | High |
| TC-BOOK-020 | Đặt xe | Sai format – Dữ liệu địa điểm chứa ký tự/chuỗi không hợp lệ | Khách hàng đã đăng nhập | 1. Nhập dữ liệu vị trí sai format<br>2. Gửi | Điểm đón: ###@@@<br>Điểm đến: !!! | Hệ thống không tạo yêu cầu; hiển thị lỗi dữ liệu | Medium |

## Tìm tài xế

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
| --- | --- | --- | --- | --- | --- | --- | --- |
| TC-DRIVER-001 | Tìm tài xế | Positive – Tìm được tài xế phù hợp | Yêu cầu ở trạng thái SEARCHING_DRIVER; có tài xế AVAILABLE | 1. Tạo yêu cầu<br>2. Hệ thống tìm tài xế<br>3. Kiểm tra kết quả | Tài xế AVAILABLE, gần khách, đúng loại xe | Tài xế được gán; trạng thái DRIVER_ASSIGNED | High |
| TC-DRIVER-002 | Tìm tài xế | Positive – Tìm tài xế theo vị trí gần khách hàng | Có nhiều tài xế sẵn sàng | 1. Gửi yêu cầu<br>2. Theo dõi kết quả tìm | Nhiều tài xế AVAILABLE ở các vị trí khác nhau | Hệ thống trả/gán tài xế phù hợp theo rule hệ thống | High |
| TC-DRIVER-003 | Tìm tài xế | Positive – Tài xế nhận chuyến | Yêu cầu đang được tìm tài xế | 1. Tài xế nhận yêu cầu<br>2. Kiểm tra trạng thái | Driver response: ACCEPT | Chuyến chuyển sang DRIVER_ASSIGNED | High |
| TC-DRIVER-004 | Tìm tài xế | Positive – Tài xế từ chối và hệ thống tiếp tục tìm | Có nhiều tài xế phù hợp | 1. Gửi yêu cầu<br>2. Tài xế A từ chối<br>3. Theo dõi tìm kiếm | Driver A: REJECT | Hệ thống tiếp tục tìm tài xế khác theo SRS | High |
| TC-DRIVER-005 | Tìm tài xế | Negative – Không có tài xế phù hợp | Yêu cầu SEARCHING_DRIVER; không có tài xế phù hợp | 1. Gửi yêu cầu<br>2. Theo dõi | Danh sách tài xế phù hợp: empty | Không gán tài xế; xử lý trạng thái NO_DRIVER theo rule | High |
| TC-DRIVER-006 | Tìm tài xế | Negative – Tài xế không AVAILABLE | Có tài xế nhưng trạng thái BUSY/OFFLINE | 1. Gửi yêu cầu<br>2. Kiểm tra danh sách | Driver status: BUSY/OFFLINE | Không gán tài xế không sẵn sàng | High |
| TC-DRIVER-007 | Tìm tài xế | Negative – Tài xế không đúng loại xe | Có tài xế nhưng loại xe không phù hợp | 1. Gửi yêu cầu<br>2. Kiểm tra kết quả | Requested: loại xe A; Driver: loại xe B | Không gán tài xế không phù hợp | Medium |
| TC-DRIVER-008 | Tìm tài xế | Negative – Tìm tài xế cho chuyến không hợp lệ | Trip không ở trạng thái cho phép tìm | 1. Gửi request tìm tài xế | Trip status: COMPLETED | Hệ thống từ chối thao tác | High |
| TC-DRIVER-009 | Tìm tài xế | Boundary – Tài xế ở khoảng cách biên cho phép | Có tài xế ở ranh giới tìm kiếm | 1. Gửi yêu cầu<br>2. Kiểm tra kết quả | Khoảng cách đúng giới hạn hệ thống | Tài xế được xét nếu nằm trong phạm vi cho phép | Medium |
| TC-DRIVER-010 | Tìm tài xế | Boundary – Tài xế ngay ngoài phạm vi cho phép | Có tài xế ngay ngoài phạm vi | 1. Gửi yêu cầu<br>2. Kiểm tra | Khoảng cách vượt giới hạn nhỏ nhất | Tài xế không được chọn nếu ngoài phạm vi | Medium |
| TC-DRIVER-011 | Tìm tài xế | Boundary – Nhiều tài xế cùng thỏa điều kiện | Có nhiều tài xế hợp lệ | 1. Gửi yêu cầu<br>2. Theo dõi kết quả | Nhiều driver cùng thỏa điều kiện | Hệ thống chọn/gán theo rule ưu tiên được triển khai | Medium |
| TC-DRIVER-012 | Tìm tài xế | Boundary – Tài xế phản hồi ở giới hạn thời gian | Tài xế nhận request | 1. Gửi request<br>2. Phản hồi tại thời điểm giới hạn | Response time = giới hạn cấu hình | Hệ thống xử lý đúng timeout/response rule | Medium |
| TC-DRIVER-013 | Tìm tài xế | Rỗng – Không có danh sách tài xế | Yêu cầu SEARCHING_DRIVER | 1. Thực hiện tìm kiếm<br>2. Kiểm tra danh sách | Driver list: empty | Hiển thị không tìm thấy tài xế; không gán driver | High |
| TC-DRIVER-014 | Tìm tài xế | Rỗng – Không có loại xe yêu cầu | Yêu cầu đặt xe thiếu loại xe | 1. Gọi tìm tài xế | Vehicle type: empty | Không thực hiện gán; trả validation | High |
| TC-DRIVER-015 | Tìm tài xế | Rỗng – Không có vị trí khách hàng | Yêu cầu thiếu vị trí | 1. Gọi tìm tài xế | Customer location: empty | Không thể tìm tài xế; trả validation | High |
| TC-DRIVER-016 | Tìm tài xế | Rỗng – Request tìm tài xế không có trip ID | API đang hoạt động | 1. Gửi request không trip ID | Trip ID: empty | API trả validation; không tìm tài xế | High |
| TC-DRIVER-017 | Tìm tài xế | Sai format – Tọa độ tài xế sai format | Có request hợp lệ | 1. Gửi vị trí driver sai format | Location: abc@@ | Dữ liệu bị từ chối | High |
| TC-DRIVER-018 | Tìm tài xế | Sai format – Driver status sai format | API đang hoạt động | 1. Gửi trạng thái tài xế sai format | Status: 12345 | API trả validation | Medium |
| TC-DRIVER-019 | Tìm tài xế | Sai format – Driver ID sai kiểu | API đang hoạt động | 1. Gửi request với driver ID sai kiểu | Driver ID: @@@ | API từ chối request | High |
| TC-DRIVER-020 | Tìm tài xế | Sai format – Request tìm tài xế sai schema | API đang hoạt động | 1. Gửi JSON sai cấu trúc | JSON field sai tên/kiểu | API trả lỗi validation; không gán tài xế | High |

## Cập nhật trạng thái

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
| --- | --- | --- | --- | --- | --- | --- | --- |
| TC-TRIP-001 | Cập nhật trạng thái chuyến | Positive – Cập nhật trạng thái theo đúng quy trình | Tài xế đã nhận chuyến | 1. DRIVER_ARRIVED<br>2. PASSENGER_PICKED_UP<br>3. IN_PROGRESS<br>4. COMPLETED | Chuỗi trạng thái hợp lệ | Hệ thống chấp nhận và lưu từng trạng thái | High |
| TC-TRIP-002 | Cập nhật trạng thái chuyến | Positive – Chuyển DRIVER_ASSIGNED sang DRIVER_ARRIVING | Trip ở DRIVER_ASSIGNED | 1. Tài xế bắt đầu đến điểm đón<br>2. Cập nhật trạng thái | DRIVER_ARRIVING | Trạng thái được cập nhật thành công | High |
| TC-TRIP-003 | Cập nhật trạng thái chuyến | Positive – Hoàn thành chuyến sau khi IN_PROGRESS | Trip ở IN_PROGRESS | 1. Kết thúc chuyến<br>2. Cập nhật COMPLETED | IN_PROGRESS → COMPLETED | Chuyến chuyển sang COMPLETED | High |
| TC-TRIP-004 | Cập nhật trạng thái chuyến | Positive – Hủy chuyến theo trạng thái cho phép | Trip đang ở trạng thái cho phép hủy | 1. Thực hiện hủy<br>2. Cập nhật trạng thái | Status: CANCELLED | Chuyến chuyển sang CANCELLED theo rule | High |
| TC-TRIP-005 | Cập nhật trạng thái chuyến | Negative – Bỏ qua trạng thái trung gian | Trip ở DRIVER_ASSIGNED | 1. Gửi trực tiếp COMPLETED | DRIVER_ASSIGNED → COMPLETED | Hệ thống từ chối chuyển trạng thái không hợp lệ | High |
| TC-TRIP-006 | Cập nhật trạng thái chuyến | Negative – Cập nhật chuyến đã COMPLETED | Trip đã hoàn thành | 1. Gửi trạng thái mới | COMPLETED → IN_PROGRESS | Không cho thay đổi trạng thái đã kết thúc | High |
| TC-TRIP-007 | Cập nhật trạng thái chuyến | Negative – Người không có quyền cập nhật | Người dùng không phải tài xế phù hợp | 1. Gửi request cập nhật | User khác driver | API từ chối do không có quyền | High |
| TC-TRIP-008 | Cập nhật trạng thái chuyến | Negative – Cập nhật trip không tồn tại | API hoạt động | 1. Gửi trip ID không tồn tại | Trip ID: unknown | API trả lỗi; không cập nhật | High |
| TC-TRIP-009 | Cập nhật trạng thái chuyến | Boundary – Chuyển trạng thái đầu tiên hợp lệ | Trip ở trạng thái đầu phù hợp | 1. Gửi trạng thái kế tiếp hợp lệ | REQUESTED → trạng thái kế tiếp | Hệ thống chấp nhận chuyển đổi hợp lệ | Medium |
| TC-TRIP-010 | Cập nhật trạng thái chuyến | Boundary – Trạng thái cuối COMPLETED | Trip ở IN_PROGRESS | 1. Cập nhật COMPLETED | IN_PROGRESS → COMPLETED | Hệ thống cho phép kết thúc chuyến | High |
| TC-TRIP-011 | Cập nhật trạng thái chuyến | Boundary – Hủy ở thời điểm được phép cuối cùng | Trip ở trạng thái có thể hủy | 1. Hủy tại giới hạn chính sách | Thời điểm tại giới hạn rule | Hệ thống xử lý đúng chính sách hủy | Medium |
| TC-TRIP-012 | Cập nhật trạng thái chuyến | Boundary – Chuyển đổi ngay tại trạng thái trung gian | Trip đang ở trạng thái trung gian | 1. Gửi trạng thái kế tiếp đúng | Status kế tiếp hợp lệ | Trạng thái được cập nhật chính xác | Medium |
| TC-TRIP-013 | Cập nhật trạng thái chuyến | Rỗng – Không truyền status | Trip tồn tại | 1. Gửi request không status | Status: empty | API trả validation; trạng thái không đổi | High |
| TC-TRIP-014 | Cập nhật trạng thái chuyến | Rỗng – Không truyền trip ID | API hoạt động | 1. Gửi request không trip ID | Trip ID: empty | API trả validation | High |
| TC-TRIP-015 | Cập nhật trạng thái chuyến | Rỗng – Request chỉ có trip ID | Trip tồn tại | 1. Gửi request thiếu status | Trip ID có giá trị; status empty | API từ chối request | High |
| TC-TRIP-016 | Cập nhật trạng thái chuyến | Rỗng – Request cập nhật hoàn toàn trống | API hoạt động | 1. Gửi body rỗng | Body: empty | API trả validation | High |
| TC-TRIP-017 | Cập nhật trạng thái chuyến | Sai format – Status không thuộc enum | Trip tồn tại | 1. Gửi status sai | Status: ABC123 | API từ chối status | High |
| TC-TRIP-018 | Cập nhật trạng thái chuyến | Sai format – Trip ID sai kiểu | API hoạt động | 1. Gửi trip ID sai kiểu | Trip ID: @@@ | API trả lỗi validation | High |
| TC-TRIP-019 | Cập nhật trạng thái chuyến | Sai format – Request dùng kiểu dữ liệu sai | API hoạt động | 1. Gửi status dạng số/object thay vì chuỗi | Status: 12345/object | API từ chối request | High |
| TC-TRIP-020 | Cập nhật trạng thái chuyến | Sai format – JSON sai schema | API hoạt động | 1. Gửi body sai tên field/cấu trúc | JSON sai schema | API trả lỗi validation; trạng thái không đổi | High |

## Thanh toán

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
| --- | --- | --- | --- | --- | --- | --- | --- |
| TC-PAY-001 | Thanh toán | Positive – Thanh toán tiền mặt thành công | Chuyến COMPLETED; có số tiền phải trả | 1. Mở thanh toán<br>2. Chọn Cash<br>3. Xác nhận | Method: Cash | Thanh toán được ghi nhận thành công | High |
| TC-PAY-002 | Thanh toán | Positive – Thanh toán điện tử thành công | Chuyến COMPLETED; phương thức điện tử hoạt động | 1. Chọn thanh toán điện tử<br>2. Xác nhận giao dịch | Method: Electronic; transaction hợp lệ | Thanh toán thành công và lưu mã giao dịch cần thiết | High |
| TC-PAY-003 | Thanh toán | Positive – Thanh toán đúng số tiền hệ thống tính | Chuyến COMPLETED | 1. Kiểm tra fare<br>2. Thanh toán đúng số tiền | Amount = fare hệ thống | Giao dịch được ghi nhận đúng số tiền | High |
| TC-PAY-004 | Thanh toán | Positive – Kiểm tra trạng thái sau thanh toán | Giao dịch hợp lệ | 1. Thanh toán<br>2. Kiểm tra trip/payment | Payment success | Trạng thái thanh toán được cập nhật thành công | Medium |
| TC-PAY-005 | Thanh toán | Negative – Thanh toán khi chuyến chưa hoàn thành | Trip đang IN_PROGRESS | 1. Mở thanh toán<br>2. Thực hiện thanh toán | Trip status: IN_PROGRESS | Hệ thống không cho thanh toán khi chưa đủ điều kiện | High |
| TC-PAY-006 | Thanh toán | Negative – Giao dịch điện tử thất bại | Trip COMPLETED | 1. Chọn Electronic<br>2. Gửi giao dịch thất bại | Transaction: FAILED | Không ghi nhận thanh toán thành công; hiển thị lỗi | High |
| TC-PAY-007 | Thanh toán | Negative – Thanh toán trùng cho cùng chuyến | Chuyến đã thanh toán | 1. Thanh toán thành công<br>2. Gửi lại thanh toán | Same trip/payment | Hệ thống ngăn thanh toán trùng theo rule | High |
| TC-PAY-008 | Thanh toán | Negative – Phương thức thanh toán không được hỗ trợ | Trip COMPLETED | 1. Gửi payment method khác quy định | Method: Crypto/Unknown | Hệ thống từ chối phương thức không hỗ trợ | Medium |
| TC-PAY-009 | Thanh toán | Boundary – Số tiền đúng giá trị hệ thống tính | Trip COMPLETED | 1. Kiểm tra fare<br>2. Thanh toán đúng amount | Amount = fare | Thanh toán được chấp nhận | High |
| TC-PAY-010 | Thanh toán | Boundary – Số tiền lệch tối thiểu so với fare | Trip COMPLETED | 1. Gửi amount lệch rất nhỏ | Amount = fare ± đơn vị nhỏ nhất | Hệ thống xử lý theo rule sai lệch tiền tệ | Medium |
| TC-PAY-011 | Thanh toán | Boundary – Mã giao dịch ở giới hạn độ dài | Electronic payment | 1. Gửi transaction ID tại giới hạn | Transaction ID đúng giới hạn | Hệ thống chấp nhận nếu hợp lệ | Medium |
| TC-PAY-012 | Thanh toán | Boundary – Mã giao dịch vượt giới hạn | Electronic payment | 1. Gửi transaction ID vượt giới hạn | Transaction ID dài hơn giới hạn | Hệ thống từ chối dữ liệu | Medium |
| TC-PAY-013 | Thanh toán | Rỗng – Không chọn phương thức | Trip COMPLETED | 1. Mở thanh toán<br>2. Không chọn method<br>3. Xác nhận | Method: empty | Không thanh toán; yêu cầu chọn phương thức | High |
| TC-PAY-014 | Thanh toán | Rỗng – Không có transaction ID với thanh toán điện tử | Electronic payment | 1. Chọn Electronic<br>2. Bỏ trống transaction ID<br>3. Gửi | Transaction ID: empty | Hệ thống validation hoặc không ghi nhận giao dịch | High |
| TC-PAY-015 | Thanh toán | Rỗng – Amount trống | Trip COMPLETED | 1. Gửi payment request thiếu amount | Amount: empty | API/UI từ chối request | High |
| TC-PAY-016 | Thanh toán | Rỗng – Request thanh toán hoàn toàn trống | API hoạt động | 1. Gửi body rỗng | Body: empty | API trả validation | High |
| TC-PAY-017 | Thanh toán | Sai format – Amount không phải số | Trip COMPLETED | 1. Gửi amount sai kiểu | Amount: abc | API từ chối amount | High |
| TC-PAY-018 | Thanh toán | Sai format – Payment method sai enum | Trip COMPLETED | 1. Gửi method sai format | Method: UNKNOWN123 | API trả validation | High |
| TC-PAY-019 | Thanh toán | Sai format – Transaction ID sai định dạng | Electronic payment | 1. Gửi transaction ID chứa dữ liệu bất thường | Transaction ID: @@@### | Giao dịch bị từ chối/validation | Medium |
| TC-PAY-020 | Thanh toán | Sai format – Request thanh toán sai schema | API hoạt động | 1. Gửi JSON sai field/kiểu | JSON sai schema | API từ chối request; không ghi nhận thanh toán | High |

## Đánh giá

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
| --- | --- | --- | --- | --- | --- | --- | --- |
| TC-RATE-001 | Đánh giá | Positive – Đánh giá tài xế sau chuyến hoàn thành | Trip COMPLETED; khách hàng đăng nhập | 1. Mở chuyến<br>2. Chọn đánh giá<br>3. Nhập rating/comment<br>4. Gửi | Rating hợp lệ; comment: Tài xế phục vụ tốt | Đánh giá được ghi nhận | Medium |
| TC-RATE-002 | Đánh giá | Positive – Đánh giá bằng mức điểm hợp lệ | Trip COMPLETED | 1. Chọn mức điểm hợp lệ<br>2. Gửi | Rating trong thang điểm hệ thống | Đánh giá được lưu | Medium |
| TC-RATE-003 | Đánh giá | Positive – Đánh giá kèm nhận xét | Trip COMPLETED | 1. Nhập rating<br>2. Nhập comment<br>3. Gửi | Rating hợp lệ; comment hợp lệ | Rating và comment được lưu | Medium |
| TC-RATE-004 | Đánh giá | Positive – Xem lại đánh giá đã gửi | Đã có đánh giá | 1. Mở lịch sử/chuyến<br>2. Xem đánh giá | Trip đã được đánh giá | Đánh giá đã lưu được hiển thị đúng | Low |
| TC-RATE-005 | Đánh giá | Negative – Đánh giá khi chuyến chưa hoàn thành | Trip IN_PROGRESS | 1. Mở chức năng đánh giá<br>2. Gửi rating | Trip status: IN_PROGRESS | Hệ thống không cho đánh giá | High |
| TC-RATE-006 | Đánh giá | Negative – Đánh giá lại cùng chuyến nếu hệ thống không cho phép | Trip đã được đánh giá | 1. Gửi đánh giá lần hai | Same trip | Hệ thống từ chối hoặc xử lý theo rule đánh giá một lần | Medium |
| TC-RATE-007 | Đánh giá | Negative – Người dùng không phải khách của chuyến đánh giá | Trip thuộc user khác | 1. Truy cập đánh giá<br>2. Gửi | User khác trip owner | Hệ thống từ chối thao tác | High |
| TC-RATE-008 | Đánh giá | Negative – Trip không tồn tại | API hoạt động | 1. Gửi rating cho trip không tồn tại | Trip ID: unknown | API trả lỗi; không lưu đánh giá | High |
| TC-RATE-009 | Đánh giá | Boundary – Rating ở mức thấp nhất hợp lệ | Trip COMPLETED | 1. Chọn điểm thấp nhất hợp lệ<br>2. Gửi | Rating = giá trị thấp nhất hệ thống | Đánh giá được chấp nhận | Medium |
| TC-RATE-010 | Đánh giá | Boundary – Rating ở mức cao nhất hợp lệ | Trip COMPLETED | 1. Chọn điểm cao nhất hợp lệ<br>2. Gửi | Rating = giá trị cao nhất hệ thống | Đánh giá được chấp nhận | Medium |
| TC-RATE-011 | Đánh giá | Boundary – Rating vượt mức cao nhất | Trip COMPLETED | 1. Nhập điểm vượt giới hạn<br>2. Gửi | Rating = max + 1 | Hệ thống từ chối rating | High |
| TC-RATE-012 | Đánh giá | Boundary – Comment tại giới hạn độ dài | Trip COMPLETED | 1. Nhập comment đúng giới hạn<br>2. Gửi | Comment có độ dài đúng giới hạn | Comment được chấp nhận | Low |
| TC-RATE-013 | Đánh giá | Rỗng – Không nhập rating | Trip COMPLETED | 1. Mở đánh giá<br>2. Bỏ trống rating<br>3. Gửi | Rating: empty | Hệ thống yêu cầu rating | High |
| TC-RATE-014 | Đánh giá | Rỗng – Comment để trống nếu comment là trường tùy chọn | Trip COMPLETED | 1. Chọn rating<br>2. Không nhập comment<br>3. Gửi | Rating hợp lệ; Comment: empty | Đánh giá được lưu nếu comment không bắt buộc | Medium |
| TC-RATE-015 | Đánh giá | Rỗng – Không nhập rating và comment | Trip COMPLETED | 1. Không nhập dữ liệu<br>2. Gửi | Rating/comment: empty | Không tạo đánh giá | High |
| TC-RATE-016 | Đánh giá | Rỗng – Trip ID trống khi gọi API | API hoạt động | 1. Gửi request không trip ID | Trip ID: empty | API trả validation | High |
| TC-RATE-017 | Đánh giá | Sai format – Rating là chuỗi | Trip COMPLETED | 1. Gửi rating sai kiểu | Rating: abc | API từ chối rating | High |
| TC-RATE-018 | Đánh giá | Sai format – Rating là số thập phân nếu hệ thống yêu cầu số nguyên | Trip COMPLETED | 1. Gửi rating sai kiểu | Rating: 4.5 | API/UI validation theo rule | Medium |
| TC-RATE-019 | Đánh giá | Sai format – Trip ID sai kiểu | API hoạt động | 1. Gửi trip ID sai format | Trip ID: @@@ | API trả validation | High |
| TC-RATE-020 | Đánh giá | Sai format – Request đánh giá sai schema | API hoạt động | 1. Gửi JSON sai field/kiểu | JSON sai schema | API từ chối request; không lưu đánh giá | High |

## Lịch sử chuyến đi

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
| --- | --- | --- | --- | --- | --- | --- | --- |
| TC-HISTORY-001 | Lịch sử chuyến đi | Positive – Xem lịch sử khi có chuyến | Người dùng đã đăng nhập; có lịch sử | 1. Mở lịch sử chuyến đi<br>2. Kiểm tra danh sách | Có các trip đã COMPLETED/CANCELLED | Danh sách lịch sử hiển thị đúng | Medium |
| TC-HISTORY-002 | Lịch sử chuyến đi | Positive – Xem chi tiết một chuyến trong lịch sử | Có ít nhất một chuyến | 1. Mở lịch sử<br>2. Chọn một chuyến | Trip hợp lệ | Chi tiết chuyến hiển thị đúng | Medium |
| TC-HISTORY-003 | Lịch sử chuyến đi | Positive – Lịch sử hiển thị trạng thái chuyến | Có lịch sử | 1. Mở lịch sử<br>2. Kiểm tra trạng thái | Trip status hợp lệ | Trạng thái hiển thị đúng dữ liệu đã lưu | Low |
| TC-HISTORY-004 | Lịch sử chuyến đi | Positive – Lịch sử hiển thị thông tin chuyến đã thanh toán | Có chuyến đã thanh toán | 1. Mở lịch sử<br>2. Chọn chuyến đã thanh toán | Trip/payment hợp lệ | Thông tin thanh toán liên quan hiển thị đúng theo SRS | Low |
| TC-HISTORY-005 | Lịch sử chuyến đi | Negative – Truy cập lịch sử khi chưa đăng nhập | Người dùng chưa xác thực | 1. Truy cập lịch sử | Token/session: none | Hệ thống yêu cầu đăng nhập | High |
| TC-HISTORY-006 | Lịch sử chuyến đi | Negative – Xem lịch sử của người dùng khác | Có dữ liệu user khác | 1. Gửi request với user/trip khác | Trip thuộc user khác | Hệ thống không cho truy cập dữ liệu trái quyền | High |
| TC-HISTORY-007 | Lịch sử chuyến đi | Negative – Truy vấn trip không thuộc lịch sử | Đã đăng nhập | 1. Yêu cầu chi tiết trip không thuộc user | Trip ID khác user | API từ chối hoặc không trả dữ liệu trái quyền | High |
| TC-HISTORY-008 | Lịch sử chuyến đi | Negative – Trip ID không tồn tại | API hoạt động | 1. Yêu cầu trip không tồn tại | Trip ID: unknown | API trả lỗi phù hợp | Medium |
| TC-HISTORY-009 | Lịch sử chuyến đi | Boundary – Lịch sử có số lượng bản ghi tại giới hạn | Có nhiều lịch sử | 1. Mở lịch sử<br>2. Kiểm tra số bản ghi | Số bản ghi tại giới hạn phân trang hệ thống | Danh sách hiển thị đầy đủ trong giới hạn | Medium |
| TC-HISTORY-010 | Lịch sử chuyến đi | Boundary – Số bản ghi vượt giới hạn một trang | Có nhiều lịch sử | 1. Mở lịch sử<br>2. Kiểm tra phân trang | Số bản ghi > page size | Hệ thống phân trang/giới hạn đúng rule | Medium |
| TC-HISTORY-011 | Lịch sử chuyến đi | Boundary – Trang đầu tiên | Có lịch sử đủ nhiều | 1. Truy vấn page đầu | Page = giá trị đầu tiên hợp lệ | Trả đúng trang đầu | Low |
| TC-HISTORY-012 | Lịch sử chuyến đi | Boundary – Trang cuối cùng | Có lịch sử | 1. Truy vấn trang cuối | Page = last page hợp lệ | Trả đúng bản ghi cuối | Low |
| TC-HISTORY-013 | Lịch sử chuyến đi | Rỗng – Người dùng chưa có lịch sử | Đã đăng nhập nhưng chưa từng đặt xe | 1. Mở lịch sử | History: empty | Hiển thị danh sách rỗng/không có chuyến, không lỗi hệ thống | Medium |
| TC-HISTORY-014 | Lịch sử chuyến đi | Rỗng – Trip ID để trống khi xem chi tiết | Đã đăng nhập | 1. Gửi request chi tiết không ID | Trip ID: empty | API trả validation | High |
| TC-HISTORY-015 | Lịch sử chuyến đi | Rỗng – User ID/token trống | API hoạt động | 1. Gửi request thiếu xác thực | Token/User ID: empty | API từ chối truy cập | High |
| TC-HISTORY-016 | Lịch sử chuyến đi | Rỗng – Query/filter trống | Đã đăng nhập | 1. Gửi query/filter rỗng | Filter: empty | Hệ thống trả lịch sử mặc định hoặc validation theo thiết kế | Low |
| TC-HISTORY-017 | Lịch sử chuyến đi | Sai format – Trip ID sai kiểu | API hoạt động | 1. Gửi trip ID sai format | Trip ID: @@@ | API trả validation | High |
| TC-HISTORY-018 | Lịch sử chuyến đi | Sai format – Page/limit sai kiểu | API hoạt động | 1. Gửi page/limit sai kiểu | Page: abc; Limit: xyz | API từ chối tham số sai kiểu | Medium |
| TC-HISTORY-019 | Lịch sử chuyến đi | Sai format – Filter sai format | Đã đăng nhập | 1. Gửi filter không đúng schema | Filter: ###@@@ | API/UI xử lý validation | Medium |
| TC-HISTORY-020 | Lịch sử chuyến đi | Sai format – Request lịch sử sai schema | API hoạt động | 1. Gửi JSON/query sai cấu trúc | Request sai field/kiểu | API trả lỗi validation; không trả dữ liệu sai quyền | High |
