# Bảng lỗi và cách khắc phục · Nhiệm vụ C

20 ca lỗi nằm trong `docs/Ngay13_Lab13_De_bai_hoc_vien.docx`. Năm loại theo Google PAIR: **Do người dùng · Hệ thống · Ngữ cảnh · Giới hạn hệ thống · Ngầm**. Gắn nhãn theo nguyên nhân gốc, không theo chỗ cần sửa.

## Hai bộ nhãn độc lập

Người gắn nhãn 1: Chu Mai Hong (2A202603377, Người 3 — phân loại lõi C) · Người gắn nhãn 2: Người 4 (gắn độc lập, giữ riêng bộ nhãn đến khi cả hai hoàn thành) — gắn trong 8 phút, không trao đổi; bộ nhãn 2 của Người 4 nhận qua tin nhắn ngày lab.

| Ca | Nhãn người 1 | Nhãn người 2 | Trùng? | Nhãn thống nhất |
| --: | --- | --- | --- | --- |
| 1 | Do người dùng | Do người dùng | Trùng | Do người dùng |
| 2 | Hệ thống | Hệ thống | Trùng | Hệ thống |
| 3 | Ngữ cảnh | Ngữ cảnh | Trùng | Ngữ cảnh |
| 4 | Giới hạn hệ thống | Giới hạn hệ thống | Trùng | Giới hạn hệ thống |
| 5 | Ngầm | Ngầm | Trùng | Ngầm |
| 6 | Do người dùng | Do người dùng | Trùng | Do người dùng |
| 7 | Hệ thống | Hệ thống | Trùng | Hệ thống |
| 8 | Hệ thống | Hệ thống | Trùng | Hệ thống |
| 9 | Do người dùng | Do người dùng | Trùng | Do người dùng |
| 10 | Ngữ cảnh | Ngữ cảnh | Trùng | Ngữ cảnh |
| 11 | Giới hạn hệ thống | Giới hạn hệ thống | Trùng | Giới hạn hệ thống |
| 12 | Ngầm | Ngầm | Trùng | Ngầm |
| 13 | Giới hạn hệ thống | Giới hạn hệ thống | Trùng | Giới hạn hệ thống |
| 14 | Do người dùng | Do người dùng | Trùng | Do người dùng |
| 15 | Hệ thống | Hệ thống | Trùng | Hệ thống |
| 16 | Ngữ cảnh | Ngữ cảnh | Trùng | Ngữ cảnh |
| 17 | Ngầm | Ngầm | Trùng | Ngầm |
| 18 | Ngữ cảnh | Ngữ cảnh | Trùng | Ngữ cảnh |
| 19 | Giới hạn hệ thống | Giới hạn hệ thống | Trùng | Giới hạn hệ thống |
| 20 | Hệ thống | Hệ thống | Trùng | Hệ thống |

Ghi chú nhãn Người 1 (theo nguyên nhân gốc):
- Ca 1, 6, 9, 14: đầu vào của khách sai (thiếu số, chọn sai mục, sai mã, bấm nhầm) — việc trợ lý không gợi ý hay không phát hiện là điểm cải thiện, thuộc cột khắc phục, không đổi nhãn.
- Ca 2, 7, 8, 15, 20: trợ lý làm sai so với thiết kế/chính sách và lỗi đã lộ ra (khách mở lại, nhân viên bắt được, trích dẫn nhìn thấy được).
- Ca 3, 10, 16, 18: kết quả đúng theo thiết kế, chỉ giả định (khách hiểu kênh hoàn tiền, hiểu cách tính, chấp nhận lịch gửi) không khớp hoàn cảnh.
- Ca 4, 11, 13, 19: không thể trả lời — thiếu dữ liệu, ngoài phạm vi, đầu vào không xử lý được; ngoài phạm vi là giới hạn dù trợ lý xử lý kém (ca 13).
- Ca 5, 12, 17: sai (tiền, chi phí, dữ liệu) nhưng không ai nhận ra cho tới khi kiểm tra mẫu; "sai" có thể là sai về chi phí, không chỉ về câu trả lời.

