1. Phân tích kiến trúc
   1.1 Đề xuất kiến trúc
     - Kiến trúc tổng quát
       Kiến trúc của Hệ thống Quản lý Tiền lương sẽ được xây dựng dựa trên mô hình client-server, với các thành phần chính sau:
       Giao diện người dùng (Client): Ứng dụng desktop cho nhân viên và quản trị viên.
       Backend Server: Máy chủ xử lý logic nghiệp vụ và tương tác với cơ sở dữ liệu.
       Cơ sở dữ liệu (Database): Lưu trữ thông tin nhân viên, tiền lương, thời gian làm việc, đơn đặt hàng mua hàng và kết nối với cơ sở dữ liệu quản lý dự án.
       -Các thành phần trong kiến trúc
        + Giao diện người dùng (UI)
          Ý nghĩa: Cung cấp giao diện tương tác cho nhân viên và quản trị viên để nhập thông tin, truy xuất báo cáo và thực hiện các thao tác liên quan đến tiền lương.
          Lý do lựa chọn: Một giao diện người dùng thân thiện giúp người dùng dễ dàng thao tác mà không cần kiến thức kỹ thuật sâu.
        + API (Application Programming Interface)
          Ý nghĩa: Đóng vai trò là cầu nối giữa giao diện người dùng và backend, cho phép truyền tải dữ liệu và yêu cầu từ người dùng đến server.
          Lý do lựa chọn: Sử dụng API giúp tổ chức mã nguồn rõ ràng và dễ bảo trì, đồng thời cho phép phát triển các ứng dụng khác (như mobile app) trong tương lai.
        + Backend Server
          Ý nghĩa: Xử lý logic nghiệp vụ, quản lý các yêu cầu từ người dùng, tính toán tiền lương và truy xuất dữ liệu từ cơ sở dữ liệu.
          Lý do lựa chọn: Backend server giúp tách biệt logic nghiệp vụ với giao diện người dùng, dễ dàng bảo trì và mở rộng trong tương lai.
        + Cơ sở dữ liệu (DB)
          Ý nghĩa: Lưu trữ thông tin liên quan đến nhân viên, tiền lương, đơn đặt hàng mua hàng và các thông tin khác cần thiết cho hệ thống.
          Lý do lựa chọn: Sử dụng cơ sở dữ liệu quan hệ để dễ dàng quản lý và truy vấn dữ liệu một cách hiệu quả.
        + Project Management Database
          Ý nghĩa: Cơ sở dữ liệu kế thừa lưu trữ thông tin về dự án và số charge, mà hệ thống mới sẽ truy cập để thực hiện tính toán tiền lương.
          Lý do lựa chọn: Tránh việc thay thế hệ thống cũ, tiết kiệm chi phí và đảm bảo tính nhất quán của dữ liệu.
          
   1.2 Biểu đồ package mô tả kiến trúc.
    ![Diagram](https://www.planttext.com/api/plantuml/png/T99DQiCm48NtFiMGVJOvG4dZT578mYJTXIucyjI8wiUCv80fFLaNFLAl4Dc2D1RIzisJtlT6-llvtJgFx0UjgXx59tO4guR9aV7efJLmm95u1LyLmFb5zygEHF1gFF472dgVvETMIoETP_IMazcHUilUFQhVrN_KRd3Ia7Dmi9qKYx0tgKaWjz2m5S4YJJVVsE38LYceKOb1pP2pNbkjPR05vdGK8S85S2A-oXHYZnxpFQV91LsiSWTQg2TKv9RIVhU1sXf38XA4hDpgOBr-AjGisxFjYoyGpsJgPsEZErC-cvhWFxWBBn4FfFjAjrM4s99ffszw0m00__y30000)
2. Cơ chế phân tích
   Phân tích yêu cầu
Xác thực và phân quyền người dùng

Yêu cầu: Hệ thống cần đảm bảo rằng chỉ những người dùng hợp lệ mới có thể truy cập vào hệ thống, và mỗi người dùng phải chỉ có quyền truy cập vào thông tin phù hợp với vai trò của họ.
Cơ chế đề xuất:
Cơ chế xác thực người dùng: Xác thực danh tính thông qua tên người dùng và mật khẩu.
Cơ chế phân quyền: Xác định quyền truy cập dựa trên vai trò (nhân viên, quản trị viên).
Quản lý thông tin nhân viên

Yêu cầu: Hệ thống cần lưu trữ và quản lý thông tin chi tiết của 5,000 nhân viên, bao gồm thông tin cá nhân, lương, giờ làm việc và đơn đặt hàng mua hàng.
Cơ chế đề xuất:
Cơ chế quản lý cơ sở dữ liệu: Tổ chức cơ sở dữ liệu để lưu trữ và truy xuất thông tin nhân viên, thời gian làm việc, và đơn đặt hàng mua hàng.
Tính toán và xử lý tiền lương

Yêu cầu: Hệ thống cần tính toán tiền lương cho các loại nhân viên khác nhau (theo giờ, cố định, có hoa hồng) dựa trên thông tin thời gian làm việc và doanh thu.
Cơ chế đề xuất:
Cơ chế tự động hóa thanh toán: Tự động tính toán và phát hành thanh toán cho nhân viên vào đúng ngày quy định mà không cần can thiệp thủ công.
Báo cáo và truy xuất thông tin

Yêu cầu: Nhân viên và quản trị viên cần có khả năng truy xuất và báo cáo thông tin liên quan đến giờ làm việc, lương, và thời gian nghỉ phép còn lại.
Cơ chế đề xuất:
Cơ chế báo cáo và phân tích: Cung cấp các báo cáo chi tiết để giúp người dùng truy xuất và phân tích dữ liệu một cách dễ dàng.
Bảo mật và bảo vệ dữ liệu

Yêu cầu: Dữ liệu tiền lương và thông tin cá nhân cần được bảo vệ khỏi các truy cập trái phép và bảo mật trong quá trình lưu trữ và truyền tải.
Cơ chế đề xuất:
Cơ chế mã hóa dữ liệu: Sử dụng mã hóa để bảo vệ thông tin nhạy cảm trong cơ sở dữ liệu và khi truyền qua mạng.
Cơ chế kiểm tra và ghi log: Theo dõi và ghi lại các hành động của người dùng trong hệ thống để phát hiện và xử lý các vấn đề bảo mật.
Tích hợp với hệ thống hiện tại

Yêu cầu: Hệ thống mới cần tích hợp và truy cập thông tin từ cơ sở dữ liệu quản lý dự án hiện có mà không làm thay đổi dữ liệu trong đó.
Cơ chế đề xuất:
Cơ chế truy cập cơ sở dữ liệu kế thừa: Cung cấp các phương thức để truy cập thông tin từ cơ sở dữ liệu DB2 mà không cập nhật dữ liệu.
Danh sách cơ chế phù hợp
a, Cơ chế xác thực người dùng
b, Cơ chế phân quyền
c, Cơ chế quản lý cơ sở dữ liệu
d, Cơ chế tự động hóa thanh toán
e, Cơ chế báo cáo và phân tích
f, Cơ chế mã hóa dữ liệu
g, Cơ chế kiểm tra và ghi log
h, Cơ chế truy cập cơ sở dữ liệu kế thừa
3.  Phân tích cho ca sử dụng Select Payment Method, bao gồm xác định các lớp phân tích, mô tả hành vi thông qua biểu đồ sequence, và xác định nhiệm vụ, thuộc tính, và quan hệ giữa các lớp phân tích.

1. Xác định các lớp phân tích
Dựa trên mô tả ca sử dụng, có thể xác định các lớp phân tích sau:

Employee: Đại diện cho nhân viên trong hệ thống.

Thuộc tính:
employeeId: Mã nhân viên
name: Tên nhân viên
paymentMethod: Phương thức thanh toán
Nhiệm vụ:
Chọn phương thức thanh toán.
Cung cấp thông tin địa chỉ hoặc thông tin ngân hàng nếu cần.
PaymentMethod: Đại diện cho các phương thức thanh toán của nhân viên.

Thuộc tính:
methodType: Loại phương thức (pick up, mail, direct deposit)
address: Địa chỉ (nếu phương thức là "mail")
bankName: Tên ngân hàng (nếu phương thức là "direct deposit")
accountNumber: Số tài khoản ngân hàng (nếu phương thức là "direct deposit")
Nhiệm vụ:
Lưu trữ thông tin phương thức thanh toán mà nhân viên chọn.
System: Đại diện cho hệ thống xử lý thông tin.

Nhiệm vụ:
Xử lý yêu cầu của nhân viên về việc chọn phương thức thanh toán.
Cập nhật thông tin phương thức thanh toán của nhân viên.

Biểu đồ Sequence: ![Diagram](https://www.planttext.com/api/plantuml/png/T99DQiCm48NtFiMGVJOvG4dZT578mYJTXIucyjI8wiUCv80fFLaNFLAl4Dc2D1RIzisJtlT6-llvtJgFx0UjgXx59tO4guR9aV7efJLmm95u1LyLmFb5zygEHF1gFF472dgVvETMIoETP_IMazcHUilUFQhVrN_KRd3Ia7Dmi9qKYx0tgKaWjz2m5S4YJJVVsE38LYceKOb1pP2pNbkjPR05vdGK8S85S2A-oXHYZnxpFQV91LsiSWTQg2TKv9RIVhU1sXf38XA4hDpgOBr-AjGisxFjYoyGpsJgPsEZErC-cvhWFxWBBn4FfFjAjrM4s99ffszw0m00__y30000)

 Nhiệm vụ của từng lớp phân tích
Employee: Tương tác với hệ thống để chọn phương thức thanh toán và cung cấp thông tin cần thiết.
PaymentMethod: Lưu trữ thông tin phương thức thanh toán mà nhân viên đã chọn.
System: Quản lý yêu cầu và cập nhật thông tin phương thức thanh toán cho nhân viên.
Biểu đồ lớp mô tả lớp phân tích: ![Diagram](https://www.planttext.com/api/plantuml/png/T99DQiCm48NtFiMGVJOvG4dZT578mYJTXIucyjI8wiUCv80fFLaNFLAl4Dc2D1RIzisJtlT6-llvtJgFx0UjgXx59tO4guR9aV7efJLmm95u1LyLmFb5zygEHF1gFF472dgVvETMIoETP_IMazcHUilUFQhVrN_KRd3Ia7Dmi9qKYx0tgKaWjz2m5S4YJJVVsE38LYceKOb1pP2pNbkjPR05vdGK8S85S2A-oXHYZnxpFQV91LsiSWTQg2TKv9RIVhU1sXf38XA4hDpgOBr-AjGisxFjYoyGpsJgPsEZErC-cvhWFxWBBn4FfFjAjrM4s99ffszw0m00__y30000)

4. Phân tích cho ca sử dụng Maintain Timecard, bao gồm xác định các lớp phân tích, mô tả hành vi thông qua biểu đồ sequence, và xác định nhiệm vụ, thuộc tính, và quan hệ giữa các lớp phân tích.

1. Xác định các lớp phân tích
Dựa trên mô tả ca sử dụng, có thể xác định các lớp phân tích sau:

Employee: Đại diện cho nhân viên trong hệ thống.

Thuộc tính:
employeeId: Mã nhân viên
name: Tên nhân viên
paymentMethod: Phương thức thanh toán
Nhiệm vụ:
Ghi lại thời gian làm việc vào bảng thời gian.
Yêu cầu hệ thống gửi bảng thời gian.
Timecard: Đại diện cho bảng thời gian của nhân viên.

Thuộc tính:
timecardId: Mã bảng thời gian
startDate: Ngày bắt đầu
endDate: Ngày kết thúc
submittedDate: Ngày nộp
status: Trạng thái bảng thời gian (đã nộp hoặc chưa)
hoursWorked: Danh sách số giờ làm việc cho từng charge number
Nhiệm vụ:
Lưu trữ thông tin giờ làm việc.
Cập nhật trạng thái nộp bảng thời gian.
ChargeNumber: Đại diện cho số charge mà nhân viên ghi giờ làm việc.

Thuộc tính:
chargeNumberId: Mã charge
description: Mô tả charge
Nhiệm vụ:
Cung cấp thông tin về charge number cho nhân viên khi ghi giờ.
ProjectManagementDatabase: Đại diện cho cơ sở dữ liệu quản lý dự án.

Nhiệm vụ:
Cung cấp danh sách charge numbers cho nhân viên.
Kiểm tra tính khả dụng của charge numbers.

Biểu đồ Sequence: ![Diagram](https://www.planttext.com/api/plantuml/png/T99DQiCm48NtFiMGVJOvG4dZT578mYJTXIucyjI8wiUCv80fFLaNFLAl4Dc2D1RIzisJtlT6-llvtJgFx0UjgXx59tO4guR9aV7efJLmm95u1LyLmFb5zygEHF1gFF472dgVvETMIoETP_IMazcHUilUFQhVrN_KRd3Ia7Dmi9qKYx0tgKaWjz2m5S4YJJVVsE38LYceKOb1pP2pNbkjPR05vdGK8S85S2A-oXHYZnxpFQV91LsiSWTQg2TKv9RIVhU1sXf38XA4hDpgOBr-AjGisxFjYoyGpsJgPsEZErC-cvhWFxWBBn4FfFjAjrM4s99ffszw0m00__y30000)
 Nhiệm vụ của từng lớp phân tích
Employee: Tương tác với hệ thống để ghi lại giờ làm việc và nộp bảng thời gian.
Timecard: Chịu trách nhiệm lưu trữ và xử lý thông tin giờ làm việc, cũng như quản lý trạng thái của bảng thời gian.
ChargeNumber: Cung cấp thông tin liên quan đến charge mà nhân viên ghi giờ làm việc.
ProjectManagementDatabase: Cung cấp danh sách charge numbers và kiểm tra tính khả dụng của chúng.
Biểu đồ lớp mô tả lớp phân tích:![Diagram](https://www.planttext.com/api/plantuml/png/T99DQiCm48NtFiMGVJOvG4dZT578mYJTXIucyjI8wiUCv80fFLaNFLAl4Dc2D1RIzisJtlT6-llvtJgFx0UjgXx59tO4guR9aV7efJLmm95u1LyLmFb5zygEHF1gFF472dgVvETMIoETP_IMazcHUilUFQhVrN_KRd3Ia7Dmi9qKYx0tgKaWjz2m5S4YJJVVsE38LYceKOb1pP2pNbkjPR05vdGK8S85S2A-oXHYZnxpFQV91LsiSWTQg2TKv9RIVhU1sXf38XA4hDpgOBr-AjGisxFjYoyGpsJgPsEZErC-cvhWFxWBBn4FfFjAjrM4s99ffszw0m00__y30000)
5. Hợp nhất kết quả phân tích 02 ca sử dụng
Hợp nhất hai ca sử dụng cho thấy sự tương tác giữa các lớp và cách mà thông tin được xử lý trong hệ thống. Mỗi ca sử dụng đóng vai trò quan trọng trong việc đảm bảo rằng nhân viên có thể quản lý thông tin thanh toán và giờ làm việc một cách hiệu quả.

Employee là trung tâm của cả hai ca sử dụng, tương tác với hệ thống để thực hiện các chức năng liên quan đến thanh toán và bảng thời gian.
System đóng vai trò là bộ điều phối, quản lý tất cả các yêu cầu và cập nhật thông tin cho nhân viên.
PaymentMethod và Timecard là các lớp lưu trữ thông tin cụ thể về phương thức thanh toán và giờ làm việc của nhân viên, tương ứng.

