# Phân tích kiến trúc hệ thống Payroll System
## 1. Phân tích kiến trúc
Kiểu kiến trúc _Model-View-Controller_ là lựa chọn phù hợp nhất cho hệ thống này.

Kiểu kiến trúc này sẽ giúp cho việc quản lý và bảo trì hệ thống và codebase trở nên dễ dàng hơn, giúp tăng tính mở rộng của hệ thống.

### Ý nghĩa các thành phần trong MVC
- Model: Chứa dữ liệu nghiệp vụ của hệ thống. Hệ thống này sẽ bao gồm các lớp như `Employee`, `Payroll`,...
- View: Hiện thị dữ liệu qua giao diện trực quan cho người dùng thông qua báo cáo, biểu đồ, các form nhập liệu,...
- Controller: Tiếp nhận và xử lý các yêu cầu từ người dùng ở các _View_, tương tác với _Model_ để lưu trữ dữ liệu và chọn _View_ phù hợp để hiển thị kết quả.

![Packages - Payroll System](https://www.planttext.com/api/plantuml/png/XLJ1JiCm3BtdAwoT2jiENAjfceJWDca2n3qqPaHBaoX9GHNQl-CbATtQKGvL6llvsU_LwiO7xa9JAyRyGMfmnYDZGGQ5iEFLWU_Hmv9UMsUKWkVM1wmPioa5MoDGmMhrQ9H0jrx3DmEe5FSU7cghJ8iOGq0SKfGWTSWtpMiimGSdzJw7k10ElHz4BMzhr66BuSCGm-xycY6XjSJLDNoX6oMEz8o6oRaK75Abw1DQum8xzYBlZGudzUYcbPxXakOvAIgmjlriDoLy6fdcdfDr6702q5Z1Xu05l4jKeZDf0GJX9N3TNfJkKQEZugIce5pM5RCLLrMZA4qMZFeBqxofaODv0yOQhJCLVRMSB_efZkSUlahycdOl8ZAdaDugtdQfAGyJikl-Bp3xuUBHcJAO-NTpPtSpM2xNyRpOeAk8otLYLxOYeWbyszD12JNNvD0KFf4Fx2-XyUZ_xZDe5EsbchXIdetv9egoTzHiWrgSVXO_)

## 2. Cơ chế phân tích
- Hệ thống cần được tích hợp và có thể truy xuất thông từ CSDL dự án cũ Project Management Database. Vì lý do chi phí, Acme muốn tận dụng lại cơ sở dữ liệu cũ để sử dụng cho hệ thống mới này.
- Hệ thống cần lưu trữ thông tin về nhân viên, bảng chấm công, hoá đơn mua hàng,... để có thể truy cập và cập nhật dữ liệu. Hệ thống cần phải có tính bền vững giúp duy trì dữ liệu lâu dài, đảm bảo CSDL không bị mất khi hệ thống không còn hoạt động.
- Hệ thống phải đảm bảo có mức bảo mật cao nhất có thể, chỉ cho phép nhân viên truy cập và chỉnh sửa thông tin cá nhân của họ, ngăn chặn truy cập trái phép để bảo vệ những thông tin nhạy cảm.

## 3. Phân tích ca sử dụng Payment
### 3.1. Các lớp phân tích
- **Boundary**: `PaymentForm`, `ProjectManagementDatabase`
- **Control**: `PaymentController`
- **Entity**: `Employee`

### 3.2. Nhiệm vụ của từng lớp phân tích
- **PaymentForm**: Hiển thị giao diện và các trường nhập để người dùng nhập thông tin thanh toán.
- **ProjectManagementDatabase**: Truy xuất thông tin theo phương thức thanh toán hiện tại từ CSDL để hiển thị cho người dùng.
- **PaymentController**: Xử lý các yêu cầu thanh toán.
- **Employee**: Chứa các thông tin cá nhân và phương thức liên quan đến quản lý nhân viên.

![Biểu đồ lớp cho ca sử dụng Payment](https://www.planttext.com/api/plantuml/png/VLDBRi8m4Dtx5BDhKCK58eHG2qWia5g92mpnDBWujcKxI575keVegYVe0LZs9Doa-JWavRVmOZv-d_5uuZnQdsUICRSL2gnsn9Z1P8ifmPFE5KTRm6WqrvAJ7O_XWm4a4fs35omoKdwkRLPd0HwvS4PYKQMYGGmxBNXJICc7zeLwqrMj5vOj-_9qm5Q_K-ANg4eHLTCKFQxHKKjZoLj1EmeOI_8RpIFAZDG5qOB789JlE9fwpRBlp3rhvQsMTxs57acsfJPM9-HSg5USCSm2SUVu7z5CUU5lpB2z6k2781hn8LAOKGokTAlIa4BERIdWB6lwJY-DLos-CDHfNPNHwMdQv9Gy2kcYlf7paJIOxJYoEbhLq2T1jVi7UCrHmUPu-8HK70y_2CdlTmBoUFWohByxm-7uohnBl7oTYNPjeW6xxAbltboM6AxloIsaqrl4a1kEdjf49u5DIF7gj_m1)

![Biểu đồ tuần tự cho ca sử dụng Payment](https://www.planttext.com/api/plantuml/png/LP4nRiCm34LtdO9ZEkG27Oe0jW9aCE351w0j9bLhImP51_3jIzaoaexYV_oVf2v9a6MPHfD-VG2EYGmE4XcwH0oOe3DzN893Ng75TQ8WryXJLjgh6M8GZkEXLFjpt3lRwgsLumyDqc301sMqHi4U4srWKnijULd1JlCOLzhArfWEpb-Q0vzWWwXhoO5RkEiGA3u6etA6AeNIqazU2dJwC5hCKbEhnYJiwKb5RKY-epjHoRivfPKx7rQABnpW7rtyhChBx53ecFQLQ5yEUfkxrqljwDPxBEDycaTSOIxh57JVnrmekFmZVm00)

## 4. Phân tích ca sử dụng Maintain Timecard 
### 4.1. Các lớp phân tích: 
- **Boundary**: `TimecardForm`, `ProjectManagementDatabase`
- **Control**: `TimecardController`
- **Entity**: `Employee`, `Timecard` 
### 4.2. Nhiệm vụ của từng lớp phân tích: 
**TimecardForm**: Hiển thị giao diện và các trường input để người dùng nhập thông tin vào.
**ProjectManagementDatabase**: Truy xuất thông tin theo timecard method hiện tại để hiển thị lên cho người dùng.
**TimecardController**: Xử lý các yêu cầu về chấm công.
**Employee**: Chứa các thông tin cá nhân và phương thức liên quan đến quản lý nhân viên.
**Timecard**: Đại diện cho thẻ chấm công, chứa các thông tin và phương thức liên quan đến việc chấm công.

![Biểu đồ lớp cho ca sử dụng Maintain Timecard](https://www.planttext.com/api/plantuml/png/VLEzJiCm4Dxz5ASkj407rgYg4BILEY21XCHyZO_KrF55jbDKeSuy11DFm0Dqv4dw9ZXjagP_31dy-Vpzt5rkdKVhyrGBuMRAW6L7GcGOpp0XkEFSIBGBwFL6h2NPVXy-142iqJbuLYd5QEM8RRg10QwaSfd6HG6rEn7CMSdjHKA-gX-RLoukc-TGj0nVpVre-OrY_u0c-4Z9-05wdA2ZIiYIjuhcL96qASqqBuZ6CW9bV8D_mxtSfRfduoth_qELHPfifPXPZicvfc04mrBr6do9xtJtyizHAub-v_Ta_OHP4vf3nqFZbJypXSf1QRCBQjk0ycGmfGXSQ9P9IWYbj2787bhCfs8Qa4UbNMD-mSfXVsgv8bG4OJnK0bFEhNjXEwDWH78-qNIq0gSaWiW5FELeOBfUVKAYrgiVXFZtEmQzNdrbOc_Vkjt-gLc5KFaaLRLGkoDEL1MFpszO14VBTPQbxdu4ULQqeW8QJ-kQrarhywXrsThrCG9-Dqw8MpAo-0__0000)

![Biểu đò tuần tự cho ca sử dụng Maintain Timecard](https://www.planttext.com/api/plantuml/png/PP4nRiCm34Ltda9ZC-G27Oe0ZWDa2931FW1jCOLQMJ8eEe1l7ygsd08TnVVvFqcTaY3BD7Y0zEk2uPW807k9RDf4R32P5heu1OiycyODr2FRI-GXe-O2VGp2qU-eMjz-xMsgT_ETum_rSiE0tpHGa3CATfWe2--tCsZ9oMpgOVHnfgLSbsAnNqm1MdFyqdJpQUeW6hNZQtZeR2Wk1b2ULPMgqjGDJehgum1QLQQf2fc47JrfnxHDSBK7o99ZiL7bn65FsrmQ9K_qpgBGluXQuJHcLFRw8wdVrdh7XzEhhjgbkQneNHezpaRAafjstH9E56p-mHS0)