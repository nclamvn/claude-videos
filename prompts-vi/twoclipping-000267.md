# Video Opus 5.5 của @twoclipping

[▶ Xem bản gốc và bản làm lại trực tiếp trên Skillry](https://skillry.dev/ai-videos/opus-5-5/twoclipping-000267?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos) · [Bài đăng gốc](https://x.com/twoclipping/status/2102554209166000267)

- **Danh mục:** Cảnh 3D
- **Bản làm lại dùng:** SVG · CSS
- **Tác giả:** [@twoclipping](https://x.com/twoclipping)

Trang gốc (chưa dịch): [prompts/twoclipping-000267.md](../prompts/twoclipping-000267.md)

## Prompt (tiếng Việt)

```text
<inputs>
Hãy hỏi tôi: tên sản phẩm và một câu cam kết, 3 đến 5 khoảnh khắc UI cần thể hiện, một màu nhấn, 10 đến 20 clip dọc thật do tôi sở hữu, và một bài hát miễn phí bản quyền có cú drop rõ ràng (ví dụ Mixkit, miễn phí cho mục đích thương mại).
</inputs>

<direction>
Tối giản cao cấp. Mỗi shot một ý, nhiều khoảng trống, một màu nhấn, một font sans sạch (Geist hoặc Inter) với tracking khít. Chữ hiện ra qua mask, match cut, một ngôn ngữ camera mượt thống nhất. Chỉ dùng footage thật, không bao giờ dùng thẻ placeholder. Không có dấu chấm câu trong chữ trên màn hình.
Cấm: vòng sóng xung kích, nổ hạt, tách RGB, rung camera, lens flare, quầng neon, sàn lưới, nền nhấp nháy, easing nảy.
</direction>

<structure>
10 ô nhịp ở 120 BPM, mỗi ô 2 giây.
Ô 1: câu hook rơi xuống từng từ theo beat.
Ô 2: một từ trong hook biến hình thành UI sản phẩm. Một con trỏ gõ chữ và click.
Cú drop: một vòng tròn mở ra từ nút bấm thành một cảnh tối.
Sau đó mỗi ô nhịp một chuyển động: một bức tường clip thật với một đường quét và 3 clip thắng, kết quả chính dưới dạng chữ lớn, một carousel 3D các video thật có phản chiếu trên sàn và một cú whip có motion blur vào một clip chủ đạo, clip chủ đạo trong một chiếc điện thoại cạnh một panel lật ra kết quả, số liệu lớn trên các cú push cut, một ticker 3 từ, màn hiện logo, mờ dần về đen.
</structure>

<build>
1. Một file HTML ở 1920x1080. Mọi style được tính từ thời gian bên trong
http://
window.seek(t): không CSS animation, không timer, không có trạng thái giữa các khung hình.
2. Video thật: tách các clip thành chuỗi JPEG 30fps bằng ffmpeg và đổi src của img theo từng khung hình. seek chờ ảnh decode xong.
3. Phân tích bài hát bằng numpy: tempo, lưới beat, năng lượng mỗi ô nhịp, cú drop. Hiệu chỉnh lưới theo các tiếng kick thật. Mọi cú cắt nằm trên phách mạnh, mọi điểm nhấn UI nằm trên một beat.
4. Render bằng Playwright: 3 subframe mỗi khung hình ở t trừ, tại t, và t cộng 1/240s, rồi trộn bằng ffmpeg tmix để có motion blur thật ở 60fps.
5. Đặt mỗi hiệu ứng âm thanh sao cho đỉnh đo được của nó, chứ không phải điểm bắt đầu file, rơi đúng sự kiện. Giữ hiệu ứng nhỏ bên dưới nhạc. Loudnorm về -14 LUFS.
6. Thăm dò 20 khung hình trở lên trước khi render toàn bộ. Sửa mọi thứ rối, chồng lấn hoặc khó đọc.
</build>

<gotchas>
Không bao giờ đặt opacity hay filter lên một phần tử preserve-3d, vì nó làm phẳng phần tử và cả hai mặt đều hiện ra. Hãy làm mờ wrapper của nó thay vào đó. Đo vị trí phần tử lúc runtime cho các match cut. Chỉ dùng nhạc và hiệu ứng âm thanh có giấy phép cho phép sử dụng thương mại.
</gotchas>

<start>
Hãy hỏi tôi các đầu vào, rồi cho tôi xem một storyboard với mọi mốc thời gian nằm trên lưới beat trước khi bạn viết bất kỳ dòng code nào.
</start>
```

## Prompt gốc

```text
<inputs>
Ask me for: the product name and a one-line promise, 3 to 5 UI moments to show, one accent color, 10 to 20 real vertical clips I own, and a royalty-free song with a clear drop (e.g. Mixkit, free for commercial use).
</inputs>

<direction>
High-end minimal. One idea per shot, lots of empty space, one accent color, one clean sans (Geist or Inter) with tight tracking. Masked type reveals, match cuts, one smooth camera language. Real footage only, never placeholder cards. No full stops in on-screen text.
Banned: shockwave rings, particle bursts, RGB split, camera shake, lens flares, neon glows, grid floors, flashing backgrounds, bouncy easing.
</direction>

<structure>
10 bars at 120 BPM, 2 seconds each.
Bar 1: the hook lands word by word on the beats.
Bar 2: one hook word morphs into the product UI. A cursor types and clicks.
The drop: a circle opens out of the button into a dark scene.
Then one move per bar: a wall of real clips with a scan line and 3 winners, the key output as big type, a 3D carousel of real videos with floor reflections and a motion-blurred whip onto one hero clip, the hero in a phone next to a panel that flips into results, big stats on push cuts, a 3-word ticker, a logo reveal, a fade to black.
</structure>

<build>
1. One HTML file at 1920x1080. Every style is computed from time inside 
http://
window.seek(t): no CSS animations, no timers, no state between frames.
2. Real video: extract clips to 30fps JPEG sequences with ffmpeg and swap img sources per frame. seek awaits the image decodes.
3. Analyze the song with numpy: tempo, beat grid, energy per bar, the drop. Calibrate the grid to the real kick hits. Every cut sits on a downbeat, every UI hit on a beat.
4. Render with Playwright: 3 subframes per frame at t minus, at, and plus 1/240s, then blend with ffmpeg tmix for real motion blur at 60fps.
5. Place each sound effect so its measured peak, not its file start, lands on the event. Keep the effects quiet under the music. Loudnorm to -14 LUFS.
6. Probe 20 or more frames before the full render. Fix anything cluttered, overlapping or hard to read.
</build>

<gotchas>
Never set opacity or filter on a preserve-3d element, because it flattens and both faces show. Fade its wrapper instead. Measure element positions at runtime for match cuts. Only use music and sound effects whose license allows commercial use.
</gotchas>

<start>
Ask me for the inputs, then show me a storyboard with every timing on the beat grid before you write any code.
</start>
```