**Tỉ lệ đồng thuận:** 20/20 = 100% — đạt mốc từ 16/20 (80%); không có ca bất đồng nên không cần viết lại định nghĩa loại.

## Quy tắc phân biệt cho các ca không trùng

Hai bộ nhãn trùng 20/20 nên không có ca bất đồng phải thống nhất lại; cách xử lý bất đồng đã chuẩn bị: mỗi ca không trùng một câu, nếu đồng thuận dưới 80% thì viết lại định nghĩa loại trước khi đi tiếp. Bộ quy tắc dưới đây vẫn giữ lại như tài liệu phân biệt các ca dễ lẫn (dùng khi có ca mới tương tự):

- Ca 6, 9 là **do người dùng**, không phải hệ thống: gốc lỗi là khách chọn sai mục hoặc nhập sai mã; việc trợ lý không gợi ý là việc cần cải thiện, nằm ở cột khắc phục.
- Ca 13 là **giới hạn hệ thống**: ngoài phạm vi thì là giới hạn, kể cả khi trợ lý xử lý giới hạn đó kém.
- Ca 8, 15 là **hệ thống**, không phải ngầm: sai đã lộ ra (trích dẫn nhìn thấy được, nhân viên bắt được); ngầm chỉ dùng khi không ai nhận ra cho tới khi kiểm tra.
- Ca 18 là **ngữ cảnh**: số tiền đúng chính sách, chỉ giả định "khách hiểu cách tính" là không khớp.
- Ca 12 là **ngầm**: kết quả vẫn đúng nhưng chi phí gấp 3 lần suốt 3 tuần mà không ai thấy; "sai" có thể là sai về chi phí, không chỉ về câu trả lời.

## Bảng khắc phục cho 5 ca, mỗi loại một ca

Chọn ca: 9 (Do người dùng), 7 (Hệ thống), 18 (Ngữ cảnh), 4 (Giới hạn hệ thống), 17 (Ngầm). Cách phát hiện đo được (event, ngưỡng, tần suất); người phụ trách là một vai trò.

| Ca | Loại lỗi | Phát hiện bằng gì | Khắc phục thế nào | Ai phụ trách |
| --: | --- | --- | --- | --- |
| 9 | Do người dùng | Event `input_validation_failed`; cảnh báo khi quá 2% số yêu cầu/ngày | Nhận diện mã sàn TMĐT và tra sang mã vận đơn; không tra được thì hướng dẫn kèm ảnh | PM trợ lý hoàn phí |
| 7 | Hệ thống | Đối soát mỗi giờ: tin nhắn "đã hoàn" không có bản ghi sổ cái ok cùng `trace_id`; ngưỡng 0 ca | Chỉ báo "đã hoàn" khi sổ cái trả ok; lỗi 503 sau 3 lần thì báo "đang xử lý" và chuyển nhân viên | Kỹ sư trưởng agent |
| 18 | Ngữ cảnh | Tỉ lệ mở lại vì số tiền mà kiểm tra thấy đúng, theo tuần | Mẫu tin nhắn luôn ghi cách tính: 30.000 đ × 50% = 15.000 đ | Trưởng nhóm CSKH |
| 4 | Giới hạn hệ thống | Event `handoff_to_staff` với `reason = thieu_du_lieu`, theo loại yêu cầu | Giữ cách chuyển kèm tóm tắt; đưa `quoc_te` ra khỏi pilot | PM trợ lý hoàn phí |
| 17 | Ngầm | Kiểm tra mẫu 100 đơn/tuần so với bảng giá hiện hành; ngưỡng 1% đơn lệch | Xoá bộ nhớ đệm khi có bảng giá mới, ghi phiên bản bảng giá vào trace | Kế toán trưởng |
