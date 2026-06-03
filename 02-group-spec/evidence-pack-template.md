# Evidence Pack — Nền Tảng Hỗ Trợ Tìm Việc, Luyện Phỏng Vấn Cho Sinh Viên

## 1. Nhóm và track

**Tên nhóm:** Đang cập nhật  
**Track:** AI Product/App  
**Product/app đã chọn:** Nền Tảng Hỗ Trợ Tìm Việc, Luyện Phỏng Vấn Cho Sinh Viên Việt Nam  
**Build slice đang nghĩ:** Trợ lý luyện phỏng vấn AI dạng Video Call (WebRTC Video Interview Coach) và Trình chấm điểm tương thích CV-JD.  

## 2. Self-use evidence

| Observation | Screenshot/link | Path liên quan | Điều học được |
|---|---|---|---|
| Dùng Teal HQ lập CV | Tealhq.com | Happy | Score CV-JD theo thời gian thực giúp tăng tốc độ hồ sơ, nhưng không hỗ trợ luyện tập phỏng vấn. |
| Chi phí phỏng vấn trên Interviewing.io | interviewing.io | Failure | Quá đắt đỏ (từ $225/phiên), sinh viên Việt không thể tiếp cận đại trà. |

## 3. User / review / social evidence

| Quote / review / observation | Nguồn | User là ai? | Pain/failure mode |
|---|---|---|---|
| 61,2% doanh nghiệp tại Việt Nam đã tích hợp công nghệ AI vào lọc hồ sơ. | Báo cáo xu hướng TopCV 2024-2025 | SV chuẩn bị ra trường | Bị loại từ vòng tự động do CV không tối ưu hệ thống ATS. |
| 89,9% yêu cầu CV khớp JD nhưng chỉ 55,7% người ứng tuyển đồng ý làm. | Báo cáo TopCV | SV chuẩn bị ra trường | Thói quen dùng 1 CV rải hàng loạt (spam), tỷ lệ rớt cao. |
| Khoảng 38% sinh viên vẫn tìm việc qua mạng xã hội Facebook. | QandMe | Sinh viên VN | Thông tin phân mảnh, thiếu định hướng dài hạn, nhiều rủi ro lừa đảo. |

## 4. Competitor / analog evidence

| App / mô hình tham khảo | Họ xử lý task này thế nào? | Pattern học được | Có áp dụng trong 1 ngày không? |
|---|---|---|---|
| Teal HQ | Chấm điểm Match Score 15 tiêu chí và tạo Metric-driven CV. | Chỉ điểm ra keyword thiếu và đề xuất câu mô tả hướng kết quả. Rất hiệu quả tránh bị loại từ đầu. | Có |
| Huntr | Tự động điền form (Autofill) bằng extension. | Tiết kiệm hàng giờ nhập form. Theo dõi trạng thái ứng tuyển. | Có |
| Revarta | Luyện phỏng vấn AI thời gian thực, trả đánh giá <30s theo nhiều khía cạnh (độ chuẩn xác nội dung, ngôn ngữ...). | Không cần bỏ chi phí lớn thuê chuyên gia, giải pháp Mock Interview AI hiệu quả. | Có |

## 5. Evidence -> Insight

```text
Evidence nổi bật nhất:
Nhà tuyển dụng cần CV tùy chỉnh sát JD và đã dùng AI lọc hồ sơ, nhưng lượng ứng viên (sinh viên mới) lười tùy chỉnh rất nhiều. Giai đoạn rèn luyện phòng vấn thiếu môi trường thực hành chi phí thấp.

Insight:
User không chỉ gặp [khó khăn ở việc có tin tuyển dụng].
Thật ra họ cần [những giải pháp thông minh để vượt qua bước filter ATS khắc nghiệt tự động và tập phỏng vấn như thật],
vì [họ không có thói quen chuẩn bị keyword và yếu phản xạ giao tiếp trả lời phỏng vấn theo framework STAR].

Opportunity:
AI có thể giúp bằng cách [augment/automate việc chấm điểm CV/JD Match Score và đóng vai AI Interviewer tương tác ngay trên Video],
giúp user [tăng tỷ lệ nhận cuộc gọi và tự tin qua vòng phỏng vấn thực tế],
trong khi vẫn kiểm soát [đảm bảo hạn chế tối đa giật lag (turn gap <500ms) để không làm vỡ cảm xúc hội thoại].
```

## 6. Evidence đổi SPEC như thế nào?

- [x] Đổi build slice.
- [x] Đổi thuật toán/môi trường (Auto/Aug decision).

Ghi rõ 1-2 thay đổi quan trọng:

```text
Trước evidence, nhóm định xây một hệ thống tạo CV chung chung hay chatbot AI text đơn điệu.
Sau evidence, nhóm đổi thành "Tập trung vào Trợ lý phỏng vấn WebRTC AI Video Call loại bỏ nói TTS (chỉ gõ text màn hình) và Nâng cấp Matching CV-JD".
Lý do: WebSockets nếu truyền media sẽ bị lag packet loss làm hỏng cuộc gọi phỏng vấn, cần dùng WebRTC UDP. Loại bỏ TTS AI giúp giảm độ trễ (delay) từ AI và hạ tầng, mang tới phản hồi ngay lập tức như người thật.
```
