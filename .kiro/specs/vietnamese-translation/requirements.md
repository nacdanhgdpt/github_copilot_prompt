# Tài liệu Yêu cầu: Dịch Dự án sang Tiếng Việt

## Giới thiệu

Dự án này cần được dịch toàn bộ sang tiếng Việt để phục vụ cộng đồng lập trình viên Việt Nam. Mục tiêu là tạo ra một bản dịch chính xác, dễ hiểu và giữ nguyên ý nghĩa kỹ thuật của tài liệu gốc, đồng thời lưu trữ trong thư mục `prompt_vn/` để dễ dàng quản lý và sử dụng.

## Thuật ngữ

- **Source Files**: Các file gốc bằng tiếng Anh cần được dịch
- **Target Directory**: Thư mục đích `prompt_vn/` chứa các file đã dịch
- **Translation System**: Hệ thống thực hiện việc dịch và quản lý các file dịch
- **Technical Terms**: Các thuật ngữ kỹ thuật cần được giữ nguyên hoặc dịch có chú thích

## Yêu cầu

### Yêu cầu 1: Tạo cấu trúc thư mục đích

**User Story:** Là một người dùng Việt Nam, tôi muốn có một thư mục riêng chứa tất cả tài liệu tiếng Việt, để tôi có thể dễ dàng truy cập và phân biệt với bản gốc.

#### Tiêu chí chấp nhận

1. THE Translation_System SHALL create a directory named `prompt_vn` at the root level of the project
2. WHEN the target directory already exists, THE Translation_System SHALL preserve existing content and only update specified files
3. THE Translation_System SHALL maintain the same file structure as the source files within the target directory

### Yêu cầu 2: Dịch file README.md

**User Story:** Là một lập trình viên Việt Nam, tôi muốn đọc README bằng tiếng Việt, để tôi có thể hiểu tổng quan về dự án một cách nhanh chóng.

#### Tiêu chí chấp nhận

1. THE Translation_System SHALL translate the complete content of `README.md` into Vietnamese
2. THE Translation_System SHALL preserve all markdown formatting, including headers, lists, code blocks, and links
3. THE Translation_System SHALL keep technical terms in English with Vietnamese explanations in parentheses when appropriate
4. THE Translation_System SHALL save the translated content to `prompt_vn/README.md`
5. WHEN code examples or command-line instructions are present, THE Translation_System SHALL keep them in their original form

### Yêu cầu 3: Dịch các file prompt

**User Story:** Là một người dùng, tôi muốn tất cả các file prompt được dịch sang tiếng Việt, để tôi có thể sử dụng chúng với các công cụ AI hỗ trợ tiếng Việt.

#### Tiêu chí chấp nhận

1. THE Translation_System SHALL translate all prompt files: `commit.prompt.md`, `createSpec.prompt.md`, `createTask.prompt.md`, `design.prompt.md`, `executeTask.prompt.md`, and `prReview.prompt.md`
2. THE Translation_System SHALL preserve the YAML frontmatter (if present) in its original form
3. THE Translation_System SHALL maintain all markdown formatting and structure
4. THE Translation_System SHALL keep code examples, command-line instructions, and technical syntax unchanged
5. THE Translation_System SHALL translate instructional text, explanations, and user-facing content into natural Vietnamese
6. THE Translation_System SHALL save each translated file to `prompt_vn/` with the same filename as the source

### Yêu cầu 4: Dịch file hướng dẫn nguyên tắc thiết kế

**User Story:** Là một lập trình viên, tôi muốn hiểu các nguyên tắc phát triển bằng tiếng Việt, để tôi có thể áp dụng chúng một cách chính xác.

#### Tiêu chí chấp nhận

1. THE Translation_System SHALL translate `design-principle.instructions.md` into Vietnamese
2. THE Translation_System SHALL preserve the YAML frontmatter in its original form
3. THE Translation_System SHALL maintain the tone and emphasis of Linus Torvalds' development philosophy
4. THE Translation_System SHALL translate principle names and explanations while keeping key English terms in parentheses for reference
5. THE Translation_System SHALL save the translated content to `prompt_vn/design-principle.instructions.md`

### Yêu cầu 5: Đảm bảo chất lượng dịch thuật

**User Story:** Là một người dùng, tôi muốn bản dịch chính xác và dễ hiểu, để tôi không bị nhầm lẫn khi sử dụng.

#### Tiêu chí chấp nhận

1. THE Translation_System SHALL use natural, fluent Vietnamese that is easy to understand for native speakers
2. THE Translation_System SHALL maintain technical accuracy and preserve the original meaning
3. WHEN translating technical terms, THE Translation_System SHALL use commonly accepted Vietnamese translations or keep English terms with Vietnamese explanations
4. THE Translation_System SHALL ensure consistency in terminology throughout all translated documents
5. THE Translation_System SHALL preserve all URLs, file paths, and code identifiers in their original form

### Yêu cầu 6: Xử lý các trường hợp đặc biệt

**User Story:** Là một người dùng kỹ thuật, tôi muốn các ví dụ code và lệnh được giữ nguyên, để tôi có thể sao chép và sử dụng trực tiếp.

#### Tiêu chí chấp nhận

1. WHEN encountering code blocks, THE Translation_System SHALL keep all code content unchanged
2. WHEN encountering command-line examples, THE Translation_System SHALL keep commands unchanged but MAY translate explanatory comments
3. WHEN encountering file paths or directory structures, THE Translation_System SHALL keep them in their original form
4. WHEN encountering API endpoints or technical specifications, THE Translation_System SHALL keep them unchanged
5. THE Translation_System SHALL translate comments within code blocks only if they are instructional text, not code comments
