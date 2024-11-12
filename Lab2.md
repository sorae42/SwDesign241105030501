# 1. Ca sử dụng Create Administrative Report
## 1.1. Phân tích lớp
- Boundary:
	- `ReportCreationForm`: Lớp này cung cấp giao diện cho Payroll Administrator để nhập các tiêu chí báo cáo.
	- `ReportSaveForm`: Lớp này cung cấp giao diện để Payroll Administrator nhập tên và vị trí lưu báo cáo sau khi báo cáo đã được tạo.
- Control:
	- `ReportController`: Đây là lớp điều khiển xử lý các yêu cầu từ Payroll Administrator. Nó sẽ có các phương thức để tạo và lưu báo cáo dựa trên các tiêu chí từ ReportCreationForm.
- Entity:
	- `Report`: Lớp này đại diện cho báo cáo với các thuộc tính như loại báo cáo (số giờ làm hoặc trả theo năm), ngày bắt đầu, ngày kết thúc, tên nhân viên, v.v.
	- `Employee`: Lớp này đại diện cho thông tin của nhân viên liên quan đến báo cáo.

## 1.2. Biểu đồ lớp
![](https://www.planttext.com/api/plantuml/png/hLInReCm4Dtz5IUMGjiCNL64gYQfEaGTaaXLHmUkgHLZ8zjKGbN_lGORWXFQBcK0-TsxqtkFWtjjg39roOa-CW5AQWHo1KjyOmBXGTQYeAg1d5EjKPFk2Hkif38BXTGmAHwbAc4-xxbP1fy4x7MZEjgkgJ25hL5C71o-nmCJIseitDuTYAAuWCgAomRncPQeKrWpRUPkJkO81TCLfqqh84uST43JgsC65QDnaaA8a2yI-DZI3_p3GwiWzC1btfaFKI-edpWIrK9htzDAybrMoX3sGWgZ97TPXqcx2aTbDVh3IMBUlWTqp3Zt9izD3oa4GdsJCzapl6Xj5K_MR-7SV38CpQagVXWwjheIXfdfhR8ENVN_zwZVePK_P_tR4QWiEKw2REBaj2XznuIuyPA6yemqb3_9MkaNgOvOf538Ui-zg8eshqZLJZgrljI5j47UnQlVMQN9nCSscsKNcq7EblaNpcYTJYnVW-WkWkiPH2KLJJGO9-JU1jl-9hu1)

## 1.3. Biểu đồ tuần tự
![](https://www.planttext.com/api/plantuml/png/dPDDJiGm38NtEOKr6rffvWBLg1f-XYL2b0kOra14cnJ7BUhjIMWBeiqW3Rl4VlxoOYS79yZIDRLoRze0MqUWi1JBS8y3sxg-h1fjj1D67rIjL-jIjsW4DW_KMfPh9XHjpQtbPWFx_PNjJ8Kyv7bKROq4B77GJhkujC2U8b0oecMOHI5v_8hubBg0WjuxCYM1VGRglTQfs4LWbyFQVkPZljp9b8CvgTRQG8YH8mmjn1hFyk6lHFnT2id4UXnQsi8D2haj79ksjWCHt653BbKdJ2xxde7hdXejCpmffqKQ1gzx3r_Lg6NW1vn16GwaSNSQDY5W5xNqGePyGwW27jKLBUl_yF2xTvLsROt3P6ZafMTDi7Yr7_yzDhpQGb0wb_YH7CXKuNTz0W00)

# 2. Ca sử dụng Create Employee
## 2.1. Phân tích lớp
- Boundary: 
	- `CreateEmployeeForm`: Cung cấp giao diện để nhập thông tin nhân viên mới.
	- `ProjectManagementDatabase`: Cơ sở dữ liệu lưu trữ thông tin nhân viên.
- Control: `EmployeeController`: Phương thức xử lý các yêu cầu, kiểm tra tính hợp lệ của dữ liệu đầu vào, và lưu dữ liệu vào `ProjectManagementDatabase`.
- Entity: `Employee`: Thông tin của nhân viên để dùng cho việc xử lý trong `EmployeeController`.

## 2.2. Biểu đồ lớp
![Biểu đồ lớp](https://www.planttext.com/api/plantuml/png/TLBRJiCm37tFL_YDLcW_K4tLn3RUa11yWRUO4aYSAdQHAiI_q_iqwFAIn3uvFiVEJXIJDi4R8v-E8KKXSmS7UdDCy10RjfXQE7iK8J733lj4g7GCjOyjqMDC0RRR6LkMy6sWM_VMIUsnxVDPFeOgqldP0HMpl83vRdxCHF-SuWUTzGaPAmh4saDFABHQHV1haP9Hg2-C_sjcpXRWMF-KNVpk8skAVhGxgPc1KyvJwcHCbuiAj7Ofabzn7bcTjgkK7T6ONNWcVSEPCL01hveSLqEWZkBKHRuA2lgk7GNOs9pyvEQ5FFP0UNUrc9LfRJRbYY-pOhL7tfp7hGTBRysEsFQVwnS0)

## 2.3. Biểu đồ tuần tự
![Biểu đồ tuần tự](https://www.planttext.com/api/plantuml/png/VLCnRi904Epl5IigAF812o4KGaIJA4NoWCEiy2NsddLUer2dJCKFGj95YaIH2fUE-8T_aZk4YS2-TBxPsRdPdVCmOsauJsAHFIa2epCKGeQi3JnaQ4HggofKgII6piYWP1mdQQoNYDVQ91tezozrJZDfbeF1ARlcZJInqN6Cnh4FftFodT6F6FAD93d718cl9CkfpF3i1bjHlFmJT-Nn7hD5uIp3nG2QHWEuZQhjLmeSbTyq1xR3KbI-4onK-KcYsU5qcYC4aENJHEtjTNlxLQc5xMoXYYRaypP7he63S9iVZw4Q4vuBQpI0-sgxrl2pgegL0jvjgkB3hkBOtzxkJSQkGYwE5hlrHqzuExmZF9VhqCPX0oA8TvlSfVH64OGkAzzSROiyf3ijxPmd6ktvklSIm4HLnGjPVbMy-XLc-5_MOeWqSx_HBm00)

# 3. Ca sử dụng Login
## 3.1. Phân tích lớp
- Boundary:
	- `LoginForm`: Lớp này cung cấp giao diện để người dùng nhập tên và mật khẩu, hiển thị các thông báo lỗi khi đăng nhập thất bại.
- Control:
	- `LoginController`: Lớp điều khiển này xử lý yêu cầu đăng nhập từ LoginForm. Nó xác minh tên và mật khẩu, thực hiện đăng nhập nếu thông tin đúng hoặc trả về thông báo lỗi nếu sai.
Entity:
	- `User`: Lớp này lưu trữ thông tin về người dùng, bao gồm tên và mật khẩu để xác thực.

## 3.2. Biểu đồ lớp
![](https://www.planttext.com/api/plantuml/png/XP9lIyCm4CRVvrFSEpkqNs2CCPmJ10LH_03dShR1z5BkKcM8tzsahQph1FCYaFkJ-prFij684hl66trt31AKm5p03Rqv9hWE7LkK0-mzgff-X_jGERuDqi1gzLkmNiENWRGkEoLXR6W9pr4SLqEqJOsVGUnfr3fjFHxoNSLY25KKjqAME3hqMYoMC3cUTEr4WZoGAbQKkh_D4NiRE4hmvzHZmfCazl5mHFz0xon6cWBCvLp1N4f2V0t14_9mYy-3-hublAHz55OZMqztt0_fOMRGkpGndZgTsnFeaFd7uh96hSa-_caqTh7EYlP9NU6uxUAyRgAYXteYZz45rjgrQevFNfRhkPLcRcskoUXdYLLP3Wcp8RRvq_q0)

## 3.3. Biểu đồ tuần tự
![](https://www.planttext.com/api/plantuml/png/lPB1IWCn48RlynH3Bsv1Nw2KKYmL10LXqVku6TjWDbadIKlVtantxHQfwCaSGi9yyy__aonZ8acvTH3VhKS9aH6eIK7mER90LwgsiHtvX9E7iB7-BaWxmVdyDcHlI0wBnGLe5NoIu1oBeiEjaEoJJGUSgBPMriTxAS0LrloHsJUCuGrvLyW8Yk7D0a-3PrWwkFVcgMKaR_29Ojm7CN32JZsZZnd6_DhQj18swe9ShFAWSetT834589VmXPmrU8O2blLDKOUeZnbIJbi56qfSZLBQqoUuP6UdCtxIFGliz5Zdfk4Og-dOy9Mpjr1lmxv7IyuZ2y2kFEQzt_r36El_6iVOs3awh4M2F1QRjE5VKh6YsFPi-K46O5bs_REV)

# 4. Ca sử dụng Maintain Employee Infomation
## 4.1. Phân tích lớp
- Boundary:
	- `EmployeeManagementForm`: Lớp này cung cấp giao diện để Payroll Administrator chọn các chức năng (thêm, cập nhật, hoặc xóa nhân viên) và nhập thông tin nhân viên hoặc ID nhân viên khi cần.
- Control:
	- `EmployeeController`: Lớp này xử lý các yêu cầu từ `EmployeeManagementForm`.
- Entity:
	- `Employee`: Lớp này lưu trữ thông tin của nhân viên, bao gồm ID, tên, loại nhân viên, địa chỉ, số điện thoại, mức lương, v.v.
	- `User`: Lớp này lưu thông tin đăng nhập của nhân viên như tên người dùng và mật khẩu, liên kết với Employee.

## 4.2. Biểu đồ lớp
![](https://www.planttext.com/api/plantuml/png/XLJRJi9047tVhzWt8SeFD8GG5HCJKOFn0vRkG3TiPvgzI1hZlpkzS6cfs8ScFNDccNFcB7CVb0injyBl34f77gIuaO-mCGZodY9gvKgPMkMzgDzoaHUMIe2bGhM5730yaSlbT7fWpsRoMqX-Rg6bFkj4VWHdSDl3SKF9yS3ggwbhumkhohSY648_6ZVe5i8vTJI-qhfmZjmIlESHkVz7d4Gz40P7Tb1JMxFWM4_xSPAZj3uGH-PYzFDnTDCG2wq277ikxRYJ0-UqGi32rTwMbn9kZCiVApgxDKHCv9h8WiAE3miC9hIhXRuHBB-f_xzCL3bqaL0MFOITSxoCBbXaXF0QypMuRY6Zw6ovOkiIgIckBJIuLvRZrSKgxel9JKZOoj0UhCeqWtJ7dfWlSEKIGaQzgLcisU9fOOUGDIkhyuMmlmnedQN6gqzVnwJlKsJumfD9fdm6-ftxzkJwiyIGyJKoAVyo1wk8eS_hht05LjLt8pE55t_SoCbaDX1iCP3rS-QnNgELHY7cWBhwZ_W5)

## 4.3. Biểu đồ tuần tự
![](https://www.planttext.com/api/plantuml/png/xPRFRe904CRl-nGJByL4Ny0OeoqsuM1YslG1jknWDi8kNHORthwpW7-gG0lnrdeWWPtvpJ3VDyHbPhcnUHApR2yL69qXC1vQRM3B2wFZU2KIgMHc3QU7BALe6SgKAmkZTPB6ka3SSCLtcA2opzea8vZF7tMk13V5Oj6SyQILTN0qBhg-es12I5kSuzpfkdn6X-m1Nl4ZHnKYw0ZmGD4PQseJfWjeRcv6Y1X32r6kGYkr0cybn0JUKi4jJe1oVGgmE6RDW4lq-Iq8cxydqa9Mqb6S-8pns0BLE6KneDyjegld5_VQcGMipq6gY0vuMU0ITzjhqtXcuCiiZNa1Zk8kG1befDgrb-WxvxKZ3kcuOxe_qfh7EGCknF76SxdZRramRIbxh1U80Q8TPwpmyznuu3E6CIrPPRYxceBOGxnm9LHDwIltrkY35DYZcz_eV0LfazUWDPA-1oUDpyBrLBgdizeqlziMRRIGKGTlq7ZpqdkYznPLUG5bUMJgeDoZoitLD_FVpN_CpNt5eRAHf03Xx39q9HeX_OJfHBJ9ad2p9wXVvtZE-qemjgIh-mFr1G00)

# 5. Ca sử dụng Maintain Purchase Order
## 5.1. Phân tích lớp
- Boundary:
	- `PurchaseOrderManagementForm`: Lớp này cung cấp giao diện để Commissioned Employee chọn các chức năng (tạo, cập nhật, hoặc xóa đơn hàng) và nhập thông tin đơn hàng hoặc ID đơn hàng khi cần.
- Control:
	- `PurchaseOrderController`: Lớp này xử lý các yêu cầu từ `PurchaseOrderManagementForm`. Nó cũng đảm bảo mỗi đơn hàng mới được tạo với ID duy nhất.
Entity:
	- `PurchaseOrder`: Lớp này lưu trữ thông tin của đơn hàng, bao gồm ID, thông tin liên hệ khách hàng, địa chỉ thanh toán, sản phẩm, ngày đặt hàng, và trạng thái đơn hàng.
	- `CommissionedEmployee`: Lớp này đại diện cho nhân viên có hoa hồng, liên kết với các đơn hàng mà họ đã tạo để nhận hoa hồng cho các giao dịch này.
	
## 5.2. Biểu đồ tuần tự
![](https://www.planttext.com/api/plantuml/png/ZLHHRi8m3FtFAV8tqCO5AbIn0PCc3O6s4uJ6b6YfNJcf9ZJjxaj94PIsZ7v4YlFyalTiT-QyObyLLhWlWvB9WHGFSW4xWo1Vg4Aj-20pgvmJnrLkAixsoi6QDV1AeSgX0FIln8MSJayfQIf_X0pVOtc9VzE9_FHiCEyxn1qbRVuw597QkDAgmxhqXj2DnZ6QW-_WH-F_I9RCn2jmBhmzCFsAi-GveMUomueRW0KEQflDMMp6e3oq4aQcNrRdbJfILANkK0nu-2I7k1kvOE5EgYOZ8zmPBXPrOl1v49t8BP45XItpbkYDRxe5UjqBdaNGdVsHLSvJ4LrNcMyVResrOVEiDOTQNZKMawuoxqwt1zvtu_nq4-DfH55zvoBOdSXwZS4m4hwweWj2J8vNzJerOQpOkVyGlWTQ-TXhqPOv5OK9h8IWbqLfwG3GumuqHpS7nvt4NGRJM9eFiEeuCdjJEd5hU2UJTAZLnT08T794hwukJCm0TVtV-GC0)

## 5.3. Biểu đồ lớp
![](https://www.planttext.com/api/plantuml/png/xLP1Ri8m4Bpx5Iik1Qby02642bJYW8fQzG5kl6cj9dPgErJvVTSEq08X4OdeYHmI9TwTtVNC99bQnutBquJPJwd0Q8l0UEIqWPbEKscjr0h58iqINI2oZA9b93Ek7FJMkOa-kCKd8z2ikEBlcA9oZzgaFHYF7tIk13V5P5AJDjFA6PqaQ7pAzeuo24UwuYZOXop20aMmEtZ1hnnLXA1Zm0sbM5RLDGmdKDFhY70IZ1p4kOeSPK9_Pf0xl8VNJ8GhRSUSOXmEM0tGIPtVuQX6_fPA1pQKGh4lnXXF79G5zzaGqXdGSGQmSQPdlpVMGRQ3r3uAf8ffcOVA9_2durHjvmZcqcO9By13-HDG1XgftfkgjM9duS4xpj54ooNeDIIC80f47ZpiUxJ1AGuCwnhB_YuiHISjxFXI-7qywNBE62PqMqhz7nH85LiBhr8AMy1MsbeRlP42s_LueQYgG6krPD0PIU-rGpKT2QEri3fA_Pp6hl46M6aXuqReZcpbmG2YW_TBX98N0kcJtPR1-gN3oY_8pM4tXrtLOQrefpPYIG72QxIJLokHsjBS35PBRqWx8jUxKGd6fdJs_xq_)

# 6. Ca sử dụng Run Payroll
## 6.1. Phân tích lớp
- Boundary:
	- `PayrollScheduler`: Giao diện này được kích hoạt vào thời gian đã định (mỗi thứ Sáu và ngày làm việc cuối tháng) để khởi động quá trình chạy lương.
- Control (Điều khiển):
	- `PayrollProcessor`: Lớp điều khiển xử lý toàn bộ quy trình chạy lương. Nó sẽ thực hiện các bước như lấy danh sách nhân viên cần thanh toán, tính toán lương, và xử lý các phương thức thanh toán (in séc hoặc gửi giao dịch ngân hàng).
	- `BankTransactionHandler`: Lớp xử lý các giao dịch ngân hàng, đảm bảo rằng các giao dịch được gửi thành công.
- Entity:
	- `Employee`: Lưu trữ thông tin của nhân viên, bao gồm thông tin lương, phương thức thanh toán, và trạng thái (có thể bị xóa sau khi chạy lương).
	- `PayrollRecord`: Lưu trữ thông tin về bảng lương cho từng nhân viên, bao gồm số tiền thanh toán và các khoản khấu trừ.
	- `Timecard` và `PurchaseOrder`: Các thực thể này được liên kết với nhân viên và được dùng để tính lương cho các nhân viên tính lương theo giờ hoặc nhân viên hoa hồng.
	
## 6.2. Biểu đồ lớp
![](https://www.planttext.com/api/plantuml/png/dLFBJWCn3BpdAtAZ5VG7ggggobQ20rBLyWCXCMtKhBDol8SLuj_9lhiF3h27A1hR4tiykmkiYFFKYN2pACa7aE919l1f4UJUvsWK5L8x5OAeJdbK1NddpleA9dT0ShDfyxPR-ILa_1wPxEK2rEGkbk9RzBJF7Zd2DIkCU8_aDOJWIzuciQUb77lA2j7AwTmfXeWl8CsSBm3Myj3SbkkMzmJQawcBChB84OyZwDjCrPFCxej67CkMf6eqiGIQ4yXyiFmFhYXCFVzUuUsT50QbsNfyKMXgTISg141pbpdxg4hZJdWjZSy_73Gj4p0LVwsytzm1sN8nMbnR6bkjutsdBVzhdFiSFO6NHZjL9C3Akb3fqToxM0h8Ry1NFogBPkKyT5WdtK3IcJQ68zMOYUwjH0WTNarwWkYc4hxQB8Y9sLUhxSIfOcBTCgkLPJuwTELiohmXn2y-6JmfTj4YvL_z0m00)

## 6.3. Biểu đồ tuần tự
![](https://www.planttext.com/api/plantuml/png/dLJRReCm37tFLrXzMP6sVK1LLLKlqnwhTVi0DxWb8YGi2PNu-paKA5qlayP3aEnpV8uTmzm7TA4gjF2vCk2i9n0eWtMmhNsWGfISLrALQ0ACDbWxg_LMPfHMcjm8fjE5hKoAhfxDRc8tpahotZROfJM1Wmmb4rIeORGkIcrhefXTDx51iYtnGTAwz09neRH0atywD9wDAslUqQIjjxEUU88jVLTa987T0nrPmujJZ_0oWz-TJI0uTJYGQnFZHFo636XzanDmbRcYzEb8wJfcAB46E-aY_iqEv8IsjeGzamXb1jI21F1pg-x5i2OWKSjAOo2EZpjoSfTzxGfAh0kU4XGKCfkAXeewH7eJtzMmp4Zcm1KsIkPLsK3-y3SOLUcK2HoMiKhlyJaAdpivMIRDYxbIZcI05PNMg_1GxFPAJC2JIGVnUwAlMF1MXwJNY7t7ckrN0Ly6ZwWqxZJrcFZSrdtaA8wx_eybxaHqx_vkkck40brEQRC-AMcAbHyEx7p_3RpVoN5o5ccEEP_nV_43)

---
# Java code mô phỏng ca sử dụng Maintain Timecard
```java
// TimecardForm.java
package Boundary;

import Entity.Timecard;
import Entity.Employee;
import Control.TimecardController;

public class TimecardForm {
    private TimecardController controller;

    public TimecardForm(TimecardController controller) {
        this.controller = controller;
    }

    public void displayForm() {
        // Hiển thị form cho người dùng để nhập thông tin chấm công
        System.out.println("Enter Timecard Information.");
    }

    public void submitTimecard(Employee emp, Timecard timecard) {
        controller.processTimecard(emp, timecard);
    }
}
```

```java
// ProjectManagementDatabase.java
package Boundary;

import Entity.Timecard;
import java.util.HashMap;
import java.util.Map;

public class ProjectManagementDatabase {
    private Map<Integer, Timecard> timecardData = new HashMap<>();

    public ProjectManagementDatabase() {
        // Giả lập dữ liệu chấm công có sẵn trong cơ sở dữ liệu
        // timecardData.put(employeeId, new Timecard(...));
    }

    public Timecard retrieveTimecard(int employeeId) {
        return timecardData.get(employeeId);
    }
}
```

```java
// TimecardController.java
package Control;

import Entity.Employee;
import Entity.Timecard;
import Boundary.ProjectManagementDatabase;

public class TimecardController {
    private ProjectManagementDatabase database;

    public TimecardController(ProjectManagementDatabase database) {
        this.database = database;
    }

    public void processTimecard(Employee emp, Timecard timecard) {
        if (validateTimecard(timecard)) {
            emp.updateEmployeeTimecard(timecard);
            System.out.println("Timecard processed and updated successfully.");
        } else {
            System.out.println("Invalid Timecard.");
        }
    }

    public boolean validateTimecard(Timecard timecard) {
        // Xác thực dữ liệu của timecard
        return timecard.getHoursWorked() > 0 && timecard.getDate() != null;
    }
}
```

```java
// Employee.java
package Entity;

import java.util.ArrayList;
import java.util.List;

public class Employee {
    private int id;
    private String name;
    private String address;
    private List<Timecard> timecards = new ArrayList<>();

    public Employee(int id, String name, String address) {
        this.id = id;
        this.name = name;
        this.address = address;
    }

    public void getEmployeeDetails() {
        System.out.println("Employee ID: " + id);
        System.out.println("Name: " + name);
        System.out.println("Address: " + address);
    }

    public void updateEmployeeTimecard(Timecard timecard) {
        timecards.add(timecard);
        System.out.println("Timecard added for employee: " + id);
    }
}
```

```java
Timecard.java
package Entity;

import java.util.Date;

public class Timecard {
    private Date date;
    private double hoursWorked;

    public Timecard(Date date, double hoursWorked) {
        this.date = date;
        this.hoursWorked = hoursWorked;
    }

    public void getTimecardDetails() {
        System.out.println("Date: " + date);
        System.out.println("Hours Worked: " + hoursWorked);
    }

    public Date getDate() {
        return date;
    }

    public double getHoursWorked() {
        return hoursWorked;
    }
}
```

```java
// main.java
import Boundary.ProjectManagementDatabase;
import Boundary.TimecardForm;
import Control.TimecardController;
import Entity.Employee;
import Entity.Timecard;
import java.util.Date;

public class Main {
    public static void main(String[] args) {
        ProjectManagementDatabase database = new ProjectManagementDatabase();
        TimecardController controller = new TimecardController(database);
        TimecardForm form = new TimecardForm(controller);

        // Tạo nhân viên và thẻ chấm công mẫu
        Employee emp = new Employee(1, "Le Anh", "573 An Duong Vuong");
        Timecard timecard = new Timecard(new Date(), 8.0);

        // Nhập thông tin và gửi thẻ chấm công
        form.displayForm();
        form.submitTimecard(emp, timecard);
    }
}
```