# Kế hoạch Triển khai: Dịch Dự án sang Tiếng Việt

## Tổng quan

Kế hoạch này chia nhỏ công việc dịch toàn bộ dự án sang tiếng Việt thành các nhiệm vụ cụ thể, có thể thực hiện tuần tự. Mỗi nhiệm vụ tập trung vào việc dịch một hoặc nhiều file, đảm bảo chất lượng và tính nhất quán.

## Danh sách Nhiệm vụ

- [x] 1. Chuẩn bị môi trường và cấu trúc thư mục
  - Tạo thư mục `prompt_vn/` ở thư mục gốc của dự án
  - Xác minh quyền ghi vào thư mục
  - Chuẩn bị bảng thuật ngữ chuẩn để tham khảo trong quá trình dịch
  - _Yêu cầu: 1.1, 1.2_

- [x] 2. Dịch file README.md
  - Đọc và phân tích cấu trúc của `README.md`
  - Xác định các phần cần dịch và các phần cần giữ nguyên (code, URLs)
  - Dịch toàn bộ nội dung hướng dẫn sang tiếng Việt tự nhiên
  - Giữ nguyên tất cả markdown formatting (headers, lists, code blocks, links)
  - Giữ nguyên các thuật ngữ kỹ thuật phổ biến (GitHub Copilot, Pull Request, etc.)
  - Lưu file đã dịch vào `prompt_vn/README.md`
  - Xem xét lại chất lượng dịch thuật
  - _Yêu cầu: 2.1, 2.2, 2.3, 2.4, 2.5_

- [x] 3. Dịch file commit.prompt.md
  - Đọc và phân tích cấu trúc của `commit.prompt.md`
  - Giữ nguyên YAML frontmatter nếu có
  - Dịch các phần hướng dẫn và giải thích
  - Giữ nguyên tất cả code examples và command-line instructions
  - Giữ nguyên các thuật ngữ Git (commit, staging, merge, etc.)
  - Lưu file đã dịch vào `prompt_vn/commit.prompt.md`
  - _Yêu cầu: 3.1, 3.2, 3.3, 3.4, 3.5, 3.6_

- [x] 4. Dịch file createSpec.prompt.md
  - Đọc và phân tích cấu trúc của `createSpec.prompt.md`
  - Giữ nguyên YAML frontmatter (`mode: agent`)
  - Dịch toàn bộ nội dung hướng dẫn về quy trình tạo requirements
  - Giữ nguyên các ví dụ code và cấu trúc file
  - Dịch các User Story examples sang tiếng Việt
  - Giữ nguyên thuật ngữ EARS và các từ khóa kỹ thuật
  - Lưu file đã dịch vào `prompt_vn/createSpec.prompt.md`
  - _Yêu cầu: 3.1, 3.2, 3.3, 3.4, 3.5, 3.6_

- [x] 5. Dịch file createTask.prompt.md
  - Đọc và phân tích cấu trúc của `createTask.prompt.md`
  - Giữ nguyên YAML frontmatter
  - Dịch hướng dẫn về quy trình tạo task list
  - Giữ nguyên các ví dụ về cấu trúc task và format markdown
  - Dịch các ví dụ task descriptions sang tiếng Việt
  - Lưu file đã dịch vào `prompt_vn/createTask.prompt.md`
  - _Yêu cầu: 3.1, 3.2, 3.3, 3.4, 3.5, 3.6_

- [x] 6. Dịch file design.prompt.md
  - Đọc và phân tích cấu trúc của `design.prompt.md`
  - Giữ nguyên YAML frontmatter
  - Dịch hướng dẫn về quy trình tạo technical design
  - Giữ nguyên các ví dụ về API endpoints, database schema
  - Dịch các phần giải thích về kiến trúc và design patterns
  - Lưu file đã dịch vào `prompt_vn/design.prompt.md`
  - _Yêu cầu: 3.1, 3.2, 3.3, 3.4, 3.5, 3.6_

