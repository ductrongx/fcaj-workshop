# Mẫu nội dung báo cáo tuần

Mẫu này dựa trên bố cục BTC đang có trong `content/1-Worklog/1.2-Week2/_index.vi.md`: **Mục tiêu tuần → Các công việc cần triển khai trong tuần → Kết quả đạt được**. Các phần bổ sung bên dưới là đề xuất để mô tả rõ nội dung học và thực hành, không phải yêu cầu bắt buộc của BTC.

**Mục đích:** giúp người đọc xác định được tuần này học gì, đã làm đến đâu, kết quả được kiểm tra như thế nào và tuần sau cần tiếp tục việc gì. Đây là hướng dẫn biên soạn dùng chung; chỉ sao chép khung ở phần 3 vào trang báo cáo.

## 1. Bố cục đề xuất

| Thứ tự | Phần | Nội dung cần trình bày | Cơ sở |
| --- | --- | --- | --- |
| Đầu trang | Thông tin tuần | Số tuần, chủ đề, khoảng thời gian, ngày cập nhật và phạm vi bài/lab. | Bổ sung |
| 1 | Mục tiêu tuần | Kiến thức hoặc kỹ năng cần đạt, kèm tiêu chí xác định hoàn thành. | Theo mẫu BTC, bổ sung tiêu chí |
| 2 | Các công việc cần triển khai trong tuần | Bảng theo ngày: công việc, ngày bắt đầu, ngày hoàn thành và nguồn tài liệu. | Theo mẫu BTC |
| 3 | Kết quả đạt được | Đối chiếu mục tiêu với kết quả; trạng thái của từng bài/lab và minh chứng tương ứng. | Theo mẫu BTC, bổ sung đối chiếu |
| 4 | Chi tiết nội dung học và thực hành | Kiến thức, cấu hình đáng chú ý và cách kiểm tra kết quả theo từng mã bài/lab. | Bổ sung |
| 5 | Minh chứng thực hành | Ảnh, kết quả lệnh, mã nguồn hoặc sản phẩm có liên hệ đến bài/lab. | Bổ sung |
| 6 | Vấn đề gặp phải và hướng xử lý | Hiện tượng, nguyên nhân đã xác minh, cách xử lý và trạng thái còn lại. | Bổ sung khi có |
| 7 | Bài học rút ra và kế hoạch tuần tiếp theo | Điều học được và việc cần tiếp tục. | Bổ sung |

Tuần ít nội dung có thể gộp phần 4 vào phần 3. Phần 6 có thể bỏ nếu không có vấn đề cần ghi nhận. Giữ ba phần chính của mẫu BTC để các báo cáo thống nhất và dễ đối chiếu. Tuần chỉ học lý thuyết không cần tạo phần lab hoặc ảnh giả định.

**Mức độ chi tiết:** phần 3 trả lời “đạt được gì”; phần 4 giải thích “đã thực hiện và kiểm tra như thế nào”; phần 5 cung cấp minh chứng. Mỗi thông tin chỉ trình bày đầy đủ tại một vị trí, các phần còn lại dẫn chiếu đến đó. Không chép lại toàn bộ hướng dẫn lab hoặc lặp cùng một kết quả ở nhiều bảng.

## 2. Quy tắc điền mẫu

### Phạm vi chương trình, bài/lab và tuần

