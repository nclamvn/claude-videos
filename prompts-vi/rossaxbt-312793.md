# Motion quảng bá sản phẩm

_Product Promo Motion_

Video Opus 5.5 của [@rossaxbt](https://x.com/rossaxbt) · [Bài đăng gốc kèm video](https://x.com/rossaxbt/status/2107483570885312793)

- **Danh mục:** Cảnh 3D
- **Tác giả:** [@rossaxbt](https://x.com/rossaxbt)

Thêm video Opus 5.5, mỗi video kèm bản làm lại trực tiếp: [skillry.dev/ai-videos/opus-5-5](https://skillry.dev/ai-videos/opus-5-5?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos)

Trang gốc (chưa dịch): [prompts/rossaxbt-312793.md](../prompts/rossaxbt-312793.md)

## Prompt (tiếng Việt)

```text
<inputs>
Hãy hỏi tôi: một câu hỏi người dùng hỏi sản phẩm của tôi và câu trả lời một dòng cho nó, hai ảnh bìa album, một bài nhạc miễn phí bản quyền khoảng 110 BPM với intro nhẹ và một cú drop mạnh (Mixkit, miễn phí cho mục đích thương mại), và logo của tôi cho đoạn kết. Nếu tôi bỏ qua thứ gì, dùng các giá trị mặc định sau: "is this all code?" / "yes. every frame.", hai ảnh giàu không khí, và bài "Head Bang" của Mixkit.
</inputs>

<direction>
Một loop vuông 22 giây, 1440x1440 ở 60fps. Chỉ 2D, một cú máy liền mạch. Không có gì bị cắt: mỗi cảnh mọc ra từ cảnh trước, và mọi cử chỉ đều đưa camera vào không gian tiếp theo. Mỗi lần biến hình kéo dài 0.8s theo cubic-bezier(.45,0,.15,1). Zoom của camera đi theo đúng đường cong đó, khiến các thay đổi hình dạng gần như vô hình. Nội dung tan biến trong nửa sau của mỗi lần lướt. Mỗi cảnh một cử chỉ.

Diện mạo: một sân khấu sáng ấm (#f3f3f0 đến #e3e3de), UI màu đen, và một thế giới app tối (#121212) được nhuốm màu theo ảnh bìa album hiện tại. Dùng một màu nhấn xanh lá duy nhất (#1ed760), Geist cho UI, con trỏ macOS thật, và bóng đổ nhiều lớp mềm lớn dần khi các hình nhấc lên.

Cấm: cắt cứng, lò xo nảy, hạt, glow, zoom vào rồi lập tức zoom ra, giữ hình lâu hơn 1s, bất cứ thứ gì có cảm giác như template.
</direction>

<structure>
Bám theo nhịp của bài hát. Cú nhấn rơi đúng vào drop.

Generate: con trỏ click. Viên pill lướt thành một spinner, rồi trở thành dấu check.

Chat: dấu check tách thành ba chấm đang gõ với hiệu ứng goo. Chấm bên trái bay lên, trở thành bong bóng câu hỏi và gõ câu hỏi. Chấm bên phải bay xuống thành câu trả lời. Cả hai bong bóng co lại thành chấm khi lướt về giữa và hợp nhất với chấm ở giữa.

Play: chấm ở giữa uốn thành tam giác play, từng đỉnh một. Con trỏ nhấn vào nó đúng lúc drop. Một nút trắng xuất hiện dưới cú click khi app tối tràn ngập khung hình xung quanh nó, để lại hình trắng làm nút play. Camera lùi ra để lộ toàn bộ màn hình now-playing: ảnh bìa lớn, tiêu đề, trái tim (đã thích, tô đầy xanh lá), thanh tiến trình, các nút điều khiển và âm lượng.

Swipe: con trỏ kéo ảnh bìa sang ngang. Bài tiếp theo trượt vào, và app đổi tông màu cho khớp với ảnh bìa mới.

Drag: camera lướt về phía thanh trượt âm lượng. Con trỏ kéo nó lên tối đa và tiếp tục kéo. Thanh bị giãn kiểu rubber-band, kéo camera sang ngang ra khỏi app và lên một canvas tối có chấm, trong khi camera bám theo núm.

Chart: đường kẻ đáp xuống và cong lên thành một biểu đồ xanh lá khi con số đếm tăng lên. Núm âm lượng trở thành điểm cuối của biểu đồ.

Dive: con trỏ click vào điểm đó. Camera lao vào trong nó cho đến khi sân khấu sáng lấp đầy khung hình.

Ending: một nút "Ask [sản phẩm của tôi]" mọc ra từ ánh sáng, thu hẹp thành một đường kẻ, rồi xòe ra thành logo của tôi (mặc định: Claude spark, với sáu bản sao xoay thành mười hai tia màu cam Claude). Giữ 2s.
```

## Prompt gốc

```text
<inputs>
Ask me for: one question a user asks my product and its one-line answer, two album covers, a royalty-free song around 110 BPM with a quiet intro and a hard drop (Mixkit, free for commercial use), and my logo for the ending. If I skip anything, use these defaults: "is this all code?" / "yes. every frame.", two atmospheric photos, and Mixkit "Head Bang".
</inputs>

<direction>
A 22-second square loop, 1440x1440 at 60fps. 2D only, one continuous take. Nothing cuts: each scene grows from the one before it, and every gesture carries the camera into the next space. Each morph takes 0.8s on cubic-bezier(.45,0,.15,1). The camera zoom follows the same curve, making the shape changes feel almost invisible. Content dissolves during the second half of each glide. One gesture per scene.

Look: a warm light stage (#f3f3f0 to #e3e3de), black UI, and a dark app world (#121212) tinted by the current album cover. Use one green accent (#1ed760), Geist for UI, the real macOS pointer, and soft layered shadows that grow as shapes lift.

Banned: hard cuts, bouncy springs, particles, glows, zooming in and immediately back out, holds longer than 1s, anything that feels like a template.
</direction>

<structure>
Follow the song's beats. The press lands on the drop.

Generate: the cursor clicks. The pill glides into a spinner, then becomes a check.

Chat: the check splits into three typing dots with goo. The left dot flies up, becomes the question bubble and types the question. The right dot flies down into the reply. Both bubbles shrink back into dots as they glide toward the center and merge with the middle dot.

Play: the middle dot bends into a play triangle, one point at a time. The cursor presses it on the drop. A white button appears under the click as the dark app floods the frame around it, leaving the white shape as the play button. The camera pulls back to reveal the full now-playing screen: large cover, title, heart (liked, filling green), progress bar, controls and volume.

Swipe: the cursor drags the cover sideways. The next track slides in, and the app changes its tint to match the new cover.

Drag: the camera glides toward the volume slider. The cursor pulls it to max and keeps going. The bar rubber-bands, dragging the camera sideways out of the app and onto a dark dotted canvas while the camera follows the knob.

Chart: the line lands and curves upward into a green chart as the number counts up. The volume knob becomes the chart's final point.

Dive: the cursor clicks that point. The camera dives into it until the light stage fills the frame.

Ending: an "Ask [my product]" button grows from the light, narrows into a line, then fans out into my logo (default: the Claude spark, with six copies rotating into twelve rays in Claude orange). Hold for 2s.
```
