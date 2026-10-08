---
title: "Worklog Tuần 1"
date: 2026-09-28
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

## AWS Free Tier và quản lý chi phí

**Thời gian tuần 1:** 28/09/2026–04/10/2026.

**Ngày cập nhật kết quả:** 09/10/2026.

Tuần đầu tập trung tạo tài khoản AWS, làm quen với Console, hoàn thành 5 nhiệm vụ nhận credits và thiết lập quản lý chi phí trước khi triển khai workload thực tế. Kết quả dưới đây tổng hợp từ quá trình thực hành và xác nhận hoàn thành mới nhất.

### Nội dung và lab đã học trong chương trình

Tuần 1 học hai bài thuộc **Mục 1 — Explore AWS Services (Khám phá dịch vụ AWS)** trong [lộ trình First Cloud Journey](https://cloudjourney.awsstudygroup.com/1-explore/). Mỗi mục của chương trình gồm nhiều bài học và lab; một mục có thể được học trong nhiều tuần.

| Mã bài/lab | Nội dung đã học | Kết quả thực hành |
| --- | --- | --- |
| [000001 — Tạo AWS Account / AWS Free Tier 2025](https://000001.awsstudygroup.com/) | Tạo tài khoản, Free Plan và Paid Plan, AWS Credits, kiến thức cơ bản về các dịch vụ trong 5 nhiệm vụ, Monitoring & Cost Optimization và FAQ. | Đã tạo tài khoản, hoàn thành 5 nhiệm vụ nhận credits, nhận $200 credits và nâng cấp Paid Plan. Trạng thái các phần giám sát được trình bày riêng bên dưới. |
| [000007 — Quản lý chi phí với AWS Budgets](https://000007.awsstudygroup.com/vi/) | Nội dung về AWS Budgets, phân biệt ngân sách chi phí và ngân sách mức sử dụng. | Đã thiết lập Cost Budget và Usage Budget. |

**Phạm vi kết quả:** 5 nhiệm vụ nhận credits là các hoạt động trong bài **000001**. Việc thực hành EC2, Bedrock, Lambda và RDS ở mức cơ bản trong bài này không đồng nghĩa đã hoàn thành các lab chuyên sâu riêng của từng dịch vụ hoặc toàn bộ Mục 1. RI Budget và Savings Plans Budget chưa được ghi nhận là đã triển khai.

### Mục tiêu tuần 1

- Hiểu Free Plan, Paid Plan và cách theo dõi AWS Credits.
- Hoàn thành 5 nhiệm vụ; hiểu vai trò cơ bản của EC2, Amazon Bedrock, AWS Budgets, AWS Lambda và Amazon RDS.
- Thiết lập Cost Budget, Usage Budget và Project Spend Limit.
- Làm quen với Cost Explorer, kiểm tra tài nguyên và các biện pháp hạn chế chi phí ngoài ý muốn.

### Phân bổ nội dung trong tuần

Bảng sau phân bổ nội dung theo ngày làm việc từ mốc bắt đầu thực tập 28/09/2026; đây là lịch tổng hợp nội dung, không phải nhật ký xác nhận thời điểm thực hiện từng thao tác. Ngày 09/10/2026 là ngày cập nhật báo cáo, thuộc tuần 2.

| Thứ | Ngày | Nội dung học và thực hành | Tài liệu |
| --- | --- | --- | --- |
| Thứ Hai | 28/09/2026 | Tìm hiểu AWS Free Tier; tạo tài khoản; làm quen Console, Free Plan và Paid Plan. | [AWS Free Tier 2025](https://000001.awsstudygroup.com/) |
| Thứ Ba | 29/09/2026 | Thực hành nhiệm vụ EC2 và Amazon Bedrock; tìm hiểu máy chủ ảo và mô hình nền tảng AI. | [5 nhiệm vụ nhận credits](https://000001.awsstudygroup.com/4-hướng-dẫn-chi-tiết-5-nhiệm-vụ-kiếm-tiền/) |
| Thứ Tư | 30/09/2026 | Thực hành nhiệm vụ AWS Budgets; tạo Cost Budget và Usage Budget; tìm hiểu ngưỡng cảnh báo. | [Quản lý chi phí với AWS Budget](https://000007.awsstudygroup.com/vi/) |
| Thứ Năm | 01/10/2026 | Thực hành nhiệm vụ Lambda và RDS; tìm hiểu serverless và cơ sở dữ liệu quan hệ được quản lý. | [5 nhiệm vụ nhận credits](https://000001.awsstudygroup.com/4-hướng-dẫn-chi-tiết-5-nhiệm-vụ-kiếm-tiền/) |
| Thứ Sáu | 02/10/2026 | Tổng hợp 5 nhiệm vụ; kiểm tra credits, Paid Plan và spend limit; thiết lập Cost Explorer, tìm hiểu Monitoring & Cost Optimization và FAQ. | [AWS Free Tier 2025](https://000001.awsstudygroup.com/) |

### Kết quả tổng quan

Các số liệu ghi nhận tại thời điểm kiểm tra trong báo cáo cập nhật ngày 09/10/2026:

| Hạng mục | Kết quả |
| --- | --- |
| AWS Account | Đã tạo và sử dụng Console |
| Nhiệm vụ nhận credits | Hoàn thành 5/5 theo xác nhận thực hành |
| AWS Credits hiện có | $200.00 |
| Account plan | Đã nâng cấp Paid Plan |
| Chi phí ghi nhận / số tiền cần thanh toán | $0.00 / $0.00 |
| Project | Happy Path — Within limit |
| Project Spend Limit | $20/tháng |
| Cost Budget | Đã thiết lập |
| Usage Budget | Đã thiết lập |
| Cost Explorer | Hoàn thành thiết lập ban đầu, chờ dữ liệu |

### Năm nhiệm vụ và kiến thức đạt được

Danh sách nhiệm vụ được đối chiếu với [hướng dẫn AWS Study Group](https://000001.awsstudygroup.com/4-hướng-dẫn-chi-tiết-5-nhiệm-vụ-kiếm-tiền/). Trạng thái hoàn thành dựa trên xác nhận mới nhất của mình.

| Nhiệm vụ | Trạng thái | Kiến thức cơ bản |
| --- | --- | --- |
| Khởi tạo EC2 Instance | Hoàn thành | Máy chủ ảo; vai trò của AMI, loại instance và security group. |
| Sử dụng Amazon Bedrock Playground | Hoàn thành | Mô hình nền tảng AI; gửi prompt và xem phản hồi. |
| Thiết lập AWS Budgets | Hoàn thành | Theo dõi ngân sách và cảnh báo chi phí. |
| Tạo ứng dụng web với AWS Lambda | Hoàn thành | Chạy hàm theo mô hình serverless. |
| Tạo cơ sở dữ liệu Amazon RDS | Hoàn thành | Cơ sở dữ liệu quan hệ do AWS quản lý. |

Vấn đề nút tạo Aurora/RDS không phản hồi trong bản ghi trước là trở ngại ở một lần thực hành. Trạng thái nhiệm vụ RDS được cập nhật thành **hoàn thành** theo xác nhận mới nhất; chưa có thông tin xác định nguyên nhân của lần gặp lỗi đó.

### AWS Budgets và Cost Explorer

Đã thiết lập **Cost Budget** để theo dõi chi phí và **Usage Budget** để theo dõi mức sử dụng dịch vụ. Hai loại ngân sách có mục tiêu và đơn vị theo dõi khác nhau, theo [bài thực hành AWS Budget](https://000007.awsstudygroup.com/vi/).

Ảnh danh sách Budgets ghi nhận `daily-budget-10` ($10), `monthly-budget-25` ($25) và `monthly-budget-50` ($50), đều có trạng thái OK và mức sử dụng $0.00. Ảnh này minh họa danh sách ngân sách; không hiển thị cấu hình chi tiết của Usage Budget hoặc việc gửi email cảnh báo.

Project Spend Limit của Happy Path là **$20/tháng**, được theo dõi riêng với các Budgets. Giao diện Budgets lưu ý rằng ngân sách không đặt giới hạn chi tiêu cứng; tạo ngân sách không đồng nghĩa mọi tài nguyên sẽ tự dừng.

Đã truy cập và hoàn thành bước thiết lập Cost Explorer, tìm hiểu Unblended Cost, cách theo dõi theo ngày, phân nhóm theo dịch vụ và xác định Top 5 Cost Drivers. Tại lần kiểm tra, hệ thống đang chuẩn bị dữ liệu và yêu cầu kiểm tra lại sau 24 giờ; chưa có dữ liệu để kết luận dịch vụ nào có chi phí cao nhất.

### Giám sát tài nguyên và các phần chưa triển khai

| Nội dung | Kết quả thực hành |
| --- | --- |
| Emergency Cost Control | Đã kiểm tra Billing Dashboard và EC2 tại Region được kiểm tra; không thấy EC2 Instances, chi phí ghi nhận $0 và credits còn $200. Không cần shutdown khẩn cấp. |
| CloudWatch Billing Alerts | Chưa triển khai: không thấy metrics `AWS/Billing`; giao diện Billing Preferences hiển thị yêu cầu Enterprise AWS tại lần kiểm tra. Ghi nhận là hạn chế quan sát được, chưa xác minh nguyên nhân cuối cùng. |
| Resource Tagging qua Tag Editor | Chưa triển khai: `AccessDeniedException` với explicit deny trong AWS Organizations SCP. |
| AWS CloudShell | Chưa sử dụng được tại lần kiểm tra do thông báo account verification in progress. |
| Custom CloudWatch Metrics | Đã tìm hiểu, chưa triển khai Lambda xuất metrics chi phí. Lambda của nhiệm vụ nhận credits là nội dung thực hành riêng. |

Đã tìm hiểu cách audit tài nguyên và dừng EC2 không quan trọng khi cần. Kết quả kiểm tra ở một Region không đại diện cho toàn bộ tài nguyên trong mọi Region.

### Hình ảnh thực hành

**Ảnh 1 — Console ghi nhận $200 credits và chi phí tháng $0.00 trước khi nâng cấp plan.** Ảnh không hiển thị danh sách trạng thái 5 nhiệm vụ; kết quả 5/5 được ghi nhận theo xác nhận thực hành.

![Console hiển thị $200 AWS Credits và chi phí tháng $0.00](</images/1-worklog/1.1-week1/full_5_task_earn%20_credit.png>)

**Ảnh 2 — Các Budgets đã tạo và Project Spend Limit $20 của Happy Path.**

![Danh sách Budgets đã tạo và spend limit $20](/images/1-worklog/1.1-week1/list_budget_created.png)

**Ảnh 3 — Billing ghi nhận $200 available credits, $0 amount due và Happy Path trong giới hạn $20.** Việc nâng cấp Paid Plan được ghi nhận theo xác nhận thực hành; ảnh Billing không hiển thị tên account plan.

![Billing hiển thị credits, số tiền cần thanh toán và trạng thái dự án](/images/1-worklog/1.1-week1/total_200_and_paid_plan.png)

### Bài học rút ra

- Hiểu rõ hơn vai trò của 5 dịch vụ qua nhiệm vụ thực hành, đồng thời chủ động theo dõi chi phí trước khi triển khai tiếp.
- Qua [phần FAQ](https://000001.awsstudygroup.com/8-faq---giải-đáp-mọi-thắc-mắc/), đã tìm hiểu điều kiện sử dụng credits, các khoản có thể không được credits chi trả và việc mỗi nhiệm vụ chỉ được tính thưởng một lần.
- Phân biệt lỗi cấu hình với giới hạn quyền IAM/SCP, trạng thái xác minh tài khoản và thời gian chuẩn bị dữ liệu.
- Phân biệt nhiệm vụ đã hoàn thành, cấu hình đang chờ dữ liệu và chức năng chưa triển khai; không coi $0 tại thời điểm kiểm tra là bảo đảm không phát sinh chi phí về sau.

**Tổng kết:** Hoàn thành nội dung nền tảng tuần 1: tạo AWS Account, hoàn thành 5 nhiệm vụ, nhận $200 credits, nâng cấp Paid Plan và thiết lập Cost Budget, Usage Budget cùng Project Spend Limit. Các phần giám sát nâng cao còn hạn chế được ghi nhận riêng để tiếp tục xử lý.
