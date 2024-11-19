<<<<<<< HEAD
  1. Phân tích tất cả các ca sử dụng còn lại trong hệ thống Payroll System.
=======
 1. Phân tích tất cả các ca sử dụng còn lại trong hệ thống Payroll System.
>>>>>>> 0a09ab92c57aecd8781bb8f0515770078d214a33
    a, Run Payroll
 Mô Tả Ngắn Gọn
Ca sử dụng "Run Payroll" mô tả quy trình hệ thống xử lý việc thanh toán lương cho nhân viên, diễn ra tự động vào thứ Sáu hàng tuần và ngày làm việc cuối cùng của mỗi tháng. Quá trình này bao gồm việc truy xuất dữ liệu nhân viên cần được trả lương, tính toán tiền lương dựa trên các yếu tố liên quan và tiến hành các thao tác như in phiếu lương hoặc gửi yêu cầu chuyển khoản đến ngân hàng.

Các Thành Phần Của Ca Sử Dụng
- Tác Nhân Tham Gia (Actor):
Employee: Là người được trả lương và là đối tượng nhận kết quả từ ca sử dụng này.
Bank System: Là hệ thống bên ngoài nhận và xử lý các giao dịch chuyển khoản từ hệ thống.
Payroll System: Là hệ thống nội bộ, chịu trách nhiệm chính trong việc xử lý thanh toán lương.
- Các Yêu Cầu Chức Năng Chính:
Hệ thống phải tự động kích hoạt ca sử dụng vào các thời điểm đã định (thứ Sáu hàng tuần và ngày làm việc cuối cùng của tháng).
Tính toán chính xác tiền lương cho từng nhân viên dựa trên các dữ liệu đầu vào.
Thực hiện in phiếu lương hoặc gửi yêu cầu chuyển khoản tùy thuộc vào phương thức thanh toán của nhân viên.
Xử lý các trường hợp đặc biệt như hệ thống ngân hàng không khả dụng hoặc khi có nhân viên đã được đánh dấu để xóa sau khi thanh toán.
Luồng Sự Kiện
Luồng Chính (Basic Flow)
Khởi Tạo: Hệ thống tự động khởi chạy quy trình vào các ngày định sẵn (thứ Sáu hàng tuần và ngày làm việc cuối tháng).
Truy Xuất Nhân Viên: Hệ thống lấy danh sách các nhân viên cần được trả lương vào ngày hiện tại.
Tính Toán Lương: Hệ thống tính toán tiền lương của từng nhân viên dựa trên các bảng thời gian (timecards), đơn đặt hàng, và các thông tin như mức lương, phúc lợi, cùng với các khoản khấu trừ hợp pháp.
In hoặc Chuyển Khoản:
Nếu phương thức thanh toán là qua bưu điện hoặc nhận tại chỗ, hệ thống in phiếu lương.
Nếu phương thức là chuyển khoản trực tiếp, hệ thống tạo giao dịch ngân hàng và gửi đến hệ thống ngân hàng.
Kết Thúc: Quy trình kết thúc sau khi tất cả các nhân viên có lịch nhận lương trong ngày đã được xử lý thành công.
Luồng Thay Thế (Alternative Flows)
Hệ Thống Ngân Hàng Không Khả Dụng:
Nếu hệ thống ngân hàng gặp sự cố, hệ thống sẽ tiếp tục thử gửi yêu cầu chuyển khoản cho đến khi ngân hàng hoạt động trở lại.
Nhân Viên Bị Xóa:
Sau khi đã xử lý thanh toán cho nhân viên, nếu nhân viên đó đã được đánh dấu để xóa (theo yêu cầu từ ca sử dụng “Maintain Employee”), hệ thống sẽ tiến hành xóa nhân viên khỏi danh sách.
 Điều Kiện Trước và Sau Khi Thực Hiện
Điều Kiện Trước: Không có yêu cầu cụ thể nào được đặt ra trước khi ca sử dụng này được khởi chạy.
Điều Kiện Sau: Toàn bộ thanh toán cho các nhân viên trong lịch trình trả lương của ngày hiện tại đã được xử lý. Các giao dịch ngân hàng đã được gửi đi cho hệ thống ngân hàng, hoặc các phiếu lương đã được in.
 Yêu Cầu Phi Chức Năng
