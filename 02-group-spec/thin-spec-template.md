# Thin SPEC Cuối Day 05 — Nền Tảng Hỗ Trợ Tìm Việc, Luyện Phỏng Vấn

## 1. Track, product/app và user

**Track:** AI Product/App  
**Product/app thật:** Nền Tảng Hỗ Trợ Tìm Việc và Trợ lý Luyện Phỏng vấn AI tích hợp WebRTC Video Call.  
**User cụ thể:** Sinh viên Việt Nam từ các trường Đại học, Cao đẳng chuẩn bị tốt nghiệp ứng tuyển các doanh nghiệp và tập đoàn.  
**Nhóm có phải user thật không? Nếu không, khác ở đâu?** Có, chính lực lượng sinh viên tham gia xây dựng trong Lab cũng là người chịu chung áp lực.  

## 2. Evidence summary

| Evidence | Nguồn | User/pain nói lên điều gì? | SPEC phải đổi gì? |
|---|---|---|---|
| Chỉ 55.7% ứng viên chịu sửa CV khớp mức độ JD | Khảo sát TopCV | SV hay rải CV chung (spam) dẫn đến tạch vòng đầu tiên | Bổ sung module chấm độ Score CV-JD Match |
| Thiếu sự chuẩn bị phản xạ phỏng vấn thời gian thực | Khảo sát đào tạo DH | Sự thiếu phản xạ ở các vòng gặp người và kĩ thuật | Thiết kế bộ đánh giá phỏng vấn bằng Video Call mô phỏng |
| Chi phí Interviewing.io quá đắt đỏ (qua người thật) | Thực tế năm 2026 | Không đủ chi phí lặp lại liên tục nhiều buổi | Dùng giải pháp LLM giá rẻ kết hợp mô hình AI Mock Interview, loại bỏ TTS để tiết kiệm |
| TCP WebSockets bị lag với truyền audio/video | Khảo sát Data Streaming | Bị head-of-line blocking do mạng kém | Thay hoàn toàn bằng luồng truyền tải WebRTC (UDP) |

## 3. Pain statement

```text
User [Sinh viên Việt Nam mới/chuẩn bị tốt nghiệp] đang gặp khó ở [bước làm CV qua hệ thống sơ loại ATS tự động và vòng phỏng vấn sơ bộ],
vì [họ dùng các mẫu CV thiếu keywords chuẩn hóa, và thiếu trầm trọng tương tác để rèn luyện tư duy thực tế lúc phỏng vấn],
dẫn tới [bị doanh nghiệp gạch hồ sơ mà không hiểu nguyên nhân hoặc trượt phỏng vấn do giao tiếp kém].
Bằng chứng chính là [Theo thống kê có 61.2% Doanh nghiệp Việt Nam ứng dụng AI để lọc ứng viên và chỉ 55% UV chịu gọt giũa hồ sơ theo JD].
```

## 4. Build slice

```text
Cho [sinh viên Việt] đang [chỉnh sửa CV và thử phản xạ giao tiếp phỏng vấn],
prototype sẽ dùng AI để [so khớp Hybrid Search Cosine góc CV với mô tả JD, và sinh câu hỏi Text stream tiếp theo trên màn hình phỏng vấn âm thanh],
tạo ra [điểm % đạt ATS và báo cáo phân tích năng lực STAR Report Evaluation],
và xử lý [vấn đề độ trễ hoặc nhận diện lẫn âm môi trường gây lag mạch thoại] bằng [bắt VAD qua LiveKit SFU trên giao thức WebRTC].
```

## 5. Auto/Aug decision

Chọn một:
- [x] **Augmentation:** AI gợi ý/draft/phân loại, user quyết cuối.

**Lý do chọn:** Phỏng vấn mô phỏng mang tính gợi ý, đóng vai như 1 Coach, ứng viên là trung tâm học hỏi. Điểm số từ CV là để tham khảo tinh chỉnh.  
**Human role:** reviewer / decider / trainee.  

## 6. Four paths

| Path | Prototype phải thể hiện gì? |
|---|---|
| Happy | User trả lời bằng giọng nói chuẩn chỉ xong, AI (im lặng) phản hồi câu hỏi dưới 500ms ra phụ đề màn hình Text rất mượt. |
| Low-confidence | Không nghe rõ lời của ứng viên, AI hiển thị dòng nhắc nhở tăng mức Mic hoặc đổi vị trí ngồi cho chuẩn Video hơn. |
| Failure | Kết nối đường truyền UDP đứt gói tín hiệu/ngắt mạng, hệ thống WebRTC Packet Loss Concealment (PLC) bù lại và phục hồi luồng. |
| Correction | Ứng viên xin ngắt và trả lời đính chính lại câu vừa nói, bổ sung thêm ý tưởng cũ bị bỏ quên. |

## 7. Failure mode nguy hiểm nhất

```text
Nếu user [giao tiếp bằng song ngữ lẫn lộn Code-switching Anh-Việt, có các quãng ngập ngừng lặp lại kiểu "ừm", "à"],
AI có thể [tưởng người dùng đã dứt phát ngôn và sinh luôn câu hỏi mới],
hậu quả là [ngắt lượt khi UV chưa kịp phát biểu hết ý, đi sai quy trình phỏng vấn].
Prototype sẽ xử lý bằng [đẩy Delay Endpointing Timeout của engine VAD, chọn model như Nova-3 Multi ngôn ngữ].
Owner kiểm thử path này là [Thành viên số 4 - QA].
```

## 8. Owner plan cho sáng Day 06

| Thành viên | Việc phụ trách | Bằng chứng cần có trong repo |
|---|---|---|
|  | Research / evidence | Báo cáo đánh giá đối thủ như TealHQ, Revarta và độ khớp |
|  | SPEC | Bảng vẽ kiến trúc luồng dữ liệu Pipeline WebRTC SFU |
|  | Prototype | Source Code LlamaIndex Match Engine và Next.JS WebRTC |
|  | Test / failure path | Video quay màn hình test ứng viên giao tiếp nói lắp/Anh-Việt |
|  | Demo script / repo | Video Demo hoàn thiện luồng sản phẩm dưới 5 phút |
