# Prompts Phát triển theo Spec với AI

Bộ sưu tập toàn diện các prompt được thiết kế cho GitHub Copilot và các coding agent khác để hỗ trợ quy trình phát triển phần mềm có cấu trúc, với các cổng phê duyệt. Hệ thống này chuyển đổi ý tưởng cấp cao thành các đặc tả chính thức, thiết kế kỹ thuật và kế hoạch triển khai theo các thực tiễn tốt nhất của ngành.

## Vai trò

Dự án này tuân thủ **Nguyên tắc Phát triển của Linus Torvalds** được định nghĩa trong `design-principle.instructions.md`:

### Nguyên tắc Cốt lõi
- **Hợp tác Trên hết**: Tuyệt đối không triển khai mà không có sự phê duyệt rõ ràng từ người dùng
- **Keep It Simple, Stupid (KISS)**: Tránh thiết kế quá mức và độ phức tạp không cần thiết
- **Tiếng Anh cho Code**: Tất cả code, comment và tài liệu phải bằng tiếng Anh để dễ bảo trì
- **Giải pháp Thực dụng**: Ưu tiên code rõ ràng đúng đắn hơn là các thủ thuật thông minh
- **Khả năng Bảo trì**: Sự tiện lợi lâu dài hơn các giải pháp tạm thời

Phương pháp phát triển nhấn mạnh tính trực tiếp, thực dụng và "gu thẩm mỹ tốt" trong code, đảm bảo mọi abstraction đều có lý do tồn tại và chỉ thêm độ phức tạp khi nó giải quyết vấn đề thực sự.

## Quy trình Kiro

Hệ thống triển khai quy trình phát triển theo spec có cấu trúc bốn giai đoạn với các cổng phê duyệt bắt buộc:

### `/createSpec`

**Giai đoạn Tạo Yêu cầu**

Chuyển đổi ý tưởng tính năng cấp cao thành tài liệu yêu cầu chính thức, rõ ràng sử dụng các chuẩn của ngành.

**Tính năng Chính:**
- Tạo `requirements.md` trong thư mục có cấu trúc `.kiro/specs/[feature-name]/`
- Sử dụng định dạng User Story: "As a [role], I want [feature], so that [benefit]"
- Triển khai EARS (Easy Approach to Requirements Syntax) cho tiêu chí chấp nhận
- Tích hợp ngữ cảnh dự án từ thư mục `.kiro/steering/`
- Áp dụng các cổng phê duyệt rõ ràng trước khi tiếp tục

**Quy trình:**
1. Nhận yêu cầu tính năng cấp cao
2. Tạo bản nháp đầu tiên toàn diện với các kịch bản và trường hợp đặc biệt
3. Chờ sự phê duyệt rõ ràng từ người dùng
4. Lặp lại dựa trên phản hồi cho đến khi được phê duyệt

### `/design`

**Giai đoạn Thiết kế Kỹ thuật**

Chuyển đổi các yêu cầu đã được phê duyệt thành bản thiết kế kỹ thuật toàn diện.

**Tính năng Chính:**
- Tạo kế hoạch triển khai kỹ thuật chi tiết `design.md`
- Tổng hợp yêu cầu, ngữ cảnh dự án và phân tích codebase hiện có
- Bao gồm tổng quan kiến trúc, sơ đồ luồng dữ liệu và định nghĩa thành phần
- Chỉ định API endpoint, thay đổi database schema và các cân nhắc bảo mật
- Phác thảo chiến lược kiểm thử toàn diện

**Các Thành phần:**
- **Tổng quan Kiến trúc**: Tích hợp giải pháp cấp cao
- **Sơ đồ Luồng Dữ liệu**: Trực quan hóa bằng Mermaid.js
- **Định nghĩa Interface**: TypeScript types và đặc tả component
- **API Contract**: Đặc tả endpoint đầy đủ
- **Phân tích Bảo mật**: Đánh giá rủi ro và chiến lược giảm thiểu
- **Chiến lược Kiểm thử**: Lập kế hoạch unit test, integration test và E2E test

### `/createTask`

**Giai đoạn Lập Kế hoạch Triển khai**

Phân tách thiết kế kỹ thuật đã được phê duyệt thành các cấu trúc nhiệm vụ có thể thực thi.

