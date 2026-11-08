# Phim ra mắt sản phẩm đồ ăn gây thèm

_Food Craving Product Launch Film_

Video Opus 5.5 của [@ultimaxbt](https://x.com/ultimaxbt) · [Bài đăng gốc kèm video](https://x.com/ultimaxbt/status/2108210884799549714)

- **Danh mục:** Cảnh 3D
- **Tác giả:** [@ultimaxbt](https://x.com/ultimaxbt)

Thêm video Opus 5.5, mỗi video kèm bản làm lại trực tiếp: [skillry.dev/ai-videos/opus-5-5](https://skillry.dev/ai-videos/opus-5-5?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos)

Trang gốc (chưa dịch): [prompts/ultimaxbt-549714.md](../prompts/ultimaxbt-549714.md)

## Prompt (tiếng Việt)

```text
<inputs>
Hãy hỏi tôi: sản phẩm của tôi, chính xác yêu cầu mà người dùng gõ vào nó, 6 đến 8 ảnh cho các thẻ kết quả, một bài nhạc miễn phí bản quyền khoảng 130 BPM có đoạn drop rõ ràng (Mixkit, miễn phí cho mục đích thương mại), và logo thương hiệu của tôi cho thẻ kết. Nếu tôi bỏ qua mục nào, dùng mặc định: câu chuyện đặt đồ ăn bên dưới, ảnh đồ ăn từ Pexels (mì cay lửa, taco birria, gà cay, cánh gà buffalo, smash burger, ramen cay), và bài "Cat Walk" của Mixkit.
</inputs>

<direction>
Một phim ra mắt sản phẩm dài 15 giây, 1920x1080 ở 60fps. Chỉ 2D, một cú máy liên tục. Không fade, không blur, không cắt: mỗi cảnh mọc ra từ cảnh trước. Chữ trồi lên từ một đường mask, nút bấm mở rộng thành trang, và màu sắc tràn ra từ một vật thể trước khi thu nhỏ vào một vật thể khác. Cho camera một chuyển động có easing ở mỗi cảnh, và không bao giờ zoom vào rồi zoom ra liên tiếp.

Giao diện: nền trắng ấm (#f5f5f2), UI đen (#0e0e10), màu nhấn xanh chanh (#cdf24f), cam (#ff6a2a) và nút gửi màu xanh dương (#2f6bff). Thêm một vầng sáng óng ánh kiểu Apple Intelligence quanh ô nhập: một conic gradient được blur, xoay qua hồng, cam, xanh chanh, cyan và tím. Dùng ảnh chụp đồ ăn thật trên các thẻ tối, Geist cho UI và một font serif cho tên sản phẩm ở thẻ kết.

Cấm: crossfade, blur-in, 3D, hạt, chuyển động camera đảo chiều, giữ hình lâu hơn 1s, bất cứ thứ gì trông như template.
</direction>

<structure>
130 BPM, 32 phách (14.8s). Bắt đầu bài nhạc 12 phách trước đoạn drop.

Phách 0-6, hỏi: đẩy chậm vào ô soạn tin đang phát sáng, zoom khoảng 3x. Gõ yêu cầu trên ba dòng cố định với nhịp gõ phím tự nhiên:
"I'm really hungry, I don't know
what I want but something
spicy, crispy and filling"

Phách 6, gửi: nhấn nút gửi. Một gợn sóng xanh chanh lan ra từ nút và biến tin nhắn thành bong bóng chat. Kéo lùi một lần để lộ chiếc điện thoại bao quanh (màn hình 428x900, viền đen 11px, thanh trạng thái 9:41).

Phách 6-12, suy nghĩ: nút gửi lớn lên thành một chiếc chảo wok màu cam, hình nửa đĩa với tay cầm mảnh. Nó tung 6 nguyên liệu nhiều màu ở các phách 8, 9, 10 và 11, bên dưới dòng chữ lấp lánh "Finding something for you…".

Phách 12, drop: một vòng tròn xanh chanh nở ra từ chảo wok lấp đầy khung hình trong khoảng 0.35s. Các thẻ đồ ăn tối màu (330x440, bo góc 28, ảnh ở trên, tên, mô tả một dòng, giá và đánh giá) bung ra từ tâm. Trượt dải thẻ qua ba thẻ và dừng ở "Fire Noodles", thẻ này nhấc lên kèm một pill "Best match".

Phách 16-21, chat: màu xanh chanh co lại vào bong bóng của người dùng, mang theo chữ của nó trong khi thẻ được chọn bay vào vị trí. "Found it. Fire Noodles from Wok & Fire, smoky, spicy and seriously filling." trồi lên, theo sau là "Want me to order it for you?" Rồi hiện hai pill: "Order now" màu đen và "More options" dạng viền. Con trỏ click Order now → spinner → "✓ Ordered".

Phách 21-32, kết: nút đen mở rộng thành trang, vẫn giữ dạng pill khi chạm tới mép trong khi camera đẩy vào nó. Nhãn của nó lớn lên cỡ tiêu đề rồi trượt đi. Đưa vào "You were craving noodles." và "Now it's on the way." từng chữ một (92px, trắng trên đen). Một chấm shipper đi theo lộ trình tới một ghim. Ghim trở thành logo thương hiệu, và wordmark được wipe ra từ phía sau nó, với "made with" ở trên và tên sản phẩm ở dưới.
</structure>

<build>
1. Một file HTML, 1920x1080. Tính mọi style từ thời gian bên trong seek(t): không CSS transition, không timer, không trạng thái mang từ khung hình này sang khung hình khác.
2. Dùng một transform camera duy nhất trên một container, đặt keyframe theo [time, zoom, x, y] với các đoạn có easing và nội suy zoom trong không gian log.
3. Dùng spring dạng đáp ứng bước closed-form cho mọi cú bật và ổn định.
4. Biến mọi lần chuyển giao thành phần tử dùng chung: lớp xanh chanh tràn ra mang theo một bản sao chữ của bong bóng, và nút mang nhãn của nó vào trang.
5. Âm thanh: dùng SFX Mixkit tải về cho từng sự kiện - gõ phím, tiếng bật khi gửi, mỗi lần tung, cú va ở drop, tiếng vút của thẻ, click, âm báo thành công, tiếng vụt khi lấp đầy trang và tiếng lấp lánh của logo. Đặt từng âm theo đỉnh đo được và loudnorm về -14 LUFS.
6. Render bằng Playwright ở 60fps với 8 subframe mỗi khung hình, trộn bằng ffmpeg tmix. Xem lại từng khoảnh khắc nhanh theo từng khung hình và rà toàn bộ video theo từng khung hình.
</build>
```

## Prompt gốc

```text
<inputs>
Ask me for: my product, the exact request a user types into it, 6 to 8 photos for the result cards, a royalty-free song around 130 BPM with a clear drop (Mixkit, free for commercial use), and my brand mark for the end card. If I skip anything, use the defaults: the food-ordering story below, food photos from Pexels (fire noodles, birria tacos, hot chicken, buffalo wings, smash burger, spicy ramen), and Mixkit "Cat Walk".
</inputs>

<direction>
A 15-second product launch film, 1920x1080 at 60fps. 2D only, one continuous take. No fades, blurs or cuts: each scene grows from the last. Text rises from a mask line, buttons expand into pages, and color floods from one object before shrinking into another. Give the camera one eased move per scene, and never zoom in and out consecutively.

Look: warm white canvas (#f5f5f2), black UI (#0e0e10), lime accent (#cdf24f), orange (#ff6a2a), and a blue send button (#2f6bff). Add an Apple Intelligence-style iridescent glow around the input: a blurred conic gradient rotating through pink, orange, lime, cyan and violet. Use real food photography on dark cards, Geist for UI and a serif for the product name on the end card.

Banned: crossfades, blur-ins, 3D, particles, camera moves that reverse direction, holds longer than 1s, anything that feels like a template.
</direction>

<structure>
130 BPM, 32 beats (14.8s). Start the song 12 beats before its drop.

Beats 0-6, ask: push slowly into the glowing composer, about 3x zoom. Type the request over three fixed lines with a natural keystroke rhythm:
"I'm really hungry, I don't know
what I want but something
spicy, crispy and filling"

Beat 6, send: press the send button. A lime ripple spreads from it and transforms the message into a chat bubble. Pull back once to reveal the phone around it (428x900 screen, 11px black bezel, 9:41 status bar).

Beats 6-12, think: the send button grows into an orange wok, a half-disc with a thin handle. It tosses 6 colorful ingredients on beats 8, 9, 10 and 11 beneath the shimmering text "Finding something for you…".

Beat 12, the drop: a lime circle expands from the wok to fill the frame in about 0.35s. Dark food cards (330x440, radius 28, photo on top, name, one-line description, price and rating) burst in from the center. Slide the strip across three cards and land on "Fire Noodles", which lifts with a "Best match" pill.

Beats 16-21, chat: the lime contracts back into the user's bubble, carrying its words as the chosen card flies into its slot. "Found it. Fire Noodles from Wok & Fire, smoky, spicy and seriously filling." rises in, followed by "Want me to order it for you?" Then show two pills: "Order now" in black and "More options" outlined. The cursor clicks Order now → spinner → "✓ Ordered".

Beats 21-32, outro: the black button expands into the page, staying pill-shaped as it reaches the edges while the camera pushes into it. Its label grows to headline size, then slides away. Bring in "You were craving noodles." and "Now it's on the way." word by word (92px, white on black). A courier dot follows a route to a pin. The pin becomes the brand mark, and the wordmark wipes out from behind it, with "made with" above and the product name below.
</structure>

<build>
1. One HTML file, 1920x1080. Compute every style from time inside seek(t): no CSS transitions, timers or state carried between frames.
2. Use one camera transform on a container, keyed by [time, zoom, x, y] with eased segments and zoom interpolated in log space.
3. Use closed-form step-response springs for every pop and settle.
4. Make every handoff a shared element: the lime flood carries a copy of the bubble's words, and the button carries its label into the page.
5. Sound: use a downloaded Mixkit SFX for each event - typing, send pop, each toss, drop impact, card swoosh, click, success tone, page-fill whoosh and mark sparkle. Place each by its measured peak and loudnorm to -14 LUFS.
6. Render with Playwright at 60fps using 8 subframes per frame, blended with ffmpeg tmix. Review every fast moment frame by frame and scan the full video frame by frame.
</build>
```
