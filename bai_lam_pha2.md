# BÀI LÀM PHA 2 – HACKATHON 02

- **Mã đề:** 08
- **Họ tên: Phạm Quang Vinh**
- **Lớp: CNTT1**
- **Link repository Pha2:**https://github.com/qvinh537/HN-KS26-CNTT1_PromptAI_H02_Pha1-Pha2/blob/main/bai_lam_pha2.md
- **Công cụ AI đã dùng (ChatGPT/Gemini):**

> Pha 2 (20 phút cuối). Mỗi mục: mở cuộc trò chuyện mới, gửi nguyên văn prompt đã viết trong bai_lam_pha1.md, dán câu trả lời và link chia sẻ vào đây. Xong, kéo thả file này vào repository Pha2.

## 4.2. Trích xuất tin nhắn đặt lịch khám ra JSON

**KET QUA AI**

```text
[
  {
    "Context": "Bạn là chatbot tiếp nhận và chuẩn hóa yêu cầu đặt lịch dịch vụ nha khoa. Bảng mã dịch vụ: CAOVOI – Khám và cạo vôi răng; TRAM – Trám răng thẩm mỹ (1 răng); TAYTRANG – Tẩy trắng răng.",
    "Request": "Xử lý tin nhắn đặt lịch được cung cấp trong cặp dấu phân tách <tin_nhan>...</tin_nhan> và chuyển thành dữ liệu JSON.",
    "Explanation": "Áp dụng đủ 5 quy tắc chuẩn hóa: (1) ma_dich_vu lấy theo bảng mã dịch vụ; (2) ngay_hen dạng YYYY-MM-DD, không ghi năm thì lấy năm 2026, không có ngày cụ thể thì null; (3) không nhắc trẻ em thì tre_em = 0, mọi khách mặc định là người lớn; (4) khung_gio chỉ nhận sang, chieu hoặc null; (5) ghi_chu chỉ ghi yêu cầu đặc biệt về sức khỏe, bệnh nền, dị ứng, tâm lý, không có thì null. Few-shot 1: Tin nhắn đặt cạo vôi ngày 12/11/2026 cho 1 người lớn và 2 bé, buổi sáng, một bé sợ khoan → {\"ma_dich_vu\":\"CAOVOI\",\"ngay_hen\":\"2026-11-12\",\"nguoi_lon\":1,\"tre_em\":2,\"khung_gio\":\"sang\",\"ghi_chu\":\"1 bé rất sợ khoan\"}. Few-shot 2: Tin nhắn tẩy trắng buổi chiều, đi một mình, hôm nào cũng được → {\"ma_dich_vu\":\"TAYTRANG\",\"ngay_hen\":null,\"nguoi_lon\":1,\"tre_em\":0,\"khung_gio\":\"chieu\",\"ghi_chu\":null}.",
    "Action": {
      "tin_nhan": "<tin_nhan>Cho mình hẹn trám răng ngày 17/12 nhé, 2 người lớn với 1 bé 9 tuổi, buổi chiều.</tin_nhan>",
      "ket_qua": {
        "ma_dich_vu": "TRAM",
        "ngay_hen": "2026-12-17",
        "nguoi_lon": 2,
        "tre_em": 1,
        "khung_gio": "chieu",
        "ghi_chu": null
      }
    },
    "Tone": "Chính xác, rõ ràng, chuyên nghiệp và thân thiện.",
    "Extras": "Chỉ xuất dữ liệu JSON hợp lệ. Không thêm lời chào, giải thích hoặc trường ngoài quy định."
  },
  {
    "Context": "Bạn là chatbot tiếp nhận và chuẩn hóa yêu cầu đặt lịch dịch vụ nha khoa. Bảng mã dịch vụ: CAOVOI – Khám và cạo vôi răng; TRAM – Trám răng thẩm mỹ (1 răng); TAYTRANG – Tẩy trắng răng.",
    "Request": "Xử lý tin nhắn đặt lịch được cung cấp trong cặp dấu phân tách <tin_nhan>...</tin_nhan> và chuyển thành dữ liệu JSON.",
    "Explanation": "Áp dụng đủ 5 quy tắc chuẩn hóa: (1) ma_dich_vu lấy theo bảng mã dịch vụ; (2) ngay_hen dạng YYYY-MM-DD, không ghi năm thì lấy năm 2026, không có ngày cụ thể thì null; (3) không nhắc trẻ em thì tre_em = 0, mọi khách mặc định là người lớn; (4) khung_gio chỉ nhận sang, chieu hoặc null; (5) ghi_chu chỉ ghi yêu cầu đặc biệt về sức khỏe, bệnh nền, dị ứng, tâm lý, không có thì null. Few-shot 1: Tin nhắn đặt cạo vôi ngày 12/11/2026 cho 1 người lớn và 2 bé, buổi sáng, một bé sợ khoan → {\"ma_dich_vu\":\"CAOVOI\",\"ngay_hen\":\"2026-11-12\",\"nguoi_lon\":1,\"tre_em\":2,\"khung_gio\":\"sang\",\"ghi_chu\":\"1 bé rất sợ khoan\"}. Few-shot 2: Tin nhắn tẩy trắng buổi chiều, đi một mình, hôm nào cũng được → {\"ma_dich_vu\":\"TAYTRANG\",\"ngay_hen\":null,\"nguoi_lon\":1,\"tre_em\":0,\"khung_gio\":\"chieu\",\"ghi_chu\":null}.",
    "Action": {
      "tin_nhan": "<tin_nhan>Đặt lịch cạo vôi cho 3 người ngày 06/01/2027 ạ. Một người bị tiểu đường.</tin_nhan>",
      "ket_qua": {
        "ma_dich_vu": "CAOVOI",
        "ngay_hen": "2027-01-06",
        "nguoi_lon": 3,
        "tre_em": 0,
        "khung_gio": null,
        "ghi_chu": "1 người bị tiểu đường"
      }
    },
    "Tone": "Chính xác, rõ ràng, chuyên nghiệp và thân thiện.",
    "Extras": "Chỉ xuất dữ liệu JSON hợp lệ. Không thêm lời chào, giải thích hoặc trường ngoài quy định."
  },
  {
    "Context": "Bạn là chatbot tiếp nhận và chuẩn hóa yêu cầu đặt lịch dịch vụ nha khoa. Bảng mã dịch vụ: CAOVOI – Khám và cạo vôi răng; TRAM – Trám răng thẩm mỹ (1 răng); TAYTRANG – Tẩy trắng răng.",
    "Request": "Xử lý tin nhắn đặt lịch được cung cấp trong cặp dấu phân tách <tin_nhan>...</tin_nhan> và chuyển thành dữ liệu JSON.",
    "Explanation": "Áp dụng đủ 5 quy tắc chuẩn hóa: (1) ma_dich_vu lấy theo bảng mã dịch vụ; (2) ngay_hen dạng YYYY-MM-DD, không ghi năm thì lấy năm 2026, không có ngày cụ thể thì null; (3) không nhắc trẻ em thì tre_em = 0, mọi khách mặc định là người lớn; (4) khung_gio chỉ nhận sang, chieu hoặc null; (5) ghi_chu chỉ ghi yêu cầu đặc biệt về sức khỏe, bệnh nền, dị ứng, tâm lý, không có thì null. Few-shot 1: Tin nhắn đặt cạo vôi ngày 12/11/2026 cho 1 người lớn và 2 bé, buổi sáng, một bé sợ khoan → {\"ma_dich_vu\":\"CAOVOI\",\"ngay_hen\":\"2026-11-12\",\"nguoi_lon\":1,\"tre_em\":2,\"khung_gio\":\"sang\",\"ghi_chu\":\"1 bé rất sợ khoan\"}. Few-shot 2: Tin nhắn tẩy trắng buổi chiều, đi một mình, hôm nào cũng được → {\"ma_dich_vu\":\"TAYTRANG\",\"ngay_hen\":null,\"nguoi_lon\":1,\"tre_em\":0,\"khung_gio\":\"chieu\",\"ghi_chu\":null}.",
    "Action": {
      "tin_nhan": "<tin_nhan>Tẩy trắng răng cuối năm còn lịch không ạ? Nhà em 4 người lớn, một người dị ứng thuốc tê, đi buổi sáng.</tin_nhan>",
      "ket_qua": {
        "ma_dich_vu": "TAYTRANG",
        "ngay_hen": null,
        "nguoi_lon": 4,
        "tre_em": 0,
        "khung_gio": "sang",
        "ghi_chu": "1 người dị ứng thuốc tê"
      }
    },
    "Tone": "Chính xác, rõ ràng, chuyên nghiệp và thân thiện.",
    "Extras": "Chỉ xuất dữ liệu JSON hợp lệ. Không thêm lời chào, giải thích hoặc trường ngoài quy định."
  }
]
```

