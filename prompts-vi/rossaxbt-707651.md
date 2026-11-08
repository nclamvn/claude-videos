# Hệ thống motion design

_Motion Design System_

Video Opus 5.5 của [@rossaxbt](https://x.com/rossaxbt) · [Bài đăng gốc kèm video](https://x.com/rossaxbt/status/2107121188027707651)

- **Danh mục:** Game & tương tác
- **Tác giả:** [@rossaxbt](https://x.com/rossaxbt)

Thêm video Opus 5.5, mỗi video kèm bản làm lại trực tiếp: [skillry.dev/ai-videos/opus-5-5](https://skillry.dev/ai-videos/opus-5-5?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos)

Trang gốc (chưa dịch): [prompts/rossaxbt-707651.md](../prompts/rossaxbt-707651.md)

## Prompt (tiếng Việt)

```text
<inputs>
Hãy hỏi tôi: một nhãn ngắn cho công tắc mở đầu, một từ chủ đạo, một tỉ lệ phần trăm cho biểu đồ, chữ cho thẻ kết, một màu nhấn, và một bản nhạc có nhịp rõ.
</inputs>

<direction>
Một phim motion design 2D tỉ lệ 16:9. Dùng canvas trắng ngà ấm, nền gần đen, chữ đậm và một màu nhấn cam rực. Chấm cam nối mọi cảnh: nó bắt đầu trong UI, trở thành dấu chấm trên một chữ cái, vẽ một biểu đồ spring, lớn dần thành một hình và quay lại ở thẻ kết. Một con trỏ làm cho cú click mở đầu có cảm giác thật. Giữ chuyển động sắc gọn và có kiểm soát, với các cú vượt ngưỡng spring nhỏ và không có thời gian chết.
Cấm: footage stock, gradient, glow, nổ hạt, chuyển cảnh ngẫu nhiên và chuyển động không gắn với một phần tử đã có trên màn hình.
</direction>

<structure>
Khoảng 15 giây, có thay đổi hình ảnh ở mỗi nhịp chính.
Mở đầu: một con trỏ click vào công tắc màu cam cạnh "Reduce Motion". Các chữ cái uốn cong và di chuyển vào vị trí cho tới khi chỉ còn "Motion", với chấm cam phía trên chữ "i".
Spring: chấm nhảy khỏi chữ và đáp xuống một biểu đồ. Đường đi của nó vẽ ra một đáp ứng spring, vượt quá mục tiêu rồi ổn định bên cạnh chú thích "+22%".
Hình: chấm phóng dọc một đường thẳng, lớn thành một hình tròn cam và lấp đầy khung hình. Một hình vuông bo góc màu đen xoay bên trong nó, rồi kéo dài thành hình pill. Cảnh co lại thành một chấm cam duy nhất trên nền đen.
Chữ: các từ như "SPRINGS", "EASING", "KINETIC TYPE", "3D" và "SOUND" quay quanh chấm. Vòng chữ mở rộng ra thành một trường các chấm nhỏ li ti.
Lộ diện: trường halftone mở rộng và lật sang đen, để lộ thẻ kết: "Opus 5.5", "Motion designer." và "0 keyframes".
Quay về: chấm cam di chuyển ngược qua halftone, biểu đồ và công tắc. Khớp khung hình cuối với khung hình đầu để video lặp sạch.
</structure>

<build>
1. Một file HTML, 1920x1080 ở 60fps. Tính mọi yếu tố hình ảnh từ thời gian bên trong seek(t): không CSS transition, không timer, không state mang qua giữa các khung hình.
2. Dùng spring dạng nghiệm đóng (closed-form) cho công tắc, chấm nảy và biểu đồ. Vẽ biểu đồ từ chính hàm spring đã di chuyển chấm.
3. Animate từng chữ cái riêng lẻ cho phép biến đổi "Reduce Motion" thành "Motion". Giữ chấm cam gắn vào chữ "i" cho tới khi nó bắt đầu cú nhảy.
4. Làm cho hình tròn cam, hình vuông xoay và hình pill là các trạng thái khác nhau của cùng một hình. Giữ nguyên vị trí và chuyển động của nó qua mỗi lần biến đổi.
5. Đặt các từ quay quanh dọc theo một đường tròn, rồi đẩy các chữ cái của chúng ra ngoài để nhường khung hình cho lưới halftone.
6. Vẽ halftone như một lưới chấm có kích thước phản ứng theo chấm cam. Để nó lớn tràn qua mép khung hình trước khi lộ thẻ kết.
7. Đồng bộ cú click, lúc chấm đáp xuống, đỉnh biểu đồ, các lần đổi hình và tiêu đề cuối với các nhịp đã đo.
```

## Prompt gốc

```text
<inputs>
Ask me for: a short label for the opening toggle, one hero word, a percentage for the graph, the text for the final card, one accent color, and a track with a clear beat.
</inputs>

<direction>
A 2D motion design film in 16:9. Use a warm off-white canvas, near-black backgrounds, bold typography and one vivid orange accent. The orange dot connects every scene: it starts in the UI, becomes the dot over a letter, traces a spring graph, grows into a shape and returns on the end card. A cursor makes the opening click feel real. Keep the motion sharp and controlled, with small spring overshoots and no dead time.
Banned: stock footage, gradients, glows, particle bursts, random transitions and motion that isn't connected to an element already on screen.
</direction>

<structure>
Around 15 seconds, with a visual change on every major beat.
Open: a cursor clicks the orange toggle beside "Reduce Motion". The letters bend and move into place until only "Motion" remains, with the orange dot above the "i".
Spring: the dot jumps away from the word and lands on a graph. Its path draws a spring response, overshoots the target and settles beside a "+22%" callout.
Shape: the dot shoots across a line, grows into an orange circle and fills the frame. A black rounded square rotates inside it, then stretches into a pill. The scene contracts to a single orange dot on black.
Type: words like "SPRINGS", "EASING", "KINETIC TYPE", "3D" and "SOUND" orbit the dot. The circle of type opens out into a field of tiny dots.
Reveal: the halftone field expands and flips to black, revealing the final card: "Opus 5.5", "Motion designer." and "0 keyframes".
Return: the orange dot moves back through the halftone, graph and toggle. Match the final frame to the first so the video loops cleanly.
</structure>

<build>
1. One HTML file, 1920x1080 at 60fps. Compute every visual from time inside seek(t): no CSS transitions, timers or state carried between frames.
2. Use closed-form springs for the toggle, bouncing dot and graph. Draw the graph from the same spring function that moves the dot.
3. Animate letters individually for the "Reduce Motion" to "Motion" transformation. Keep the orange dot attached to the "i" until it begins its jump.
4. Make the orange circle, rotating square and pill different states of the same shape. Preserve its position and motion through each transformation.
5. Place the orbiting words along a circular path, then move their letters outward to hand the frame over to the halftone grid.
6. Draw the halftone as a grid of dots whose sizes respond to the orange dot. Let it grow past the frame edges before revealing the end card.
7. Sync the click, dot landing, graph peak, shape changes and final title to measured beats.
```