- Chương trình có **7 mục nội dung học**, mỗi mục gồm nhiều bài và lab; không tính mục FCJ Workforce Program vào 7 mục này.
- **Mục chương trình ≠ mã bài/lab ≠ tuần thực tập.** Một mục có thể học trong nhiều tuần; một tuần có thể học nhiều bài/lab.
- Ghi đúng mã bài đủ 6 chữ số, ví dụ `000001`, `000007`, kèm tên bài và liên kết.
- Tuần 1 đã học bài `000001` và `000007` thuộc Mục 1 — Explore AWS Services. Đây là ví dụ về cách xác định phạm vi, không phải nội dung mặc định của các tuần sau.
- Task nhỏ trong một bài không được ghi thành đã hoàn thành lab chuyên sâu khác. Ví dụ: task EC2 nhận credits trong `000001` khác với bài EC2 riêng `000004`.
- Với bài đang làm từ tuần trước, ghi rõ phần đã có và phần mới thực hiện trong tuần này. Chỉ ghi thêm tiến độ phát sinh, tránh tính lại toàn bộ lab như một kết quả mới.
- Chỉ tính tỷ lệ hoàn thành khi xác định được danh sách công việc và tiêu chí của từng việc. “Hoàn thành 2 bài” không đủ để suy ra phần trăm hoàn thành cả mục chương trình.

### Mục tiêu và tiêu chí hoàn thành

- Mỗi tuần nên có 3–5 mục tiêu phù hợp khối lượng thực tế, dùng động từ cụ thể như **giải thích, phân biệt, cấu hình, triển khai, kiểm tra, xử lý**.
- Mỗi mục tiêu cần một dấu hiệu hoàn thành có thể đối chiếu. Ví dụ: “Phân biệt Cost Budget và Usage Budget” đi kèm tiêu chí “Giải thích được mục đích, đơn vị theo dõi và tình huống sử dụng của từng loại”.
- Với thực hành, tiêu chí phải bao gồm kiểm tra đầu ra, không chỉ thao tác tạo tài nguyên. Tạo thành công một budget và xác nhận nhận được email cảnh báo là hai kết quả riêng.
- Mục tiêu là dự định đầu tuần; cuối tuần đối chiếu với kết quả, ghi rõ mục tiêu chưa đạt hoặc thay đổi phạm vi và lý do. Không sửa mục tiêu thành những việc đã làm chỉ để tất cả đều có trạng thái hoàn thành.

### Ngày và phân bổ nội dung

- Mốc bắt đầu hiện tại: **thứ Hai, 28/09/2026**.
- Tuần N bắt đầu tại `28/09/2026 + 7 × (N − 1) ngày`, kết thúc sau 6 ngày, tức từ thứ Hai đến Chủ nhật.
- Ví dụ: tuần 1 là **28/09–04/10/2026**; tuần 2 là **05/10–11/10/2026**.
- Bảng công việc thường trình bày từ thứ Hai đến thứ Sáu; thêm thứ Bảy/Chủ nhật khi thực tế có học hoặc làm lab.
- Dùng **DD/MM/YYYY** trong cả hai bản ngôn ngữ. Ngày cập nhật báo cáo có thể nằm ngoài khoảng thời gian của tuần.
- Phân biệt **ngày thực hiện** với **ngày viết/cập nhật báo cáo**. Việc thực hiện sau khi tuần kết thúc được ghi vào tuần thực hiện; nếu cần nhắc ở báo cáo cũ, ghi riêng “Cập nhật sau tuần: [ngày] — [kết quả]”. Không chuyển ngày hoàn thành về tuần trước.
- Công việc kéo dài qua nhiều tuần giữ ngày bắt đầu thực tế; kết quả tuần hiện tại chỉ mô tả phần đã làm đến cuối tuần và phần còn lại.
- Ngày bắt đầu và hoàn thành phải dựa trên thông tin thực tế. Nếu chỉ biết tổng nội dung đã học, ghi rõ bảng là **phân bổ nội dung**, không khẳng định đó là nhật ký thực hiện đã xác minh.
- Cột ngày chỉ ghi ngày thực tế hoặc `—` nếu chưa hoàn thành; dùng `Chưa ghi nhận` khi không biết ngày. Đặt trạng thái ở cột riêng để không trộn ngày với kết quả.

### Trạng thái và minh chứng

