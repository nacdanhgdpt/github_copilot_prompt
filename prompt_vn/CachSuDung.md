ví dụ như tôi muốn: thêm chức năng giỏ hàng cho hệ thống hiện tại. ví dụ như thế, thì tôi sẽ làm thế nào?

🧠 BƯỚC 0 – Nạp luật nền (chỉ làm 1 lần)

    Dán nội dung design-principle.instructions.md vào Copilot Chat, nói rõ:
    Use these design principles for all following work.
    Do not skip phases.

BƯỚC 1 – Tạo REQUIREMENTS (Spec)
    Prompt cuối cùng của bạn = (NỘI DUNG createSpec.prompt.md) + (context bạn cung cấp - yêu cầu của bạn (your input))
    Copilot KHÔNG tự hiểu “createSpec.prompt.md” là gì, nên bạn phải dán TOÀN BỘ prompt đó vào chat.

BƯỚC 2 – DESIGN (Thiết kế kỹ thuật)
    design.prompt.md + your input, ex:
    Use the approved requirements.
    Design the shopping cart feature for an existing system.
    Consider:
    - Data model
    - API changes
    - Frontend state management
    - Backward compatibility

    Do NOT create tasks yet.

BƯỚC 3 – TASK BREAKDOWN
    createTask.prompt.md + your input, ex:
    Break the approved cart design into sequential tasks.
    Each task must be small and independently verifiable.
    Do NOT write code.

BƯỚC 4 – CODE (thực thi từng task)
    executeTask.prompt.md  + your input, ex:
    Execute task 1 only.
    Do not work on other tasks.
    Ask questions if assumptions are needed.

BƯỚC 5 – REVIEW
    prReview.prompt.md + your input, ex:
    Review the implemented shopping cart feature.
    Check alignment with requirements and design.
    Identify risks or missing cases.

