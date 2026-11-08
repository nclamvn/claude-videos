# Video Opus 5.5 của @AnnaCher___

[▶ Xem bản gốc và bản làm lại trực tiếp trên Skillry](https://skillry.dev/ai-videos/opus-5-5/annacher-433425?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos) · [Bài đăng gốc](https://x.com/AnnaCher___/status/2103571096549433425)

- **Danh mục:** Motion graphics
- **Bản làm lại dùng:** SVG
- **Tác giả:** [@AnnaCher___](https://x.com/AnnaCher___)

Trang gốc (chưa dịch): [prompts/annacher-433425.md](../prompts/annacher-433425.md)

## Prompt (tiếng Việt)

```text
Hãy phân tích http://sprites.ai và dựng một video quảng bá sản phẩm từ chính UI của chúng tôi, không dùng component chung chung.

<direction>
UI motion đẳng cấp Dribbble. Một hình duy nhất, không bao giờ cắt: mọi trạng thái là cùng một phần tử morph kích thước, bo góc và màu sắc trong khi nội dung bên trong hoán đổi với một chút blur ngắn. Một con trỏ điều khiển mọi thay đổi bằng các cú click và kéo thật. Canvas xám ấm, component đen trắng, một màu nhấn (#FD9543), Geist. Dùng spring ở mọi nơi, cùng lắm là một chút overshoot rất nhỏ. Camera zoom để mỗi trạng thái lấp đầy khung hình. Khung hình cuối = khung hình đầu, để nó lặp lại.
Cấm: easing nảy, hạt, glow, gradient trên phần khung UI, nét icon không đồng bộ, thời gian chết, bất cứ thứ gì trông như template.
</direction>

<structure>
120 BPM, 7 ô nhịp, nhịp nào cũng có gì đó xảy ra.
Kết nối tài khoản quảng cáo (logo Meta, Google, LinkedIn, TikTok, Reddit) → loader → dấu check → thanh prompt gõ "Launch ads that convert" → island "Researching 42 competitors" → bức tường Ads Library gồm các quảng cáo thật cuộn qua và dừng ở một quảng cáo hiệu quả nhất → thẻ phê duyệt → Approve & launch → thanh trượt ngân sách bị kéo giãn vượt mức tối đa → công tắc Autopilot → núm biến thành một thanh chỉ báo tab dạng lỏng chạy qua các kênh → biểu đồ ROAS tự vẽ ra kèm tooltip khi hover → ⌘K → gõ "pause" → toast "Paused 3 losing ads" → quay lại nút ban đầu.
</structure>

<build>
1. Một file HTML, 1440x1440. Mọi style được tính bên trong seek(t): không CSS transition, không timer, không có state giữa các khung hình.
2. Spring là các đáp ứng bậc thang dạng nghiệm đóng (closed-form). Một giá trị đổi đích nhiều lần là tổng của nhiều spring, nên nó vẫn là một hàm thuần của thời gian.
3. Thanh chỉ báo tab và núm công tắc: hai mép đi theo hai spring khác nhau, để mép dẫn đầu giãn ra phía trước.
4. Các cú kéo là thao tác trực tiếp: trong khi giữ, giá trị đi theo con trỏ. Khi thả ra, nó spring trở về từ bất cứ vị trí nào nó đang ở.
5. Không có nhạc. Tổng hợp âm thanh UI bằng numpy và đặt mỗi âm theo đỉnh đo được của nó trên lưới nhịp.
6. Render bằng Playwright: 4 subframe mỗi khung hình, blend bằng ffmpeg tmix để tạo motion blur ở 60fps.
7. Render trước một khung hình mỗi nhịp. Sửa mọi chỗ lệch lưới, chật chội hoặc khó đọc.
</build>

<gotchas>
Không dùng will-change cho bất cứ thứ gì mà camera scale. Text được hoán đổi cần có thời điểm vào/ra riêng. Khớp khung hình cuối với khung hình đầu, kể cả vị trí và tốc độ con trỏ, nếu không loop sẽ bị giật.
</gotchas>

Hãy cho tôi xem danh sách trạng thái trên lưới nhịp trước khi viết bất kỳ dòng code nào.
```

## Prompt gốc

```text
Analyze http://sprites.ai and build a product promo from our own UI, not generic components.

<direction>
Dribbble-level UI motion. One shape, never cut: every state is the same element morphing its size, radius and color while its content swaps with a short blur. A cursor drives every change with real clicks and drags. Warm-gray canvas, black and white components, one accent (#FD9543), Geist. Springs everywhere, a tiny overshoot at most. The camera zooms so each state fills the frame. Last frame = first frame, so it loops.
Banned: bouncy easing, particles, glows, gradients on UI chrome, mismatched icon strokes, dead time, anything that looks like a template.
</direction>

<structure>
120 BPM, 7 bars, something on every beat.
Connect ad account (Meta, Google, LinkedIn, TikTok, Reddit logos) → loader → check → prompt bar types "Launch ads that convert" → island "Researching 42 competitors" → Ads Library wall of real ads scrolls and lands on a top performer → approval card → Approve & launch → budget slider that stretches past max → Autopilot toggle → knob becomes a liquid tab indicator across channels → ROAS chart draws itself with hover tooltip → ⌘K → type "pause" → toast "Paused 3 losing ads" → back to the button.
</structure>

<build>
1. One HTML file, 1440x1440. Every style is computed inside seek(t): no CSS transitions, no timers, no state between frames.
2. Springs are closed-form step responses. A value that changes target many times is a sum of springs, so it stays a pure function of time.
3. Tab indicator and toggle knob: the two edges ride different springs, so the leading edge stretches ahead.
4. Drags are direct manipulation: while held, the value follows the cursor. On release it springs back from wherever it was.
5. No music. Synthesize UI sounds with numpy and place each one by its measured peak on the beat grid.
6. Render with Playwright: 4 subframes per frame, blended with ffmpeg tmix for motion blur at 60fps.
7. Render one frame per beat first. Fix anything off-grid, cramped or hard to read.
</build>

<gotchas>
No will-change on anything the camera scales. Swapped text needs its own enter/exit timing. Match the last frame to the first, cursor position and speed included, or the loop stutters.
</gotchas>

Show me the state list on the beat grid before writing any code.
```