- Phân biệt kết quả học lý thuyết với kết quả chạy lab. Ghi rõ đã kiểm tra bằng cách nào và kết quả quan sát được.
- Chỉ ghi nguyên nhân lỗi khi có căn cứ; nếu chưa xác định, ghi `Chưa xác định nguyên nhân`.
- Chú thích ảnh đúng nội dung ảnh hiển thị. Ảnh số dư credits không tự chứng minh trạng thái từng task; ảnh danh sách ngân sách không tự chứng minh email cảnh báo đã được gửi.
- Số liệu chi phí, credits và tài nguyên phải kèm thời điểm hoặc phạm vi kiểm tra nếu có. Không suy ra mọi Region đều sạch tài nguyên từ một lần kiểm tra ở một Region.
- Chỉ thêm mục chi phí/dọn dẹp tài nguyên khi phù hợp với lab; không bắt buộc lặp lại toàn bộ nội dung cost management mỗi tuần.

Chọn trạng thái theo phạm vi cụ thể của công việc:

| Trạng thái | Khi sử dụng | Nội dung cần đi kèm |
| --- | --- | --- |
| Hoàn thành | Đã đạt tiêu chí đặt ra cho phạm vi báo cáo. | Kết quả kiểm tra hoặc đầu ra cụ thể. |
| Đang thực hiện | Đã bắt đầu nhưng còn bước chưa xong. | Phần đã làm và phần còn lại. |
| Đã cấu hình — chờ kiểm chứng | Cấu hình xong nhưng chưa có dữ liệu hoặc chưa kiểm tra được đầu ra. | Điều kiện cần chờ và bước kiểm tra tiếp theo. |
| Đã học lý thuyết — chưa thực hành | Đã học nội dung nhưng chưa chạy lab. | Kiến thức đạt được; phạm vi chưa thực hành. |
| Bị chặn | Không thể tiếp tục do điều kiện chưa đáp ứng. | Trở ngại, bằng chứng và điều kiện để tiếp tục. |
| Chưa bắt đầu | Công việc có trong kế hoạch nhưng chưa thực hiện. | Lý do hoặc thời điểm dự kiến chuyển tiếp. |

Trạng thái **Hoàn thành** có thể áp dụng cho mục tiêu lý thuyết nếu tiêu chí là giải thích hoặc phân biệt khái niệm; không suy ra lab tương ứng cũng hoàn thành. “Đã cấu hình — chờ kiểm chứng” không tính là đã xác nhận đầu ra hoạt động.

### Cách sử dụng minh chứng và tài liệu

- Dẫn tài liệu học ngay tại dòng công việc hoặc tiêu đề bài/lab. Ưu tiên liên kết đến bài cụ thể thay vì trang chủ chung.
- Tài liệu tham khảo mô tả kiến thức hoặc các bước hướng dẫn; minh chứng thực hành thể hiện kết quả của chính người học. Giữ rõ vai trò của hai loại nguồn này.
- Đánh số minh chứng trong từng tuần: **MC-01, MC-02…** và dùng cùng mã ở bảng kết quả, phần chi tiết, chú thích ảnh. Nếu chỉ có một hình, có thể dùng “Hình 1” thống nhất.
- Minh chứng có thể là ảnh Console, đoạn output ngắn, đường dẫn commit/file mã nguồn, sơ đồ hoặc sản phẩm đã tạo. Chọn loại phù hợp; không cần chụp mọi thao tác.
- Mỗi minh chứng nêu bài/lab liên quan, kết quả nhìn thấy và phạm vi xác nhận. Với nội dung chỉ được người học xác nhận nhưng chưa có ảnh/log, ghi nguồn là “Ghi nhận thực hành”, không coi là đã kiểm chứng bằng ảnh.
- Không đưa access key, secret key, token hoặc mật khẩu vào báo cáo và ảnh minh chứng.

### Văn phong và nội dung kỹ thuật

