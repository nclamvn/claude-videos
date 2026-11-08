# Video Opus 5.5 của @twoclipping

[▶ Xem bản gốc và bản làm lại trực tiếp trên Skillry](https://skillry.dev/ai-videos/opus-5-5/twoclipping-496100?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos) · [Bài đăng gốc](https://x.com/twoclipping/status/2103835273813496100)

- **Danh mục:** Cảnh 3D
- **Bản làm lại dùng:** Canvas
- **Tác giả:** [@twoclipping](https://x.com/twoclipping)

Trang gốc (chưa dịch): [prompts/twoclipping-496100.md](../prompts/twoclipping-496100.md)

## Prompt (tiếng Việt)

```text
<inputs>
Hãy hỏi tôi: một tên thương hiệu một từ cho wordmark (động từ là tốt nhất), 9 đến 12 ảnh độ phân giải cao, một bài nhạc miễn phí bản quyền khoảng 120 BPM có một đoạn drop và một đoạn breakdown yên ắng (Mixkit, miễn phí cho mục đích thương mại), và một clip stock miễn phí quay một bức tường trơn có bóng cây chuyển động (Pexels).
</inputs>

<direction>
Một phim ra mắt kiểu keynote của Apple, chỉ 2D, một cú máy liền mạch. Mỗi cảnh được tạo ra từ chính cảnh trước: không có gì mờ dần, nhòe hay cắt. Thay vào đó, các vật thể đổi hình dạng: chữ trồi lên từ một đường mask, icon bật ra từ 0 theo lò xo, các thanh vẽ ngang qua, các trang đẩy nhau, và một khối đen tràn kín cả khung hình rồi co lại thành cảnh tiếp theo. Canvas màu trắng ngà ấm, UI màu đen, liquid glass của iOS 26 phủ trên ảnh. Archivo (wdth 125, weight 800) cho wordmark, Geist cho UI. Một con trỏ điều khiển mọi thay đổi bằng các cú click, kéo và nhấn giữ thật. Camera zoom theo kiểu Screen Studio để mỗi khoảnh khắc lấp đầy khung vuông, và con trỏ phóng to thu nhỏ theo.
Cấm: crossfade, hiện dần từ nhòe, hiệu ứng độ sáng kiểu "rửa ảnh", lật 3D, hạt, glow, giữ hình lâu hơn 1s, bất cứ thứ gì trông như template.
</direction>

<structure>
120 BPM, 54 nhịp, nhịp nào cũng có chuyện xảy ra.
Mở đầu: wordmark co ép vào chính dấu chấm của nó như đàn accordion, dấu chấm phình thành một viên thuốc màu đen, một nhãn trồi lên bên trong. Click: sáu lá khẩu đóng lại trên nhãn rồi bật mở ra một tấm ảnh. Hình tròn thành hình vuông, thu nhỏ lại, lưới ảnh mở ra từ phía sau nó như một tấm bản đồ giấy (giữa, dấu cộng, các góc), sắp xếp lại thành bento, và một cú click zoom vào một ô, đáp đúng vào đoạn drop.
Glass: một chữ bằng kính bật ra từng chữ cái, tan chảy thành một giọt nước rồi kéo dài thành một thanh công cụ bằng kính. Icon chỉnh ảnh biến nó thành một thanh trượt. Kéo thanh trượt sẽ đổi ánh sáng của ảnh từ ban ngày sang giờ vàng (hai ảnh chụp thẳng hàng nhau), và núm kéo biến thành một thấu kính bằng kính trong lúc được giữ. Nó nhấc lên thành một quả cầu kính, ảnh tiếp theo mở ra bên trong nó dưới dạng hình tròn, và quả cầu nở ra thành màn hình khóa: chữ số đồng hồ bằng kính, ngày tháng, và một thanh home kéo dài thành một trình phát nhạc bằng kính.
Stage: màn hình khóa lùi ra thành một chiếc điện thoại (viền máy mọc ra từ mép màn hình). Dynamic Island kéo giãn như chất lỏng, thắt lại tách ra, bay qua và lớn dần thành một cửa sổ Mac cuộn lên như rèm. Nhấn giữ hình nền, kéo nó vào một tab Safari, trang đẩy vào, thả xuống và nó trở thành hero của một landing page. Cuộn: hero biến thành một bức ảnh in đóng khung trên thẻ sản phẩm, với lớp passe-partout và nẹp khung mọc ra từ mép ảnh. Chọn màu khung (màu quét sơn lan ra) và kích thước, rồi nút điều hướng bay xuống thành "Order print".
Order: một khối đen duy nhất liên tục biến hình: Ordered ✓ → Printing % → On its way (một chiếc xe van chạy trên lộ trình) → Delivered ✓.
Wall: hình tròn "đã giao" tràn kín khung hình từ mép này sang mép kia, giữ màu đen trong một nhịp, rồi co lại thành bức ảnh đóng khung treo trên footage bức tường thật. Cùng bộ khẩu đó mở ra trên bức ảnh, lại đóng vào, khung ảnh tràn kín màn hình rồi co lại thành viên thuốc → dấu chấm → các chữ cái bật ngược ra, đáp đúng lúc nhịp quay lại. Khung hình cuối = khung hình đầu.
</structure>

<build>
1. Một file HTML, khung vuông 1440x1440. Mọi style được tính từ thời gian bên trong một hàm async seek(t): không CSS transition, không timer, không trạng thái nào giữa các khung hình.
2. Lò xo là đáp ứng bước dạng nghiệm đóng. Một giá trị có nhiều đích là tổng của một lò xo cho mỗi lần thay đổi, nhờ vậy nó vẫn là hàm thuần của thời gian.
3. Liquid glass: mỗi phần tử kính giữ một bản sao riêng của cảnh phía sau nó, lọc bằng displacement map qua SVG feImage (một trường khoảng cách hình chữ nhật bo góc) qua ba feDisplacementMap ở các tỉ lệ hơi khác nhau để tạo viền tán sắc, cộng thêm một ánh sáng viền. Chữ bằng kính: một trường khoảng cách vẽ bằng canvas cho mỗi glyph cung cấp map, mask và highlight.
4. Goo: blur + ngưỡng alpha, rồi composite nguồn lên trên để kính vẫn sắc nét ở bên trong.
5. Khẩu: 6 lá quanh một lỗ khẩu lục giác. Mỗi lá gồm hai đỉnh của nó, cả hai phần kéo dài cạnh và cung NGẮN giữa chúng.
6. Wordmark co ép: mọi chữ cái dịch về phía dấu chấm theo cùng một hệ số và độ rộng vẽ của nó cũng theo đó (thu hẹp trục wdth, scale phần còn lại), để các chữ cái luôn chạm nhau.
7. Footage: encode lại toàn bộ intra (ffmpeg -g 1), nạp dưới dạng blob URL, await 'seeked' trước khi vẽ mỗi khung hình.
8. Âm thanh: một SFX tải về cho mỗi sự kiện (Mixkit), không bao giờ tự tổng hợp, mỗi cái đặt theo đỉnh đã đo của nó. Bài nhạc bắt đầu trên một phách mạnh: cú zoom đáp vào đoạn drop, bức tường nằm trong đoạn breakdown, wordmark quay lại cùng nhịp. Loudnorm về -14 LUFS.
9. Render bằng Playwright: 4 khung phụ mỗi khung hình, trộn bằng ffmpeg tmix, 60fps. Kiểm một khung hình mỗi nhịp, rồi quét tìm các cú giật một khung (đỉnh chênh lệch khung hình gấp 3 lần các khung lân cận).
</build>

<gotchas>
backdrop-filter: url() đọc sai displacement map trong Chromium, nên hãy clone cảnh thay vì dùng nó. Một cú tràn phải phóng quá các góc và mất khoảng 0.3s, nếu không nửa màn hình sẽ đổi chỉ trong một khung hình. Một phần tử con có visibility: visible vẫn hiện xuyên qua phần tử cha bị ẩn, nên hãy dùng inherit. Chữ đổi bên trong một hình đang biến hình cần mask riêng của nó. python http.server không seek theo range được với video, nên hãy dùng blob URL.
</gotchas>

<start>
Hãy hỏi tôi các đầu vào, rồi cho tôi xem beat map và 4 ảnh tĩnh (open, glass, stage, wall) trước khi bạn viết toàn bộ phim.
</start>
```

## Prompt gốc

```text
<inputs>
Ask me for: a one-word brand name for the wordmark (a verb works best), 9 to 12 high-res photos, a royalty-free song around 120 BPM with a drop and a quiet breakdown (Mixkit, free for commercial use), and a free stock clip of a plain wall with moving plant shadows (Pexels).
</inputs>

<direction>
An Apple-keynote launch film, 2D only, one continuous take. Every scene is made out of the previous one: nothing fades, blurs or cuts. Objects change shape instead: text rises out of a mask line, icons pop from zero on a spring, bars draw across, pages push, and a black shape floods the whole frame and contracts into the next scene. Warm off-white canvas, black UI, iOS 26 liquid glass over the photos. Archivo (wdth 125, weight 800) for the wordmark, Geist for UI. A cursor drives every change with real clicks, drags and long-presses. The camera zooms screen-studio style so each moment fills the square, and the cursor scales with it.
Banned: crossfades, blur-ins, brightness "developing", 3D flips, particles, glows, holds longer than 1s, anything that looks like a template.
</direction>

<structure>
120 BPM, 54 beats, something happens on every beat.
Open: the wordmark squeezes into its own period like an accordion, the dot grows into a black pill, a label rises inside it. Click: six iris blades close over the label and snap open onto a photo. The circle becomes a square, shrinks, the grid unfolds from behind it like a paper map (center, plus, corners), reflows into a bento, and a click zooms into one tile, landing exactly on the drop.
Glass: a glass word pops in letter by letter, melts into a droplet that stretches into a glass toolbar. The adjust icon turns it into a slider. Dragging relights the photo from day to golden hour (two aligned shots), and the knob turns into a glass lens while held. It lifts into a glass orb, the next photo opens inside it as a circle, and the orb expands into a lock screen: glass clock digits, date, and a home bar that stretches into a glass music player.
Stage: the lock screen pulls back into a phone (the bezel grows out of the screen edge). The Dynamic Island stretches like liquid, pinches off, flies over and grows into a Mac window that rolls up like a blind. Long-press the wallpaper, drag it onto a Safari tab, the page pushes in, drop it and it becomes the hero of a landing page. Scroll: the hero morphs into a framed print on a product card, with the mat and molding growing out of the photo's edge. Pick a frame color (it paints across) and a size, then the nav button flies down into "Order print".
Order: one black shape keeps morphing: Ordered ✓ → Printing % → On its way (a van on a route) → Delivered ✓.
Wall: the delivered circle floods the frame edge to edge, holds black for a beat, and contracts into the framed print hanging on the real wall footage. The same iris opens onto the print, closes again, the frame floods the screen and contracts into the pill → the dot → the letters spring back out, landing on the beat return. Last frame = first frame.
</structure>

<build>
1. One HTML file, square 1440x1440. Every style is computed from time inside an async seek(t): no CSS transitions, no timers, no state between frames.
2. Springs are closed-form step responses. A value with many targets is the sum of one spring per change, so it stays a pure function of time.
3. Liquid glass: each glass element holds its own clone of the scene behind it, filtered with an SVG feImage displacement map (a rounded-rect distance field) through three feDisplacementMaps at slightly different scales for chromatic edges, plus a rim light. Glass letters: a canvas distance field per glyph gives the map, mask and highlights.
4. Goo: blur + alpha threshold, then composite the source atop it so the glass stays sharp inside.
5. Iris: 6 blades around a hexagonal aperture. Each blade is its two vertices, both edge extensions and the SHORT arc between them.
6. Wordmark squeeze: every letter moves toward the dot by the same factor and its drawn width follows (narrow the wdth axis, scale the rest), so the letters stay touching.
7. Footage: re-encode all-intra (ffmpeg -g 1), load it as a blob URL, await 'seeked' before drawing each frame.
8. Sound: a downloaded SFX for every event (Mixkit), never synthesized, each placed by its measured peak. The song starts on a downbeat: the zoom lands on the drop, the wall sits in the breakdown, the wordmark returns with the beat. Loudnorm to -14 LUFS.
9. Render with Playwright: 4 subframes per frame blended with ffmpeg tmix, 60fps. Check one frame per beat, then scan for single-frame pops (frame-difference spikes 3x their neighbours).
</build>

<gotchas>
backdrop-filter: url() misreads displacement maps in Chromium, so clone the scene instead. A flood must overscale past the corners and take about 0.3s, or half the screen changes in one frame. A child with visibility: visible shows through a hidden parent, so use inherit. Text that swaps inside a morphing shape needs its own mask. python http.server can't range-seek video, so use the blob URL.
</gotchas>

<start>
Ask me for the inputs, then show me the beat map and 4 stills (open, glass, stage, wall) before you write the full film.
</start>
```
