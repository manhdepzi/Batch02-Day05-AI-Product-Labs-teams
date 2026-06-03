# Toolkit — Từ Evidence Đến Build Slice

## 1. Gom evidence thành cụm

- "Rải rác hàng loạt 1 file CV chung chung thay vì tối ưu cho từng JD (89.9% nhà tuyển dụng yêu cầu CV khớp JD)."
- "Sử dụng mạng lưới không chính thức như Facebook để tìm việc, rủi ro phân mảnh và lừa đảo cao."
- "Môi trường tập phỏng vấn đắt đỏ (như Interviewing.io) hoặc hệ thống lọc ứng viên bằng giọng nói qua các phiên bản mới của tương lai (PyjamaHR)."

## 2. Viết insight

```text
User [Sinh viên mới tốt nghiệp] không chỉ cần [một nơi để upload CV đơn thuần].
Họ thật ra cần [hướng dẫn tùy chỉnh từng CV sát với chuyên môn và được tập dượt kĩ càng về phản xạ phỏng vấn],
vì [sinh viên hay làm CV một cách rập khuôn dễ bị loại qua ATS và yếu kỹ năng phản xạ cấu trúc trả lời hoặc xử lý tình huống].
```

## 3. Viết opportunity

```text
Cơ hội là dùng AI để [chấm điểm tương thích CV/JD và chạy các phiên mô phỏng câu hỏi phỏng vấn dựa trên âm thoại ứng viên phát ra],
giúp user [rèn luyện kỹ năng qua Framework STAR và tối ưu hoá chuẩn ATS Readability],
trong khi vẫn kiểm soát [Tốc độ đàm thoại - yêu cầu cực khắt khe độ trễ Turn Gap dưới 500ms để giữ mạch truyện].
```

## 4. Chọn build slice

| Câu hỏi | Đạt khi |
|---|---|
| User cụ thể chưa? | Sinh viên các khối đại học, cao đẳng hệ kỹ thuật/kinh tế sắp ra trường. |
| Task đủ hẹp chưa? | Luyện phỏng vấn video giả lập với AI (AI yên lặng đưa ra câu hỏi Text, sinh viên bật video và trả lời bằng Voice). |
| AI decision rõ chưa? | AI lắng nghe âm thanh từ VAD -> gọi API Speech-To-Text streaming -> LLM sinh câu hỏi follow-up (dạng token stream) tiếp theo từ kiến thức chuyên môn và ngữ cảnh. |
| Failure path rõ chưa? | Sinh viên trả lời Code-switching (dùng cả Tiếng Anh và Tiếng Việt) hoặc ngậm ngừng có câu từ thừa (à, ừ), AI có rủi ro ngắt lượt chưa nói xong. |
| Có evidence không? | Revarta đã thành công trên toàn cầu chứng minh chi phí AI rẻ và tác dụng thật. Nhóm rút kinh nghiệm dùng WebRTC UDP thay cho TCP WebSocket tránh HOL Blocking. |

## 5. Quyết định: giữ, giảm scope, hay đổi hướng?

| Tình huống | Quyết định |
|---|---|
| Không demo được trong 1 ngày | Đưa phân hệ Application Autofill, Job Tracker đa nền tảng và Smart Mailer vào backlog. Day 06 chỉ giữ SLICE CHÍNH: Lõi Engine Match CV-JD bằng RAG Hybrid Search và Màn mô phỏng Phỏng vấn WebRTC. |

## 6. Câu chốt cuối

```text
Dựa trên [đánh giá hệ thống Teal HQ, Revarta và khảo sát về hành vi ứng tuyển của đa phần sinh viên VN],
nhóm sẽ build [Trợ lý phỏng vấn AI dạng Video Call WebRTC kết hợp Engine chấm điểm CV Match],
cho [sinh viên chuẩn bị ra trường],
để giải quyết [nỗi đau vượt hệ thống ATS, yếu phản xạ các vòng phỏng vấn sơ loại AI thực tế],
bằng cách AI [phân tích luồng VAD lấy câu trả lời giọng âm thanh và Stream trả về câu hỏi chữ theo thời gian thực (đóng vai NTD)],
và sẽ test failure path [mất vài frame âm thanh (UDP), user nói lẫn Anh-Việt, ngập ngừng quá lâu sinh ra ngắt trễ lượt (Turn Detection)].
```

## 7. Backlog

Những thứ **không build trong Day 06**:
- Hệ thống thu thập thông tin tuyển dụng đa nền tảng bằng Chrome Extension Job Clipper.
- Tự động điền form ứng tuyển (Application Autofill).
- Quản lý quá trình tìm việc kiểu Kanban CRM (Job Tracker).
- Tự động sinh nội dung Cover Letter thông qua Email (Contextual Mailer).
