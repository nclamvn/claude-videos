# Music video hoạt hình sinh bằng code

_Code-Generated Music Video Animation_

Video Opus 5.5 của [@thewevr](https://x.com/thewevr) · [Bài đăng gốc kèm video](https://x.com/thewevr/status/2106774417732681887)

- **Danh mục:** Motion graphics
- **Tác giả:** [@thewevr](https://x.com/thewevr)

Thêm video Opus 5.5, mỗi video kèm bản làm lại trực tiếp: [skillry.dev/ai-videos/opus-5-5](https://skillry.dev/ai-videos/opus-5-5?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos)

Trang gốc (chưa dịch): [prompts/thewevr-681887.md](../prompts/thewevr-681887.md)

## Prompt (tiếng Việt)

```text
Hãy làm một music video hoàn chỉnh cho bài hát trong thư mục này, với
toàn bộ hình ảnh được vẽ và tạo chuyển động bằng JavaScript. Dùng toàn bộ bài hát.

THIẾT LẬP
Hãy kiểm tra thư mục này và xác định bài hát cùng mọi file lời bài hát hoặc
tài liệu tham khảo. Giữ nguyên các file gốc của tôi, không thay đổi.

Dùng bộ khởi tạo animation có sẵn này:
https://t.co/oN3A7ZZyEl

Clone nó vào một thư mục con mới ./video, trừ khi đã có sẵn
một bản sao. Không ghi đè công việc hiện có và không clone vào
thư mục gốc dự án đang có nội dung.

Đọc toàn bộ README.md và ANIMATION_GUIDE.md của nó, rồi kiểm tra
render.mjs và cấu hình dự án. Dùng bộ máy render có sẵn
thay vì tự chế một bộ thay thế.

Kiểm tra Node.js, Chrome và FFmpeg. Kiểm tra cấu hình package
và cài đặt các dependency của dự án. Hãy hỏi trước khi thay đổi toàn hệ thống
hoặc tải thêm các công cụ dung lượng lớn.

Không dùng fal, công cụ tạo ảnh/video bên ngoài, API trả phí, hoặc
plugin music-video lai. Mọi hình ảnh hoàn thiện phải được vẽ bằng code.

ĐỊNH HƯỚNG SÁNG TẠO
Hãy tạo một music video hoạt hình liền mạch, giàu trí tưởng tượng về hình ảnh, với
cảm giác thủ công, chất giấy, minh hoạ. Thể hiện ý nghĩa bài hát qua
các cảnh, nhân vật, ẩn dụ hình ảnh và chuyển cảnh có chủ đích.
Xây dựng một đoạn mở đầu cuốn hút và phát triển các motif hình ảnh lặp lại.
Không làm slideshow, visualizer âm thanh chung chung, hay một loop animation
lặp lại suốt cả bài. Thiết kế nhân vật phù hợp với
bài hát này thay vì mặc định dùng mascot của bộ khởi tạo.

ÂM NHẠC VÀ THỜI GIAN
Dùng bản thu được cung cấp làm soundtrack gốc liên tục.
Không remix, thay thế, tăng tốc hay cắt ngắn nó.

Đo thời lượng và dùng các công cụ phân tích âm thanh cục bộ có sẵn để
xác định các đoạn nhạc và các mốc beat/nhấn khả dĩ.
Ghi lại chúng trong một timeline dùng chung và điều khiển animation từ timeline đó.

Coi lời bài hát được cung cấp là chuẩn. Nếu thiếu lời, chỉ dùng công cụ
chép lời cục bộ nếu có sẵn, đánh dấu những từ không chắc chắn, và
không bịa lời. Tiếp tục với hình ảnh không lời ở những chỗ cần thiết.

Khi có lời bài hát đã được xác minh, hãy dùng animation lời biểu cảm, dễ đọc
ở những chỗ nó làm cảnh mạnh hơn. Điều này ghi đè rõ ràng
mặc định của bộ khởi tạo là hạn chế dùng chữ.

SẢN XUẤT
Viết STORYBOARD.md với các cảnh có mốc thời gian bao phủ toàn bộ bản thu.
Lưu brief dự án và hướng dẫn render lại trong CLAUDE.md.

Sau đó dựng video. Hãy tự đưa ra các quyết định sáng tạo hợp lý và tiếp tục
mà không dừng lại xin duyệt ở từng cảnh.

Thử một vài khung hình tiêu biểu và một đoạn ngắn trước khi render toàn bộ.
Kiểm tra các ảnh và chuỗi khung hình thu được, sửa các lỗi nhìn thấy được, và
giữ animation ở mức thực tế cho máy tính này.

Dùng texture vẽ bằng code hiệu quả nếu các hiệu ứng màu nước tốn kém
làm việc render trở nên không khả thi.

BÀN GIAO
Render toàn bộ video
```

## Prompt gốc

```text
Make a complete music video for the song in this folder, with all
visuals drawn and animated in JavaScript. Use the entire song.

SETUP
Inspect this folder and identify the song and any lyrics or reference
files. Preserve my original files unchanged.

Use this existing animation starter:
https://t.co/oN3A7ZZyEl

Clone it into a new ./video subfolder, unless an existing copy is
already present. Do not overwrite existing work or clone into the
nonempty project root.

Read its README.md and ANIMATION_GUIDE.md completely, then inspect
render.mjs and the project configuration. Use the existing rendering
machinery rather than inventing a replacement.

Check Node.js, Chrome, and FFmpeg. Inspect the package configuration
and install the project dependencies. Ask before making system-wide
changes or downloading large additional tools.

Do not use fal, external image/video generation, paid APIs, or the
hybrid music-video plugin. All finished visuals must be code-drawn.

CREATIVE DIRECTION
Create a cohesive, visually imaginative animated music video with a
handmade, papery, illustrated feel. Express the song's meaning through
scenes, characters, visual metaphors, and purposeful transitions.
Establish an engaging opening and develop recurring visual motifs.
Do not make a slideshow, a generic audio visualizer, or one animation
loop repeated for the entire song. Design characters appropriate to
this song rather than automatically using the starter's mascot.

MUSIC AND TIMING
Use the supplied recording as the continuous master soundtrack.
Do not remix, replace, speed up, or shorten it.

Measure its duration and use available local audio-analysis tools to
identify musical sections and likely beat/accent timings. Record these
in a shared timeline and drive animation from that timeline.

Use supplied lyrics as authoritative. If lyrics are missing, use a
local transcription tool only if available, flag uncertain words, and
do not invent lyrics. Continue with non-lyric visuals where necessary.

When verified lyrics are available, use expressive, readable lyric
animation where it strengthens the scene. This explicitly overrides
the starter's default preference against lettering.

PRODUCTION
Write STORYBOARD.md with timed scenes covering the complete recording.
Save the project brief and rerender instructions in CLAUDE.md.

Then build the video. Make reasonable creative decisions and continue
without stopping for approval at every scene.

Test a few representative frames and a short section before the full
render. Inspect the resulting images and frame sequences, fix visible
defects, and keep the animation practical for this computer.

Use efficient code-drawn textures if expensive watercolor effects
make rendering impractical.

DELIVERY
Render the complete video
```
