# Hướng dẫn dự án

Áp dụng cho toàn bộ repository. Khi biên soạn, ưu tiên yêu cầu hiện tại của người dùng; dùng file này làm quy tắc chung và template làm hướng dẫn bố cục chi tiết.

## Bối cảnh

Đây là website Hugo song ngữ Việt–Anh ghi nhận quá trình tham gia chương trình **First Cloud AI Journey** theo hình thức **tự học theo tiến độ cá nhân (self-paced)**:

- **3 tháng đầu:** học AWS và thực hành lab theo tài liệu được cung cấp.
- **3 tháng tiếp theo:** thực hiện project, vận dụng kiến thức đã học.

Repository hiện dùng để ghi worklog, kiến thức tự học, kết quả thực hành và các hoạt động liên quan. Chỉ báo cáo kết quả thực tế của người học.

## Tài liệu tham chiếu

- Trang tài liệu chính: [First Cloud Journey](https://cloudjourney.awsstudygroup.com/).
- Nội dung học gồm **7 mục**, mỗi mục có nhiều bài/lab; không tính mục FCJ Workforce Program vào 7 mục học.
- Format báo cáo tuần: [WEEKLY_WORKLOG_TEMPLATE.md](WEEKLY_WORKLOG_TEMPLATE.md).
- Format các phần khác: tham khảo mẫu BTC có sẵn trong thư mục `content/` tương ứng.
- Đọc template liên quan trước khi sửa. Nội dung mẫu dùng để tham khảo cấu trúc, không phải bằng chứng người học đã hoàn thành công việc.

## Quy tắc viết và cập nhật

- Tuân theo bố cục mẫu BTC; có thể bổ sung chi tiết giúp kết quả rõ hơn. Báo cáo tuần phải theo `WEEKLY_WORKLOG_TEMPLATE.md`, giữ ba phần chính: **mục tiêu, công việc trong tuần, kết quả đạt được**.
- Viết **ngắn gọn, chuyên nghiệp, cụ thể**; tránh lặp ý hoặc chép lại toàn bộ tài liệu lab.
- Ghi đúng mục chương trình, mã bài/lab, phạm vi đã học và trạng thái thực hành. Không coi task nhỏ là hoàn thành một lab chuyên sâu khác.
- Dùng trạng thái theo template, phân biệt đã học lý thuyết, đã triển khai và đã kiểm chứng. Dựa trên thông tin người học cung cấp và minh chứng hiện có; khi chúng mâu thuẫn, ghi rõ điểm chưa xác định. Không tự tạo kết quả, ngày, số liệu hoặc nguyên nhân lỗi.
- Mốc bắt đầu hiện tại là **28/09/2026**; chia tuần từ thứ Hai đến Chủ nhật theo template. Phân biệt ngày thực hiện với ngày cập nhật báo cáo; ghi rõ khi lịch chỉ là phân bổ nội dung.
- Mặc định cập nhật cả bản Việt và Anh, trừ khi người dùng chỉ yêu cầu một bản; thống nhất ngày, mã bài, số liệu, trạng thái và minh chứng.
- Chỉ chỉnh phần được yêu cầu; giữ nội dung mẫu của các phần chưa cần cập nhật.
- Giữ front matter, đường dẫn trang và cấu hình hiển thị hiện có, trừ khi yêu cầu cần thay đổi. Không ghi đè thay đổi của người dùng; chỉ commit, push hoặc deploy khi được yêu cầu.

## Thông tin còn thiếu

Khi đối chiếu với template, đặt placeholder **ngay tại phần liên quan** nếu thiếu thông tin cần thiết, để người học bổ sung:

```markdown
> **Cần bổ sung — Minh chứng:** [Ảnh hoặc log kiểm tra kết quả của lab 000xxx.]
> **Cần bổ sung — Phạm vi triển khai:** [Các bước đã làm, phần chưa triển khai và trạng thái hiện tại.]
> **Cần bổ sung — Ngày thực hiện:** [Ngày bắt đầu và hoàn thành thực tế.]
```

- Placeholder mô tả cụ thể cần bổ sung gì; dùng `Cần bổ sung` thống nhất trong bản Việt và `To be added` trong bản Anh.
- Nếu đã xác nhận chưa triển khai, ghi trạng thái **chưa triển khai** và phần còn lại; không dùng placeholder để che trạng thái đó.
- Chỉ đặt placeholder cho phần cần thiết nhưng thiếu dữ liệu. Có thể bỏ phần tùy chọn không liên quan đến tuần, ví dụ phần lab khi chỉ học lý thuyết.
- Phân biệt chỗ giữ chỗ của mẫu (`N`, `URL`, `[Tên bài]`) với ghi chú thiếu dữ liệu: thay hoặc xóa chỗ giữ chỗ của mẫu, giữ ghi chú **Cần bổ sung** trong bản nháp cho đến khi có thông tin.
- Tiếp tục hoàn thiện các phần có đủ dữ liệu; chỉ hỏi lại khi thiếu thông tin làm thay đổi phạm vi hoặc kết luận chính.
- Xóa placeholder sau khi có thông tin. Khi bàn giao bản nháp, nêu ngắn gọn các mục còn cần bổ sung; không tuyên bố đã đầy đủ nếu vẫn còn placeholder.

## Vị trí file và kiểm tra

- Trang tuần: `content/1-Worklog/1.N-WeekN/_index.vi.md` và `_index.md`.
- Ảnh tuần: `static/images/1-worklog/1.N-weekN/`; liên kết trong trang dùng `/images/1-worklog/1.N-weekN/ten-anh.png`.
- Chú thích minh chứng đúng nội dung ảnh/log; không đưa thông tin xác thực vào báo cáo.
- Sau khi sửa trang hoặc cấu hình, kiểm tra liên kết, đường dẫn ảnh, tính thống nhất Việt–Anh và chạy `hugo --minify` nếu có Hugo. Phiên bản build tham chiếu nằm trong `.github/workflows/hugo.yml`.
- Với thay đổi chỉ ở tài liệu hướng dẫn gốc, kiểm tra nội dung và liên kết là đủ. Khi bàn giao, nêu phần đã sửa, kiểm tra đã thực hiện và thông tin còn thiếu; ghi rõ nếu chưa build được.
