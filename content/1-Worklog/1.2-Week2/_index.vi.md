---
title: "Worklog Tuần 2"
menuTitle: "Week2"
date: 2026-10-05
weight: 2
chapter: false
pre: " <b> 1.2 </b> "
---

## IAM, policy và quyền tạm thời cho ứng dụng

**Thời gian tuần 2:** 05/10/2026–11/10/2026. **Ngày cập nhật báo cáo:** 11/10/2026.

**Phạm vi học:** Mục 1 — Explore AWS Services; ôn Region/AZ, các phần user/group/role của `000002` và kiến thức/cấu hình role ứng dụng liên quan `000048`.

Tuần này tập trung phân biệt danh tính với quyền truy cập, thực hành IAM trên account Happy Path và mô phỏng policy có phạm vi hẹp. Đã tạo các đối tượng IAM, chuyển sang AdminRole và ghi nhận cleanup; role EC2 mới dừng ở cấu hình, chưa kiểm chứng ứng dụng đọc S3 thực tế.

### Mục tiêu tuần 2

| Mục tiêu | Tiêu chí hoàn thành |
| --- | --- |
| Phân biệt Region/AZ và các danh tính AWS. | Giải thích Region/AZ, AWS account, Builder ID, root, IAM user và phiên role; ghi rõ phần bảo mật chưa xác minh. |
| Thực hành user/group và Switch Role. | Tạo đối tượng IAM, đăng nhập và xác nhận phiên AdminRole hoạt động; ghi trạng thái cleanup. |
| Đọc policy và áp dụng least privilege. | Giải thích Effect/Action/Resource/Condition; mô phỏng Allow, implicit deny và explicit deny. |
| Hiểu role cho ứng dụng. | Phân biệt trust/permissions policy, giải thích credentials tạm thời và cấu hình role EC2 đọc S3 có phạm vi hẹp. |
| Tiếp tục học CLI và kiểm thử quyền thực tế. | Xác định caller/Region và kiểm tra trước/sau thay đổi một quyền nhỏ; chưa có kết quả trong ba note được tổng hợp. |

### Các công việc cần triển khai trong tuần

Bảng dưới là **phân bổ nội dung theo note Thứ Hai–Thứ Tư**, không xác nhận thao tác diễn ra đúng ngày trong lịch. Ngày thực tế chưa được ghi nhận; không dùng ngày cập nhật thay cho ngày thực hành.

