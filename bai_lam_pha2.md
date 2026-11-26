# BÀI LÀM PHA 2 – HACKATHON 02

- **Mã đề:** 04
- **Họ tên:Hoàng Khánh Nhi**
- **Lớp:Hoàng Khánh Nhi**
- **Link repository Pha2: https://github.com/khanhnhi132022-hash/HN_K26_CNTT2_PROMTAI_H02_Pha1_Pha2.git**
- **Công cụ AI đã dùng (ChatGPT/Claude/Gemini): Chat GPT**

> Pha 2 (20 phút cuối). Mỗi mục: mở cuộc trò chuyện mới, gửi nguyên văn prompt đã viết trong bai_lam_pha1.md, dán câu trả lời và link chia sẻ vào đây. Xong, kéo thả file này vào repository Pha2.

## 4.2. Trích xuất tin nhắn đặt vé xe ra JSON

**KET QUA AI**

```JSON
[
  {
    "ma_tuyen": "SGDL",
    "ngay_di": "2026-12-22",
    "ve_nguoi_lon": 2,
    "ve_tre_em": 1,
    "loai_cho": "giuong",
    "ghi_chu": null
  },
  {
    "ma_tuyen": "SGNT",
    "ngay_di": "2027-01-02",
    "ve_nguoi_lon": 3,
    "ve_tre_em": 0,
    "loai_cho": null,
    "ghi_chu": "một người đang mang thai 6 tháng"
  },
  {
    "ma_tuyen": "SGCT",
    "ngay_di": null,
    "ve_nguoi_lon": 4,
    "ve_tre_em": 0,
    "loai_cho": "ghe",
    "ghi_chu": "bà nội đi xe lăn"
  }
]
```

**Link trò chuyện: https://chatgpt.com/share/6b079dba-31c4-83ec-a99e-ddfd2c53507c**

## 4.3. Báo giá bằng Chain-of-Thought

**KET QUA AI**

```COT
1. **Giá vé người lớn tuyến SGDL** là 320.000 đồng/vé. Tiền vé cho 8 người lớn = 8 vé × 320.000 đồng/vé = **2.560.000 đồng**.

2. **Giá vé trẻ em theo từng độ tuổi**
   - 6 tuổi (1 bé) = 75% × 320.000 đồng = **240.000 đồng**.
   - 7 tuổi (1 bé) = 75% × 320.000 đồng = **240.000 đồng**.
   - 9 tuổi (1 bé) = 75% × 320.000 đồng = **240.000 đồng**.

   Tổng vé của 3 bé = 3 × 240.000 = **720.000 đồng**. Bé 2 tuổi được miễn phí nếu ngồi cùng người lớn. Các bước dưới đây áp dụng cho trường hợp đó.

3. **Tiền vé trước giảm** = 2.560.000 + 720.000 + 0 = **3.280.000 đồng**.

4. **Giảm giá đoàn**. Đoàn có 8 người lớn, đủ điều kiện giảm 5%. Số tiền được giảm = 5% × 3.280.000 = **164.000 đồng**. Tiền vé sau giảm = 3.280.000 − 164.000 = **3.116.000 đồng**.

5. **Phụ thu hành lý** = 2 kiện × 100.000 đồng/kiện = **200.000 đồng**, tính nguyên mức.

6. **Tổng tiền phải trả** = 3.116.000 + 200.000 = **3.316.000 đồng**.

[RESULT: 3.316.000 đồng]
```

**Link trò chuyện: https://chatgpt.com/share/6b079e24-6434-83ec-b56f-fef6744e038a**

### b) Kiểm tra kết quả AI

Đúng, AI trả theo đúng thứ tự sắp xếp đã cập nhật.

## 4.4. Dây chuyền xử lý khiếu nại – kết quả Trạm 1

**KET QUA AI**

```text
{
  "loai_su_co": "sai_loai_xe",
  "so_khach": 3,
  "so_chang_bi_doi": 2,
  "tom_tat": "Ba khách đặt giường nằm nhưng nhà xe đổi sang ghế ngồi ở cả chặng đi và chặng về."
}
```

**Link trò chuyện: https://chatgpt.com/share/6b079ef7-9800-83ec-8b5a-7761a20978cc**

## 4.5. Prompt chấm bài theo Rubric

**KET QUA AI**

```text
| Tiêu chí | Điểm | Minh chứng | Đề xuất sửa |
|---|---:|---|---|
| Đúng thông tin | 0/5 | **Giá (0/2,5).** “Vé đi Nha Trang bên em 350.000đ nha chị, xe xịn lắm luôn.” Giá chuẩn là 380.000 đồng/vé người lớn. **Chính sách đổi vé (0/2,5).** “Chị đổi trước 12 tiếng thì đổi free nha chị.” Tại mốc 12 giờ, phí đổi là 20% giá vé. Bài cũng thiếu hai mốc còn lại. | **Giá vé.** “Vé tuyến Sài Gòn – Nha Trang có giá 380.000 đồng/vé người lớn.” **Đổi vé.** “Chị được đổi vé miễn phí nếu còn từ 24 giờ trở lên trước giờ xe chạy. Nếu còn từ 6 đến dưới 24 giờ, phí đổi là 20% giá vé. Nếu còn dưới 6 giờ, chị không thể đổi vé.” |
| Đầy đủ | 2/3 | Theo thông tin chuẩn và rubric, nội dung cần chấm là **đổi vé** và **ngày đi**. Bài đã trả lời về giá (1/1) và đổi vé (1/1) qua hai câu trích ở hàng trên. “Cần gì chị nhắn em liền!” chỉ là lời mời liên hệ chung, thiếu cả ngày đi và số vé để đặt chỗ (0/1). | “Chị cho em biết ngày đi và số lượng vé cần đặt để em hỗ trợ giữ chỗ cho chị nhé.” |
| Giọng điệu | 1/2 | “Dạ chào chị!” thể hiện sự lịch sự. “Vé đi Nha Trang bên em 350.000đ nha chị, xe xịn lắm luôn.” dùng từ suồng sã và khen chất lượng xe khi chưa có căn cứ. “Chị đổi trước 12 tiếng thì đổi free nha chị.” dùng cách nói “free nha chị” thiếu chuyên nghiệp. “Cần gì chị nhắn em liền!” có giọng thúc giục. | Giữ lời chào. Dùng hai câu tư vấn đã sửa ở hàng đầu để báo giá và giải thích phí đổi bằng từ ngữ trung tính. Thay câu cuối bằng lời hỏi ngày đi và số vé ở hàng trên. |

Tổng điểm: 3/10
```

**Link trò chuyện:https://chatgpt.com/share/6b079f57-2474-83ec-9453-193f62363001**
