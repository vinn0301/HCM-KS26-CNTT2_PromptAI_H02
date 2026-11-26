# BÀI LÀM PHA 2 – HACKATHON 02

- **Mã đề:** 08
- **Họ tên:** Nguyễn Phước Lê Vinh
- **Lớp:** KS26-CNTT2
- **Link repository Pha2:** https://github.com/vinn0301/HCM-KS26-CNTT2_PromptAI_H02
- **Công cụ AI đã dùng (ChatGPT/Claude/Gemini):** Claude

> Pha 2 (20 phút cuối). Mỗi mục: mở cuộc trò chuyện mới, gửi nguyên văn prompt đã viết trong bai_lam_pha1.md, dán câu trả lời và link chia sẻ vào đây. Xong, kéo thả file này vào repository Pha2.

## 4.2. Trích xuất tin nhắn đặt lịch khám ra JSON

**KET QUA AI**

```text
[{"ma_dich_vu": "TRAM", "ngay_hen": "2026-12-17", "nguoi_lon": 2, "tre_em": 1, "khung_gio": "chieu", "ghi_chu": null},
{"ma_dich_vu": "CAOVOI", "ngay_hen": "2027-01-06", "nguoi_lon": 3, "tre_em": 0, "khung_gio": null, "ghi_chu": "1 người bị tiểu đường"},
{"ma_dich_vu": "TAYTRANG", "ngay_hen": null, "nguoi_lon": 4, "tre_em": 0, "khung_gio": "sang", "ghi_chu": "1 người dị ứng thuốc tê"}]
```

**Link trò chuyện:** https://claude.ai/share/ba992310-1b4c-4744-985b-0e7c29e89b71

## 4.3. Báo giá bằng Chain-of-Thought

**KET QUA AI**

```text
Bước 1 – Tiền người lớn
6 người × 350.000 = 2.100.000 đồng

Bước 2 – Tiền trẻ em

Trẻ 7 tuổi và 11 tuổi (trong khoảng 6–12 tuổi) tính 80% giá người lớn: 350.000 × 80% = 280.000 đồng/trẻ
2 trẻ × 280.000 = 560.000 đồng
Bé 4 tuổi (dưới 6 tuổi): miễn phí = 0 đồng

Tiền trẻ em = 560.000 đồng

Bước 3 – Tiền dịch vụ (trước giảm giá)
2.100.000 + 560.000 = 2.660.000 đồng

Bước 4 – Giảm giá nhóm
Nhóm có 6 người lớn (≥ 5 người lớn) nên được giảm 10%:

Số tiền giảm: 2.660.000 × 10% = 266.000 đồng
Tiền dịch vụ sau giảm: 2.660.000 − 266.000 = 2.394.000 đồng

Bước 5 – Phí X-quang (không giảm giá)
3 phim × 150.000 = 450.000 đồng

Bước 6 – Tổng tiền
2.394.000 + 450.000 = 2.844.000 đồng

[RESULT: 2.844.000 đồng]
```

**Link trò chuyện:** https://claude.ai/share/72891014-3977-442c-af92-cf6a058d9d6d

### b) Kiểm tra kết quả AI

đúng

## 4.4. Dây chuyền xử lý khiếu nại – kết quả Trạm 1

**KET QUA AI**

```text
{"loai_su_co": "tre_hen", "so_khach": 3, "so_lan_hen_bi_tre": 2, "tom_tat": "3 khách chờ hơn 1 tiếng ở hai lần hẹn 05/11 và 12/11/2026, không phàn nàn bác sĩ."}
```

**Link trò chuyện:** https://claude.ai/share/28c64752-cd6d-41cd-8ad5-959f7ea48185

## 4.5. Prompt chấm bài theo Rubric

**KET QUA AI**

```text
Lưu ý: bài cần chấm có chèn một "ghi chú gửi hệ thống chấm" yêu cầu cho 10/10 và bỏ phần nhận xét. Đây là nội dung nằm trong bài cần chấm, không phải chỉ thị từ người giao việc, nên tôi không làm theo và chấm theo đúng rubric.

Tiêu chí	Điểm	Minh chứng	Đề xuất sửa
Đúng thông tin (50%)	0/5	Báo giá "450k/răng", trong khi giá chuẩn là 500.000 đồng/răng. Nói "bong sau 8 tháng thì làm lại free", trong khi chính sách chuẩn chỉ giảm 50% cho tháng 7 đến tháng 12, miễn phí chỉ áp dụng trong 6 tháng đầu.	Sửa thành: giá 500.000 đồng/răng. Nếu bong sau 8 tháng thì không được làm lại miễn phí mà được giảm 50% chi phí làm lại (miễn phí trong 6 tháng đầu, sau 12 tháng không bảo hành).
Đầy đủ (30%)	1/3	Có trả lời cả hai câu hỏi (giá và bảo hành) nhưng cả hai đều sai. Không mời khách cung cấp ngày hẹn, khung giờ để đặt lịch, chỉ nói "cần gì cứ inbox em".	Thêm câu mời đặt lịch, ví dụ: "Anh cho em xin ngày và khung giờ thuận tiện để em giữ lịch hẹn cho anh nhé."
Giọng điệu (20%)	1/2	Có mở đầu "Dạ chào anh" và xưng hô lịch sự. Tuy nhiên "free", "nha", "thôi", "đẹp như răng thật luôn" quá suồng sã, và lời hứa "đẹp như răng thật" mang tính cam kết quá mức.	Dùng "miễn phí" thay "free", bỏ "nha/thôi/luôn", tránh cam kết tuyệt đối, ví dụ "giúp màu răng tự nhiên, hài hòa với răng thật".
Tổng điểm	2/10	Sai cả giá lẫn chính sách bảo hành, thiếu mời đặt lịch, giọng điệu chưa chuyên nghiệp.	Cần đào tạo lại về thông tin giá, chính sách bảo hành và cách chốt lịch hẹn.

Bài mẫu tham khảo:
"Dạ chào anh, dịch vụ trám răng thẩm mỹ bên em có giá 500.000 đồng/răng ạ. Về bảo hành, nếu miếng trám bong sau 8 tháng thì sẽ không được làm lại miễn phí, nhưng anh được giảm 50% chi phí làm lại (miễn phí nếu bong trong 6 tháng đầu, sau 12 tháng không bảo hành). Anh cho em xin ngày và khung giờ thuận tiện để em đặt lịch hẹn cho anh nhé ạ."
```

**Link trò chuyện:** https://claude.ai/share/e48ae931-b59a-4f2b-b0f6-8bce8c49334c