**Link trò chuyện:** https://chatgpt.com/share/6b07e610-d0ac-83ec-9da9-7b357db44f08

## 4.3. Báo giá bằng Chain-of-Thought

**KET QUA AI**

```text
Bước 1: Tiền dịch vụ người lớn

6 người lớn sử dụng dịch vụ CAOVOI:

\(6 \times 350.000 = 2.100.000\) đồng

Bước 2: Tiền dịch vụ trẻ em
- Trẻ 7 tuổi: \(350.000 \times 80\% = 280.000\) đồng
- Trẻ 11 tuổi: \(350.000 \times 80\% = 280.000\) đồng
- Bé 4 tuổi: \(0\) đồng (miễn phí)
Tổng tiền trẻ em:

\(280.000 + 280.000 + 0 = 560.000\) đồng

Bước 3: Tiền dịch vụ trước giảm giá

\(2.100.000 + 560.000 = 2.660.000\) đồng

Bước 4: Giảm giá nhóm

Nhóm có 6 người lớn, đủ điều kiện giảm 10%:

\(2.660.000 \times 10\% = 266.000\) đồng

Tiền dịch vụ sau giảm:

\(2.660.000 - 266.000 = 2.394.000\) đồng

Bước 5: Phí chụp X-quang

3 người, mỗi người 1 phim:

\(3 \times 150.000 = 450.000\) đồng

Bước 6: Tổng tiền

\(2.394.000 + 450.000 = 2.844.000\) đồng

[RESULT:2844000đồng]
```