- Viết câu ngắn, cụ thể, thống nhất cách xưng hô; ưu tiên “Đã cấu hình…”, “Kết quả kiểm tra…” trong bảng.
- Thay nhận xét chung như “hiểu rõ AWS” bằng điều có thể giải thích hoặc thực hiện. Tránh các từ “thành thạo”, “hoàn toàn”, “tất cả” nếu chưa có căn cứ tương ứng.
- Chỉ ghi cấu hình ảnh hưởng đến việc hiểu kết quả: Region, dịch vụ, thành phần, quyền truy cập hoặc tham số quan trọng. Không biến worklog thành bản sao từng bước của tutorial.
- Với lab triển khai nhiều thành phần, có thể thêm sơ đồ kiến trúc nhỏ. Với lab phát sinh tài nguyên, ghi trạng thái giữ lại/dọn dẹp và phần chưa kiểm tra sau khi kết thúc.
- Kế hoạch tuần sau cần việc cụ thể, lý do ưu tiên, tiêu chí hoàn thành và điều kiện phụ thuộc nếu có. Việc còn tồn tại ở phần vấn đề phải có bước tiếp theo tương ứng.

### File và ngôn ngữ

- Bản Việt: `content/1-Worklog/1.N-WeekN/_index.vi.md`.
- Bản Anh: `content/1-Worklog/1.N-WeekN/_index.md`.
- Ảnh: `static/images/1-worklog/1.N-weekN/`.
- Trong Markdown của trang, dùng `/images/1-worklog/1.N-weekN/ten-anh.png`; render hook hiện có sẽ xử lý đường dẫn theo baseURL.
- Hai bản phải thống nhất ngày, số liệu, mã bài/lab, trạng thái và ảnh. Dịch phần mô tả; giữ nguyên tên dịch vụ AWS và thông tin kỹ thuật.
- Thay mọi chỗ giữ chỗ trong mẫu trước khi dùng. Không tạo thêm sự kiện hoặc kết quả để lấp đầy báo cáo.

## 3. Mẫu để sao chép vào trang tuần

Thay `N`, `YYYY-MM-DD`, `URL` và các nội dung trong ngoặc vuông bằng thông tin thực tế. `date` là ngày bắt đầu tuần; giữ `weight: 1` theo cấu trúc trang tuần đang dùng trong repository. Xóa hướng dẫn giữ chỗ và các phần tùy chọn không sử dụng trước khi hoàn tất.

