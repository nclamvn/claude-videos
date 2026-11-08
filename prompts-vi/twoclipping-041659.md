# Phim pixel art có lồng tiếng

_Pixel Art Voiceover Film_

Video Opus 5.5 của [@twoclipping](https://x.com/twoclipping) · [Bài đăng gốc kèm video](https://x.com/twoclipping/status/2107822293653041659)

- **Danh mục:** Game & tương tác
- **Tác giả:** [@twoclipping](https://x.com/twoclipping)

Thêm video Opus 5.5, mỗi video kèm bản làm lại trực tiếp: [skillry.dev/ai-videos/opus-5-5](https://skillry.dev/ai-videos/opus-5-5?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos)

Trang gốc (chưa dịch): [prompts/twoclipping-041659.md](../prompts/twoclipping-041659.md)

## Prompt (tiếng Việt)

```text
<inputs>
Hãy hỏi tôi: một đoạn lồng tiếng hoặc bài hát có một câu nói (file âm thanh) kèm bản transcript, 10-12 đồ vật nhỏ tóm gọn cuộc đời tôi, hai hình bóng (silhouette) để chiếu sáng như camera nhiệt (một cái đầu nhìn nghiêng và một bàn tay giơ lên), và 3 từ tôi muốn nhấn mạnh nhất. Nếu tôi bỏ qua mục nào, hãy dùng mặc định: đĩa vinyl, sách, máy ảnh, mèo, đồng xu, tay cầm chơi game, mũ lưỡi trai, trái tim, tiền, cây cảnh, bảng clapper, ván trượt; hình bóng CC0 miễn phí từ Openverse; action, intention, curiosity.
</inputs>

<direction>
Một phim 20 giây tỉ lệ 4:3, 1440x1080 ở 60fps, cắt theo giọng nói. Nền giấy trắng ngà, đen, một màu đỏ, một màu vàng, dùng Geist cho mọi chữ. Film grain phủ lên mọi thứ, vignette nhẹ, và một camera không bao giờ đứng yên: một chuyển động trôi cầm tay chậm bên dưới tất cả, cộng với một cú đẩy chậm vào trong mỗi cảnh.
Không cảnh nào cắt sang cảnh tiếp theo: mỗi lần chuyển giao bắt đầu đúng ở khung hình cuối của cảnh trước. Những cú cắt cứng duy nhất là các lần lật theo nhịp ở từ cuối cùng.
Mọi đồ vật đều là pixel art do bạn tự vẽ: một lưới 16x16 cho mỗi đồ vật, mỗi ô là một màu được đặt bằng tay, render thành khối 3D (phần đùn sẫm màu hơn hướng xuống-phải, một đường vát mỏng trên mỗi ô) với bóng tiếp xúc mềm.
Các hình bóng được chiếu sáng như camera nhiệt: nhiệt đến từ độ dày của cơ thể tại mỗi điểm, nên mũi, tóc và đầu ngón tay mát hơn, cộng thêm một điểm nóng và một lớp noise chuyển động chậm, ánh xạ qua dải màu đen > đỏ > cam > kem. Mép giữ sắc như dao cạo, có quầng sáng mềm bên ngoài.
Quy tắc chuyển động: không có gì bật hiện ra đột ngột (lướt có easing khoảng 0.5s với khởi đầu mềm), chuyển động nhanh có motion blur thật thay vì bản sao bóng ma, và phụ đề gõ chữ theo giọng nói sau một con trỏ dạng khối.
Cấm: stock footage, video AI, chuyển động camera 3D, hạt, glitch.
</direction>

<structure>
Treo mọi cảnh lên mốc thời gian từng từ của transcript (đo bằng word timestamps của faster-whisper, mỗi lần một đoạn ngắn):
1. Từ đầu tiên lấp đầy một tấm thẻ vàng. Tấm thẻ quét sang trái và câu hỏi gõ ra bên dưới thành hai dòng căn giữa, lướt để luôn căn giữa khi dài ra, từ khoá được gạch chân đỏ đúng lúc nó được nói.
2. Các đồ vật lao vút qua theo các làn phía trên và phía dưới dòng chữ, một tia lóe bốn cánh màu cyan quét vào, rồi trang giấy cháy rụi: màu đen khép từ các mép vào cái đầu, phía sau là một viền đỏ nóng.
3. Cái đầu nóng dần lên trên nền đen trong khi câu trả lời gõ ra ở thấp bên trái. Một quỹ đạo trắng mảnh tự vẽ quanh cái đầu, nửa xa của nó đi ra phía sau. Ở từ cuối, giấy bung nở ra từ bên trong cái đầu cùng các đồ vật trong đó, và camera rơi xuyên qua: cái đầu lao vụt qua ống kính cho tới khi chỉ còn thấy giấy.
4. Các đồ vật nằm trên một vòng tròn nghiêng nhìn phối cảnh (những cái phía trước to hơn và thấp hơn, vẽ sau cùng), xoay chậm, mỗi cái nhấp nhô; đồng xu lật và đáp xuống kèm tia lửa.
5. Ở mỗi từ trong 3 từ, đồ vật tương ứng bay ra khỏi vòng sang trái và to dần, trang giấy ngập đen từ nó, và từ đó gõ ra bên cạnh (máy ảnh: một ngôi sao màn trập đỏ; sách: một dải ruy băng đỏ quét qua; đĩa: hai quỹ đạo trắng và các nốt nhạc đỏ). Sau đó lớp ngập rút ngược vào đồ vật khi nó bay về chỗ, và camera lao gần hơn vào vòng. Đặt mỗi đồ vật chính vào vị trí ở phía trước-bên trái đúng lúc từ của nó vang lên.
6. Vòng co vào một chút, bung ra ngoài, mọi đồ vật hoá thành mực, và các vết mực loang lớn dần nuốt chửng trang giấy.
7. Bàn tay nâng lên vào khung hình, nóng rực, câu thoại tách ra hai bên. Trái tim rơi vào lòng bàn tay, rồi nâng lên giữa khung hình ở đúng kích thước cảnh tiếp theo giữ nó.
8. Từ cuối cùng, mỗi nhịp một chữ cái, nền lật giấy / đen / đỏ, trái tim giữ nguyên vị trí qua cú cắt, đồ vật ở giữa biến hình từng pixel thành đồ vật kế tiếp.
9. Những nét cọ mảnh quét qua, các chữ cái trôi tách ra và lơ lửng, rồi lắng lại thành từ với trái tim ở phía trên. Camera tiếp tục đẩy vào suốt đoạn giữ hình.
</structure>

<build>
1. Một HTML canvas. Mọi khung hình là một hàm thuần của thời gian bên trong seek(t).
2. Bake mỗi sprite pixel một lần vào một offscreen canvas (các lớp đùn, rồi đến mặt trước), rồi vẽ nó có scale và xoay.
3. Nhiệt: tính trước nhiệt nền của mỗi hình bóng một lần (một distance transform của mask, giữ ở giá trị mép bên ngoài nó để không có vùng tối nào loang vào khi upscale). Mỗi khung hình, cộng thêm điểm nóng và hai octave value noise ở một phần tư độ phân giải, ánh xạ qua một bảng tra 256 bậc, upscale lên, rồi cắt bằng mask độ phân giải đầy đủ.
4. Cú rơi xuyên qua cái đầu: vẽ cảnh vòng tròn vào một lớp offscreen, mask nó bằng cái đầu được scale lên quanh một điểm bên trong hộp sọ, và tăng scale đó theo đường cong bậc ba cho tới khi cái đầu phủ kín khung hình. Vòng bên trong zoom ít hơn cái đầu, nên nó đọc ra thành chiều sâu.
5. Biến hình pixel: ghép mỗi ô của đồ vật A với một ô của đồ vật B và cho vị trí lẫn màu của từng ô lướt dần, mỗi ô có một độ trễ ngẫu nhiên nhỏ.
6. Render bằng Playwright ở 60fps với 8 subframe motion blur, rồi ghép lại âm thanh gốc bằng ffmpeg.
</build>

<gotchas>
Một PNG mask không có kênh alpha sẽ đổ nhiệt kín cả khung, nên hãy đặt hình bóng vào kênh alpha. Một chi bị cắt bởi mép ảnh sẽ hiện thành đường thẳng, nên hãy kéo dài mask ra ngoài khung. Một lần chuyển giao chỉ trông mượt khi khung hình cuối của cảnh này là khung hình đầu của cảnh kế tiếp: vẽ cảnh đang ra bên dưới chuyển cảnh, và cho các cảnh cùng hiển thị vòng tròn dùng chung một hàm zoom. Một lớp ngập vẫn đang rút khi cảnh tiếp theo bắt đầu sẽ trông như cú cắt cứng, nên hãy để nó hoàn tất trước. Một lớp ngập ease-out nhanh trông như bị giật; hãy dùng khởi đầu mềm.
</gotchas>

<start>
Hãy hỏi tôi các đầu vào, đo mốc thời gian từng từ, rồi cho tôi xem 8 ảnh tĩnh trước khi bạn render.
</start>
```

## Prompt gốc

```text
<inputs>
Ask me for: a voiceover or song with a spoken line (the audio file) and its transcript, 10-12 small objects that sum up my life, two silhouettes to light like a heat camera (a head in profile and a raised hand), and the 3 words I want to land hardest. If I skip any, use the defaults: vinyl, book, camera, cat, coin, game controller, cap, heart, money, plant, clapperboard, skateboard; free CC0 silhouettes from Openverse; action, intention, curiosity.
</inputs>

<direction>
A 20 second 4:3 film, 1440x1080 at 60fps, cut to the voice. Off-white paper, black, one red, one yellow, Geist for every word. Film grain on everything, a soft vignette, and a camera that never rests: a slow handheld float under everything plus a slow push inside every scene.
No scene cuts to the next: each handoff starts on the exact last frame of the scene before. The only hard cuts are the beat flips on the last word.
Every object is pixel art you draw yourself: a 16x16 grid per object, every cell a hand-placed colour, rendered as a 3D block (a darker extrusion down-right, a thin bevel on every cell) with a soft contact shadow.
The silhouettes are lit like a heat camera: the heat comes from how thick the body is at each point, so the nose, the hair and the fingertips run cooler, plus one hotspot and a slow moving noise, mapped through a black > red > orange > cream ramp. The edge stays razor sharp, with a soft glow outside it.
Motion rules: nothing pops in (eased glides of about 0.5s with a soft start), fast moves get real motion blur instead of ghost copies, and captions type with the voice behind a block cursor.
Banned: stock footage, AI video, 3D camera moves, particles, glitch.
</direction>

<structure>
Hang every scene on the transcript's word timings (measure them with faster-whisper word timestamps, one short chunk at a time):
1. The first word fills a yellow card. The card wipes off to the left and the question types underneath on two centred lines that glide to stay centred as they grow, the key word underlined in red as it's spoken.
2. The objects streak past in lanes above and below the words, a cyan four-point flare sweeps in, then the page burns away: black closes in from the edges onto the head, behind a hot red edge.
3. The head heats up on black while the answer types low on the left. A thin white orbit draws itself around the head, its far half passing behind it. On the last word, paper blooms out from inside the head with the objects in it, and the camera falls through: the head rushes past the lens until the paper is all we see.
4. The objects sit on a tilted ring seen in perspective (the front ones bigger and lower, drawn last), slowly turning, each one bobbing; the coin flips and lands with sparks.
5. On each of the 3 words, that object flies out of the ring to the left and grows, the page floods black from it, and the word types beside it (camera: a red shutter star; book: a red ribbon sweep; record: two white orbits and red notes). Then the flood drains back into the object as it flies home, and the camera dives closer into the ring. Put each hero object in the slot that is front-left when its word lands.
6. The ring pulls in a touch, bursts outward, every object turns to ink, and ink blots grow and swallow the page.
7. The hand rises into frame, hot, with the line split either side of it. The heart drops into its palm, then lifts to the centre at the size the next scene holds it.
8. The last word, one letter per beat, the background flipping paper / black / red, the heart holding its place across the cut, the centre object morphing pixel by pixel into the next one.
9. Thin brush strokes sweep through, the letters drift apart and float, then settle back into the word with the heart above it. The camera keeps pushing through the hold.
</structure>

<build>
1. One HTML canvas. Every frame is a pure function of time inside seek(t).
2. Bake each pixel sprite once to an offscreen canvas (the extrusion layers, then the face), then draw it scaled and rotated.
3. The heat: precompute each silhouette's base heat once (a distance transform of the mask, held at the edge value outside it so nothing dark bleeds in when it is upscaled). Every frame, add the hotspot and two octaves of value noise at quarter resolution, map it through a 256-step lookup, upscale it, and cut it with the full-resolution mask.
4. The fall through the head: draw the ring scene into an offscreen layer, mask it with the head scaled up about a point inside the skull, and grow that scale on a cubed curve until the head covers the frame. The ring inside zooms less than the head does, so it reads as depth.
5. The pixel morph: pair every cell of object A with a cell of object B and glide each one's position and colour, with a small random delay per cell.
6. Render with Playwright at 60fps with 8 motion-blur subframes, then lay the original audio back on with ffmpeg.
</build>

<gotchas>
A mask PNG with no alpha channel fills the whole box with heat, so put the silhouette in the alpha. A limb cut by the photo's border shows as a straight edge, so extend the mask past the frame. A handoff only reads as smooth when the last frame of one scene is the first frame of the next: draw the outgoing scene under the transition, and give scenes that show the same ring one shared zoom function. A flood that's still retreating when the next scene starts reads as a hard cut, so let it finish first. A fast ease-out flood reads as a jump; use a soft start.
</gotchas>

<start>
Ask me for the inputs, measure the word timings, then show me 8 stills before you render.
</start>
```