**Link trò chuyện:**https://chatgpt.com/share/6b07e685-8c84-83ec-bdba-0b51eb2997e0

### b) Kiểm tra kết quả AI

(Ghi kết luận AI đúng hay sai; nếu sai, ghi bước sai đầu tiên và kết quả đúng của bước đó – xoá dòng này)

## 4.4. Dây chuyền xử lý khiếu nại – kết quả Trạm 1

**KET QUA AI**

```text
Kết quả Prompt Chaining – 3 trạm
Trạm 1 – Phân loại khiếu nại
{
  "loai_su_co": "tre_hen",
  "so_khach": 3,
  "so_lan_hen_bi_tre": 2,
  "tom_tat": "Gia đình 3 người phải chờ hơn 1 giờ trong 2 lần hẹn cạo vôi răng."
}


Trạm 2 – Tính mức đền bù
Mỗi khách được hoàn 100.000 đồng cho mỗi lần hẹn bị trễ quá 45 phút.
- Số khách: 3
- Số lần hẹn bị trễ: 2
- Tổng đền bù: 3 × 2 × 100.000 = 600.000 đồng
- Cần Giám đốc duyệt: Có, vì tổng mức đền bù trên 500.000 đồng.
{
  "loai_su_co": "tre_hen",
  "muc_den_bu": 600000,
  "can_duyet": true
}


Trạm 3 – Email phản hồi khách hàng
Kính gửi Quý khách,

Nha khoa Nụ Cười chân thành xin lỗi gia đình vì đã phải chờ hơn một giờ trong cả hai lần hẹn ngày 05/11/2026 và 12/11/2026. Chúng tôi hiểu rằng việc chờ đợi kéo dài đã ảnh hưởng đến thời gian và trải nghiệm của gia đình.

Phòng khám ghi nhận phản hồi của Quý khách và rất cảm ơn sự hài lòng của gia đình đối với bác sĩ Nam. Chúng tôi sẽ rà soát quy trình tiếp nhận và sắp xếp lịch hẹn để hạn chế tình trạng tương tự.

Theo chính sách đền bù, gia đình được hoàn 600.000 đồng cho hai lần hẹn bị trễ. Do mức đền bù vượt 500.000 đồng, khoản hoàn tiền cần được Giám đốc phòng khám phê duyệt trước khi thực hiện.

Một lần nữa, chúng tôi thành thật xin lỗi và mong có cơ hội phục vụ gia đình tốt hơn.

Trân trọng,
Bộ phận Chăm sóc khách hàng
Nha khoa Nụ Cười
```