```markdown
---
title: "Worklog Tuần N"
date: YYYY-MM-DD
weight: 1
chapter: false
pre: " <b> 1.N. </b> "
---

## [Chủ đề chính của tuần]

**Thời gian tuần N:** [DD/MM/YYYY–DD/MM/YYYY].

**Ngày cập nhật báo cáo:** [DD/MM/YYYY].

**Phạm vi học:** [Mục chương trình — mã và tên các bài/lab].

[Đoạn mở đầu 2–3 câu: trọng tâm tuần, kết quả nổi bật và việc đang tiếp tục nếu có.]

### Mục tiêu tuần N

| Mục tiêu | Tiêu chí hoàn thành |
| --- | --- |
| [Kiến thức cần hiểu.] | [Khái niệm có thể giải thích, so sánh hoặc áp dụng.] |
| [Bài/lab hoặc thao tác cần thực hiện.] | [Đầu ra mong đợi và cách kiểm tra.] |
| [Kỹ năng cần rèn luyện.] | [Thao tác có thể thực hiện hoặc vấn đề có thể xử lý.] |

### Các công việc cần triển khai trong tuần

[Nếu chưa có nhật ký ngày thực tế, ghi rõ đây là bảng phân bổ nội dung học.]

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Trạng thái | Nguồn tài liệu |
| --- | --- | --- | --- | --- | --- |
| Thứ Hai | [Mã bài — học lý thuyết / thực hành / kiểm tra.] | [Ngày] | [Ngày / — / Chưa ghi nhận] | [Trạng thái] | [Tên bài](URL) |
| Thứ Ba | [Nội dung.] | [Ngày] | [Ngày / — / Chưa ghi nhận] | [Trạng thái] | [Tên bài](URL) |
| Thứ Tư | [Nội dung.] | [Ngày] | [Ngày / — / Chưa ghi nhận] | [Trạng thái] | [Tên bài](URL) |
| Thứ Năm | [Nội dung.] | [Ngày] | [Ngày / — / Chưa ghi nhận] | [Trạng thái] | [Tên bài](URL) |
| Thứ Sáu | [Nội dung.] | [Ngày] | [Ngày / — / Chưa ghi nhận] | [Trạng thái] | [Tên bài](URL) |

### Kết quả đạt được tuần N

- **Mục tiêu đã đạt:** [Đối chiếu với các mục tiêu đầu tuần; nêu đầu ra chính.]
- **Mục tiêu chưa đạt hoặc thay đổi:** [Phần còn lại và lý do; bỏ dòng nếu không có.]
- **Tiến độ mới trong tuần:** [Phần mới hoàn thành của bài/lab kéo dài từ tuần trước; bỏ dòng nếu không có.]

| Bài/lab hoặc mục tiêu | Kết quả trong phạm vi tuần | Trạng thái | Minh chứng |
| --- | --- | --- | --- |
| [Mã bài — Tên bài](URL) | [Kiến thức hoặc đầu ra thực tế; ghi rõ toàn bộ hay một phần lab.] | [Trạng thái thực tế.] | [MC-01 / Ghi nhận thực hành / Chưa có.] |

### Chi tiết nội dung học và thực hành

#### [Mã bài] — [Tên bài/lab]

**Thuộc mục:** [Số và tên mục chương trình]. **Tài liệu:** [Tên bài](URL).

**Kiến thức đã học:** [Giải thích ngắn gọn khái niệm, vai trò dịch vụ và điều hiểu được sau khi học.]

**Phạm vi thực hành:** [Phần lab thực hiện trong tuần; nếu tiếp nối tuần trước, nêu điểm bắt đầu.]

**Môi trường và cấu hình chính:** [Region, thành phần hoặc tham số ảnh hưởng đến kết quả; bỏ nếu chỉ học lý thuyết.]

**Các bước thực hành chính:**

1. [Chuẩn bị và cấu hình cần thiết.]
2. [Thao tác triển khai chính.]
3. [Kiểm tra kết quả.]

**Kiểm tra kết quả:**

| Nội dung kiểm tra | Kết quả mong đợi | Kết quả thực tế | Minh chứng |
| --- | --- | --- | --- |
| [Thao tác hoặc phép kiểm tra.] | [Dấu hiệu đạt yêu cầu.] | [Kết quả đã quan sát / Chưa kiểm tra được.] | [MC-01 hoặc nguồn ghi nhận.] |

**Phạm vi hoàn thành:** [Toàn bộ lab hay những phần cụ thể; phần nào còn chờ hoặc chưa thực hiện.]

**Tài nguyên sau thực hành:** [Đã dọn dẹp / Giữ lại để học tiếp / Chưa kiểm tra; loại tài nguyên và phạm vi kiểm tra. Bỏ nếu không tạo tài nguyên.]

[Lặp lại cho bài/lab tiếp theo. Nếu chỉ học lý thuyết, giữ kiến thức, ví dụ áp dụng hoặc câu hỏi đã giải đáp; bỏ các trường thực hành không phù hợp.]

### Minh chứng thực hành

**MC-01 — [Mã bài/lab]: [Kết quả được minh chứng].**

![Mô tả ngắn nội dung ảnh](/images/1-worklog/1.N-weekN/ten-anh.png)

[Nêu kết quả quan sát được; bổ sung ngày kiểm tra, Region hoặc giới hạn phạm vi khi có liên quan. Có thể thay ảnh bằng liên kết mã nguồn/sản phẩm hoặc output ngắn.]

### Vấn đề gặp phải và hướng xử lý

| Bài/lab hoặc tính năng | Hiện tượng | Nguyên nhân đã xác minh | Cách xử lý / bước tiếp theo | Trạng thái |
| --- | --- | --- | --- | --- |
| [Nội dung.] | [Thông báo lỗi hoặc hành vi quan sát được.] | [Nguyên nhân có căn cứ / Chưa xác định.] | [Đã xử lý gì; còn cần làm gì.] | [Đã xử lý / Còn tồn tại / Chờ xử lý.] |

[Bỏ phần này nếu không có vấn đề cần ghi nhận.]

### Bài học rút ra và kế hoạch tuần tiếp theo

- **Bài học rút ra:** [Điều hiểu rõ hơn hoặc kinh nghiệm có thể áp dụng.]
- **Điều có thể cải thiện:** [Thay đổi cụ thể trong cách học, thực hành hoặc kiểm tra kết quả.]

| Ưu tiên | Công việc dự kiến | Tiêu chí hoàn thành | Điều kiện cần / Việc còn tồn tại |
| --- | --- | --- | --- |
| [Cao / Vừa] | [Mã bài/lab hoặc việc cần tiếp tục.] | [Kết quả có thể kiểm tra.] | [Quyền truy cập, dữ liệu cần chờ hoặc Không có.] |

**Tổng kết:** [1–2 câu về kết quả chính của tuần và phần còn lại.]
```

