# Tài liệu thiết kế hệ thống Payroll System
## 1. Subsystem context diagrams
### 1.1. BankSystem
- `PayrollController` yêu cầu `BankSystem` thực hiện công việc tạo giao dịch chuyển khoản.
- `BankSystem` giao tiếp với API hệ thống ngân hàng thực để thực hiện việc chuyển tiền.
- `Employee` chứa các thông tin của nhân viên, trong đó bao gồm thông tin chuyển khoản.

![](https://www.planttext.com/api/plantuml/png/jLBBQiD03BplLuYSKcZy0IQOq9A2BwMqNw2ibR1u7-vAFfYIVw-zjLsdyRMd5JEpcf7GWGMZjCughes769YKQb3NU24elL0yeoROxr-2hIWM1Nmf03CJvHFw-gDZ8PSO08de-KnnU-gP75YYyPT7GAr3w-MrTIUA2zWDQ3vqVEY_NzNrr_uvU8d1Mef__RL5PdZ3Rg0Nify45JM1ZRpJPqiiMtAD3HrH3iUnMh45cDl-uqH7BqQwzMccSAEfgLABL7jqD1aa8CkozDu4IiXgg2d6_S9sks8nRmuRZTPkr685WwAyaRHCV2SvpaiUUNKWN_LtzGq0)

### 1.2. PrintService
- `PrintController` yêu cầu API hệ thống của máy in để in tài liệu.
- `PrintService` giao tiếp với API hệ thống máy tính để thực hiện công việc in.
- `Document` chứa thông tin về tệp tài liệu để in ra.
- `PrintSettings` chứa yêu cầu về tài liệu sẽ được in ra.

![](https://www.planttext.com/api/plantuml/png/jL91QiCm4Bph5KjEBIGVCC44cWPyA1Jy0Y5lZ8Wi6Uswu9RylMlBJckJ77heHMXtPsT6Wmx4EdBNE4KNwo46GgLQRIwwHYWyOpnhWx3VduAhCEOvV2a0UniKxr6A4kE7bMgO0HZjNDaJOpCECJvLmNGDUixWEDssGCXiVKqPJ1IfV1QAgxh-c7W9dcDm3kFQXN6QA6t_0YKFxT3zkox0alS_7_RgsN9__r4psoHyjWupECcv7MkHvRwL5h58r0-i9zqv494ixQVibEDE8ZB1XVWMAcdBojnhBTBOc2slCzxbYtWos0pHRDGYivsWYXMi8wGxi8NXnx3ZBUq9eGxeA_cytm00)

### 1.3. ProjectManagementDatabase
- `ProjectManagementController` lấy thông tin dự án và cập nhật giờ làm việc.
- `DatabaseService` giao tiếp với cơ sở dữ liệu để lưu và lấy thông tin về dự án.
- `Project` là thông tin cụ thể về một dự án.

![](https://www.planttext.com/api/plantuml/png/nLDDImCn4BtdLmoUjc3t1oob56o57WH5R-9XDXbBRBwSP8KY_UzckxkrBhKUlOHXtfkPDnzPn8IS6cj4t6e7x2C94L1kSKEmTedu5IN1R7RhZIAUp-5J0EWZi5vYmXeZFH9_wEneOG3fhTMfU6-8TnKiwuVMc5mVCEqYyI-O8aE9pcDbMHQJREt5_blYZNU9lJ74OutIO8nmp_wDPBf3bzcMN3e9wAKoOQAULmJseHgY-i9DK7ymEja3GwiA2eiXO6reqdjBhJhn04Tn_poxbKiwxIxEhPVKTfHttkLoQAc2c5YxpL0vIjOXQUz-0fPiJHmhMDbW_8xe-QK33bUNsy-9slT9MnfIeJBQdVW7rPSsEPtEnyEiu4gYCLTYFEIMExxQJ6uYnVFall2H8nRaLFunNm00)