# Ghi chú học tập — 06/10/2026

- Tuần: 2 (05/10/2026–11/10/2026).
- Buổi theo lịch: Thứ Ba — 06/10/2026; đây là ngày phân bổ nội dung, không phải ngày thực hành đã xác minh.
- Ngày cập nhật: 11/10/2026.
- Ngày học/thực hành thực tế: Chưa ghi nhận.
- Vị trí FCJ: Mục 1 — Explore AWS Services → `000002` — IAM → Policy và least privilege.
- Nguồn kết quả: người học xác nhận ngày 11/10/2026 đã học và thực hành toàn bộ bài hướng dẫn policy/role trong cuộc trao đổi. Chưa có ảnh/log riêng cho các phép thử bên dưới.

> **Cần bổ sung — Ngày thực hiện:** Ngày thực tế học policy và chạy các phép thử bằng IAM Policy Simulator.

## Mục tiêu

- Đọc được Effect, Action, Resource và Condition trong policy JSON.
- Phân biệt implicit deny, explicit deny và nguyên tắc đặc quyền tối thiểu.
- Mô phỏng quyền đọc/xóa S3, đối chiếu dự đoán với kết quả theo action, resource và context.

## Nội dung học

| Thành phần | Kiến thức đã học |
| --- | --- |
| Version | Phiên bản ngôn ngữ policy; `2012-10-17` không phải ngày tạo policy. |
| Statement | Danh sách các quy tắc quyền. |
| Effect | Allow cho phép; Deny từ chối rõ ràng. |
| Action | API được xét quyền, ví dụ `s3:GetObject` hoặc `s3:DeleteObject`. |
| Resource | Phạm vi tài nguyên; ARN `arn:aws:s3:::fcaj-example-bucket/photos/*` chỉ khớp các object có tiền tố `photos/` trong bucket ví dụ. |
| Condition | Điều kiện để statement áp dụng, ví dụ `aws:SecureTransport` phải là `true`. |

**Least privilege:** cấp đúng action và phạm vi tài nguyên cần cho công việc. Ứng dụng đọc ảnh không cần quyền xóa object, toàn quyền S3 hoặc AdministratorAccess.

**Implicit deny:** không có Allow phù hợp thì yêu cầu bị từ chối. **Explicit deny:** có Deny áp dụng thì yêu cầu bị từ chối dù có Allow. Quyền thực tế còn chịu các lớp giới hạn như SCP và permissions boundary.

## Thực hành và kết quả

Đã dùng IAM Policy Simulator để thử custom policy theo hướng dẫn; kết quả dưới đây được ghi theo xác nhận đã thực hiện toàn bộ bài của người học, chưa đối chiếu ảnh/log từng lần chạy.

### 1. Policy chỉ đọc ảnh

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

| Phép thử | Kết quả ghi nhận | Điều rút ra |
| --- | --- | --- |
| GetObject với `photos/cat.jpg` | Allowed. | Action và resource khớp Allow. |
| GetObject với `private/report.pdf` | Implicit deny. | Object nằm ngoài tiền tố được phép. |
| DeleteObject với `photos/cat.jpg` | Implicit deny. | Quyền đọc không bao gồm quyền xóa. |

Các đường dẫn trên đều thuộc bucket ví dụ `fcaj-example-bucket` của bài mô phỏng; không ghi nhận đã tạo bucket hoặc object thật.

### 2. Thêm explicit deny

Đã thử policy cho đọc `photos/*`, đồng thời có statement Deny `s3:GetObject` với resource `arn:aws:s3:::fcaj-example-bucket/photos/private/*`.

- Đọc `photos/cat.jpg`: Allowed.
- Đọc `photos/private/secret.jpg`: Explicit deny, dù resource cũng khớp statement Allow rộng hơn.
- Kết luận: explicit deny thắng Allow khi cùng áp dụng cho request.

### 3. Thêm điều kiện kết nối bảo mật

Đã thử statement Allow đọc ảnh với điều kiện:

```json
"Condition": {
  "Bool": {
    "aws:SecureTransport": "true"
  }
}
```

| Context mô phỏng | Kết quả ghi nhận |
| --- | --- |
| `aws:SecureTransport = true` | Allowed. |
| `aws:SecureTransport = false` | Implicit deny trong policy đang thử. |

Khi điều kiện không đạt, Allow này không áp dụng. Đây không phải explicit deny HTTP trên toàn bucket; một Allow khác có thể thay đổi kết quả nếu không có lớp kiểm soát chặn.

**Trạng thái:** Hoàn thành phạm vi học và mô phỏng policy theo xác nhận người học. Simulator không gửi request tới S3 và không kiểm tra tài nguyên thật; chưa hoàn thành phép thử API thực tế qua CLI của checklist tuần 2. Custom policy trong Simulator không tự được lưu/gắn vào IAM.

> **Cần bổ sung — Minh chứng:** Ảnh hoặc output kết quả Allowed, implicit deny, explicit deny và hai giá trị context SecureTransport; kèm policy được thử và ngày kiểm tra. Nếu kết quả thực tế khác bảng ghi nhận, bổ sung kết quả đó để đối chiếu.

## Kết quả đạt được

- Đọc được các trường chính của policy và giải thích phạm vi action/resource/condition.
- Thực hành phân biệt quyền đọc với quyền xóa; nhận diện tài nguyên nằm ngoài phạm vi được cấp.
- Giải thích được implicit deny, explicit deny và tác động của Condition bằng các phép thử mô phỏng.
- Vận dụng least privilege để thiết kế quyền đọc ảnh thay vì cấp quyền quản trị rộng.

## Ghi chú và việc cần làm tiếp

- Chưa có ghi nhận phép thử bằng AWS CLI với tài nguyên thật; tiếp tục ở buổi CLI/lab tổng hợp.
- Khi thử thực tế, giữ cùng danh tính, action và Region để so sánh trước/sau một thay đổi quyền nhỏ.
- Không cần tạo lại tài nguyên chỉ để bổ sung ảnh; có thể dùng minh chứng đã lưu hoặc ghi rõ nguồn là ghi nhận thực hành.

## Tài liệu tham khảo

- [FCJ — IAM `000002`](https://000002.awsstudygroup.com/vi/).
- [AWS — IAM Policy Simulator](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_testing-policies.html).
