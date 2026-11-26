# BÀI LÀM PHA 2 – HACKATHON 02

- **Mã đề:** 07
- **Họ tên:**Trần Mạnh Hoa
- **Lớp:**CNTT1
- **Link repository Pha2:**https://github.com/accountstool/HN-KS26-CNTT1_PromptAI_H02_Pha1-Pha2/
- **Công cụ AI đã dùng (ChatGPT/Claude/Gemini):**Gemini

> Pha 2 (20 phút cuối). Mỗi mục: mở cuộc trò chuyện mới, gửi nguyên văn prompt đã viết trong bai_lam_pha1.md, dán câu trả lời và link chia sẻ vào đây. Xong, kéo thả file này vào repository Pha2.

## 4.2. Trích xuất tin nhắn đặt vé vào cổng ra JSON

**KET QUA AI**

```text
[
  {
    "loai_ve": "VECH",
    "ngay_choi": "2026-12-20",
    "nguoi_lon": 2,
    "tre_em": 1,
    "loai_tu": "nho",
    "ghi_chu": null
  },
  {
    "loai_ve": "VECN",
    "ngay_choi": "2027-01-03",
    "nguoi_lon": 3,
    "tre_em": 0,
    "loai_tu": null,
    "ghi_chu": "1 người đang bó bột tay"
  },
  {
    "loai_ve": "VEVIP",
    "ngay_choi": null,
    "nguoi_lon": 4,
    "tre_em": 0,
    "loai_tu": "lon",
    "ghi_chu": "1 bạn đi xe lăn"
  }
]

```

**Link trò chuyện:**https://share.gemini.google/70PoeDmvpmRp

## 4.3. Báo giá bằng Chain-of-Thought

**KET QUA AI**

```text
1. **Tiền người lớn:**
Đoàn mua vé cả ngày (VECN) với đơn giá 250.000 đồng/vé cho 8 người lớn:
8 × 250.000 = 2.000.000 đồng
2. **Tiền trẻ em theo độ tuổi:**

* 4 trẻ em cao từ 1 m đến 1,4 m (1,05 m; 1,15 m; 1,2 m; 1,3 m) tính 60% giá vé người lớn: 4 × (250.000 × 60%) = 4 × 150.000 = 600.000 đồng
* 2 bé cao dưới 1 m được miễn phí: 2 × 0 = 0 đồng
Tổng tiền vé trẻ em: 600.000 + 0 = 600.000 đồng

3. **Tiền vé trước giảm:**
2.000.000 + 600.000 = 2.600.000 đồng
4. **Mức giảm nhóm và tiền vé sau giảm:**

* Vì đoàn có 8 người lớn (đạt điều kiện từ 8 người lớn trở lên) nên được giảm 10% trên tổng tiền vé:
Mức giảm: 2.600.000 × 10% = 260.000 đồng
* Tiền vé sau giảm: 2.600.000 - 260.000 = 2.340.000 đồng

5. **Phụ thu:**
Đoàn thuê 6 áo phao với giá 40.000 đồng/chiếc (không áp dụng giảm giá):
6 × 40.000 = 240.000 đồng
6. **Tổng thanh toán:**
2.340.000 + 240.000 = 2.580.000 đồng

[RESULT: 2.580.000 đồng]
```

**Link trò chuyện:**https://share.gemini.google/IjkDLtYZI1R6

### b) Kiểm tra kết quả AI

AI Đúng

## 4.4. Dây chuyền xử lý khiếu nại – kết quả Trạm 1

**KET QUA AI**

```text
{
  "loai_su_co": "dong_khu_choi",
  "so_khach": 4,
  "so_hiep_bi_anh_huong": null,
  "tom_tat": "Khu trượt nước chính và khu sóng nhân tạo đóng cả ngày mà không thông báo trước trên website."
}

```

**Link trò chuyện:**https://share.gemini.google/MLqpdUUMa89j

## 4.5. Prompt chấm bài theo Rubric

**KET QUA AI**

```text
| Tiêu chí | Điểm | Minh chứng | Đề xuất sửa |
| --- | --- | --- | --- |
| **Đúng thông tin** (50% - tối đa 5.0đ) | 0.0 / 5.0 | - *"Vé chiều bên em 150k thôi ạ"*: Sai giá vé so với quy định (180.000 đồng).<br>

<br>- *"Mưa mà đóng cửa thì bên em hoàn tiền mặt 100% cho chị nha"*: Sai chính sách hoàn bù (vào dưới 2 giờ được tặng 1 vé cùng loại dùng trong 30 ngày, không hoàn tiền mặt). | "Dạ, giá vé buổi chiều (VECH) là 180.000 đồng/vé người lớn ạ. Trong trường hợp công viên phải đóng cửa vì thời tiết xấu khi chị mới vào chơi được 1 tiếng (dưới 2 giờ), công viên sẽ tặng chị 01 vé cùng loại có hạn sử dụng trong 30 ngày (không áp dụng hoàn tiền mặt) ạ." |
| **Đầy đủ** (30% - tối đa 3.0đ) | 1.5 / 3.0 | Đã đề cập đến cả 2 vấn đề khách hỏi (giá vé và chính sách mưa) nhưng **thiếu** lời mời khách cung cấp ngày đi chơi và số lượng vé để hỗ trợ đặt vé (trừ 1.5đ). | "Chị dự định đi vào ngày nào và cần đặt bao nhiêu vé để em hỗ trợ giữ vé cho mình luôn ạ?" |
| **Giọng điệu** (20% - tối đa 2.0đ) | 0.5 / 2.0 | Sử dụng nhiều từ ngữ suồng sã, thiếu chuyên nghiệp: *"Hello chị!"*, *"150k"*, *"mát rượi luôn"*, *"nha"*, *"Cần gì ới em nhé!"* (trừ 1.5đ). | "Dạ em chào chị ạ!" (thay cho *"Hello chị!"*) và "Nếu cần thêm thông tin gì, chị cứ nhắn lại để em hỗ trợ ngay nhé ạ!" (thay cho *"Cần gì ới em nhé!"*). |

**Tổng điểm: 2.0 / 10**
```

**Link trò chuyện:**https://share.gemini.google/iQN2OL38FQVV