- [x] 7. Dịch file executeTask.prompt.md
  - Đọc và phân tích cấu trúc của `executeTask.prompt.md`
  - Giữ nguyên YAML frontmatter
  - Dịch hướng dẫn về quy trình thực thi tasks
  - Giữ nguyên các command examples (`implement`, `continue`, etc.)
  - Dịch các quy tắc và checklist
  - Lưu file đã dịch vào `prompt_vn/executeTask.prompt.md`
  - _Yêu cầu: 3.1, 3.2, 3.3, 3.4, 3.5, 3.6_

- [x] 8. Dịch file prReview.prompt.md
  - Đọc và phân tích cấu trúc của `prReview.prompt.md`
  - Giữ nguyên YAML frontmatter
  - Dịch hướng dẫn về quy trình code review
  - Giữ nguyên tất cả Git commands và GitHub CLI commands
  - Giữ nguyên các ví dụ về API calls và JSON structures
  - Dịch các phần giải thích về review checklist và best practices
  - Lưu file đã dịch vào `prompt_vn/prReview.prompt.md`
  - _Yêu cầu: 3.1, 3.2, 3.3, 3.4, 3.5, 3.6_

- [x] 9. Dịch file design-principle.instructions.md
  - Đọc và phân tích cấu trúc của `design-principle.instructions.md`
  - Giữ nguyên YAML frontmatter (`applyTo: '**'`)
  - Dịch các nguyên tắc phát triển của Linus Torvalds
  - Giữ nguyên các thuật ngữ như KISS, nhưng thêm giải thích tiếng Việt
  - Dịch các quy tắc và guidelines một cách tự nhiên
  - Giữ nguyên tone và emphasis của phong cách Linus
  - Lưu file đã dịch vào `prompt_vn/design-principle.instructions.md`
  - _Yêu cầu: 4.1, 4.2, 4.3, 4.4, 4.5_

- [x] 10. Kiểm tra tính nhất quán thuật ngữ
  - Đọc lại tất cả các file đã dịch
  - Tạo danh sách các thuật ngữ kỹ thuật đã sử dụng
  - Xác minh rằng mỗi thuật ngữ được dịch/giữ nguyên một cách nhất quán
  - Sửa các trường hợp không nhất quán nếu phát hiện
  - _Yêu cầu: 5.4_

- [x] 11. Kiểm tra chất lượng tổng thể
  - Đọc từng file đã dịch để kiểm tra tính tự nhiên của ngôn ngữ
  - Xác minh rằng tất cả code blocks được giữ nguyên
  - Xác minh rằng tất cả URLs và file paths được giữ nguyên
  - Xác minh rằng markdown formatting được bảo toàn
  - Kiểm tra encoding (UTF-8) và ký tự tiếng Việt có dấu
  - _Yêu cầu: 5.1, 5.2, 5.5, 6.1, 6.2, 6.3, 6.4_

- [x] 12. Tạo file tóm tắt (optional)
  - Tạo file `prompt_vn/TRANSLATION_NOTES.md` để ghi chú về quá trình dịch
  - Ghi lại các quyết định dịch thuật quan trọng
  - Liệt kê các thuật ngữ được giữ nguyên và lý do
  - Ghi chú về các thách thức và cách giải quyết

- [x] 13. Checkpoint cuối cùng
  - Xác minh tất cả 8 file đã được dịch và lưu trong `prompt_vn/`
  - Kiểm tra lại một lần nữa chất lượng dịch thuật
  - Đảm bảo không có file nào bị thiếu
  - Sẵn sàng để commit và push

## Ghi chú

- Các nhiệm vụ nên được thực hiện theo thứ tự để đảm bảo tính nhất quán
- Mỗi file nên được xem xét kỹ lưỡng sau khi dịch
- Ưu tiên chất lượng dịch thuật hơn là tốc độ
- Tham khảo bảng thuật ngữ chuẩn trong design.md khi dịch
- Luôn giữ nguyên code, commands, và technical syntax
