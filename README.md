# Harness Map — req-tool

Bộ bản vẽ tương tác (HTML tĩnh) trực quan hóa **harness** của req-tool: vòng lặp đồ thị quyết định và 5 thành phần tạo nên nó. Mục đích giáo dục — giúp người đọc hình dung được agent xử lý một tài liệu yêu cầu phần mềm như thế nào.

## Harness là gì

Một LLM "trần" chỉ nhận câu hỏi, trả lời một lần rồi dừng. **Harness** là bộ khung bao quanh model để biến một lần-gọi thành một *quy trình*: lặp nhiều lượt, gọi đúng công cụ vào đúng lúc, kiểm định chất lượng trước khi chốt, và giữ lại "sự thật" đã xác nhận giữa các lượt.

Ví von như dây đai an toàn của người leo núi — không leo thay bạn, nhưng giữ bạn trong giới hạn an toàn và cho thử lại khi trượt.

## Bộ bản vẽ

| Sheet | Trang | Nội dung |
|-------|-------|----------|
| 00 | `index.html` | Sơ đồ tổng — vòng lặp đồ thị 6 node + bản đồ 5 thành phần |
| 01 | `instructions.html` | Stack chỉ dẫn 4 lớp tĩnh + các khối inject động/lượt |
| 02 | `tools.html` | 28 tool state-gated, dispatch qua native tool-calling |
| 03 | `states.html` | `WorkflowState` + `DecisionNode` — nguồn sự thật |
| 04 | `env.html` | 6 node đồ thị, 4 LLM client, persistence, document registry |
| 05 | `feedback.html` | Critique judge, quality gate, readiness, impact ripple |

Quy ước màu xuyên suốt: **teal = phần khung cố định**, **amber = phần chảy động** (vòng lặp, tín hiệu, phản hồi).

## Xem

- **Online:** GitHub Pages (tự deploy qua GitHub Actions khi push lên `main`).
- **Local:** mở `index.html` bằng trình duyệt — không cần build.

## Kỹ thuật

HTML/CSS tĩnh thuần, không build step. Font qua Google Fonts (Space Grotesk · IBM Plex Sans · IBM Plex Mono). Tôn trọng `prefers-reduced-motion`, focus bàn phím, responsive xuống mobile.

Nội dung bám sát mã nguồn thực tế của `req-tool-be` (tên node, tool, field state). Đây là tài liệu mô tả, không phải mã chạy được.
