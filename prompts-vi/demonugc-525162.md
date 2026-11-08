# Video Opus 5.5 của @demonugc

[▶ Xem bản gốc và bản làm lại trực tiếp trên Skillry](https://skillry.dev/ai-videos/opus-5-5/demonugc-525162?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos) · [Bài đăng gốc](https://x.com/demonugc/status/2103526713208525162)

- **Danh mục:** Motion graphics
- **Bản làm lại dùng:** SVG
- **Tác giả:** [@demonugc](https://x.com/demonugc)

Trang gốc (chưa dịch): [prompts/demonugc-525162.md](../prompts/demonugc-525162.md)

## Prompt (tiếng Việt)

```text
<inputs>
Hãy hỏi tôi: 8 đến 12 trạng thái UI tôi muốn hình khối biến thành (ví dụ button, loader, player, slider, toggle, tabs, chart, command palette, toast), thuần đen trắng hay một màu nhấn, và một bài nhạc miễn phí bản quyền khoảng 120 BPM (ví dụ Mixkit, miễn phí cho mục đích thương mại).
</inputs>

<direction>
Motion UI đẳng cấp Dribbble. Một hình khối, không bao giờ cắt: mọi trạng thái đều là cùng một phần tử biến hình về kích thước, bo góc và màu sắc trong khi nội dung của nó hoán đổi bằng một cú blur ngắn. Một con trỏ điều khiển mọi thay đổi bằng các cú click và kéo thật. Nền xám ấm sáng, thành phần đen trắng, một font UI gọn gàng (Geist). Spring ở mọi nơi, vọt lố rất nhỏ là tối đa. Camera zoom để mỗi trạng thái lấp đầy khung hình. Khung hình cuối chính là khung hình đầu, nên nó lặp lại.
Cấm: easing nảy, bùng nổ hạt, glow, gradient trên phần khung UI, nét icon không đồng nhất, thời gian chết, bất cứ thứ gì trông như template.
</direction>

<structure>
120 BPM, 7 ô nhịp, mỗi phách đều có điều gì đó xảy ra.
Button → loader → check → dynamic island → trình phát nhạc với play/pause biến hình → tua thanh tiến trình → nó trở thành thanh trượt âm lượng giãn ra khi bị kéo quá mức tối đa → một toggle bật đúng phách → núm trở thành thanh chỉ báo tab dạng chất lỏng → các tab mở ra thành một biểu đồ tự vẽ, có tooltip khi hover → nó thu lại thành ⌘K → gõ để lọc → enter → toast → quay về button.
</structure>

<build>
1. Một file HTML, khung vuông 1440x1440. Mọi style được tính từ thời gian bên trong seek(t): không CSS transition, không timer, không trạng thái mang từ khung hình này sang khung hình khác.
2. Spring là các đáp ứng bước closed-form. Một giá trị đổi target nhiều lần là tổng của một spring cho mỗi lần đổi, nên nó vẫn là hàm thuần của thời gian.
3. Hai cạnh của thanh chỉ báo tab chạy trên hai spring khác nhau, nên cạnh dẫn giãn ra trước cạnh sau. Dùng cùng mẹo cho núm toggle.
4. Thao tác kéo là thao tác trực tiếp: khi con trỏ đang giữ, giá trị được tính từ vị trí của nó. Khi thả, nó bật về bằng spring từ bất cứ vị trí nào nó đang ở.
5. Phân tích bài nhạc bằng numpy để lấy lưới phách và bắt đầu ở một phách mạnh đầu ô nhịp. Đặt mỗi âm thanh UI theo đỉnh đo được của nó.
6. Render bằng Playwright: 4 subframe mỗi khung hình, trộn bằng ffmpeg tmix để có motion blur ở 60fps.
7. Render một khung hình mỗi phách trước khi render đầy đủ. Sửa mọi chỗ lệch lưới, chật chội hoặc khó đọc.
</build>

<gotchas>
Không bao giờ đặt will-change lên bất cứ thứ gì camera scale, nếu không chữ sẽ render bị mờ. Chữ hoán đổi bên trong một container đang biến hình cần thời điểm vào và ra riêng, nếu không sẽ chồng lên nhau. Làm khung hình cuối giống hệt khung hình đầu, kể cả vị trí và tốc độ con trỏ, nếu không vòng lặp sẽ bị giật.
</gotchas>

<start>
Hãy hỏi tôi các đầu vào, rồi cho tôi xem danh sách trạng thái trên lưới phách trước khi bạn viết bất kỳ dòng code nào.
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