Tính Tự Động: Hệ thống cần phải tự động chạy quy trình này vào thời gian định sẵn mà không cần can thiệp thủ công.
Độ Tin Cậy: Phải có cơ chế xử lý nếu hệ thống ngân hàng không khả dụng, nhằm đảm bảo các giao dịch được hoàn thành khi ngân hàng hoạt động trở lại.
Bảo Mật: Thông tin tài chính của nhân viên và các giao dịch cần được bảo mật.
Điểm Mở Rộng
Không có điểm mở rộng nào trong ca sử dụng này.

Kết Luận
Ca sử dụng "Run Payroll" đóng vai trò quan trọng trong hệ thống quản lý lương. Nó giúp tự động hóa quy trình thanh toán lương định kỳ và đảm bảo tính chính xác trong việc chi trả cho nhân viên, bao gồm cả việc tính toán các khoản khấu trừ và phúc lợi. Các luồng thay thế giúp đảm bảo quy trình vẫn hoạt động kể cả khi gặp sự cố với hệ thống ngân hàng hoặc có thay đổi về danh sách nhân viên.
Biểu đồ lớp ca sử dụng Run Payroll: ![Diagram](https://www.planttext.com/api/plantuml/png/V9913e8m44NtFGLBJEG2B0oQk72XCS4B53fH8otOcIw8yMGkF99NK6X1YaGsJMS-yr_cz_Lu9aXSav45omkE6AnbLPGrG71ZGVE1ksz47AIap-fewufBy2iLhoKesWAToezuFxnQ1K81ENcDKBR7eQxwQJDsPmx6atP4lt_OEXT20w9VpBYwx7vGUPwNHj7Eo0oqtq9mTet195qdMrg_SEJx5QoSTpY66CmOWeIJM8Drf3KIo6uF6gu6SBHEDzfKWXFuhIx9kCzu_ZUprhX_3b6q6CKHkpoHEQufYGL1be0IpIDx0m00__y30000)
b, Maintain Purchase Order
Các luồng sự kiện chính:

Create a Purchase Order: Nhân viên tạo mới một đơn đặt hàng, bao gồm các thông tin liên hệ khách hàng, địa chỉ thanh toán, sản phẩm mua, và ngày đặt hàng. Hệ thống sẽ tạo và gán một mã số đơn hàng duy nhất.

Update a Purchase Order: Nhân viên yêu cầu chỉnh sửa một đơn hàng hiện có bằng cách cung cấp ID của đơn hàng và thay đổi các thông tin cần thiết nếu đơn hàng đang ở trạng thái mở (open).

Delete a Purchase Order: Nhân viên yêu cầu xóa một đơn hàng nếu đơn hàng đó là của họ và đang ở trạng thái mở. Hệ thống sẽ yêu cầu xác nhận trước khi xóa.

Các luồng thay thế:

Purchase Order Not Found: Khi ID không tồn tại, hệ thống thông báo lỗi và yêu cầu nhân viên nhập lại hoặc hủy thao tác.

Invalid Access to a Purchase Order: Nếu nhân viên cố gắng truy cập một đơn hàng không thuộc về họ, hệ thống hiển thị lỗi và yêu cầu nhập lại hoặc hủy thao tác.

Purchase Order is Closed: Nếu đơn hàng đã đóng, nhân viên không thể cập nhật hoặc xóa. Hệ thống hiển thị thông báo lỗi.

Delete Cancelled: Nếu nhân viên hủy xác nhận khi xóa đơn hàng, thao tác xóa bị hủy.

Điều kiện tiên quyết: Nhân viên phải đăng nhập vào hệ thống trước khi thực hiện các thao tác.

Điều kiện sau cùng: Nếu thành công, thông tin đơn hàng sẽ được thêm, cập nhật, hoặc xóa. Nếu không, trạng thái hệ thống không thay đổi.
Biểu đồ lớp ca sử dụng Run Payroll: ![Diagram](https://www.planttext.com/api/plantuml/png/X5DBQiCm5Dpx50-ld98GkZKbf2HT1Deca1CereiZqCVL9y6KdgoB7gbNg1pPJUMOr6336utUQ9x6tvzVSsE9jaxmn3BB4Lu8azQ_i76wE123iDOKDKnWmOani6Iar4GaIN4k5qe8PWnJ4kcJgBYg4U4zWUR1jbxH7BPMCra6N1A1CL9e91OxnRDWLgaS8cIKmr4n6dQuYWxik2YDGU9f9VStcr3aUAj9H_xet4RKpgPgYhx7mXch1Eg5yjCiRBouOvpxuf5IZSR4QvLMr1NMey_Cs8TDA6T_f9RUU0xDDu3-0gthTJ5ejsSuYrUl7ON-dPTMlU-cXL-lBkxD4UbpK-VWKzDnMU5PLBaTnulGjZOMHQTpHCtszVeaKPi3gp8VbNmmIsCOoi5EAOv4HhqgbAtbVtUKw7Nz_DRXvhBHhob_tC54f_SfJ2OpIE_INWZoDhnc6Y9ffY5L9ebvKOTswCtK2kwe9xVZQHY31yY3JHPJ-qSHH9BIKv8vIjhyqyaF0000__y30000)
c,Maintain Employee Information
Các luồng sự kiện chính:

Add an Employee: Người quản lý bảng lương thêm thông tin nhân viên mới, bao gồm các thông tin cá nhân, loại nhân viên, mức lương và các khoản khấu trừ thuế, y tế. Hệ thống sẽ tạo mã nhân viên duy nhất và đặt phương thức nhận bảng lương mặc định là "pickup".

Update an Employee: Người quản lý bảng lương yêu cầu cập nhật thông tin của nhân viên hiện có bằng cách cung cấp mã nhân viên (ID) và chỉnh sửa các thông tin cần thiết.

Delete an Employee: Người quản lý bảng lương yêu cầu xóa thông tin của một nhân viên nhất định. Hệ thống sẽ yêu cầu xác nhận xóa và đánh dấu nhân viên đó để tạo bảng lương cuối cùng, sau đó xóa khỏi hệ thống.

Các luồng thay thế:

Employee Not Found: Khi mã nhân viên không tồn tại, hệ thống sẽ thông báo lỗi và yêu cầu nhập lại hoặc hủy thao tác.

Delete Cancelled: Nếu người quản lý bảng lương hủy thao tác xóa nhân viên, hành động xóa sẽ bị hủy và quy trình sẽ quay lại từ đầu.

Điều kiện tiên quyết: Người quản lý bảng lương phải đăng nhập vào hệ thống trước khi thực hiện các thao tác.

Điều kiện sau cùng: Nếu thành công, thông tin của nhân viên sẽ được thêm, cập nhật, hoặc xóa. Nếu không thành công, trạng thái của hệ thống vẫn giữ nguyên.
Biểu đồ lớp ca sử dụng Run Payroll: ![Diagram](https://www.planttext.com/api/plantuml/png/X5DBJiCm4Dtd55PMBQ8BjbcW8bgaIXHLb0jCusbYrP_8dfHQY9Enu4XS0QT9seQa8b8Mdddpnc_c-UVhU-e8B9LAHYH88bk2q1H-DbU5D1wHBVJMM0KaZ6OJzYZ1EJOJa5bGKPGUZolmraZvm9NGmf45CfPzHApwe0ekUCBMP8NEwg06XTq8SDvs7A4gabF_SSBsHl0QLHOS22-1P-PRfl6zkkoLMeuIhzMsmCzMqKbzemARy_z2MkIRB_eIBJhN3JgJ2f1hJ4ihoB-KQeEsYo0up92NQRM0KCnDkP5OfmpbQAybYzne72BCJMcbVms3x1Oua61zDvOQfOHpWRsFhtYUXHAKiE2PfYduDCTqDqCfzcZz4YatVsRca5Q3i97ge7jBMNj7gDgLPAZHNhXXmKVZRgF0BBQ-pSyFmPgeq_xgDyP815qNAR2xjkJ9XEa6rmJvmwOCLnlqVdmNiydadiKtyTbAIU2k7vUB6YaLPf2Wmch8i8EyO3fA4o4TJL7pwld-0W00__y30000)
d, Login
Các luồng sự kiện chính:
Người dùng nhập tên và mật khẩu.
Hệ thống xác thực tên và mật khẩu đã nhập. Nếu thông tin hợp lệ, người dùng sẽ được đăng nhập vào hệ thống.
Các luồng thay thế:

Invalid Name/Password:
Nếu trong luồng chính, người dùng nhập tên và/hoặc mật khẩu không hợp lệ, hệ thống sẽ hiển thị thông báo lỗi. Người dùng có thể chọn quay lại bắt đầu từ luồng chính hoặc hủy thao tác đăng nhập, lúc này use case sẽ kết thúc.
Điều kiện tiên quyết: Hệ thống đang ở trạng thái đăng nhập và đã hiển thị màn hình đăng nhập.

Điều kiện sau cùng: Nếu đăng nhập thành công, người dùng sẽ được đăng nhập vào hệ thống. Nếu không thành công, trạng thái của hệ thống vẫn giữ nguyên.
Biểu đồ lớp ca sử dụng Run Payroll: ![Diagram](https://www.planttext.com/api/plantuml/png/P91D2W8n34RtFKMM8pWNc8KCZ2u4TJDuW6Z34EYqGrALGJoP2u_a5RG5yQ-hD2JVU-tzUgireiH3xqpaw0XMeMCF9JGELM7Es0dsnkppTQiaS3QGpk5PBsq5RHJstRktmPw-kyDpzHJaPzObK36fO1U28_Jcyg9aXNRKIFqBTaJ75YCrGfPyP7HQ_CAcVw2Fy9nYMGU7OyvVY0HPaofsb2oEWMrIo4yiozcNHPLi5TWRKvEtwRSU0000__y30000)
e, Create Employee Report
Các luồng sự kiện chính:

Nhân viên chọn loại báo cáo mà họ muốn tạo (có thể là “Tổng Giờ Làm Việc”, “Tổng Giờ Làm Việc Cho Một Dự Án”, “Nghỉ Phép/Ốm”, hoặc “Tổng Lương Năm Đến Nay”).
Hệ thống yêu cầu nhân viên cung cấp các tiêu chí báo cáo, bao gồm:
Loại báo cáo
Ngày bắt đầu và ngày kết thúc cho báo cáo
Nếu loại báo cáo là “Tổng Giờ Làm Việc Cho Một Dự Án”, hệ thống sẽ truy xuất và hiển thị danh sách các số charge có sẵn từ cơ sở dữ liệu Quản lý Dự án. Hệ thống yêu cầu nhân viên chọn một số charge.
Khi nhân viên cung cấp thông tin yêu cầu, hệ thống cung cấp báo cáo thỏa mãn tiêu chí báo cáo.
Nhân viên có thể yêu cầu hệ thống lưu báo cáo. Hệ thống sẽ yêu cầu nhân viên cung cấp tên và vị trí lưu báo cáo.
Khi nhân viên cung cấp thông tin yêu cầu và xác nhận việc lưu báo cáo, hệ thống lưu báo cáo theo tên và vị trí đã chỉ định.
Nếu nhân viên không chọn lưu báo cáo, báo cáo sẽ bị bỏ qua.
Các luồng thay thế:

Requested Information Unavailable:

Nếu trong luồng chính, thông tin yêu cầu không khả dụng, hệ thống sẽ hiển thị thông báo lỗi. Nhân viên có thể chọn quay lại bắt đầu từ luồng chính hoặc hủy thao tác, lúc này use case sẽ kết thúc.
Invalid Format or Insufficient Information:

Nếu trong luồng chính, nhân viên không cung cấp đủ thông tin để tạo báo cáo đã chọn, hệ thống sẽ yêu cầu nhân viên cung cấp thông tin còn thiếu. Nhân viên có thể nhập thông tin còn thiếu hoặc chọn hủy thao tác, lúc này use case sẽ kết thúc.
Điều kiện tiên quyết: Nhân viên phải đăng nhập vào hệ thống trước khi use case này bắt đầu.

Điều kiện sau cùng: Trạng thái của hệ thống không bị thay đổi bởi use case này.
Biểu đồ lớp ca sử dụng Run Payroll: ![Diagram](https://www.planttext.com/api/plantuml/png/T99HIiGm48RVSufvNA6zG91beUk3u8ge5vXDXnffafBC5XRnP3vu9AzWsgJPBM8VMcOo-Vx_7_hpzRqBZ9vFfXUikITeF24Jt9cXTsSYUAR1UOOQcXv3WBt6pgCHGirb6ViGC3sKw_jMmWjxRRlKjsXetL6pJg9l_FnvFGzbg8BPrpxEI9ZU5P1jB-MDpCuIBU2uPYt75VHE8MjdB-HhCv4pEjsApoLHpflp_3MMzTRcSlXhWwdL8cEvMJIUl7idnGUqs94XEv7mYA6iiIDktj1tz7WoH_9X4sq-wC2tYRITK6NrTRrTNCkyrh0-_LzFneGHIIC5KBCYs2Gfn2xccVwBNm000F__0m00)
f, Create Administrative Report
Các luồng sự kiện chính:

Quản trị viên Bảng lương yêu cầu hệ thống tạo một báo cáo hành chính.
Hệ thống yêu cầu Quản trị viên cung cấp các tiêu chí báo cáo, bao gồm:
Loại báo cáo (tổng giờ làm việc hoặc tổng lương năm đến nay).
Ngày bắt đầu và ngày kết thúc cho báo cáo.
Tên nhân viên (có thể là nhiều tên).
Khi Quản trị viên cung cấp thông tin yêu cầu, hệ thống cung cấp báo cáo thỏa mãn tiêu chí báo cáo.
Quản trị viên có thể yêu cầu hệ thống lưu báo cáo. Hệ thống sẽ yêu cầu Quản trị viên cung cấp tên và vị trí lưu báo cáo.
Khi Quản trị viên cung cấp thông tin yêu cầu và xác nhận việc lưu báo cáo, hệ thống lưu báo cáo theo tên và vị trí đã chỉ định.
Nếu Quản trị viên không chọn lưu báo cáo, báo cáo sẽ bị bỏ qua.
Các luồng thay thế:

Requested Information Unavailable:

Nếu trong luồng chính, thông tin yêu cầu không khả dụng, hệ thống sẽ hiển thị thông báo lỗi. Quản trị viên có thể chọn quay lại bắt đầu từ luồng chính hoặc hủy thao tác, lúc này use case sẽ kết thúc.
Invalid Format or Insufficient Information:

Nếu trong luồng chính, Quản trị viên không cung cấp đủ thông tin để tạo báo cáo đã chọn, hệ thống sẽ yêu cầu Quản trị viên cung cấp thông tin còn thiếu. Quản trị viên có thể nhập thông tin còn thiếu hoặc chọn hủy thao tác, lúc này use case sẽ kết thúc.
Điều kiện tiên quyết: Quản trị viên Bảng lương phải đăng nhập vào hệ thống trước khi use case này bắt đầu.

Điều kiện sau cùng: Trạng thái của hệ thống không bị thay đổi bởi use case này.
Biểu đồ lớp ca sử dụng Run Payroll: ![Diagram](https://www.planttext.com/api/plantuml/png/T95VIWGn3CRVUueyAinSeCYoiliYY8XwWJ0DIw5_XZGE3EB9VF18Ni7EjBDkKVlGqgz9lb_Ihu_FVH9aUVLEYHL7S6128RWrtWQRX57iHF14OsI17WuEKuAZnHEZLsfOhuyuStJk8YSol2bO5YxYdT7mB6p3gOW1FRNAiDeMcojUZvTvF0Tri68USuo6PU-0WcckVdHn9dh8fPE6-ynnKt9trxho5wk4KskqFNVWuf3xZU77zf8qrvcYDUfzwxjEfNRwcxhwjUH5REYhz7y79S2WuBbqXlXpx7s_sxXqdMfIQf_zbZ_-1W00__y30000)


  2. Viết code Java mô phỏng ca sử dụng Maintain Timecard.
Mô hình mô phỏng
Chương trình này bao gồm các lớp sau:
Lớp Employee: Đại diện cho một nhân viên.
Lớp Timecard: Quản lý thông tin về bảng thời gian làm việc của nhân viên.
Lớp TimecardManager: Quản lý các bảng thời gian làm việc của nhân viên.
Lớp Main: Chương trình chính để chạy mô phỏng.

Code Java mô phỏng ca sử dụng Maintain Timecard.

import java.util.*;

// Lớp đại diện cho một nhân viên
class Employee {
    private String name; // Tên nhân viên
    private String employeeId; // ID nhân viên

    // Constructor để khởi tạo tên và ID của nhân viên
    public Employee(String name, String employeeId) {
        this.name = name;
        this.employeeId = employeeId;
    }

    // Phương thức lấy tên nhân viên
    public String getName() {
        return name;
    }

    // Phương thức lấy ID nhân viên
    public String getEmployeeId() {
        return employeeId;
    }
}

// Lớp đại diện cho bảng thời gian làm việc của nhân viên
class Timecard {
    private String employeeId; // ID của nhân viên
    private Date startDate; // Ngày bắt đầu
    private Date endDate; // Ngày kết thúc
    private Map<String, Integer> hoursWorked; // Bản đồ lưu số giờ làm việc theo charge number
    private boolean isSubmitted; // Trạng thái đã gửi hay chưa
    private Date submittedDate; // Ngày gửi

    // Constructor khởi tạo bảng thời gian
    public Timecard(String employeeId) {
        this.employeeId = employeeId;
        this.startDate = new Date(); // Thiết lập ngày bắt đầu
        this.endDate = new Date(); // Thiết lập ngày kết thúc
        this.hoursWorked = new HashMap<>(); // Khởi tạo bản đồ giờ làm việc
        this.isSubmitted = false; // Mặc định chưa gửi
    }

    // Phương thức thêm giờ làm việc cho charge number
    public void addHours(String chargeNumber, int hours) {
        if (isSubmitted) {
            System.out.println("Timecard already submitted. No changes allowed.");
            return; // Không cho phép thêm giờ nếu đã gửi
        }
        if (hours < 0 || hours > 24) {
            System.out.println("Invalid number of hours. Please enter a valid number.");
            return; // Kiểm tra số giờ hợp lệ
        }
        hoursWorked.put(chargeNumber, hours); // Thêm giờ vào charge number
        System.out.println("Added " + hours + " hours for charge number " + chargeNumber);
    }

    // Phương thức gửi bảng thời gian
    public void submit() {
        if (isSubmitted) {
            System.out.println("Timecard already submitted.");
            return; // Không cho phép gửi nếu đã gửi
        }
        this.submittedDate = new Date(); // Thiết lập ngày gửi
        this.isSubmitted = true; // Đánh dấu đã gửi
        System.out.println("Timecard submitted on " + submittedDate);
    }

    // Phương thức kiểm tra trạng thái đã gửi
    public boolean isSubmitted() {
        return isSubmitted;
    }

    // Phương thức lấy giờ làm việc đã lưu
    public Map<String, Integer> getHoursWorked() {
        return hoursWorked;
    }
}

// Lớp quản lý các bảng thời gian
class TimecardManager {
    private Map<String, Timecard> timecards = new HashMap<>(); // Bản đồ lưu bảng thời gian theo ID nhân viên

    // Phương thức lấy bảng thời gian cho nhân viên
    public Timecard getTimecardForEmployee(Employee employee) {
        // Nếu chưa có bảng thời gian thì tạo mới
        return timecards.computeIfAbsent(employee.getEmployeeId(), k -> new Timecard(employee.getEmployeeId()));
    }
}

// Chương trình chính để chạy mô phỏng
public class Main {
    public static void main(String[] args) {
        TimecardManager timecardManager = new TimecardManager(); // Khởi tạo quản lý bảng thời gian
        Employee employee = new Employee("John Doe", "EMP001"); // Tạo nhân viên mới

        // Lấy bảng thời gian cho nhân viên
        Timecard timecard = timecardManager.getTimecardForEmployee(employee);

        // Nhân viên thêm giờ làm việc
        timecard.addHours("ProjectA", 8); // Thêm 8 giờ cho ProjectA
        timecard.addHours("ProjectB", 6); // Thêm 6 giờ cho ProjectB

        // Nhân viên gửi bảng thời gian
        timecard.submit();

        // Cố gắng thêm giờ làm việc sau khi đã gửi
        timecard.addHours("ProjectA", 4); // Đây không được phép

        // Hiển thị số giờ làm việc đã lưu
        System.out.println("Hours worked: " + timecard.getHoursWorked());
    }
}
<<<<<<< HEAD

=======
  
>>>>>>> 0a09ab92c57aecd8781bb8f0515770078d214a33
