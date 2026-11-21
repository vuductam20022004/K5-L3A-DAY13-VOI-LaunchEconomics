# Báo cáo cá nhân — Chu Mai Hong

## 1. Thông tin thành viên

- Họ tên: Chu Mai Hong
- MSSV: 2A202603377
- Email:
- Vai trong nhóm: Người 3, phụ trách phân loại lỗi C và phiếu duyệt chéo.

## 2. Phần việc phụ trách

- Gắn nhãn độc lập 20 ca lỗi theo năm loại Google PAIR, giữ riêng bộ nhãn cho tới khi Người 4 hoàn thành.
- Phụ trách duy nhất `report/team/bang_loi.md`: hai bộ nhãn, tỉ lệ đồng thuận, quy tắc phân biệt ca không trùng và bảng khắc phục 5 ca đủ năm loại.
- Ghi kết quả duyệt chéo Gate 2a thực tế vào `report/team/phieu_cham.md`.
- Gửi tỉ lệ đồng thuận và danh sách lỗi cần kiểm soát cho Người 4 và Người 5 theo mốc 16:08.

## 3. Đóng góp cụ thể

- Gắn nhãn độc lập 20 ca theo nguyên nhân gốc, không theo chỗ cần sửa: Do người dùng (ca 1, 6, 9, 14) · Hệ thống (ca 2, 7, 8, 15, 20) · Ngữ cảnh (ca 3, 10, 16, 18) · Giới hạn hệ thống (ca 4, 11, 13, 19) · Ngầm (ca 5, 12, 17).
- Soạn sẵn bộ quy tắc phân biệt cho các ca dễ lẫn: ca 6, 9 là do người dùng (gốc lỗi ở đầu vào của khách); ca 13 là giới hạn hệ thống (ngoài phạm vi dù trợ lý xử lý kém); ca 8, 15 là hệ thống (sai đã lộ ra, không phải ngầm); ca 18 là ngữ cảnh (số tiền đúng chính sách); ca 12 là ngầm (chi phí gấp 3 lần mà không ai thấy).
- Chọn 5 ca, mỗi loại một ca (9, 7, 18, 4, 17) và điền bảng khắc phục: mỗi dòng có cách phát hiện đo được (event kèm `trace_id`, ngưỡng, tần suất) và một vai trò phụ trách.
- Kiểm chứng số A/B mà bảng khắc phục tham chiếu: chạy lại `src/lab13.py` trong `src/`, ba phép thử A1 in ĐẠT (1,20 · 1,25 · 1,25) và các số A3 khớp với `bang_chi_phi.md` (quoc_te 22.515 đ = 1,88×).

## 4. Bằng chứng

- [Bảng lỗi và cách khắc phục](bang_loi.md): hai bộ nhãn độc lập, tỉ lệ đồng thuận 20/20 = 100%, quy tắc phân biệt, bảng khắc phục 5 ca đủ năm loại.
- [Phiếu duyệt chéo](phieu_cham.md): chờ kết quả Gate 2a thực tế tại buổi để ghi.
- Chạy `src/lab13.py` trên hai CSV gốc: A1 ĐẠT; A2 ghi nhận 978/1.200 việc thành công, chi phí 4.472 đ/việc [simulated]; A3 khớp số trong `bang_chi_phi.md`.

## 5. Công cụ AI đã dùng

- Dùng Claude hỗ trợ đọc đề, liệt kê 20 ca từ `docs/Ngay13_Lab13_De_bai_hoc_vien.docx` và soát khung `bang_loi.md`. Việc gắn nhãn 20 ca và chọn ca cho bảng khắc phục do bản thân làm độc lập; kết quả được kiểm tra bằng cách chạy lại code A của Người 1 và đối chiếu số với `bang_chi_phi.md` trước khi tham chiếu vào bảng C.

## 6. Tự đánh giá

- Phần lõi C hoàn chỉnh: bộ nhãn Người 3, đối chiếu với bộ nhãn Người 4 đạt 20/20 = 100% (vượt mốc 80%), quy tắc phân biệt, bảng khắc phục 5 ca — và nhất quán với phạm vi pilot trong `pilot_plan.yaml` (loại quoc_te, ca 4; luật dừng 1 đã thêm điều kiện chặn hoàn trùng ca 20 theo Người 4). Còn lại: phiếu duyệt chéo chỉ điền được sau kết quả Gate 2a thực tế tại buổi.
