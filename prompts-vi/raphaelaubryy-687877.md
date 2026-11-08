# Video Opus 5.5 của @RaphaelAubryy

[▶ Xem bản gốc và bản làm lại trực tiếp trên Skillry](https://skillry.dev/ai-videos/opus-5-5/raphaelaubryy-687877?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos) · [Bài đăng gốc](https://x.com/RaphaelAubryy/status/2103413596822687877)

- **Danh mục:** Cảnh 3D
- **Bản làm lại dùng:** CSS
- **Tác giả:** [@RaphaelAubryy](https://x.com/RaphaelAubryy)

Trang gốc (chưa dịch): [prompts/raphaelaubryy-687877.md](../prompts/raphaelaubryy-687877.md)

## Prompt (tiếng Việt)

```text
<inputs>
Hãy hỏi tôi: tên sản phẩm và một câu hứa hẹn một dòng, 3 đến 5 khoảnh khắc UI cần thể hiện, một màu nhấn, 10 đến 20 clip dọc thật do tôi sở hữu, và một bài hát miễn phí bản quyền có đoạn drop rõ ràng (ví dụ Mixkit, miễn phí cho mục đích thương mại).
</inputs>

<direction>
Tối giản cao cấp. Mỗi shot một ý, nhiều khoảng trống, một màu nhấn, một font sans gọn (Geist hoặc Inter) với tracking chặt. Hiện chữ bằng mask, match cut, một ngôn ngữ camera mượt duy nhất. Chỉ dùng footage thật, không bao giờ dùng thẻ placeholder. Không dùng dấu chấm câu trong chữ trên màn hình.
Cấm: vòng sóng xung kích, nổ hạt, tách kênh RGB, rung camera, lens flare, glow neon, sàn lưới, nền nhấp nháy, easing nảy.
</direction>

<structure>
10 ô nhịp ở 120 BPM, mỗi ô 2 giây.
Ô nhịp 1: câu mồi hiện từng chữ theo nhịp.
Ô nhịp 2: một chữ trong câu mồi biến hình thành UI sản phẩm. Một con trỏ gõ và click.
Đoạn drop: một hình tròn mở ra từ nút bấm vào một cảnh tối.
Sau đó mỗi ô nhịp một chuyển động: một bức tường clip thật với vạch quét và 3 clip thắng, đầu ra chính dưới dạng chữ lớn, một carousel 3D các video thật có phản chiếu trên sàn và một cú lia nhanh (whip) có motion blur vào một clip chủ đạo, clip chủ đạo nằm trong điện thoại bên cạnh một panel lật ra thành kết quả, các con số lớn với push cut, một dòng chữ chạy 3 từ, một màn lộ logo, mờ dần về đen.
</structure>

<build>
1. Một file HTML ở 1920x1080. Mọi style được tính từ thời gian bên trong
http://
window.seek(t): không CSS animation, không timer, không state giữa các khung hình.
2. Video thật: trích các clip thành chuỗi JPEG 30fps bằng ffmpeg và đổi nguồn img mỗi khung hình. seek chờ (await) ảnh giải mã xong.
3. Phân tích bài hát bằng numpy: tempo, lưới nhịp, năng lượng mỗi ô nhịp, đoạn drop. Hiệu chỉnh lưới theo các cú kick thật. Mỗi cú cắt nằm trên phách mạnh, mỗi cú hit UI nằm trên một nhịp.
4. Render bằng Playwright: 3 subframe mỗi khung hình tại t trừ, tại, và cộng 1/240s, rồi trộn bằng ffmpeg tmix để có motion blur thật ở 60fps.
5. Đặt mỗi hiệu ứng âm thanh sao cho đỉnh đo được của nó, chứ không phải điểm bắt đầu file, rơi đúng vào sự kiện. Giữ hiệu ứng nhỏ dưới tiếng nhạc. Loudnorm về -14 LUFS.
6. Kiểm thử 20 khung hình trở lên trước khi render toàn bộ. Sửa mọi thứ rối, chồng lấn hoặc khó đọc.
</build>

<gotchas>
Không bao giờ đặt opacity hay filter lên một phần tử preserve-3d, vì nó sẽ bị dẹt và cả hai mặt đều hiện. Hãy làm mờ phần tử bao ngoài (wrapper) thay vào đó. Đo vị trí phần tử lúc chạy cho các match cut. Chỉ dùng nhạc và hiệu ứng âm thanh có giấy phép cho phép sử dụng thương mại.
</gotchas>

<start>
Hãy hỏi tôi các đầu vào, rồi cho tôi xem một storyboard với mọi thời điểm nằm trên lưới nhịp trước khi bạn viết bất kỳ dòng code nào.
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