## 4. Tên các phần cho bản tiếng Anh

Giữ cùng bố cục và dữ liệu, sử dụng các tiêu đề tương ứng:

| Tiếng Việt | Tiếng Anh |
| --- | --- |
| Worklog Tuần N | Week N Worklog |
| Thời gian tuần N | Week N period |
| Ngày cập nhật báo cáo | Report updated |
| Mục tiêu tuần N | Week N objectives |
| Các công việc cần triển khai trong tuần | Tasks for the week |
| Kết quả đạt được tuần N | Week N achievements |
| Chi tiết nội dung học và thực hành | Learning and lab details |
| Minh chứng thực hành | Practice evidence |
| Vấn đề gặp phải và hướng xử lý | Issues and follow-up actions |
| Bài học rút ra và kế hoạch tuần tiếp theo | Lessons learned and next-week plan |

Các trạng thái dùng thống nhất trong bản Anh: **Completed**, **In progress**, **Configured — pending verification**, **Theory studied — lab not started**, **Blocked**, **Not started**. Dịch “Ghi nhận thực hành” là **Practice notes** để phân biệt với minh chứng ảnh hoặc log.

## 5. Kiểm tra trước khi hoàn tất

- Giữ đủ ba phần chính của mẫu BTC; các phần bổ sung phục vụ nội dung thực tế.
- Mục tiêu có tiêu chí hoàn thành; kết quả đối chiếu được với từng mục tiêu.
- Số tuần và ngày đúng mốc bắt đầu; công việc ngoài tuần được ghi rõ, không chuyển ngày thực hiện về tuần trước.
- Mã bài/lab và mục chương trình đúng phạm vi đã học.
- Trạng thái hoàn thành có căn cứ; phần chưa thực hành hoặc đang chờ được ghi rõ.
- Phần việc tiếp nối tuần trước thể hiện được tiến độ mới và phần còn lại.
- Kết quả mong đợi và kết quả thực tế được phân biệt; minh chứng chỉ xác nhận đúng phạm vi hiển thị.
- Ảnh tồn tại, đường dẫn đúng và chú thích phù hợp nội dung ảnh.
- Các mã minh chứng dẫn đến đúng ảnh/log/sản phẩm; tài liệu tham khảo dẫn đến đúng bài.
- Vấn đề còn tồn tại có bước tiếp theo; kế hoạch tuần sau có tiêu chí hoàn thành.
- Trạng thái tài nguyên sau lab được ghi nhận khi có triển khai; không có thông tin xác thực trong nội dung hoặc ảnh.
- Bản Việt và Anh có cùng số liệu, trạng thái và kết quả.
- Không còn nội dung giữ chỗ hoặc kết quả mẫu của người khác.
- Báo cáo tập trung vào kết quả và bài học cá nhân; không lặp ý hoặc chép lại toàn bộ tutorial.
