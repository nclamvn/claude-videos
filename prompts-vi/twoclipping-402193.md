# Video Opus 5.5 của @twoclipping

[▶ Xem bản gốc và bản làm lại trực tiếp trên Skillry](https://skillry.dev/ai-videos/opus-5-5/twoclipping-402193?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos) · [Bài đăng gốc](https://x.com/twoclipping/status/2103273003555402193)

- **Danh mục:** Motion graphics
- **Bản làm lại dùng:** SVG
- **Tác giả:** [@twoclipping](https://x.com/twoclipping)

Trang gốc (chưa dịch): [prompts/twoclipping-402193.md](../prompts/twoclipping-402193.md)

## Prompt (tiếng Việt)

```text
<inputs>
Hãy hỏi tôi: 8 đến 12 trạng thái UI tôi muốn hình khối biến thành (ví dụ: button, loader, player, slider, toggle, tabs, chart, command palette, toast), chỉ đen trắng thuần hay có một màu nhấn, và một bài nhạc miễn phí bản quyền khoảng 120 BPM (ví dụ Mixkit, miễn phí cho mục đích thương mại).
</inputs>

<direction>
UI motion đẳng cấp Dribbble. Một hình khối, không bao giờ cắt: mọi trạng thái đều là cùng một phần tử biến hình kích thước, bo góc và màu sắc, trong khi nội dung bên trong đổi qua một cú blur ngắn. Một con trỏ điều khiển mọi thay đổi bằng các cú click và kéo thật. Canvas màu xám ấm sáng, component đen trắng, một font UI sạch sẽ (Geist). Dùng lò xo ở mọi nơi, cùng lắm chỉ vọt lố một chút xíu. Camera zoom để mỗi trạng thái lấp đầy khung hình. Khung hình cuối là khung hình đầu, để nó lặp.
Cấm: easing nảy tưng, hạt bung tóe, glow, gradient trên phần khung UI, icon có nét không đồng nhất, khoảng chết, bất cứ thứ gì trông như template.
</direction>

<structure>
120 BPM, 7 ô nhịp, nhịp nào cũng có chuyện xảy ra.
Button → loader → dấu check → dynamic island → trình phát nhạc với hiệu ứng biến hình play/pause → tua thanh tiến trình → nó biến thành thanh trượt âm lượng, kéo giãn ra khi bị kéo quá mức tối đa → một toggle bật đúng nhịp → núm toggle biến thành một chỉ báo tab dạng chất lỏng → các tab mở ra thành một biểu đồ tự vẽ, có tooltip khi hover → nó thu lại thành ⌘K → gõ để lọc → enter → toast → quay lại button.
</structure>

<build>
1. Một file HTML, khung vuông 1440x1440. Mọi style được tính từ thời gian bên trong seek(t): không CSS transition, không timer, không trạng thái nào mang từ khung hình này sang khung hình khác.
2. Lò xo là đáp ứng bước dạng nghiệm đóng. Một giá trị đổi đích nhiều lần là tổng của một lò xo cho mỗi lần thay đổi, nhờ vậy nó vẫn là hàm thuần của thời gian.
3. Hai cạnh của chỉ báo tab chạy theo hai lò xo khác nhau, nên cạnh trước kéo giãn vượt lên trước cạnh sau. Áp dụng cùng mẹo đó cho núm toggle.
4. Thao tác kéo là thao tác trực tiếp: trong lúc con trỏ đang giữ, giá trị được tính từ vị trí của nó. Khi thả ra, nó bật lò xo trở về từ bất cứ chỗ nào nó đang ở.
5. Phân tích bài nhạc bằng numpy để có lưới nhịp và bắt đầu trên một phách mạnh. Đặt mỗi âm thanh UI theo đỉnh đã đo của nó.
6. Render bằng Playwright: 4 khung phụ mỗi khung hình, trộn bằng ffmpeg tmix để tạo motion blur ở 60fps.
7. Render một khung hình mỗi nhịp trước khi render toàn bộ. Sửa mọi thứ lệch lưới, chật chội hoặc khó đọc.
</build>

<gotchas>
Đừng bao giờ đặt will-change lên bất cứ thứ gì camera scale, nếu không chữ sẽ render bị mờ. Chữ đổi bên trong một container đang biến hình cần thời điểm vào và ra riêng, nếu không chúng sẽ chồng lên nhau. Làm khung hình cuối giống hệt khung hình đầu, kể cả vị trí và tốc độ con trỏ, nếu không loop sẽ bị giật.
</gotchas>

<start>
Hãy hỏi tôi các đầu vào, rồi cho tôi xem danh sách trạng thái trên lưới nhịp trước khi bạn viết bất kỳ dòng code nào.
</start>
```

## Prompt gốc

```text
<inputs>
Ask me for: 8 to 12 UI states I want the shape to become (e.g. button, loader, player, slider, toggle, tabs, chart, command palette, toast), pure black and white or one accent color, and a royalty-free song around 120 BPM (e.g. Mixkit, free for commercial use).
</inputs>

<direction>
Dribbble-level UI motion. One shape, never cut: every state is the same element morphing its size, radius and color while its content swaps with a short blur. A cursor drives every change with real clicks and drags. Light warm-gray canvas, black and white components, one clean UI font (Geist). Springs everywhere, a tiny overshoot at most. The camera zooms so each state fills the frame. The last frame is the first frame, so it loops.
Banned: bouncy easing, particle bursts, glows, gradients on UI chrome, mismatched icon strokes, dead time, anything that looks like a template.
</direction>

<structure>
120 BPM, 7 bars, something happens on every beat.
Button → loader → check → dynamic island → music player with a play/pause morph → scrub the progress bar → it becomes a volume slider that stretches when dragged past max → a toggle flips on the beat → the knob becomes a liquid tab indicator → the tabs open into a chart that draws itself, with a tooltip on hover → it collapses into ⌘K → type to filter → enter → toast → back to the button.
</structure>

<build>
1. One HTML file, square 1440x1440. Every style is computed from time inside seek(t): no CSS transitions, no timers, no state carried between frames.
2. Springs are closed-form step responses. A value that changes target many times is the sum of one spring per change, so it stays a pure function of time.
3. The tab indicator's two edges ride different springs, so the leading edge stretches ahead of the trailing one. Same trick for the toggle knob.
4. Drags are direct manipulation: while the cursor is held, the value is computed from its position. On release it springs back from wherever it was.
5. Analyze the song with numpy for the beat grid and start on a downbeat. Place every UI sound by its measured peak.
6. Render with Playwright: 4 subframes per frame, blended with ffmpeg tmix for motion blur at 60fps.
7. Render one frame per beat before the full render. Fix anything off the grid, cramped or hard to read.
</build>

<gotchas>
Never put will-change on anything the camera scales or the text renders blurry. Text that swaps inside a morphing container needs its own enter and exit timing or it overlaps. Make the last frame identical to the first, cursor position and speed included, or the loop stutters.
</gotchas>

<start>
Ask me for the inputs, then show me the state list on the beat grid before you write any code.
</start>
```
