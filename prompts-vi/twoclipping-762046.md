# Mẫu motion design ra mắt sản phẩm

_Product Launch Motion Design Template_

Video Opus 5.5 của [@twoclipping](https://x.com/twoclipping) · [Bài đăng gốc kèm video](https://x.com/twoclipping/status/2104674464868762046)

- **Danh mục:** Cảnh 3D
- **Tác giả:** [@twoclipping](https://x.com/twoclipping)

Thêm video Opus 5.5, mỗi video kèm bản làm lại trực tiếp: [skillry.dev/ai-videos/opus-5-5](https://skillry.dev/ai-videos/opus-5-5?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos)

Trang gốc (chưa dịch): [prompts/twoclipping-762046.md](../prompts/twoclipping-762046.md)

## Prompt (tiếng Việt)

```text
<inputs>
Hãy hỏi tôi: một câu hỏi mà người dùng đặt cho sản phẩm của tôi và câu trả lời một dòng của nó, hai bìa album, một bài nhạc miễn phí bản quyền khoảng 110 BPM có intro yên tĩnh và một đoạn drop mạnh (Mixkit, miễn phí cho mục đích thương mại), và logo của tôi cho đoạn kết. Nếu tôi bỏ qua mục nào, dùng mặc định: "is this all code?" / "yes. every frame.", hai ảnh có không khí, bài "Head Bang" của Mixkit.
</inputs>

<direction>
Một loop khổ vuông dài 22 giây, 1440x1440 ở 60fps, chỉ 2D, một cú máy liền mạch. Không bao giờ có cắt cảnh: mỗi cảnh mọc ra từ cảnh trước, và mỗi cử chỉ đều mang camera vào thế giới tiếp theo một cách vật lý. Mọi morph đều lướt trong 0.8s theo cubic-bezier(.45,0,.15,1) và zoom của camera cũng đi theo cùng đường cong đó, để các hình dạng biến đổi mượt tới mức bạn hầu như không nhận ra. Nội dung tan biến ở nửa sau của mỗi cú lướt. Mỗi cảnh một cử chỉ.
Diện mạo: một sân khấu sáng ấm (#f3f3f0 tới #e3e3de), UI màu đen, thế giới app tối (#121212) được nhuốm màu từ bìa album hiện tại, một màu nhấn xanh lá (#1ed760). Geist cho UI, con trỏ thật của macOS, bóng đổ mềm nhiều lớp lớn dần theo độ cao của hình.
Cấm: cắt cứng, spring nảy, hạt, glow, zoom vào rồi zoom thẳng ra lại, giữ lâu hơn 1s, bất cứ thứ gì trông như template.
</direction>

<structure>
Nhịp là nhịp của bài nhạc, và cú nhấn rơi đúng đoạn drop.
Generate: con trỏ click, viên thuốc lướt thành một spinner, rồi thành dấu check.
Chat: dấu check tách thành ba chấm đang gõ (goo). Chấm bên trái bay lên thành bong bóng câu hỏi và gõ câu hỏi ra, chấm bên phải bay xuống thành câu trả lời. Cả hai co lại thành chấm trong khi lướt vào và đổ vào chấm ở giữa.
Play: chấm ở giữa uốn thành hình tam giác play, từng điểm một. Con trỏ nhấn vào nó đúng đoạn drop: một nút trắng bật ra dưới cú click và app tối tràn ra xung quanh nó, để phần trắng còn lại trở thành nút play. Camera lùi ra để lộ toàn bộ màn hình now-playing: bìa lớn, tên bài, trái tim (đã thích, tô đầy xanh lá), thanh tiến trình, các nút điều khiển, âm lượng.
Swipe: con trỏ kéo bìa sang ngang, bài tiếp theo trượt vào, và cả app đổi màu theo bìa mới.
Drag: camera lướt tới phần âm lượng. Con trỏ kéo nó lên tối đa và tiếp tục kéo: thanh âm lượng giãn như dây thun và kéo camera sang ngang ra khỏi app, bám theo núm qua một canvas tối có chấm.
Chart: đường kẻ đáp xuống và uốn lên thành một biểu đồ xanh lá trong khi con số đếm tăng dần. Núm âm lượng trở thành điểm cuối của biểu đồ.
Dive: con trỏ click vào điểm đó và camera lao vào trong nó cho tới khi sân khấu sáng lấp đầy khung hình.
Kết thúc: một nút "Ask [my product]" mọc ra từ ánh sáng, mảnh dần thành một đường kẻ, và đường kẻ xoè ra thành logo của tôi (mặc định: tia lửa Claude, sáu bản sao xoay thành mười hai tia màu cam Claude). Nó gập lại về đường kẻ, đường kẻ dày lên thành Generate. Khung hình cuối = khung hình đầu.
</structure>
```

## Prompt gốc

```text
<inputs>
Ask me for: the one question a user asks my product and its one-line answer, two album covers, a royalty-free song around 110 BPM with a quiet intro and a hard drop (Mixkit, free for commercial use), and my logo for the ending. If I skip any, use the defaults: "is this all code?" / "yes. every frame.", two atmospheric photos, Mixkit "Head Bang".
</inputs>

<direction>
A 22 second square loop, 1440x1440 at 60fps, 2D only, one continuous take. Nothing ever cuts: every scene grows out of the last, and every gesture physically carries the camera into the next world. Every morph glides for 0.8s on cubic-bezier(.45,0,.15,1) and the camera zoom rides the same curve, so shapes change so smoothly you barely notice. Content dissolves in the back half of each glide. One gesture per scene.
Look: a warm light stage (#f3f3f0 to #e3e3de), black UI, the app world dark (#121212) tinted from the current album cover, one green accent (#1ed760). Geist for UI, the real macOS pointer, soft layered shadows that grow with the shape's height.
Banned: hard cuts, bouncy springs, particles, glows, zooming in and straight back out, holds longer than 1s, anything that looks like a template.
</direction>

<structure>
Beats are the song's, and the press lands on its drop.
Generate: the cursor clicks, the pill glides into a spinner, then a check.
Chat: the check splits into three typing dots (goo). The left dot flies up into the question bubble and types it, the right one flies down into the reply. Both contract back into dots while gliding in and pour into the middle one.
Play: the middle dot bends into a play triangle, point by point. The cursor presses it on the drop: a white button pops in under the click and the dark app floods out around it, so the leftover white becomes the play button. The camera pulls back to reveal the full now-playing screen: big cover, title, heart (liked, fills green), progress, controls, volume.
Swipe: the cursor drags the cover sideways, the next track slides in, and the whole app retints from the new cover.
Drag: the camera glides to the volume. The cursor drags it to max and keeps pulling: the bar rubber-bands and drags the camera sideways out of the app, tracking the knob across a dark dotted canvas.
Chart: the line lands and bends up into a green chart while the number counts up. The volume knob becomes its last point.
Dive: the cursor clicks that point and the camera dives into it until the light stage fills the frame.
Ending: an "Ask [my product]" button grows out of the light, thins into a line, and the line fans out into my logo (default: the Claude spark, six copies rotating into twelve rays in Claude orange). It folds back into the line, which thickens into Generate. Last frame = first frame.
</structure>
```
