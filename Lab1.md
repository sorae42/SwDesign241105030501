# Phân tích kiến trúc hệ thống Payroll System
## 1. Phân tích kiến trúc
Kiểu kiến trúc _Model-View-Controller_ là lựa chọn phù hợp nhất cho hệ thống này.

Kiểu kiến trúc này sẽ giúp cho việc quản lý và bảo trì hệ thống và codebase trở nên dễ dàng hơn, giúp tăng tính mở rộng của hệ thống.

### Ý nghĩa các thành phần trong MVC
- Model: Chứa dữ liệu nghiệp vụ của hệ thống. Hệ thống này sẽ bao gồm các lớp như `Employee`, `Payroll`,...
- View: Hiện thị dữ liệu qua giao diện trực quan cho người dùng thông qua báo cáo, biểu đồ, các form nhập liệu,...
- Controller: Tiếp nhận và xử lý các yêu cầu từ người dùng ở các _View_, tương tác với _Model_ để lưu trữ dữ liệu và chọn _View_ phù hợp để hiển thị kết quả.

!(Packages - Payroll System)[https://www.planttext.com/api/plantuml/png/VLF1QiCm3BthAtJieFc1KafXRBT2sSRkNgnrfevjR6KZbFxxr3XjtIRq4B3VUvRqdiWwiOhSDXOWxOt3w1C1i65Bk5NrNkqeOIN7BdfhyRrBJ0r0o1Hkl2QBo-MhjvhYQeK7GAojIWbVcc1zHzH3Y4Olq3ZkpqurjC34qRXT3oYj8wLqWmNLDUHuG_pZvUsslFO2xe9KERVva9l0H_b68mnS1kyBPVIDWeyCnwkrP-_uv9dYOt-5xd0sCpkJJmlyzIRFAqaHqoJL1gqAQexVXgoUew2grEt8KHHbddOcr33tYQoLhLihh3WiksZVVjbHDiD6HzE7w6jPnK3FhjsFPJYVXluUnz8hSaaQe4dhOMWqnSLiCtkycwJSBLRLwj8ORXQC9NDvLABN161YfI8S9GMJmgBaoJkC0xvNm9gSbb_l7m00]

## 2. Cơ chế phân tích
- Hệ thống cần được tích hợp và có thể truy xuất thông từ CSDL dự án cũ Project Management Database. Vì lý do chi phí, Acme muốn tận dụng lại cơ sở dữ liệu cũ để sử dụng cho hệ thống mới này.
- Hệ thống cần lưu trữ thông tin về nhân viên, bảng chấm công, hoá đơn mua hàng,... để có thể truy cập và cập nhật dữ liệu. Hệ thống cần phải có tính bền vững giúp duy trì dữ liệu lâu dài, đảm bảo CSDL không bị mất khi hệ thống không còn hoạt động.
- Hệ thống phải đảm bảo có mức bảo mật cao nhất có thể, chỉ cho phép nhân viên truy cập và chỉnh sửa thông tin cá nhân của họ, ngăn chặn truy cập trái phép để bảo vệ những thông tin nhạy cảm.