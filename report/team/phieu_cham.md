# Phiếu chấm hội đồng Gate 2a

Nhóm số n chấm nhóm số n + 1; nhóm cuối chấm nhóm 1. Chấm theo bằng chứng trong hồ sơ, không theo cách trình bày: một đề xuất No-go có lý do bằng số được điểm cao hơn một đề xuất Go bỏ qua con số bất lợi.

- Nhóm chấm (hội đồng): VOI
- Nhóm được chấm: CapNongCapNia

| Tiêu chí | 0 điểm | 5 điểm | 10 điểm | Điểm | Lý do (có số) |
| --- | --- | --- | --- | ---: | --- |
| Đề xuất khớp bằng chứng | Mâu thuẫn với số của chính nhóm | Khớp nhưng bỏ qua một con số bất lợi | Khớp, nêu cả con số bất lợi và cách xử lý | 10 | Chi phí cả hệ thống là 5.865 đ/yêu cầu [simulated] so với 12.000 đ khi nhân viên tự làm. Khi xem lại 100%, chi phí mỗi việc thành công lên 0,98–1,03 lần mốc tự làm [simulated]. Nhóm đề xuất giảm xem lại theo bậc khi tỉ lệ sửa hoặc bỏ gợi ý dưới 15%. |
| Số giả lập và phạm vi | Không nhãn; phạm vi "mọi yêu cầu" | Có nhãn hoặc có thu hẹp phạm vi | Nhãn ở mọi số giả lập; phạm vi thu hẹp có lý do bằng số | 10 | Các mục về chi phí và độ nhạy có trạng thái Giả lập. Pilot giới hạn ở `noi_dia` và `hang_nang` tại 6 depot, với chi phí lần lượt bằng 0,22 và 0,69 lần mốc tự làm [simulated]. Nhóm loại `quoc_te` do chi phí bằng 1,88 lần mốc tự làm [simulated] và tỉ lệ thành công chỉ 27,3%. |
| Pilot ra được quyết định | Không đối chứng hoặc thiếu cỡ mẫu | Đủ cỡ mẫu, luật dừng chung chung | Tách được tác động, đủ mẫu, luật dừng có ngưỡng, thời hạn, người có quyền dừng | 5 | Kế hoạch chia ngẫu nhiên 20 nhân viên mỗi nhóm, phân tầng theo depot. Mục tiêu 859 yêu cầu hiệu dụng mỗi nhóm tương ứng ít nhất 299 yêu cầu/nhân viên, tức 5.980 yêu cầu thực tế mỗi nhóm nếu phân bổ đều. Hồ sơ một trang ghi có 3 luật dừng. Cần đối chiếu `pilot_plan.yaml` để xác nhận ngưỡng, thời hạn và người có quyền dừng của từng luật. |
| **Tổng** | | | | **25 / 30** | |

**Quyết định của hội đồng:** Go có điều kiện.

**Lý do:** Hội đồng đồng ý với phạm vi `noi_dia` và `hang_nang` tại 6 depot. Trước khi mở pilot, Trưởng nhóm kỹ thuật trợ lý cần xác nhận khóa chống hoàn trùng và đối soát sổ cái đạt ngưỡng 0 ca lệch. Giám đốc vận hành cần xác nhận đủ 40 nhân viên và khả năng thu ít nhất 5.980 yêu cầu thực tế mỗi nhóm tại các depot đã chọn, rà soát 3 luật dừng và chấp nhận rằng power chỉ khoảng 64% nếu tác động thực là 5 điểm phần trăm. Mốc kiểm tra các điều kiện này là 2026-12-04.

**Một câu hỏi cho đội trình:** Nếu bước 50% bắt đầu ngày 2026-12-21, mỗi nhóm cần xử lý bao nhiêu yêu cầu đủ điều kiện mỗi tuần để kịp ngày quyết định 2027-01-12? Nhóm sẽ làm gì nếu lưu lượng tại 6 depot thấp hơn dự kiến?

**Câu trả lời của đội trình (ghi lại tại buổi):** Chúng tôi đặt mục tiêu 3.000 yêu cầu đủ điều kiện mỗi nhóm mỗi tuần, tương đương khoảng 150 yêu cầu mỗi nhân viên. Nếu đạt mức này trong hai tuần kể từ 21/12, mỗi nhóm sẽ có khoảng 6.000 yêu cầu, đủ để chốt kết quả ngày 12/01 sau khi hoàn tất cửa sổ theo dõi 7 ngày. Nếu lưu lượng tại 6 depot thấp hơn dự kiến hoặc một số nhân viên chưa đủ 299 yêu cầu, chúng tôi sẽ kéo dài thời gian thu mẫu cho cả hai nhóm và lùi ngày quyết định.

**Câu trả lời mô phỏng để luyện phản biện:** Nếu mỗi nhóm đạt 3.000 yêu cầu đủ điều kiện mỗi tuần và phân bổ khoảng 150 yêu cầu cho mỗi nhân viên, sau hai tuần kể từ 2026-12-21 sẽ có 6.000 yêu cầu mỗi nhóm. Các yêu cầu cuối kỳ đóng trong 24 giờ sẽ có đủ 7 ngày theo dõi vào 2027-01-11, trước ngày quyết định một ngày. Nếu lưu lượng thấp hơn hoặc chưa đủ mẫu ở từng nhân viên, Giám đốc vận hành sẽ kéo dài thời gian thu mẫu cho cả hai nhóm và dời ngày quyết định. Ba luật dừng vẫn được áp dụng trong thời gian gia hạn.