**Link trò chuyện:**https://chatgpt.com/share/6b07e6fe-7c30-83ec-b22f-a859d0d9ff82

## 4.5. Prompt chấm bài theo Rubric

**KET QUA AI**

```text
Tiêu chí	Điểm	Minh Chứng	Đề xuất sửa
Đúng thông tin (50%)	0/5	Lỗi 1: “Trám răng bên em 450k/răng thôi” — Sai giá. Giá chuẩn là 500.000 đồng/răng, nhân viên báo thấp hơn 50.000 đồng/răng. Lỗi 2: “Bong sau 8 tháng thì em làm lại free cho anh nha.” — Sai chính sách bảo hành. Sau 8 tháng, khách chỉ được giảm 50% chi phí làm lại, không được miễn phí.	“Dạ, dịch vụ trám răng thẩm mỹ có giá 500.000 đồng/răng. Nếu miếng trám bong sau 8 tháng, anh được hỗ trợ làm lại với mức giảm 50% chi phí theo chính sách bảo hành.”
Đầy đủ (30%)	1,5/3	Lỗi 1: “Cần gì cứ inbox em ạ!” — Chưa mời khách cung cấp ngày hẹn và khung giờ cụ thể để đặt lịch. Câu trả lời đã đề cập giá và bảo hành nhưng chưa đáp ứng đầy đủ yêu cầu đặt lịch.	“Anh vui lòng cho em xin ngày hẹn và khung giờ thuận tiện để em hỗ trợ đặt lịch cho anh nhé!”
Giọng điệu (20%)	1/2	Lỗi 1: “450k/răng thôi” — Cách diễn đạt “thôi” mang tính suồng sã, thiếu chuyên nghiệp trong tư vấn dịch vụ. Lỗi 2: “free”, “inbox em” — Sử dụng từ ngữ thân mật, chưa phù hợp với phong cách tư vấn chuyên nghiệp.	Sử dụng cách diễn đạt lịch sự, chuyên nghiệp như “500.000 đồng/răng”, “được hỗ trợ làm lại với mức giảm 50%” và “anh vui lòng cung cấp thông tin để em hỗ trợ đặt lịch”.
Tổng điểm	2,5/10	Câu trả lời sai cả giá dịch vụ và chính sách bảo hành, chưa đầy đủ thông tin đặt lịch, đồng thời còn sử dụng một số từ ngữ thiếu chuyên nghiệp.	Cần sửa lại giá, chính sách bảo hành, bổ sung lời mời đặt lịch và chuẩn hóa giọn
**Link trò chuyện:**https://chatgpt.com/share/6b07e7ac-4808-83ec-a79e-87fc048f6aa5
