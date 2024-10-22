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

