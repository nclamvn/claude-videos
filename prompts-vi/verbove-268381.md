# Video Opus 5.5 của @verbove

[▶ Xem bản gốc và bản làm lại trực tiếp trên Skillry](https://skillry.dev/ai-videos/opus-5-5/verbove-268381?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos) · [Bài đăng gốc](https://x.com/verbove/status/2103483957266268381)

- **Danh mục:** Video giải thích
- **Bản làm lại dùng:** Canvas
- **Tác giả:** [@verbove](https://x.com/verbove)

Trang gốc (chưa dịch): [prompts/verbove-268381.md](../prompts/verbove-268381.md)

## Prompt (tiếng Việt)

```text
<inputs>
Hãy hỏi tôi:
• sản phẩm của tôi + URL
• 8–12 trạng thái UI kể câu chuyện của nó
• dữ liệu thật hiển thị trong mỗi trạng thái
• màu thương hiệu + font + màu nhấn
• các định dạng cần có (1:1, 16:9, 9:16)
</inputs>

<rules>
Một file HTML. Một canvas
Một hàm draw(t)

Không CSS transition
Không timer
Không trạng thái mang từ khung hình này sang khung hình khác

Một hình khối, không bao giờ cắt

Mọi trạng thái đều là cùng một phần tử thay đổi kích thước, bo góc và màu sắc trong khi nội dung hoán đổi

Một con trỏ điều khiển chuỗi bằng các cú click, gõ phím thật và một lần kéo

UI thật. Dữ liệu thật. Không placeholder.

</rules>
<structure>
Lưới 120 BPM

Mỗi phách đều có điều gì đó xảy ra

logo → button → ô nhập handle → “is this you?” → loader → ghim → quả địa cầu đầy dần người dùng → các kết quả khớp → tabs → RSVP → tìm kiếm → logo

</structure>

<motion>
Spring closed-form ở mọi nơi, chỉ vọt lố rất nhỏ.

Nếu một giá trị đổi target nhiều lần, cộng dồn một spring cho mỗi lần đổi

Nội dung đi vào sau khi container bắt đầu biến hình và rời đi trước lần biến hình tiếp theo để chữ không bao giờ chồng lên nhau

Dùng một cú blur ngắn ở các chuyển cảnh

Không bao giờ fade trực tiếp từ đen sang màu nhấn. Thay vào đó hãy di chuyển một phần tử màu nhấn giữa các trạng thái

Làm thanh chỉ báo tab giãn ra bằng cách đặt mỗi cạnh lên một spring khác nhau

Zoom camera để mọi trạng thái lấp đầy khung hình

Làm khung hình cuối bằng khung hình đầu để cả chuỗi lặp lại
</motion>

<export>
Trước tiên render một khung hình mỗi phách thành một contact sheet

Sửa mọi chỗ chật chội hoặc bị lỗi

Sau đó render mọi khung hình trong Chrome headless ở 60fps, lấy trung bình 6 subframe để có motion blur

Pipe vào ffmpeg:
H.264 + yuv420p

Xuất song song tất cả các tỉ lệ khung hình
</export>

motion design đang trở thành một prompt
```

## Prompt gốc

```text
<inputs> 
Ask me for: 
• my product + URL 
• 8–12 UI states that tell its story 
• the real data shown in each state 
• brand colors + fonts + accent color 
• required formats (1:1, 16:9, 9:16) 
</inputs>

<rules> 
One HTML file. One canvas
One draw(t) function

No CSS transitions
No timers
No state carried between frames

One shape, never cut

Every state is the same element changing size, radius and color while the content swaps

A cursor drives the sequence with real clicks, typing and one drag

Real UI. Real data. No placeholders.

</rules>
<structure> 
120 BPM grid

Something happens on every bea

logo → button → handle field → “is this you?” → loader → pin → globe filling with users → matches → tabs → RSVP → search → logo

</structure>

<motion> 
Closed-form springs everywhere with only a tiny overshoot.

If a value changes target multiple times, sum one spring per change

Content enters after its container starts morphing and leaves before the next morph so text never overlaps

Use a short blur on transitions

Never fade black directly into the accent color. Move an accent element between states instead

Make tab indicators stretch by putting each edge on a different spring

Zoom the camera so every state fills the frame

Make the last frame equal the first so the whole thing loops
</motion>

<export> 
First render one frame per beat as a contact sheet

Fix anything cramped or broken

Then render every frame in headless Chrome at 60fps, averaging 6 subframes for motion blur

Pipe into ffmpeg:
H.264 + yuv420p

Export all aspect ratios in parallel
</export>

motion design is becoming a prompt
```
