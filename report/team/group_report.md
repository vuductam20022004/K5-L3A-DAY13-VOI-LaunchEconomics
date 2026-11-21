# Báo cáo nhóm

## 1. Thông tin nhóm

- Tên nhóm: VOI
- Lớp: L3A
- Thành viên: Vũ Đức Tâm, Nguyễn Trung Duy, Chu Mai Hồng, Phạm Việt Hưng và Trần Việt Tiến. [Thông tin nhóm](../../TEAM.md)

## 2. Mục tiêu và cách tiếp cận

Đánh giá chi phí của trợ lý hoàn phí LogiX-VN và dùng kết quả để thiết kế pilot cho Gate 2a. Nhóm dùng mẫu giả lập gồm 1.200 yêu cầu và 1.624 lượt chạy, với mốc nhân viên tự xử lý là 12.000 đ/yêu cầu.

## 3. Giải pháp

- **A.** Cộng chi phí token, tool, xem lại và làm lại trên toàn mẫu, rồi tính chi phí mỗi việc thành công theo loại yêu cầu và khi phân bổ chi phí cố định. [Bảng chi phí](bang_chi_phi.md#a2--mô-hình-chi-phí-từ-trace)
- **B.** Thử chín kịch bản riêng, một kịch bản kết hợp, ba giới hạn chạy và kịch bản xem lại 100% trong phạm vi pilot. [Bảng độ nhạy](bang_chi_phi.md#b1--đổi-từng-yếu-tố)
- **C.** Hai thành viên gắn nhãn độc lập 20 ca theo nguyên nhân gốc, sau đó đối chiếu và lập phương án phát hiện, khắc phục cho năm loại lỗi. [Bảng lỗi trên nhánh hong](https://github.com/vuductam20022004/K5-L3A-DAY13-VOI-LaunchEconomics/blob/9f14998/report/team/bang_loi.md)
- **D.** Thiết kế pilot ngẫu nhiên theo nhân viên, phân tầng theo depot, có đối chứng đồng thời, ba luật dừng và phương án quay về quy trình thủ công. [Kế hoạch pilot](pilot_plan.yaml)
- **E.** Tính ba chỉ số từ CSV, bổ sung chỉ số sử dụng và an toàn, đề xuất 12 event có `trace_id` và ngưỡng theo dõi rủi ro kinh tế. [Đặc tả chỉ số](chi_so.md)

## 4. Kết quả

- **A.** Có 978/1.200 yêu cầu thành công, với chi phí 4.472 đ/việc (simulated). Trong phạm vi nội địa và hàng nặng, chi phí gồm cố định đạt 4.599 đ/việc tại 45.000 yêu cầu/tháng và 5.784 đ/việc khi khối lượng giảm một nửa (simulated).
- **B.** Tăng gấp đôi số ca làm lại làm chi phí tăng 51,8%. Giới hạn 2 lượt cho chi phí hệ thống thấp nhất, 6.901.220 đ trên mẫu 1.200 yêu cầu. Nếu xem lại 100%, chi phí trong phạm vi pilot là 11.743–12.415 đ/việc theo hai giả định thời gian làm lại (simulated).
- **C.** Hai bộ nhãn trùng **20/20 ca (100%)**, vượt mốc 80%. Bảng khắc phục bao gồm đối soát thông báo đã hoàn với sổ cái và kiểm toán mẫu theo bảng giá hiện hành. Kết quả đối chiếu đã có ở commit `9f14998` trên nhánh `hong`.
- **D.** Phương án gồm 20 nhân viên mỗi nhánh và tối thiểu 299 yêu cầu mỗi nhân viên, tương đương 859,2 yêu cầu hiệu dụng mỗi nhánh. Thiết kế nhắm mức chênh tối thiểu 6 điểm phần trăm với power 0,80. Nếu tác động thật là 5 điểm, power khoảng 0,64. Ngày quyết định dự kiến **05/01/2027**.
- **E.** Trên mẫu giả lập, **82,83%** yêu cầu đóng trong 24 giờ và không mở lại trong 7 ngày, **27,12%** yêu cầu được xem lại có gợi ý bị sửa hoặc bỏ, và **4,25%** yêu cầu mở lại trong 7 ngày.
- **Đề xuất Gate 2a.** **Go có điều kiện** cho yêu cầu nội địa và hàng nặng. Trước khi bật pilot, cần kiểm thử chống hoàn trùng và đối soát sổ cái, phê duyệt thiết kế và luật dừng, bật event và xác nhận chạy lại bài trên máy thứ hai. Trong tuần đầu, đo thời gian xem lại và làm lại thực tế. [Hồ sơ Gate 2a](ho_so_launch_v0.md)
- **Duyệt chéo.** Kết quả hội đồng dành cho nhóm VOI đang chờ ghi nhận.

## 5. Khó khăn và cách xử lý

Khi chọn giới hạn lượt chạy, tối ưu chi phí trợ lý trên mỗi việc thành công dẫn đến chọn một lượt. Sau khi cộng 12.000 đ cho mỗi yêu cầu nhân viên phải làm thay, hai lượt cho tổng chi phí thấp nhất (simulated). Với pilot, việc chia theo nhân viên giới hạn cỡ mẫu hiệu dụng, nên nhóm nâng mức chênh cần phát hiện từ 5 lên 6 điểm phần trăm.

## 6. Tổng hợp đóng góp

Vũ Đức Tâm xây dựng mô hình A và tích hợp mã. Nguyễn Trung Duy kiểm số, phân tích B và tổng hợp báo cáo. Chu Mai Hồng phụ trách phân loại lỗi và phiếu duyệt chéo. Phạm Việt Hưng thiết kế pilot và gắn bộ nhãn thứ hai. Trần Việt Tiến phụ trách chỉ số, event và hồ sơ Gate 2a. [Chi tiết đóng góp](../../TEAM.md)

## 7. Hạn chế và hướng cải thiện

CSV là dữ liệu giả lập và thiếu nhóm đối chứng đồng thời. Tỉ lệ 82,83% mô tả mẫu, còn 70% là mốc giả định dùng để tính cỡ mẫu. Khi pilot, cần theo dõi hai nhánh trong cùng thời gian, chờ đủ cửa sổ 7 ngày sau đóng và cập nhật mô hình chi phí bằng thời gian nhân viên đo được.

## 8. Tài liệu tham khảo

- [Dữ liệu và công thức Lab 13](../../docs/du_lieu_va_cong_thuc.md)
- [Hướng dẫn thực hiện Lab 13](../../docs/Lab13_Huong_dan_chi_tiet_buoi_chieu.md)
- [CSV yêu cầu](../../src/logix_requests.csv) và [CSV lượt chạy](../../src/logix_runs.csv)


# Phiếu chấm hội đồng Gate 2a

Nhóm số n chấm nhóm số n + 1; nhóm cuối chấm nhóm 1. Chấm theo bằng chứng trong hồ sơ, không theo cách trình bày: một đề xuất No-go có lý do bằng số được điểm cao hơn một đề xuất Go bỏ qua con số bất lợi.

- Nhóm chấm (hội đồng): CapNongCapNia 
- Nhóm được chấm: VOI

| Tiêu chí | 0 điểm | 5 điểm | 10 điểm | Điểm | Lý do (có số) |
| --- | --- | --- | --- | ---: | --- |
| Đề xuất khớp bằng chứng | Mâu thuẫn với số của chính nhóm | Khớp nhưng bỏ qua một con số bất lợi | Khớp, nêu cả con số bất lợi và cách xử lý | 10 | "Go có điều kiện" khớp số: phạm vi 4.131 đ/yêu cầu (đã cộng 82 ca nhân viên làm thay) so với 12.000 đ. Nêu cả hai con số bất lợi: power chỉ 0,64 nếu tác động thật +5 điểm, và xem lại 100% lên 11.743–12.415 đ/việc ≈ 12.000 đ [simulated]. Có cách xử lý: Giám đốc vận hành ký đánh đổi MDE 6 điểm; giảm xem lại có kiểm tra an toàn. Mục 5 còn "Chưa" (đồng thuận chưa tính) nhưng đã đưa thành điều kiện, không giấu. |
| Số giả lập và phạm vi | Không nhãn; phạm vi "mọi yêu cầu" | Có nhãn hoặc có thu hẹp phạm vi | Nhãn ở mọi số giả lập; phạm vi thu hẹp có lý do bằng số | 10 | Mọi số chi phí ở mục 1, 2, 3, 7 đều ghi simulated; mục 4 tính từ cột không giả lập nên không cần nhãn. Thu hẹp về noi_dia + hang_nang (982 yêu cầu) có lý do bằng số: quoc_te chỉ thành công 27,3%, 22.515 đ/việc [simulated]. Góp ý: doi_tac chỉ ghi "điều khoản riêng", nên thêm số (0,85× của 12.000 đ). |
| Pilot ra được quyết định | Không đối chứng hoặc thiếu cỡ mẫu | Đủ cỡ mẫu, luật dừng chung chung | Tách được tác động, đủ mẫu, luật dừng có ngưỡng, thời hạn, người có quyền dừng | 10 | Tách được tác động: đối chứng đồng thời, chia theo nhân viên 20 cụm/nhánh, DE 6,96, n hiệu dụng 859/nhánh cho MDE 6 điểm (ghi rõ đánh đổi, power 0,64 nếu +5 điểm), ngày quyết định 05/01/2027. Ba luật dừng trong `pilot_plan.yaml` đủ ngưỡng, thời hạn, người có quyền dừng (an toàn: +2 điểm so với đối chứng hoặc > 6%, 3 ngày, Giám đốc vận hành tắt trong 30 phút; chi phí > 8.000 đ, 2 tuần; sử dụng > 40%, 1 tuần). Góp ý: hồ sơ một trang chưa chép ngưỡng luật dừng; seed và ngày bắt đầu chưa chốt; ca hoàn trùng nên dừng ngay, không chờ 3 ngày. |
| **Tổng** | | | | **30 / 30** | |

**Quyết định của hội đồng:** Go có điều kiện

**Lý do:** Chi phí trong phạm vi 4.131 đ/yêu cầu, chỉ khoảng 0,34× của 12.000 đ [simulated], và thiết kế pilot tách được tác động (20 cụm/nhánh, đối chứng đồng thời). Trước khi bật pilot phải: (1) chép ngưỡng ba luật dừng vào hồ sơ một trang và tách luật hoàn trùng thành dừng ngay; (2) chốt seed và ngày bắt đầu; (3) tính đồng thuận nhãn ≥ 16/20; (4) có kế hoạch giảm tỉ lệ xem lại, vì xem lại 100% đưa chi phí lên 11.743–12.415 đ/việc, ngang mức nhân viên tự làm [simulated].

**Một câu hỏi cho đội trình:** Tỉ lệ mở lại 7 ngày hiện tại đã là 4,25% (51/1.200). Luật dừng an toàn của nhóm đặt ngưỡng bao nhiêu, đo trong bao lâu, và ai bấm dừng? Nếu đặt ngưỡng tuyệt đối dưới 4,25% thì pilot có bị dừng ngay tuần đầu không?

**Câu trả lời của đội trình (ghi lại tại buổi):** Ba luật dừng ghi trong `pilot_plan.yaml` của VOI (dòng 49). Luật an toàn không dùng ngưỡng tuyệt đối dưới 4,25% mà so với đối chứng:

| Luật | Ngưỡng | Thời hạn | Người xử lý |
| --- | --- | --- | --- |
| An toàn | Mở lại 7 ngày cao hơn đối chứng ≥ 2 điểm, hoặc vượt 6%, hoặc ≥ 1 ca hoàn trùng | 3 ngày liên tiếp | Giám đốc vận hành tắt trợ lý trong 30 phút |
| Chi phí | Chi phí mỗi việc thành công > 8.000 đ [simulated] | 2 tuần liên tiếp | PM thu hẹp về noi_dia, giới hạn tối đa 2 lần chạy |
| Sử dụng | Tỉ lệ gợi ý bị sửa hoặc bỏ > 40% | 1 tuần | Trưởng nhóm CSKH phỏng vấn 5 nhân viên trong 3 ngày |

Chỉ số chính thu mẫu từ bước rollout 50%; một yêu cầu đạt nếu đóng trong 24 giờ và không mở lại trong 7 ngày sau khi đóng; ngày quyết định 05/01/2027.

**Nhận xét của hội đồng:** theo câu chữ hiện tại, cả ba điều kiện an toàn đều nằm dưới "3 ngày liên tiếp", nên một ca hoàn trùng phải lặp 3 ngày mới dừng. Đề nghị VOI tách riêng: chỉ cần 1 ca hoàn trùng là dừng ngay.
