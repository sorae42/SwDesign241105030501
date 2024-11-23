# Thiết kế ca sử dụng cho hệ thống Payroll System
## 1. Ca sử dụng Login
### 1.1. Mô tả tương tác giữa các đối tượng
- Người dùng nhập thông tin đăng nhập (tên đăng nhập và mật khẩu) vào form đăng nhập và xác nhận.
- Hệ thống tiến hành xác thực thông tin đăng nhập với cơ sở dữ liệu.
- Nếu thông tin hợp lệ thì người dùng được phép truy cập vào hệ thống; còn không, hệ thống sẽ hiển thị lỗi cho người dùng.

### 1.2. Đơn giản hóa biểu đồ tuần tự qua các subsystem
- Login Form (Giao diện): Nhận thông tin tài khoản từ người dùng.
- Auth System (Hệ thống xác thực): Xác minh thông tin đăng nhập.
- Database (Cơ sở dữ liệu): Quản lý dữ liệu tài khoản.

![](https://planttext.com/api/plantuml/png/VP6nJiCm48PtFyMfUr-W0ogL1KYjAg4Qn6g2bLXGExATeIFgmC322o2146C5I2p40qCgtiDlmZaPudRevfE_x_uxUsmTDwvQtX5xAnKORGKXF7FQm8KLXfHuApDPSkLWCDCvCYVQB0V0BRHbh7QfuyeLi5XP9peirbsvor7k-3MteeNeX90O2CEZlY-CO5w4UbC2AvflbGF3UDQyI9WMEjHlYlGeUdqGYgV1RsJgRP-sQpns3Kd2eaadQ31JhU0orEyAQF0VC9F1FrGmp_y-Wt-MG9iVbHD4X_jPpE0mgFhxGsOQkRVbDDI_3iwhsEQgUSrmxk2_idGzDDht6S4PTb-h5dbCJJ8MwYR-v3y0)

### 1.3. Mô tả hành vi về lưu trữ
- Cơ sở dữ liệu lưu trữ thông tin về người dùng, trong đó bao gồm có tên người dùng và mật khẩu.
- Hệ thống sẽ xử lý xác thực thông tin đăng nhập và không lưu bất kì thông tin nào.

### 1.4. Cải tiến luồng sự kiện
1. Người dùng truy cập vào form đăng nhập.
2. Nhập thông tin đăng nhập.
3. Nhấn nút "Đăng nhập"
4. Hệ thống sẽ xác thực thông tin:
	- Nếu hợp lệ, hệ thống sẽ chuyển hướng cho người dùng.
	- Nếu không hợp lệ, hệ thống hiển thị lỗi cho người dùng.
	
### 1.5. Hợp nhất các lớp và subsystem
- Các lớp và subsystem liên quan đến chức năng đăng nhập sẽ được gộp thành LoginModule.
- LoginModule cũng sẽ được gộp cùng với Auth System, tạo thành AuthModule.

Lý do:
- Xử lý hiệu quả và an toàn trong hệ thống xác thực khi làm việc với cơ sở dữ liệu.
- Quản lý lỗi dễ dàng và thông báo rõ ràng lỗi, nâng cao trải nghiệm cho người dùng.

## 2. Ca sử dụng Maintain Timecard
### 2.1. Mô tả tương tác giữa các đối tượng
- Nhân viên ghi lại thời gian làm việc vào bảng chấm công, đồng thời liên kết dữ liệu này với thông tin dự án từ hệ thống quản lý dự án.
- Dữ liệu chấm công sau khi được xử lý sẽ được lưu vào cơ sở dữ liệu.

### 2.2. Đơn giản hóa biểu đồ tuần tự qua các subsystem
- Employee: Tương tác với Quản lý thẻ chấm công để chỉnh sửa thông tin chấm công.
- Timecard Manager: Cập nhật và lưu trữ dữ liệu thẻ chấm công.
- Payroll System: Dựa vào dữ liệu từ thẻ chấm công để tính toán lương.

![](https://planttext.com/api/plantuml/png/VP51IiGm58RtESMxm5oWYs4MkXG4lS0p3MqmJKloMkXIN8XBRs0H4OIY2rVDCZBto4rCYYDsB6v2uBtlp___sLb2GssbcBsM6anj1J3aL1iuhHfLzqAm9cv8BXlK19Uo4XnDVeOQ2s4MinCal4Ax1CwnDxLI5xqbKJ5s48NDzbWhWzw_ji33zD82cRPFrx41AiFaWCVpkGBkFtJ1ZaZOHBM3SXRPC3r15zmDvC6zWPB1tRLhEl-wYPlkNfTWWnjnXOREFq8HXn9Kc0RvrzNsfvBiEukE_4WpgVRlAMOoIEMiHrApHLshjkPckcX3_-BMx7q-17SBvCUOWMe_wFJaVeYnTqBdwSk_0000)

### 2.3. Mô tả hành vi về lưu trữ
Database: Quản lý và lưu trữ thông tin thẻ chấm công của nhân viên.
Timecard Manager: Cung cấp các chức năng truy xuất và cập nhật thông tin thẻ chấm công.
Payroll System: Lấy dữ liệu từ Timecard Manager để tính lương mà không thực hiện lưu trữ.

### 2.4. Cải tiến luồng sự kiện
- Nhân viên truy cập giao diện nhập chấm công.
- Hệ thống quản lý dự án cung cấp danh sách các dự án và mã chi phí tương ứng.
- Nhân viên chọn dự án phù hợp và nhập số giờ làm việc.
- Dữ liệu sau khi nhập được lưu vào cơ sở dữ liệu và hiển thị thông báo xác nhận thành công.

* Luồng ngoại lệ:
- Khi không tìm thấy dự án: Hệ thống hiện thị lỗi và cho phép nhân viên tìm lại mã dự án.
- Nếu thông tin nhập không hợp lệ: Hệ thống hiển thị lỗi và yêu cầu nhập lại thông tin cho chính xác.
- Nếu hệ thống lưu dữ liệu không thành công: Hiển thị lỗi và yêu cầu người dùng thử lại sau.

### 2.5. Hợp nhất các lớp và subsystem
- TimecardModule bao gồm Timecard và Timecard Manager sẽ quản lý việc chấm công.

## 3. Ca sử dụng Run Payroll
### 3.1. Mô tả tương tác giữa các đối tượng
- Payroll System nhận lệnh tính lương từ đồng hồ hệ thống (sử dụng Task Scheduler).
- Tính lương dựa trên Timecard và các dữ liệu liên quan.
- Gửi thông tin thanh toán đến Bank System để chuyển khoản.
- (Tùy chọn) Gửi báo cáo lương đến PrinterService để in.

### 3.2. Đơn giản hóa biểu đồ tuần tự qua các subsystem
- Payroll System: Chịu trách nhiệm tính lương và gửi kết quả cho Bank System và PrinterService.
- Bank System: Xử lý thanh toán chuyển khoản.
- Printer Service: In báo cáo lương.
- System Clock: Kích hoạt Payroll System theo lịch trình.

![](https://planttext.com/api/plantuml/png/RL1B2i8m4Dtd54FtNg0B4Ls9cq9Tk8qncD1qKf9Hw75oW89hnLMWz-XDhDHViPjPlC-ynrjuuevEfM6-q0ZEUicu8EiWhpt9ScMiA5ZLQxJG5KU2ZDVE6ZFG8sR9iPY0aynf9EbowSvQo0IuXnV4s4yApERZvobiOYCKADjTmoUOZJGJfcriK07P611CUsa37lyztwufxBfR0oRUWHH_EoTIXiefh17sCLWG_M4BYOVdUWy0)
### 3.3. Mô tả hành vi về lưu trữ
- Payroll System không lưu trữ trực tiếp các thông tin về lương mà lấy thông tin từ cơ sở dữ liệu (Timecard và User).
- Bank System và Printer không lưu trữ thông tin thanh toán hay báo cáo mà chỉ xử lý và thực hiện các hành động cụ thể (chuyển khoản và in báo cáo).

### 3.4. Cải tiến luồng sự kiện
- Quy trình tính lương tự động bắt đầu vào ngày được thiết lập trước.
- Hệ thống truy xuất dữ liệu chấm công và thông tin nhân viên từ cơ sở dữ liệu.
- Tiền lương được tính dựa trên dữ liệu chấm công, các khoản khấu trừ và đơn hàng (nếu có).
- Phiếu lương được gửi đến ngân hàng hoặc in ra.

* Luồng ngoại lệ:
- Hệ thống ngân hàng không hoạt động: Hệ thống sẽ thử lại trong một khoảng thời gian nhất định sau này.
- Hệ thống ngân hàng xử lý thất bại thì hệ thống sẽ báo lỗi.
- Nếu việc xử lý không hoàn tất, hệ thống sẽ lưu lại quy trình và chuyển đến thông báo cho bộ phận phụ trách.