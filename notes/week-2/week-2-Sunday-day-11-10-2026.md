# Ghi chú học tập — 11/10/2026

- Tuần: 2 (05/10/2026–11/10/2026).
- Buổi theo lịch: Chủ Nhật — 11/10/2026.
- Ngày cập nhật: 11/10/2026; chưa xác nhận đây là ngày thực hiện toàn bộ nội dung ôn tập.
- Phạm vi: tổng hợp IAM/policy/role và `000011`; trạng thái CloudShell, báo cáo và các mục chuyển tiếp tuần 1.
- Nguồn: note tuần 2, ảnh đã kiểm tra và xác nhận người học đã hoàn thành lab CLI, coi phần ôn tập/báo cáo đã thực hiện.

## Nội dung ôn tập

- Phân biệt account, Builder ID, root, IAM user, group, role và policy.
- Phân biệt authentication với authorization; credentials xác minh danh tính, policy quyết định action/resource được phép.
- Giải thích implicit deny, explicit deny, Condition và least privilege bằng bài mô phỏng S3.
- Trust policy xác định ai nhận role; permissions policy xác định role được làm gì. Switch Role thay danh tính/quyền của phiên, Switch back không hoàn tác thao tác đã làm.
- Profile CLI khác danh tính IAM; Region CLI có thể khác Region Console. Đọc kết quả cùng account/Region/phạm vi trước khi kết luận.
- Hiểu vòng đời S3 object/bucket, SNS subscription và email, IAM user/group, tài nguyên network và EC2.

**Trạng thái ôn tập:** Đã thực hiện theo xác nhận người học. Chưa có bài tự kiểm tra độc lập, điểm số hoặc thời lượng đo được; không tạo số liệu đánh giá.

## Tổng hợp kết quả tuần 2

| Nội dung | Trạng thái đến lúc cập nhật | Giới hạn minh chứng |
| --- | --- | --- |
| IAM cơ bản và Switch Role — `000002` | Hoàn thành phạm vi đã ghi trong note Thứ Hai. | Có ảnh tạo đối tượng và phiên AdminRole; cleanup theo ghi nhận. |
| Policy/least privilege | Hoàn thành lý thuyết và mô phỏng theo xác nhận. | Chưa có ảnh Simulator từng phép thử. |
| Role ứng dụng — `000048` | Đã cấu hình — chờ kiểm chứng EC2 đọc S3. | Không coi SSH/EC2 trong `000011` là hoàn thành luồng ứng dụng của `000048`. |
| AWS CLI — `000011` | Hoàn thành toàn bộ lab theo xác nhận người học. | Có ảnh profile, đọc EC2, S3 cleanup, SNS email, IAM và SSH; VPC và cleanup tổng còn thiếu output riêng. |
| CloudShell — `000049` | Bị chặn; tạm bỏ qua theo quyết định người học. | Lỗi account verification; chưa thử lại, không ghi hoàn thành hoặc đã hết lỗi. |
| Ôn tập | Đã thực hiện theo xác nhận người học. | Không có điểm số/bài kiểm tra độc lập. |
| Báo cáo | Đã biên soạn và push bản worklog Việt–Anh từ note Thứ Hai–Thứ Tư; đã sửa menu/breadcrumb. | Kết quả CLI mới trong note Thứ Năm–Thứ Bảy chưa đồng bộ lên worklog ở lần cập nhật note này. |

## Tài nguyên và bài học bảo mật

- S3: ảnh xác nhận xóa object và bucket lab.
- IAM/network/EC2/SNS: cleanup theo xác nhận hoàn thành bài; cần dữ liệu kiểm kê nếu muốn xác nhận đầy đủ tài nguyên phụ thuộc không còn.
- File thử upload S3 là file `.pem`; nếu đó là private key thật, cần thay khóa nếu còn dùng, không tiếp tục dùng khóa đó cho hệ thống cần bảo vệ. Không có bằng chứng để kết luận đã lộ công khai hoặc đã bị truy cập trái phép.
- Email SNS có URL hủy subscription và địa chỉ người nhận; che trước khi dùng minh chứng công khai.

## Các mục chưa được đóng bằng dữ liệu hiện có

1. Phép thử API trước/sau thêm một quyền hẹp bằng cùng danh tính/action/Region: chưa có kết quả riêng.
2. Kiểm tra bảo vệ account/root và Region/AZ theo phạm vi chuyển tiếp tuần 1: chưa đủ dữ liệu.
3. Các loại Budget, kiểm chứng Usage Budget, AWS Support, Cost Explorer, kiểm kê tuần 1 và rà Billing Alerts/Tag Editor/Custom Metrics: chưa có xác nhận mới trong lần cập nhật này.
4. Ngày thực hiện thực tế và minh chứng riêng còn thiếu ở các note; ngày tên file là lịch phân bổ.

Các mục này không phủ nhận xác nhận hoàn thành `000011`; chúng là tiêu chí theo dõi riêng. CloudShell tạm hoãn, không yêu cầu xử lý trong buổi này.

## Việc tiếp theo

- Cập nhật phần kết quả CLI và ảnh phù hợp vào worklog Việt–Anh khi biên soạn báo cáo tiếp theo.
- Bổ sung minh chứng đã lưu và phạm vi cleanup; không tạo lại tài nguyên chỉ để có ảnh.
- Tiếp tục `000048` EC2/S3 theo lịch tuần 3; giữ trạng thái cấu hình/chờ kiểm chứng cho đến khi có request ứng dụng thực tế.

> **Cần bổ sung — Dữ liệu chốt:** Ngày thực hành còn thiếu, kết quả phép thử quyền nếu đã làm và trạng thái tài nguyên sau cleanup. Chỉ ghi kết quả đã thực hiện/quan sát, không thêm ngày hoặc số liệu giả.

## Tài liệu

- [BTC — AWS CLI `000011`](https://000011.awsstudygroup.com/vi/).
- [Timeline checklist](../../TIMELINE_CHECKLIST.md).
- [Template worklog](../../WEEKLY_WORKLOG_TEMPLATE.md).
