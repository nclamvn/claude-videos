# Tạo trailer ra mắt

_Launch Trailer Video Generation_

Video Opus 5.5 của [@twoclipping](https://x.com/twoclipping) · [Bài đăng gốc kèm video](https://x.com/twoclipping/status/2106101258834551116)

- **Danh mục:** Motion graphics
- **Tác giả:** [@twoclipping](https://x.com/twoclipping)

Thêm video Opus 5.5, mỗi video kèm bản làm lại trực tiếp: [skillry.dev/ai-videos/opus-5-5](https://skillry.dev/ai-videos/opus-5-5?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos)

Trang gốc (chưa dịch): [prompts/twoclipping-551116.md](../prompts/twoclipping-551116.md)

## Prompt (tiếng Việt)

```text
<inputs>
Hãy hỏi tôi: tên sản phẩm của tôi (một từ viết thường), một tagline 4 từ, câu chuyện 3 bước về những gì sản phẩm làm, ngày ra mắt và tên miền, một bài nhạc miễn phí bản quyền có đoạn drop rõ ràng, 4 clip dọc nói chuyện trước camera và 12 ảnh chân dung khổ dọc. Nếu tôi bỏ qua mục nào, dùng mặc định: "castr", "ugc ads, cast by ai", write a brief → scan 1,000 creators → cast 4, bài "Cat Walk" của Mixkit (129.6 BPM, drop ở 29.7s), clip và ảnh chân dung miễn phí từ Pexels, và sticker nền trong suốt từ Pixabay (serum, micro, loa phóng thanh, máy ảnh cổ, đèn spotlight, đôi môi).
</inputs>

<direction>
Một trailer ra mắt khổ vuông dài 25 giây, 1440x1440 ở 60fps, phong cách poster rực rỡ. Cobalt #2B3BFF, mực #0E0F1F, kem #F6E4C6, hồng #FF7DC7, cam quýt #FF5A1F. Archivo 900 extra-condensed cho tên, expanded cho tiêu đề, Geist và Geist Mono cho nhãn. Hoạ tiết op-art tia mặt trời, sóng cuộn, film grain. Chỉ dùng media thật: các clip phát bên trong thiết kế, sticker có viền die-cut trắng và bóng đổ mềm.
Quy tắc chuyển động: camera không bao giờ đứng yên (một cú đẩy chậm 1.03-1.07 ở mọi cảnh), không có gì bật ra đột ngột (chữ cái lần lượt nhô lên qua một đường mask), không có gì giật theo nhịp (hoạ tiết xoay liên tục), các lần hoán đổi là cú lướt kiểu carousel khoảng 0.55s, đổi màu thì fade trong khoảng 0.35s, sticker ease vào rồi giữ một nhịp đung đưa chậm. Không đặt dấu chấm sau wordmark hay bất kỳ tiêu đề nào.
Cấm: xoay giật theo nhịp, nện bật ra đột ngột, chớp trắng, crossfade giữa các cảnh, cắt cứng, template.
</direction>

<structure>
54 nhịp. Bài nhạc bắt đầu 8 nhịp trước đoạn drop.
Nhịp 0-8: một hình tia mặt trời màu cobalt xoay quanh một đĩa màu kem đang "thở". Wordmark được gõ vào cùng một con trỏ nhập lướt đi, và viên thuốc tagline nhô lên. Chiếc đĩa tràn ngập khung hình để đi vào đoạn drop.
Nhịp 8, đoạn drop: màu kem trở thành một mặt của hộp 3D và "ONE BRIEF" nhô lên từng chữ cái. Camera lùi ra để thấy chiếc hộp lơ lửng trên sóng. Ở nhịp 12 hộp xoay sang "1,000 CREATORS" (xếp chồng, có các tiếng vọng dạng viền), ở nhịp 14 sang "ZERO DMs".
Nhịp 16-22: một cú whip sang một chiếc bàn tối. Một tấm vé màu cam quýt "BRIEF #042" gõ ra các dòng của nó (product, vibe, cast, due), sticker trôi vào, một tấm polaroid từ một clip thật rơi xuống góc, và con dấu "NOW CASTING" ấn xuống ở nhịp 20.
Nhịp 22-34: sân khấu casting. Một đám đông ảnh chân dung đen trắng xếp thành hình vòng cung, một khối sân khấu 3D, và các creator lướt qua như một carousel. Mỗi người phát trực tiếp trong một đĩa lớn đen trắng, với tên màu hồng trên sân khấu, số follower, và MATCH % đếm tăng dần. Một nhịp sau, con dấu "CAST ✓" đáp xuống và clip chuyển dần sang có màu. Một bộ đếm cuộn từ 1/4 đến 4/4.
Nhịp 34-39: màu hồng tràn ra từ chiếc đĩa cuối cùng. Chiếc đĩa morph thành màn hình điện thoại (clip vẫn tiếp tục phát) rồi xoè thành 4 điện thoại phát cả 4 creator, với lượt xem đếm tăng dần. "4 ADS" và "BY FRIDAY" nhô lên.
Nhịp 39-44, đoạn break của nhạc: sàn hồng sụt đi và một tấm vé màu kem "JOIN THE WAITLIST" lướt xuống trên hình tia mặt trời. Ở nhịp pickup, cuống vé bị xé rời.
Nhịp 44-54: thân vé morph thành một vòm poster. Wordmark nhô lên, rồi tới tagline, rồi một thanh thông tin trượt lên thành 3 khối (ngày, con số, tên miền) và một dải chữ chạy vòng quanh mép khung hình. Sau đó tất cả gập lại về chiếc đĩa mở đầu, để khung hình cuối chính là khung hình đầu.
</structure>

<build>
1. Một canvas HTML. Mọi khung hình là một hàm thuần của thời gian bên trong seek(t).
2. Một bản đồ nhịp tính theo nhịp, B = 60/BPM, với bài nhạc được đặt sao cho drop rơi đúng nhịp 8.
3. Hộp 3D là một phép chiếu orthographic: mỗi mặt là một offscreen canvas 1440px vẽ bằng phép biến đổi affine và đổ bóng theo pháp tuyến.
4. Cắt clip thành chuỗi JPEG 30fps bằng ffmpeg, vẽ khung hình floor(t*30), và làm đen trắng bằng ctx.filter.
5. Trim các PNG sticker và thêm viền die-cut bằng cách giãn (dilate) kênh alpha của chúng.
6. Âm thanh: một SFX tải về cho mỗi sự kiện (tiếng màn trập ở mỗi lần cast, tiếng whoosh ở các cú lướt, tiếng gõ phím khi đánh chữ), mỗi cái được đặt theo đỉnh đo được của nó. Loudnorm về -14 LUFS.
7. Render bằng Playwright ở 60fps với 8 subframe motion blur. Quét tìm các chỗ bật ra trong một khung hình, rồi so sánh chuyển động với một video tham chiếu (số cú nhảy cứng mỗi giây, tỉ lệ khung hình đứng yên).
</build>

<gotchas>
Một hoạ tiết xoay từng nấc mỗi nhịp sẽ trông như bị giật: hãy xoay liên tục, và chọn tốc độ từng vòng sao cho nó về đúng cùng hoạ tiết ở khung hình cuối. 4 subframe sẽ bị bóng ma ở các cú whip nhanh, nên dùng 8. Một layer có nền là một hình tròn tràn khổng lồ vẫn che kín màn hình sau khi trượt xuống một chiều cao khung hình, nên hãy đổi nó thành một hình chữ nhật full khung một khi nó đã tràn đầy. Các bộ đếm đọc thời gian của khung hình, không phải của subframe. Chiếc đĩa phải morph bên trong cùng phép biến đổi camera với cảnh mà nó rời khỏi, nếu không nó sẽ bị nhảy.
</gotchas>

<start>
Hãy hỏi tôi các đầu vào, rồi cho tôi xem bản đồ nhịp và 6 ảnh tĩnh (mở đầu, hộp, brief, casting, điện thoại, poster) trước khi bạn render.
</start>
```

## Prompt gốc

```text
<inputs>
Ask me for: my product's name (one lowercase word), a 4-word tagline, the 3-step story of what it does, a launch date and domain, a royalty-free song with a clear drop, 4 vertical talking-to-camera clips and 12 portrait photos. If I skip any, use the defaults: "castr", "ugc ads, cast by ai", write a brief → scan 1,000 creators → cast 4, Mixkit "Cat Walk" (129.6 BPM, drop at 29.7s), free Pexels clips and portraits, and transparent stickers from Pixabay (serum, mic, megaphone, vintage camera, spotlight, lips).
</inputs>

<direction>
A 25 second square launch trailer, 1440x1440 at 60fps, loud poster style. Cobalt #2B3BFF, ink #0E0F1F, cream #F6E4C6, pink #FF7DC7, tangerine #FF5A1F. Archivo 900 extra-condensed for names, expanded for headlines, Geist and Geist Mono for labels. Op-art sunburst, scrolling waves, film grain. Real media only: the clips play inside the design, and the stickers get a white die-cut border and a soft shadow.
Motion rules: the camera never stops (a slow 1.03-1.07 push on every scene), nothing pops in (letters rise through a mask line one by one), nothing snaps to the beat (patterns rotate continuously), swaps are carousel glides of about 0.55s, colour changes fade over about 0.35s, stickers ease in and then keep a slow sway. No full stops after the wordmark or any headline.
Banned: beat-snapped rotations, pop-in slams, white flashes, crossfades between scenes, hard cuts, templates.
</direction>

<structure>
54 beats. The song starts 8 beats before its drop.
Beats 0-8: a cobalt sunburst turns around a breathing cream disc. The wordmark types in with a gliding caret and the tagline pill rises. The disc floods the frame into the drop.
Beat 8, the drop: the cream becomes the face of a 3D box and "ONE BRIEF" rises letter by letter. The camera pulls back to the box floating on waves. On beat 12 it turns to "1,000 CREATORS" (stacked, with outlined echoes), on beat 14 to "ZERO DMs".
Beats 16-22: a whip to a dark desk. A tangerine "BRIEF #042" ticket types its rows (product, vibe, cast, due), stickers drift on, a polaroid of a real clip drops onto the corner, and a "NOW CASTING" stamp presses down on beat 20.
Beats 22-34: the casting stage. A crowd of black and white portraits in an arc, a 3D stage block, and the creators gliding through like a carousel. Each plays live in a big disc in black and white, with their name in pink on the stage, their followers, and a MATCH % that counts up. One beat later a "CAST ✓" stamp lands and the clip fades to colour. A counter rolls 1/4 to 4/4.
Beats 34-39: pink floods out of the last disc. The disc morphs into a phone screen (the clip keeps playing) and fans into 4 phones playing all 4 creators, with views counting up. "4 ADS" and "BY FRIDAY" rise.
Beats 39-44, the music's break: the pink floor drops away and a cream "JOIN THE WAITLIST" ticket glides down onto the sunburst. On the pickup its stub tears off.
Beats 44-54: the ticket body morphs into a poster arch. The wordmark rises in, then the tagline, then an info bar slides up in 3 blocks (date, numbers, domain) and a ticker runs round the frame edge. Then it all folds back into the opening disc, so the last frame is the first.
</structure>

<build>
1. One HTML canvas. Every frame is a pure function of time inside seek(t).
2. A beat map in beats, B = 60/BPM, with the song placed so its drop lands on beat 8.
3. The 3D box is an orthographic projection: each face is a 1440px offscreen canvas drawn with an affine transform and shaded by its normal.
4. Cut the clips to 30fps JPEG sequences with ffmpeg, draw frame floor(t*30), and do the black and white with ctx.filter.
5. Trim the sticker PNGs and add the die-cut border by dilating their alpha.
6. Sound: a downloaded SFX for every event (a shutter on every cast, whooshes on the glides, key clicks on the typing), each placed by its measured peak. Loudnorm to -14 LUFS.
7. Render with Playwright at 60fps with 8 motion-blur subframes. Scan for single-frame pops, then compare its motion against a reference video (hard jumps per second, share of still frames).
</build>

<gotchas>
A pattern that rotates one notch per beat reads as stutter: rotate it continuously, and pick each ring's speed so it lands on the same pattern at the last frame. 4 subframes ghost on fast whips, so use 8. A layer whose background is a huge flood circle still covers the screen after sliding down one frame height, so switch it to a full-frame rect once it has flooded. Counters read the frame's time, not the subframe's. The disc must morph inside the same camera transform as the scene it leaves, or it jumps.
</gotchas>

<start>
Ask me for the inputs, then show me the beat map and 6 stills (open, box, brief, casting, phones, poster) before you render.
</start>
```