| Thứ / ngày phân bổ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Trạng thái | Nguồn tài liệu |
| --- | --- | --- | --- | --- | --- |
| Thứ Hai — 05/10 | Ôn Region/AZ; tạo AdminGroup, AdminUser, AdminRole, OperatorUser; Switch Role và cleanup IAM. | Chưa ghi nhận | Chưa ghi nhận | Hoàn thành phạm vi tạo/chuyển role; cleanup theo ghi nhận thực hành. | [000002 — IAM](https://000002.awsstudygroup.com/vi/) |
| Thứ Ba — 06/10 | Đọc policy, least privilege; mô phỏng quyền S3 và SecureTransport. | Chưa ghi nhận | Chưa ghi nhận | Hoàn thành phạm vi mô phỏng theo xác nhận người học. | [IAM Policy Simulator](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_testing-policies.html) |
| Thứ Tư — 07/10 | Học role cho ứng dụng; cấu hình trust EC2 và quyền đọc photos trên S3. | Chưa ghi nhận | — | Đã cấu hình — chờ kiểm chứng luồng ứng dụng. | [000048 — Role cho ứng dụng](https://000048.awsstudygroup.com/) |

> **Cần bổ sung — Ngày thực hiện:** Ngày thực tế học, tạo đối tượng, chạy Simulator và cleanup tương ứng với ba note.

### Kết quả đạt được tuần 2

| Bài/lab hoặc mục tiêu | Kết quả trong phạm vi báo cáo | Trạng thái | Minh chứng |
| --- | --- | --- | --- |
| Region/AZ và danh tính | Phân biệt Region, AZ, Data Center, Edge Location; account, Builder ID, root và IAM user. | Hoàn thành phạm vi lý thuyết; bảo mật root chưa xác minh. | MC-01; ghi chú học tập. |
| `000002` — User/group và Switch Role | Tạo AdminGroup, AdminUser, AdminRole, OperatorUser; dùng phiên AdminRole đọc danh sách users. | Hoàn thành phạm vi nêu trên. | MC-03–MC-06; ghi nhận thực hành. |
| `000002` — Cleanup | Người học ghi nhận đã xóa hai users, AdminGroup và AdminRole. | Đã thực hiện; chưa đối chiếu ảnh/log sau xóa. | Ghi nhận thực hành. |
| Policy và least privilege | Mô phỏng quyền theo action/resource, explicit deny và Condition. | Hoàn thành phạm vi mô phỏng. | Xác nhận người học; chưa có ảnh/output. |
| `000048` — Role ứng dụng | Cấu hình role EC2 và policy đọc S3 theo ví dụ. | Đã cấu hình — chờ kiểm chứng. | Xác nhận người học; chưa có ảnh policy. |
| CLI / phép thử API trước–sau | Chưa có kết quả trong note Thứ Hai–Thứ Tư. | Chưa ghi nhận thực hành. | Chưa có. |

Các kết quả này không xác nhận hoàn thành toàn bộ lab `000048`, triển khai multi-AZ hoặc kiểm thử quyền qua CLI.

### Chi tiết nội dung học và thực hành

#### Region/AZ và account làm lab

Region là khu vực địa lý, một Region gồm nhiều AZ; mỗi AZ có một hoặc nhiều Data Center. Hạ tầng tách biệt giữa các AZ hỗ trợ cô lập sự cố; ứng dụng phải được thiết kế và triển khai phù hợp để hưởng lợi từ nhiều AZ. Chọn Region không tự triển khai trên mọi AZ.

Account làm lab là **Happy Path**. Phiên cấu hình qua Builder ID sử dụng `AccountFullAccessRole`; IAM users và root là các danh tính riêng. Sau kích hoạt Advanced features, account được quản lý trong AWS Organizations và Console hiển thị nhiều Region. Team name của IAM Identity Center khác AdminGroup. Đã học rằng kích hoạt không hoàn tác và xóa spend limit hiện có; cảnh báo Budgets không tương đương giới hạn chi tiêu tự động. [Tài liệu AWS](https://docs.aws.amazon.com/accounts/latest/reference/activate-advanced-features.html)

MC-06 có dấu hiệu MFA/passkey của AdminUser, còn OperatorUser hiển thị `—` tại thời điểm chụp. MFA của Builder ID/root, mật khẩu root riêng biệt và root access key vẫn chưa xác minh; MFA của IAM user không chứng minh bảo mật root.

> **Cần bổ sung — Bảo vệ account:** Trạng thái MFA của Builder ID/root Happy Path, thông tin xác thực root và root access key, kèm ngày kiểm tra. Region/tài nguyên/AZ thực tế trong các note chưa đủ dữ liệu để hoàn tất kiểm kê.

#### `000002` — IAM user/group và Switch Role

**Tài liệu:** [Tạo group/user](https://000002.awsstudygroup.com/vi/2-create-admin-user-and-group/), [Tạo role/user](https://000002.awsstudygroup.com/vi/3-aws-role/), [Switch Role](https://000002.awsstudygroup.com/vi/4-switch-roles/), [Cleanup](https://000002.awsstudygroup.com/vi/5-cleanup/).

- Đã tạo AdminGroup và AdminUser, ghi nhận sử dụng AdministratorAccess và thêm user vào nhóm. MC-03 cho thấy group lúc chưa có thành viên; MC-04 cho thấy AdminUser thuộc một group nhưng không hiển thị tên group/policy chi tiết.
- Đã tạo AdminRole và OperatorUser, đăng nhập OperatorUser rồi Switch Role. MC-05 xác nhận tạo role; MC-06 xác nhận phiên AdminRole đọc được danh sách users.
- Hiểu role không được gắn vào user/group như permissions policy. Switch Role sử dụng quyền role thay quyền user trong phiên; Switch back không hoàn tác thao tác đã làm. Chưa có phép thử riêng sau Switch back.
- Ghi nhận đã xóa AdminUser, OperatorUser, AdminGroup và AdminRole; không suy ra mọi tài nguyên hoặc role hệ thống trong account đã được dọn.

> **Cần bổ sung — Minh chứng cleanup:** Ảnh/log Users, User groups và Roles sau khi dọn, xác nhận bốn đối tượng lab không còn; kèm ngày kiểm tra.

#### Policy và least privilege — mô phỏng bổ sung cho `000002`

Đã học Effect (Allow/Deny), Action (API), Resource (phạm vi ARN), Condition (điều kiện) và nguyên tắc chỉ cấp quyền cần thiết. Policy ví dụ chỉ Allow `s3:GetObject` với `arn:aws:s3:::fcaj-example-bucket/photos/*`.

Kết quả dưới đây được ghi theo xác nhận người học đã thực hiện bài hướng dẫn trong note Thứ Ba, chưa đối chiếu ảnh/output từng lần chạy:

| Phép thử trong Simulator | Kết quả ghi nhận |
| --- | --- |
| GetObject với `photos/cat.jpg` | Allowed. |
| GetObject với `private/report.pdf` | Implicit deny — ngoài resource được phép. |
| DeleteObject với `photos/cat.jpg` | Implicit deny — chưa Allow action xóa. |
| Thêm Deny GetObject với `photos/private/*`, thử `photos/private/secret.jpg` | Explicit deny, dù khớp Allow `photos/*`. |
| Allow có Condition `aws:SecureTransport = true`; context true / false | Allowed / implicit deny trong policy đang thử. |

Các object thuộc bucket ví dụ; không ghi nhận bucket tồn tại. Simulator không gọi API S3 thật; Condition không thỏa làm Allow không áp dụng, không tương đương một explicit deny HTTP trên toàn bucket. [Tài liệu Simulator](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_testing-policies.html)

> **Cần bổ sung — Minh chứng policy:** Ảnh/output Allow, implicit deny, explicit deny và SecureTransport, policy/context đang thử và ngày kiểm tra.

#### `000048` — Role cho ứng dụng: học và cấu hình

Đã phân biệt **trust policy** (ai được nhận role) với **permissions policy** (role được làm gì). Luồng đã học: EC2 được liên kết instance profile chứa role → ứng dụng lấy credentials tạm thời qua instance metadata → SDK ký request → S3 đánh giá quyền. Ứng dụng không dùng mật khẩu Console; tránh nhúng access key dài hạn vào code. [Hướng dẫn AWS](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_use_switch-role-ec2.html)

Theo note Thứ Tư và xác nhận người học, đã cấu hình role `fcaj-ec2-photo-reader`, trust principal `ec2.amazonaws.com` với `sts:AssumeRole`, inline policy `ReadPhotosOnly` cho `s3:GetObject` trong `photos/*` của bucket ví dụ. Chưa có ảnh để đối chiếu tên/cấu hình thực tế.

**Phạm vi còn lại:** chưa triển khai EC2/bucket thật và kiểm chứng ứng dụng đọc S3 trong bài hướng dẫn này. Ảnh EC2 Terminated trao đổi riêng chưa xác nhận EC2 đó đã dùng role này hoặc đọc S3 thành công. Trạng thái giữ/xóa role và instance profile chưa ghi nhận.

> **Cần bổ sung — Role ứng dụng:** Ảnh Permissions/Trust relationships, tên thực tế nếu khác ví dụ, ngày kiểm tra và trạng thái giữ/xóa role/instance profile.

### Minh chứng thực hành

Ảnh dưới ghi trạng thái tại thời điểm chụp; chưa có ngày chụp xác minh và không phản ánh trạng thái sau cleanup.

**MC-01 — Học lý thuyết AZ qua video Module 01-01 — Introduction to AWS.**

![Video nhập môn AWS đang trình bày Availability Zone](/images/1-worklog/1.2-week2/watching_video_youtube_introduction_to_aws_t2.png)

Ảnh ghi nhận nội dung đang học, không chứng minh đã triển khai multi-AZ.

**MC-02 — Màn hình xem xét kích hoạt Advanced features và tên team.**

![AWS Settings hiển thị các thay đổi khi kích hoạt Advanced features](/images/1-worklog/1.2-week2/open_advanced_team_mode.png)

Ảnh là bước xem xét trước xác nhận, không tự chứng minh kích hoạt hoàn tất; kết quả kích hoạt dựa trên ghi nhận người học và thao tác IAM sau đó.

**MC-03 — AdminGroup tồn tại, có 0 thành viên tại thời điểm chụp.**

![Danh sách IAM groups có AdminGroup](/images/1-worklog/1.2-week2/created_IAM_group.png)

**MC-04 — Tạo AdminUser thành công; cột Groups hiển thị 1.**

![Thông báo tạo AdminUser thành công](/images/1-worklog/1.2-week2/created_user_admin.png)

**MC-05 — Console xác nhận AdminRole được tạo thành công.**

![Thông báo Role AdminRole created](/images/1-worklog/1.2-week2/created_role.png)

**MC-06 — Phiên AdminRole đọc được danh sách AdminUser và OperatorUser.**

![Phiên AdminRole và danh sách hai IAM users](/images/1-worklog/1.2-week2/switch_role.png)

### Vấn đề gặp phải và hướng xử lý

| Hiện tượng | Nguyên nhân / kết luận có căn cứ | Xử lý / bước tiếp theo | Trạng thái |
| --- | --- | --- | --- |
| IAM groups báo Feature unavailable. | Giao diện yêu cầu Advanced features. | Đã kích hoạt theo ghi nhận, sau đó tạo group. | Đã xử lý trong phạm vi lab. |
| OperatorUser bị từ chối GetUser/GetLoginProfile. | Thông báo nêu không có identity-based policy Allow action ở phiên user. | Switch Role; MC-06 xác nhận đọc được danh sách users ở phiên role. Không suy ra hai API lỗi đã được thử lại riêng. | Đã dùng phiên role; kiểm thử chi tiết chưa có. |
| Builder ID đăng nhập được nhưng root Authentication failed. | Chưa xác định sai credentials hay root sign-in bị vô hiệu hóa. | Tiếp tục dùng danh tính được cấp quyền; kiểm tra thông tin xác thực root đúng account. | Chưa xác minh root. |

### Bài học rút ra và kế hoạch tiếp theo

- Đăng nhập thành công không đồng nghĩa được phép gọi mọi API; luôn kiểm tra user/role đang dùng.
- Cấp quyền theo action/resource cần thiết; tách kết quả mô phỏng với request thật và tách role cấu hình với ứng dụng đã chạy.
- Lưu ngày, policy/context và đầu ra ngay khi kiểm tra để báo cáo có thể đối chiếu.

| Ưu tiên | Công việc tiếp theo | Tiêu chí hoàn thành |
| --- | --- | --- |
| Cao | AWS CLI: đăng nhập, profile, caller và Region. | Chạy lệnh đọc danh tính/tài nguyên, ghi output và phân biệt lỗi xác thực/quyền/phạm vi. |
| Cao | Thử trước/sau thêm một quyền nhỏ. | Cùng danh tính, action, Region; ghi kết quả API trước/sau. |
| Vừa | EC2/S3 của `000048` theo lịch tuần 3. | Xác nhận nguồn credentials, đọc object được phép, thử ngoài phạm vi và cleanup. |
| Vừa | Hoàn thiện minh chứng và các phần chuyển tiếp tuần 1. | Bổ sung ngày, policy/cleanup, bảo vệ account; rà Budgets, Support, Cost Explorer và tài nguyên theo checklist. |
