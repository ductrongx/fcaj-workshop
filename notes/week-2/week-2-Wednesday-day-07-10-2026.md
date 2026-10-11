# Ghi chú học tập — 07/10/2026

- Tuần: 2 (05/10/2026–11/10/2026).
- Buổi theo lịch: Thứ Tư — 07/10/2026; đây là ngày phân bổ nội dung, không phải ngày thực hành đã xác minh.
- Ngày cập nhật: 11/10/2026.
- Ngày học/thực hành thực tế: Chưa ghi nhận.
- Vị trí FCJ: Mục 1 — Explore AWS Services → `000048` — Cấp quyền cho ứng dụng bằng IAM role.
- Phạm vi: học luồng EC2 nhận quyền và cấu hình role theo bài hướng dẫn bổ sung; chưa triển khai toàn bộ lab `000048`.
- Nguồn kết quả: người học xác nhận ngày 11/10/2026 đã học và thực hành toàn bộ bài hướng dẫn policy/role trong cuộc trao đổi. Chưa có ảnh cấu hình riêng của role ứng dụng.

> **Cần bổ sung — Ngày thực hiện:** Ngày thực tế học role cho ứng dụng và cấu hình role EC2.

## Mục tiêu

- Phân biệt trust policy với permissions policy.
- Giải thích cách ứng dụng EC2 nhận credentials tạm thời của role.
- Cấu hình role cho EC2 với quyền đọc S3 có phạm vi hẹp, không nhúng khóa dài hạn vào ứng dụng.

## Nội dung học

| Thành phần | Vai trò |
| --- | --- |
| Trust policy | Xác định principal được phép nhận role. Ví dụ principal dịch vụ `ec2.amazonaws.com`. |
| Permissions policy | Xác định phiên role được phép thực hiện action nào trên resource nào. |
| Instance profile | Thành phần chứa role, được liên kết với EC2 để cung cấp credentials cho ứng dụng. |
| Credentials tạm thời | Thông tin xác thực có thời hạn; AWS SDK có thể lấy và làm mới thông qua cơ chế cung cấp credentials của EC2. |

Luồng đã học:

```text
EC2 được liên kết với instance profile chứa role
    → ứng dụng lấy credentials tạm thời qua instance metadata
    → SDK ký request bằng credentials của role
    → S3 đánh giá quyền và trả dữ liệu hoặc Access denied
```

Ứng dụng không nhập mật khẩu IAM user và không bấm Switch Role. Cách này khác lab OperatorUser nhận AdminRole trên Console, dù đều sử dụng phiên role với credentials tạm thời.

**Vì sao tránh nhúng access key dài hạn?** Khóa có thể bị lộ trong code, Git hoặc file cấu hình và phải tự quản lý việc thay khóa. Role giúp tránh phân phối khóa dài hạn cho ứng dụng; vẫn phải giới hạn quyền và bảo vệ môi trường chạy ứng dụng.

## Thực hành và kết quả

Đã thực hiện cấu hình role EC2 theo hướng dẫn, với các tên dưới đây được ghi theo bài người học xác nhận đã làm:

1. Trong account Happy Path, tạo role `fcaj-ec2-photo-reader`, chọn trusted entity AWS service và use case EC2.
2. Thêm inline permissions policy `ReadPhotosOnly` chỉ cho phép `s3:GetObject` với resource `arn:aws:s3:::fcaj-example-bucket/photos/*`.
3. Mở Trust relationships và đối chiếu principal dịch vụ EC2 với action `sts:AssumeRole`.

### Trust policy đã học và cấu hình theo hướng dẫn

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "Service": "ec2.amazonaws.com"
      },
      "Action": "sts:AssumeRole"
    }
  ]
}
```

### Permissions policy đã học và cấu hình theo hướng dẫn

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::fcaj-example-bucket/photos/*"
    }
  ]
}
```

| Nội dung | Kết quả / phạm vi ghi nhận |
| --- | --- |
| Tạo role cho EC2 | Đã thực hiện theo xác nhận người học. |
| Trust relationships | Đã đối chiếu trust cho dịch vụ EC2 theo hướng dẫn. |
| Quyền S3 của role | Đã cấu hình quyền đọc object trong tiền tố `photos/` của bucket ví dụ, không cấp AdministratorAccess. |
| EC2 và bucket/object thật | Chưa triển khai trong phạm vi bài hướng dẫn này. |
| Ứng dụng đọc S3 bằng role | Chưa kiểm chứng; cần EC2, instance profile và tài nguyên S3 thật. |

**Trạng thái kiến thức:** Hoàn thành phạm vi lý thuyết theo xác nhận người học. **Trạng thái triển khai:** Đã cấu hình — chờ kiểm chứng luồng ứng dụng. Không coi việc tạo role là hoàn thành toàn bộ lab `000048`.

Role có trust dành cho EC2 không dùng để Switch Role trực tiếp bằng OperatorUser như AdminRole trong bài trước.

> **Cần bổ sung — Minh chứng cấu hình:** Ảnh tab Permissions và Trust relationships của role ứng dụng, tên role/policy thực tế nếu khác ví dụ và ngày kiểm tra. Chưa có ảnh để đối chiếu cấu hình hiện tại.

**Tài nguyên sau thực hành:** Chưa ghi nhận role/instance profile được giữ để học tiếp hay đã xóa.

> **Cần bổ sung — Trạng thái tài nguyên:** Xác nhận giữ hoặc đã xóa role `fcaj-ec2-photo-reader` và instance profile tương ứng nếu có; kèm kết quả kiểm tra sau cleanup nếu đã dọn.

## Kết quả đạt được

- Giải thích được trust policy trả lời “ai nhận role”, còn permissions policy trả lời “role được làm gì”.
- Hiểu luồng credentials tạm thời của ứng dụng EC2 và vai trò instance profile.
- Đã thực hành cấu hình role EC2 với quyền đọc S3 có phạm vi hẹp theo ghi nhận của người học.
- Phân biệt được role cho người dùng và role cho ứng dụng; không sử dụng mật khẩu hoặc khóa dài hạn nhúng trong code để thiết kế luồng EC2 đọc S3.

## Ghi chú và việc cần làm tiếp

- Theo lịch tuần 3, triển khai phần EC2/S3 của bài `000048`, dùng tên bucket thật trong policy và gắn instance profile cho EC2.
- Kiểm tra danh tính ứng dụng đang dùng, đọc một object được phép và thử một thao tác ngoài phạm vi; ghi output thực tế.
- Không cấu hình khóa IAM user trên EC2 để thay thế role. Khi kiểm thử, cần xác định nguồn credentials để tránh vô tình dùng danh tính khác.
- Dọn tài nguyên sau khi hoàn tất hoặc ghi rõ phạm vi giữ lại.

## Tài liệu tham khảo

- [FCJ — Role cho ứng dụng `000048`](https://000048.awsstudygroup.com/).
- [AWS — Dùng IAM role cho ứng dụng trên EC2](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_use_switch-role-ec2.html).
- [AWS — Switch Role cho người dùng](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_use_permissions-to-switch.html).