**Tính năng Chính:**
- Tạo checklist triển khai phân cấp `tasks.md`
- Tạo các mục tiêu cấp cao được đánh số với các sub-task thụt lề
- Đảm bảo thứ tự logic và quản lý phụ thuộc
- Cung cấp khả năng truy vết đầy đủ đến yêu cầu và tiêu chí chấp nhận
- Không yêu cầu phê duyệt - báo hiệu sẵn sàng cho triển khai

**Cấu trúc:**
- Task cấp cao: `- [ ] 1. Mô tả mục tiêu`
- Sub-task: Các bullet point thụt lề với hành động cụ thể
- Khả năng truy vết: `- _Requirements: [số yêu cầu]_`

### `/executeTask`

**Giai đoạn Thực thi Triển khai**

Giai đoạn phát triển tích cực với tiến trình tự động và kiểm soát của người dùng.

**Tính năng Chính:**
- Quy trình tương tác điều khiển bằng lệnh (`implement`, `continue`, `implement 3`)
- Thu thập ngữ cảnh toàn diện bắt buộc trước khi code
- Xác minh tài liệu đầy đủ và tóm tắt hiểu biết
- Lập kế hoạch triển khai với phân tích mối quan hệ kiến trúc
- Theo dõi tiến độ tự động và đánh dấu hoàn thành nhiệm vụ

**Quy trình Bắt buộc:**
1. **Thu thập Ngữ cảnh**: Đọc tất cả tài liệu steering, design và requirements
2. **Xác minh Hiểu biết**: Tóm tắt sự hiểu biết và các kết nối
3. **Lập Kế hoạch Triển khai**: Giải thích cách tiếp cận và sửa đổi file
4. **Thực thi**: Triển khai code theo tất cả các đặc tả
5. **Theo dõi Tiến độ**: Cập nhật trạng thái nhiệm vụ và báo cáo hoàn thành

## Công cụ

### Version Control & Chất lượng Code

#### `/commit`
**Trợ lý Git Commit Chuyên nghiệp**

Phân tích các thay đổi và tạo commit message chuyên nghiệp theo các thực tiễn tốt nhất.

**Tính năng:**
- Phân loại các loại file và đánh giá mẫu thay đổi
- Lọc bỏ các artifact phát triển nội bộ
- Xác định chiến lược commit phù hợp
- Tạo conventional commit message
- Xác định breaking change và phụ thuộc

#### `/prReview`
**Trợ lý Code Review Toàn diện**

Thực hiện xem xét Pull Request chuyên sâu mô phỏng chuyên môn của senior developer.

**Yêu cầu Tiên quyết:**
- GitHub CLI (`gh`) phải được cài đặt và xác thực
- Cài đặt: `brew install gh` (macOS) hoặc truy cập https://cli.github.com/
- Xác thực: `gh auth login`

**Khả năng:**
- Lấy và phân tích metadata của PR sử dụng GitHub CLI
- Thực hiện phân tích thay đổi toàn diện
- Xác định rủi ro, vấn đề bảo mật và các mối quan tâm về kiến trúc
- Cung cấp phản hồi cụ thể, có thể hành động
- Đánh giá độ bao phủ kiểm thử và chất lượng tài liệu

## Cách Sử dụng

Mỗi prompt được thiết kế để hoạt động độc lập hoặc như một phần của quy trình hoàn chỉnh:

1. **Bắt đầu với `/createSpec`** cho các tính năng mới
2. **Tiến tới `/design`** sau khi yêu cầu được phê duyệt
3. **Sử dụng `/createTask`** để lập kế hoạch triển khai
4. **Thực thi với `/executeTask`** cho phát triển
5. **Hỗ trợ với `/commit`** và `/prReview`** cho đảm bảo chất lượng

Tất cả các prompt đều áp dụng nguyên tắc hợp tác trên hết, đảm bảo sự giám sát của con người tại các điểm quyết định quan trọng trong khi duy trì tốc độ phát triển thông qua tự động hóa có cấu trúc.

## Tài liệu Tham khảo

- [GitHub Awesome Copilot](https://github.com/github/awesome-copilot) - Danh sách tuyển chọn các tài nguyên, prompt và thực tiễn tốt nhất về GitHub Copilot *(Lưu ý: Dự án này được phát triển độc lập mà không tham khảo repository này)*
