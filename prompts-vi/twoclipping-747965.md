# Video ra mắt sản phẩm Nightshift

_Nightshift Product Launch Video_

Video Opus 5.5 của [@twoclipping](https://x.com/twoclipping) · [Bài đăng gốc kèm video](https://x.com/twoclipping/status/2105927781678747965)

- **Danh mục:** Motion graphics
- **Tác giả:** [@twoclipping](https://x.com/twoclipping)

Thêm video Opus 5.5, mỗi video kèm bản làm lại trực tiếp: [skillry.dev/ai-videos/opus-5-5](https://skillry.dev/ai-videos/opus-5-5?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos)

Trang gốc (chưa dịch): [prompts/twoclipping-747965.md](../prompts/twoclipping-747965.md)

## Prompt (tiếng Việt)

```text
<inputs>
Hãy hỏi tôi: tên sản phẩm của tôi (nightshift) (một từ viết thường, nó sẽ thành wordmark màu đen kèm dấu chấm), một việc duy nhất người dùng giao cho nó trước khi đi ngủ (book 10 sales calls this week), ba kết quả nó báo cáo vào buổi sáng (200 leads found / 200 emails sent / 10 calls booked), hai bức ảnh chụp cùng một địa điểm vào ban đêm và ban ngày (căn khớp, để một crossfade trông như bình minh thật), một bức ảnh ban ngày nắng đẹp cho phần bên ngoài logo, và một bài hát có cú hit lớn gần phần mở đầu. Nếu tôi bỏ qua mục nào, hãy dùng giá trị mặc định.
</inputs>

<direction>
Một video ra mắt sản phẩm hình vuông dài 24 giây, 1440x1440 ở 60fps, chỉ 2D, một cú máy liên tục và lặp lại. Toàn bộ video diễn ra bên trong dấu chấm của wordmark. Bên ngoài là ban ngày (bức ảnh nắng phía sau wordmark màu đen). Bên trong là bức ảnh ban đêm dưới các tấm kính kiểu iOS (ảnh làm mờ phía sau mỗi tấm, một lớp phủ màu, một viền sáng). Không có gì bị cắt: mỗi cảnh mọc ra từ cảnh trước, các hình biến hình, các chấm bay, màu thay đổi dưới các đợt tràn màu. Mỗi lần biến hình trượt trong 0.8s theo cubic-bezier(.45,0,.15,1) và zoom camera đi theo cùng đường cong đó. Font Geist, con trỏ macOS thật, bóng đổ mềm lớn dần theo độ cao của từng hình.
Cấm: nền phẳng hoặc gradient tạo bằng code, zoom camera vào các điểm nhỏ xíu, cắt cứng, crossfade giữa các cảnh, spring nảy, hạt, glow, giữ hình lâu hơn 1s, chữ bị cắt xén.
</direction>

<structure>
Các nhịp là nhịp của bài hát. Bài hát vào bằng cú hit lớn đúng lúc viên pill đầu tiên xuất hiện.
Mở đầu: các chữ cái trượt vào dấu chấm và biến mất vào trong đó trong khi dấu chấm trượt ra giữa. Dấu chấm mở ra như mống mắt máy ảnh (iris) để lộ màn đêm bên trong, và "you log off at 6", rồi "[product] doesn't", lăn qua một dòng mask trên bức ảnh ban đêm.
Hỏi: một viên pill kính "Ask [product]" bật vào. Con trỏ click vào nó, nó trượt thành một ô nhập và việc cần làm được gõ ra.
Tìm: nút gửi thu ô nhập thành một chấm, chấm gợn sóng lan thành lưới 23x15. Một vạch quét lướt qua, 200 chấm sáng lên và một bộ đếm đếm chúng.
Viết: các chấm đã sáng đổ vào một khung soạn email bằng kính. Một con trỏ thứ hai màu tím có nhãn "[product]" gõ một câu mở đầu cá nhân hoá và nhấn Send, và bộ đếm chạy tới 200/200.
Đêm: khung soạn thảo biến thành một quả cầu kính có vòng tiến độ. Một chip đồng hồ đổi lần lượt 11:42 PM, 3:17 AM, 5:02 AM, 6:59 AM trong khi bầu trời sáng dần từ đêm sang bình minh và "while you sleep" lăn vào.
Kết quả (nhịp 20): quả cầu chuyển sang đen và tách kiểu goo thành ba viên pill kết quả. Các dấu tích bật lên màu xanh lá.
Buổi sáng: các viên pill hợp lại thành một Dynamic Island rồi lớn dần thành màn hình khoá điện thoại: bức ảnh ban ngày, ngày tháng, số 7:00 cỡ lớn, viền máy mọc ra từ mép màn hình. Ba thông báo bằng kính xếp chồng vào, và con trỏ chạm vào thông báo đầu tiên, nó mở ra như trên iOS.
Bằng chứng: một lịch tuần (10 cuộc họp bật vào, di chuột qua hiện giờ của một cuộc), rồi một biểu đồ pipeline ($48,200 đếm tăng lên, đường biểu đồ được vẽ, phần hover chạy theo nó). Một đợt tràn màu đen từ cuối đường biểu đồ trở thành "Start your night shift →" và con trỏ click vào đó.
Kết thúc: nút thu nhỏ thành một chấm, toàn bộ cảnh khép lại vào chấm đó như iris, và các chữ cái trượt ngược ra khỏi dấu chấm. Tagline nổi lên. Khung hình cuối = khung hình đầu.
</structure>

<build>
1. Một canvas HTML. Mọi thứ là hàm thuần của thời gian bên trong seek(t): không timer, không state giữa các khung hình.
2. Một phần tử duy nhất biến hình qua mọi trạng thái (kích thước, bo góc, màu, chất liệu) theo một bảng thời điểm nhịp, để chỉnh lại thời gian chỉ cần sửa một chỗ.
3. Render thế giới bên trong vào một canvas offscreen và để lộ nó qua dấu chấm bằng mask hình tròn. Không bao giờ zoom camera vào chấm.
4. Kính: một bản sao đã làm mờ sẵn của bức ảnh được clip theo hình, rồi một lớp phủ màu và một viền gradient.
5. Goo: blur + ngưỡng alpha trên một lớp offscreen cho lúc tách và lúc hợp.
6. Âm thanh: một SFX tải về cho mỗi sự kiện, mỗi cái được đặt theo đỉnh đo được của nó. Bài hát vào bằng cú hit. Loudnorm về -14 LUFS.
7. Render bằng Playwright ở 60fps với 4 subframe motion blur. Quét mọi khung hình để tìm những cú nhảy chỉ một khung hình và sửa từng cái.
</build>

<gotchas>
Zoom camera vào một chấm lệch tâm sẽ văng ngang và giật vọt, nên hãy mở chấm ra thay vì zoom. Easing cho iris đang khép phải tính theo diện tích, không theo bán kính, nếu không các khung hình đầu sẽ giật. Hàm phụ nào đặt globalAlpha phải khôi phục giá trị của nơi gọi, nếu không các thẻ đang mờ dần sẽ bị bụp. Bộ đếm phải đọc thời gian của khung hình, không phải của subframe, nếu không các chữ số sẽ bị nhoè.
</gotchas>

<start>
Hãy hỏi tôi các đầu vào, rồi cho tôi xem bản đồ nhịp và 6 ảnh tĩnh (open, find, write, results, phone, out) trước khi bạn render.
</start>
```

## Prompt gốc

```text
<inputs>
Ask me for: my product's name (nightshift) (one lowercase word, it becomes a black wordmark with a period), the one job a user hands it before bed (book 10 sales calls this week), the three results it reports by morning (200 leads found / 200 emails sent / 10 calls booked), two photos of the same place at night and by day (aligned, so a crossfade reads as a real sunrise), one sunny daytime photo for outside the logo, and a song with a big hit near its start. If I skip any, use the defaults.
</inputs>

<direction>
A 24 second square product launch video, 1440x1440 at 60fps, 2D only, one continuous take that loops. The whole video happens inside the period of the wordmark. Outside it's daytime (the sunny photo behind a black wordmark). Inside it's the night photo under iOS-style glass panels (the blurred photo behind each panel, a tint, a rim light). Nothing cuts: every scene grows out of the last, shapes morph, dots fly, colours change under floods. Every morph glides 0.8s on cubic-bezier(.45,0,.15,1) and the camera zoom rides the same curve. Geist, the real macOS pointer, soft shadows that grow with each shape's height.
Banned: flat or gradient backgrounds made in code, camera zooms into tiny points, hard cuts, crossfades between scenes, bouncy springs, particles, glows, holds longer than 1s, cropped type.
</direction>

<structure>
Beats are the song's. The song enters on its big hit as the first pill appears.
Open: the letters slide into the period and vanish into it while it glides to the middle. The period opens like an iris onto the night inside it, and "you log off at 6", then "[product] doesn't", roll through one mask line over the night photo.
Ask: a glass "Ask [product]" pill springs in. The cursor clicks it, it glides into an input and the job types out.
Find: send shrinks the input to a dot that ripples into a 23x15 grid. A scan line sweeps it, 200 dots light up and a counter counts them.
Write: the lit dots pour into a glass email composer. A second, purple cursor labelled "[product]" types a personal opener and presses Send, and the counter runs to 200/200.
Night: the composer becomes a glass orb with a progress ring. A clock chip swaps 11:42 PM, 3:17 AM, 5:02 AM, 6:59 AM while the sky relights from night to dawn and "while you sleep" rolls in.
Results (beat 20): the orb turns black and goo-splits into the three result pills. The checks pop green.
Morning: the pills merge into a Dynamic Island that grows into a phone lock screen: the day photo, the date, a big 7:00, the bezel growing out of the screen edge. Three glass notifications stack in, and the cursor taps the first, which opens like iOS.
Proof: a week calendar (10 meetings pop in, a hover shows one's time), then a pipeline chart ($48,200 counts up, the line draws, a hover follows it). A black flood from the line's end becomes "Start your night shift →" and the cursor clicks it.
Out: the button shrinks into a dot, the whole scene closes down into it like an iris, and the letters slide back out of the period. The tagline rises. Last frame = first frame.
</structure>

<build>
1. One HTML canvas. Everything is a pure function of time inside seek(t): no timers, no state between frames.
2. One element morphs through every state (size, radius, colour, material) from a table of beat times, so retiming is one edit.
3. Render the inside world into an offscreen canvas and reveal it through the period with a circular mask. Never zoom the camera into the dot.
4. Glass: a pre-blurred copy of the photo clipped to the shape, then a tint and a gradient rim.
5. Goo: blur + alpha threshold on an offscreen layer for the split and the merge.
6. Sound: a downloaded SFX for every event, each placed by its measured peak. The song enters on its hit. Loudnorm to -14 LUFS.
7. Render with Playwright at 60fps with 4 motion-blur subframes. Scan every frame for single-frame jumps and fix each one.
</build>

<gotchas>
A camera zoom into an off-centre dot swings sideways and spikes, so open the dot instead. Ease a closing iris by area, not radius, or its first frames jump. A helper that sets globalAlpha must restore the caller's, or fading cards pop. Counters read the frame's time, not the subframe's, or the digits smear.
</gotchas>

<start>
Ask me for the inputs, then show me the beat map and 6 stills (open, find, write, results, phone, out) before you render.
</start>
```
