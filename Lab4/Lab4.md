1. Ca sử dụng: Đăng nhập hệ thống
Mô tả:
Đây là bước đầu tiên để người dùng có thể truy cập vào hệ thống và thực hiện các chức năng của mình.

Người sử dụng:

Nhân viên
Quản lý
Bộ phận nhân sự
Quy trình chính:

Người dùng mở giao diện đăng nhập.
Nhập tên đăng nhập và mật khẩu.
Hệ thống kiểm tra tính hợp lệ của thông tin.
Nếu thông tin đúng, người dùng được chuyển đến giao diện chính.
Quy trình phụ:

Nếu thông tin không đúng, hệ thống yêu cầu nhập lại.
Nếu tài khoản bị khóa, hệ thống thông báo yêu cầu liên hệ với quản trị viên.
Lý do thiết kế:

Đảm bảo tính bảo mật và phân quyền người dùng.
Ngăn chặn truy cập trái phép vào các chức năng của hệ thống.
2. Ca sử dụng: Nhập thông tin giờ làm việc
Mô tả:
Nhân viên nhập số giờ làm việc vào hệ thống để phục vụ việc tính toán lương.

Người sử dụng:

Nhân viên
Quy trình chính:

Nhân viên đăng nhập vào hệ thống.
Lựa chọn chức năng nhập giờ làm việc.
Nhập số giờ làm việc vào hệ thống.
Gửi yêu cầu lưu thông tin.
Hệ thống kiểm tra tính hợp lệ của dữ liệu.
Lưu dữ liệu vào cơ sở dữ liệu.
Quy trình phụ:

Nếu dữ liệu nhập không hợp lệ, hệ thống yêu cầu người dùng nhập lại.
Lý do thiết kế:

Tính chính xác và minh bạch trong việc tính lương.
Giảm thiểu lỗi khi nhập thông tin về giờ làm việc.
3. Ca sử dụng: Tính toán lương
Mô tả:
Quản lý yêu cầu hệ thống tính toán lương cho nhân viên dựa trên thông tin đã nhập về giờ làm việc và các quy định khác.

Người sử dụng:

Quản lý
Quy trình chính:

Quản lý đăng nhập vào hệ thống.
Chọn tính năng tính lương.
Hệ thống truy xuất dữ liệu nhân viên và giờ làm việc.
Áp dụng công thức tính lương (lương cơ bản + phụ cấp - các khoản trừ).
Hệ thống lưu kết quả vào cơ sở dữ liệu.
Hiển thị thông báo hoàn tất.
Quy trình phụ:

Nếu thiếu thông tin cần thiết, hệ thống yêu cầu bổ sung.
Lý do thiết kế:

Tự động hóa quy trình tính toán, giảm thiểu sai sót và tiết kiệm thời gian.
4. Ca sử dụng: Tạo phiếu lương
Mô tả:
Bộ phận nhân sự tạo phiếu lương cho nhân viên, phục vụ việc thông báo và gửi qua email.

Người sử dụng:

Bộ phận nhân sự
Quy trình chính:

Bộ phận nhân sự đăng nhập vào hệ thống.
Chọn tính năng tạo phiếu lương.
Hệ thống truy xuất dữ liệu lương từ cơ sở dữ liệu.
Tạo phiếu lương theo định dạng PDF hoặc Excel.
Gửi phiếu lương qua email hoặc lưu lại để tải xuống.
Lý do thiết kế:

Đảm bảo tính chính xác và minh bạch trong việc thông báo lương cho nhân viên.
5. Ca sử dụng: Tạo báo cáo lương
Mô tả:
Quản lý tạo báo cáo tổng hợp về tình hình lương trong công ty theo khoảng thời gian nhất định.

Người sử dụng:

Quản lý
Quy trình chính:

Quản lý đăng nhập vào hệ thống.
Chọn tính năng tạo báo cáo lương.
Nhập các tiêu chí báo cáo (tháng/năm, phòng ban, nhân viên cụ thể).
Hệ thống tổng hợp dữ liệu lương và tạo báo cáo.
Xuất báo cáo dưới dạng PDF hoặc Excel.
Quy trình phụ:

Nếu không có dữ liệu phù hợp với tiêu chí, hệ thống thông báo không có dữ liệu.
Lý do thiết kế:

Giúp quản lý dễ dàng theo dõi và phân tích chi phí lương trong công ty.
Tính năng bảo mật và phân quyền
Mô tả:
Để bảo vệ dữ liệu nhạy cảm, hệ thống yêu cầu người dùng đăng nhập trước khi thực hiện các chức năng. Các quyền hạn của người dùng sẽ được xác định dựa trên vai trò (nhân viên, quản lý, nhân sự).

Lý do thiết kế:

Ngăn chặn truy cập trái phép vào hệ thống.
Phân quyền rõ ràng giữa các vai trò người dùng để đảm bảo tính bảo mật và tính toàn vẹn của dữ liệu.
Khả năng mở rộng
Hệ thống được thiết kế để dễ dàng mở rộng trong tương lai. Các chức năng mới như quản lý thưởng, nghỉ phép có thể được bổ sung mà không làm ảnh hưởng đến các ca sử dụng hiện tại.

Lý do thiết kế:

Tạo ra một hệ thống linh hoạt, có thể đáp ứng được các yêu cầu thay đổi trong tương lai mà không gặp khó khăn.
Biểu đồ tuần tự
Biểu đồ tuần tự cho các ca sử dụng chính:

Đăng nhập:

Người dùng nhập tên đăng nhập và mật khẩu.
Hệ thống xác thực thông tin.
Nếu hợp lệ, cấp quyền truy cập vào giao diện chính.
Tính lương:

Quản lý yêu cầu hệ thống tính lương.
Hệ thống truy xuất dữ liệu từ cơ sở dữ liệu.
Áp dụng công thức tính lương và lưu kết quả.
Với cách thiết kế này, bạn có thể thấy rõ quy trình và lý do cho mỗi bước trong các ca sử dụng. Việc tự động hóa, bảo mật và phân quyền rõ ràng giúp hệ thống hoạt động hiệu quả và an toàn hơn.
