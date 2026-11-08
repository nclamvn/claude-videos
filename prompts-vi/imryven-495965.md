# Thiết lập đa agent cho Claude Code

_Claude Code Multi-Agent Setup_

Video Opus 5.5 của [@imryven](https://x.com/imryven) · [Bài đăng gốc kèm video](https://x.com/imryven/status/2105719735438495965)

- **Danh mục:** Motion graphics
- **Tác giả:** [@imryven](https://x.com/imryven)

Thêm video Opus 5.5, mỗi video kèm bản làm lại trực tiếp: [skillry.dev/ai-videos/opus-5-5](https://skillry.dev/ai-videos/opus-5-5?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos)

Trang gốc (chưa dịch): [prompts/imryven-495965.md](../prompts/imryven-495965.md)

## Prompt (tiếng Việt)

```text
Hãy dựng lại thiết lập Claude Code của tôi xoay quanh cây này:

1. Tìm trong ~/.claude/agents và .claude/agents các subagent đã đảm nhận explorer, worker và researcher. Chỉ soạn subagent mới cho những vai trò còn thiếu. Đặt mỗi cái là model: opus, effort: medium. Nếu một subagent có sẵn đang được ghim vào một model khác, hãy liệt kê nó ra, đừng động vào.

2. Đặt effortLevel của phiên chính thành high trong ~/.claude/settings.json, và đặt advisorModel thành fable.

3. Kiểm tra mọi thứ đang vô hiệu hoá advisor: CLAUDE_CODE_DISABLE_ADVISOR_TOOL, DISABLE_TELEMETRY, bất kỳ biến nào chặn việc tải feature flag, và CLAUDE_CODE_EFFORT_LEVEL, biến này ghi đè effort của subagent. Báo cáo những gì bạn tìm thấy. Chưa thay đổi gì cả.

4. Thêm một dòng vào ~/.claude/CLAUDE.md: hỏi ý kiến advisor trước một kế hoạch lớn, khi một lỗi lặp lại, và trước khi đánh dấu một tác vụ dài là xong.

Hiển thị mọi thay đổi dưới dạng diff trước. Không động vào bất cứ thứ gì cho tới khi tôi nói bắt đầu.
```

## Prompt gốc

```text
Rebuild my Claude Code setup around this tree:

1. Look in ~/.claude/agents and .claude/agents for subagents that already cover explorer, worker and researcher. Draft new ones only for roles that are missing. Set each to model: opus, effort: medium. If an existing subagent is pinned to a different model, list it, don't touch it.

2. Set the main session's effortLevel to high in ~/.claude/settings.json, and set advisorModel to fable.

3. Check for anything disabling the advisor: CLAUDE_CODE_DISABLE_ADVISOR_TOOL, DISABLE_TELEMETRY, any variable blocking feature-flag fetches, and CLAUDE_CODE_EFFORT_LEVEL, which overrides subagent effort. Report what you find. Change nothing yet.

4. Add one line to ~/.claude/CLAUDE.md: consult the advisor before a large plan, when an error repeats, and before marking a long task done.

Show every change as a diff first. Don't touch anything until I say go.
```
