# UX exercise — V-App trợ lý ảo V-AI

## Sản phẩm: V-App — Trợ lý ảo V-AI (điều hướng dịch vụ trong hệ sinh thái)

---

## Phần 1: Khám phá (Kỳ vọng vs. Thực tế)

- **Kỳ vọng trước khi dùng**: V-AI trong V-App có thể hiểu nhanh nhu cầu người dùng, trả lời trực tiếp và điều hướng liền mạch sang đúng dịch vụ trong hệ sinh thái (đặt lịch, hỗ trợ, tra cứu) mà không làm gián đoạn trải nghiệm.
- **Thực tế khi dùng**: V-AI có thể trả lời và gợi ý link/app khá nhanh. Tuy nhiên, ở các tác vụ cần hoàn thành nhiều bước (ví dụ đặt lịch bảo dưỡng xe), hệ thống chủ yếu dừng ở mức “gợi ý đi đến dịch vụ”, người dùng vẫn phải tự thoát chat, vào màn hình khác và nhập lại thông tin.

---

## Phần 2: Phân tích 4 Paths (Hành trình người dùng)

| Path | Mô tả User Story & Hành vi hệ thống |
|------|---------------------------------------|
| **1. Khi AI đúng** | **User story**: User hỏi nhu cầu đơn giản (tra cứu/hỏi dịch vụ). <br> **Hành vi UI**: V-AI trả lời đúng trọng tâm, có link điều hướng và gợi ý câu hỏi tiếp theo. Trải nghiệm nhanh, dễ hiểu. |
| **2. Khi AI không chắc** | **User story**: User hỏi thông tin mơ hồ hoặc thiếu ngữ cảnh. <br> **Hành vi UI**: V-AI có xu hướng từ chối trả lời hoặc phản hồi chung chung, chưa chủ động hỏi lại để làm rõ yêu cầu. |
| **3. Khi AI sai** | **User story**: User yêu cầu một tác vụ cụ thể nhưng AI điều hướng chưa đúng dịch vụ/màn hình. <br> **Sửa lỗi**: User phải quay lại, nhập lại câu hỏi hoặc tự tìm thủ công trong app. Flow bị đứt mạch. |
| **4. Khi user mất tin** | **Lối thoát (Exit)**: User thường tải lại màn hình, đặt lại câu hỏi mới, hoặc bỏ luồng chat để thao tác thủ công trong app. Điều này cho thấy mức tin cậy vào AI chưa ổn định ở các tác vụ nhiều bước. |

### Tự phân tích:
- **Path tốt nhất**: Path 1. V-AI phản hồi nhanh, có gợi ý rõ ràng và điều hướng tốt cho nhu cầu đơn giản.
- **Path yếu nhất**: Path 3. Khi phân luồng sai hoặc thiếu bước hoàn tất tác vụ, người dùng phải tự thao tác lại từ đầu.
- **Gap chính**: Kỳ vọng là “trợ lý làm được việc đến cùng”, nhưng thực tế hiện tại nghiêng về “trợ lý hướng dẫn”, chưa phải “trợ lý thực thi”.

---

## Phần 3: Sketch “Làm tốt hơn” (Tập trung cải tiến Path 3)

### Tình huống minh họa
- **Nhu cầu user**: “Tôi muốn đặt lịch bảo dưỡng xe”.

### 1. As-is (Hiện tại) - Chỗ gãy
- User nhập yêu cầu trong chat.
- V-AI phản hồi kiểu điều hướng: truy cập dịch vụ tương ứng trong V-App.
- User phải thoát màn hình chat, tự tìm đúng mục, rồi điền lại thông tin đặt lịch.
- **Vấn đề**: nhiều thao tác chuyển ngữ cảnh, tăng khả năng bỏ cuộc hoặc nhập sai.

### 2. To-be (Đề xuất) - In-chat Task Card
- **Cải tiến**: Sau khi user nêu nhu cầu, V-AI hiển thị ngay **card tương tác** trong khung chat.
- **Nội dung card**: chọn thời gian trống, chọn địa điểm xưởng gần nhất (gợi ý theo GPS), nút xác nhận.
- **Kết quả**: User chọn giờ -> xác nhận trực tiếp trong chat -> V-AI báo “Đặt lịch thành công” và gợi ý thêm lịch nhắc.
- **Lợi ích UX**: giảm chuyển màn hình, giảm nhập lại dữ liệu, tăng cảm giác “AI làm được việc”.

---

