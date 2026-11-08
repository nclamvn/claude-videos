# Video Opus 5.5 của @heyiamnick

[▶ Xem bản gốc và bản làm lại trực tiếp trên Skillry](https://skillry.dev/ai-videos/opus-5-5/heyiamnick-119558?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos) · [Bài đăng gốc](https://x.com/heyiamnick/status/2109174851412119558)

- **Danh mục:** Motion graphics
- **Bản làm lại dùng:** Canvas
- **Tác giả:** [@heyiamnick](https://x.com/heyiamnick)

Trang gốc (chưa dịch): [prompts/heyiamnick-119558.md](../prompts/heyiamnick-119558.md)

## Prompt (tiếng Việt)

```text
<direction>
Hãy dựng một showreel motion design dài 30 giây, lặp liền mạch, giới thiệu CLAUDE, một motion designer.
Ý tưởng, gói trong một dòng: một nét bút chì được thăng cấp ba lần (chì than trên giấy, dây trên bản vẽ kỹ thuật, ánh sáng trên nền đen) và không bao giờ rời khỏi màn hình.

Mỗi shot đều được làm ra từ shot trước: hình khối, chữ và màu sắc biến đổi thành cảnh tiếp theo. Không cắt, không fade.

Kiểu chữ: chỉ dùng Geist. Độ đậm 900 cho chữ lớn, 600 đến 800 cho nhãn nhỏ (24 đến 28 px, giãn chữ 0.14 đến 0.3 em).
Bảng màu: kem giấy #EDE6D5, xanh bản vẽ #1B3ED2, xanh lơ hologram #45F0DD, cùng đen #07080A, chì than #16161A và trắng. Màu nhấn của mỗi giai đoạn là màu của giai đoạn kế tiếp: bút chì xanh trên giấy, xanh lơ trên bản vẽ, trắng trên hologram.
Camera: cố định và nhìn thẳng chính diện suốt cả phim, như một bàn vẽ kỹ thuật. Vật thể xoay; camera không bao giờ di chuyển.
Viền trống: không có gì đứng yên trong phạm vi 150 px tính từ hai cạnh bên hoặc 90 px tính từ cạnh trên và dưới. Những thứ đang di chuyển ngang qua thì có thể đi vào vùng này.

Ba loại mực. Cùng một hình học được vẽ bằng loại mực nào đang có trên màn hình:
- PAPER: nền giấy màu kem (dùng ảnh giấy của tôi nếu tôi đưa, nếu không thì màu kem phẳng với vân hạt mịn vẽ tay) với lưới xanh 60 px ở khoảng 13% và cứ mỗi đường thứ năm ở 26%. Nét vẽ là bút chì: được lấy mẫu lại và đẩy lệch khỏi vị trí chuẩn bằng các sóng sin chậm có pha đổi 8 lần mỗi giây, vẽ nét hai lần (đủ độ rộng ở 90%, nửa độ rộng ở 40% với độ rung nhiều hơn), khoét vân sần của giấy ra khỏi nét, rồi multiply lên giấy. Phần tô là gạch chéo, vẽ ra từng đường một. Chữ lớn là phần gạch chéo được cắt theo hình chữ cái, có viền đôi.
- BLUEPRINT: nền xanh phẳng với cùng lưới đó màu trắng. Nét trắng sạch 3 đến 4 px, cạnh khuất vẽ nét đứt và mảnh hơn, phần tô là gạch chéo mảnh và sạch.
- HOLOGRAM: nền đen với cùng lưới đó màu xanh lơ. Nét xanh lơ có lõi trắng bằng 30% độ rộng nét. Phần tô là các đường quét ngang với bước 8 px, độ dày thay đổi theo mức độ được chiếu sáng của bề mặt. Không có quầng mờ ở bất cứ đâu: cảm giác ánh sáng đến hoàn toàn từ mật độ nét.

Cấm: hạt bung tóe, glow, lóa ống kính, rung camera, tách kênh RGB, crossfade, gradient chung chung, easing nảy, giữ khung lâu hơn nửa giây, bất cứ thứ gì trông như template.
</direction>

<structure>
120 BPM, 60 phách, 15 ô nhịp mỗi ô 2 giây. Phách nào cũng có gì đó xảy ra. Chuyển động bắt đầu sớm 0.05 s trước phách của nó để chạm đích đúng phách.
Easing: một lò xo tắt dần tới hạn, 1 - (1 + w t) e^(-w t) với w trong khoảng 12 đến 40, để không có gì vượt quá đích; ease-in và ease-out hàm mũ cho các cú wipe, nhấn và rời cảnh.
Đổi cảnh: từ giấy sang bản vẽ bằng một hình khối tràn kín khung hình với mép sắc; từ bản vẽ sang hologram và từ hologram về giấy bằng một đường quét ngang duy nhất.
Khung hình cuối là khung hình đầu, để phim lặp lại.
Hai nhãn ở góc luôn hiện suốt phim: góc trên bên trái "FIG. 07 — GEAR" (số ô nhịp và tên), góc dưới bên phải "BEAT 27 / 60". Tên các ô nhịp: DRAFT, TYPE, CURVE, MORPH, TILE, SOLID, GEAR, PANEL, DATA, LIGHT, WAVE, GLOBE, DRUM, FORM, END.
</structure>
<mascot>

Giám đốc sáng tạo: một nhân vật hình hộp nhỏ. Thân 76 x 54 đơn vị bo góc tròn, hai cánh tay ngắn cụt (24 x 16) ở giữa chiều cao, bốn chân thẳng (11 x 33), hai mắt hình chữ nhật bo tròn cao (8 x 14). Vẽ nó rộng khoảng 250 px. Tay phải của nó giơ lên 58 độ, cầm một cây bút chì.
Trên giấy: viền chì than, gạch chéo xanh thưa và mắt chì than. Trong hologram: viền xanh lơ, tô bằng đường quét và mắt trắng. Nó không bao giờ là màu thứ tư.
Nó chạy với hai cặp chân nhấc xen kẽ, sáu bước mỗi giây, nghiêng 7 độ về hướng chạy.
</mascot>
<storyboard>

Ô nhịp 1, HOOK, 0-2 s, giấy.
Khung hình 0: CLAUDE bằng Geist 900, co cho vừa rộng 1500 px, căn giữa, gạch chéo bút chì. INTRODUCING cỡ nhỏ phía trên, A MOTION DESIGNER cỡ nhỏ phía dưới. Một thanh ray bút chì rộng 1620 px nằm cách các chữ 96 px về phía trên. Linh vật đứng trên thanh ray tại x = 1560, bên trái nó có dòng chữ CREATIVE DIRECTOR.

0.0: các dòng chữ nhỏ tự xóa ngược như gõ lùi; linh vật chạy ra khỏi mép phải, ngày càng nhanh.

0.36 đến 0.5: thanh ray rơi xuống, tăng tốc, tới vị trí 26 px dưới đường chân chữ và ép dẹt các chữ vào chính nó.

1.0: đường kẻ nâng lên giữa, rút ngắn còn 1320 px và tách thành hai thanh ray cách nhau 140 px; 41 vạch thước xanh quét dọc thanh ray trên.

1.5: hai thanh ray mở ra 300 px; một đường kích thước chiều cao màu xanh được vẽ ở bên phải, kèm con số chạy trực tiếp.

Ô nhịp 2, KINETIC TYPE, 2-4 s, giấy. Các từ nằm giữa hai thanh ray và bị cắt theo khe đó; thanh ray di chuyển để vừa từng từ.

2.0: INTRODUCING trồi lên qua đường chân chữ từng chữ cái một, rồi nhấc ra qua mép trên.

2.5: A MOTION quất vào từ bên trái (1400 px trong 0.2 s).

3.0: hai thanh ray đập khép lại lên nó rồi mở ra, kéo giãn DESIGNER ra khỏi đường kẻ; sau đó các chữ cái của nó bay ra hai bên.

3.5: CLAUDE bằng bút chì xanh, các chữ cái rơi từ trên xuống, mỗi chữ cách nhau 0.05 s. Tại 4.0 hai thanh ray khép lại và nghiền nó thành một đường kẻ dài 1476 px.

Ô nhịp 3, CURVES, 4-6 s, giấy.

4.1: đường kẻ có thêm tay nắm của công cụ pen (dài 430 px ở góc 58 độ, ô vuông nhỏ ở hai đầu, vòng tròn ở đầu tay nắm, nhãn EASE) và uốn thành hình chữ S.

4.5: tay nắm xoay sang góc đối xứng; tám bản sao màu xanh xòe ra cách nhau 34 px, nối ở hai đầu như một chiếc lá.

5.0: tay nắm thu lại; dải ruy băng biến thành các sóng sin chạy (biên độ 92 px, 2.75 chu kỳ, mỗi đường lệch pha một chút).

5.5: nó gom lại thành một đường thẳng phẳng.

Ô nhịp 4, SHAPE MORPH, 6-8 s, giấy.

6.1: đường kẻ cuộn thành hình tròn bán kính 235 (độ cong tăng, chiều dài giữ nguyên). 6.5: tam giác, xoay 120 độ trong lúc biến đổi. 7.0: hình vuông. 7.5: lục giác, đỉnh hướng lên, bán kính 270. Gạch chéo xanh dày dần bên trong, rồi gạch chéo đan.

Ô nhịp 5, TILING, 8-10 s, giấy.

8.0: lục giác thu nhỏ còn bán kính 96 và sáu cái nữa trượt ra quanh nó. 8.5: thêm mười hai cái, thành một tổ ong gồm

19. 9.0: gạch chéo dày đặc quét ngang cho tới khi mọi ô đều xanh đặc. 9.6 đến 10.0: hình của ô trung tâm phóng to vượt ra ngoài khung hình với mép sắc; bên trong nó là bản vẽ kỹ thuật, với tổ ong bằng nét trắng.

Ô nhịp 6, 2D TO 3D, 10-12 s, bản vẽ.

10.0: ba đường được vẽ bên trong mỗi lục giác, cùng ba đường khuất nét đứt: mỗi ô là một khối lập phương nhìn từ góc.

10.5: mười tám khối lập phương bên ngoài trượt vào khối trung tâm, khối này phóng to tới bán kính 270. 11.0: nó xoay một phần tư vòng và phối cảnh được bật lên. 11.5: nó quay về mặt chính diện.

Ô nhịp 7, MECHANISM, 12-14 s, bản vẽ.

12.0: khối lập phương dẹt lại và mặt vuông phía trước mọc răng: một bánh răng 16 răng, bán kính vòng chia 208. Từ 12.25 cả cụm bánh răng nhích 45 độ trên mỗi nốt móc đơn. 12.5: một bánh răng 10 răng mọc ra phía trên bên phải, ăn khớp. 13.0: một bánh răng 12 răng ở phía trên bên trái. Mỗi bánh có vòng chia nét đứt, một moay-ơ và một nhãn (16T, 10T, 12T). 13.5: các bánh răng nhỏ thu lại; bánh răng trở lại thành hình vuông và khối lập phương có lại chiều sâu.
Ô nhịp 8, UNFOLD, 14-16 s, bản vẽ.

14.0: khối lập phương mở ra theo các bản lề thành hình chữ thập gồm sáu ô vuông. 14.5: các ô vuông trượt và kéo giãn thành sáu panel: một dải header, một sidebar cao, một biểu đồ rộng, hai tile, một dải timeline.

15.0: chúng được lấp đầy nội dung. Header: "CLAUDE — MOTION REEL", một công tắc BARS / RING, một nút gạt LIGHT. Biểu đồ: 30 cột, mỗi cột cho một giây của phim này, chiều cao 42 30 36 44 50 46 52 62 50 56 62 72 60 66 58 76 56 62 68 74 70 78 86 94 100 93 97 90 80 50. Timeline: 15 tên ô nhịp, mỗi tên có một hình thoi keyframe.
15.5: các bộ đếm cuộn lên: 120 BPM, 60 BEATS, 1800 FRAMES, 0 CUTS.
Ô nhịp 9, DATA, 16-18 s, bản vẽ.

16.0: một đường đồ thị được vẽ ngang qua đỉnh các cột; một playhead xanh lơ đáp xuống timeline đúng thời điểm thực. Cột của giây hiện tại tô xanh lơ đặc, các cột trước đó gạch chéo, các cột sau chỉ có viền. Một con trỏ xuất hiện.
16.5: nó click vào RING: đường đáy của biểu đồ uốn tròn thành một vòng tròn bán kính 110 với các
```

## Prompt gốc

```text
<direction>
Build a 30-second looping motion design showreel that introduces CLAUDE, a motion designer.
Concept, in one line: one pencil line gets promoted three times (graphite on paper, wire on a blueprint, light on black) and never leaves the screen.

Every shot is made out of the previous one: shapes, type and colour transform into the next scene. No cuts, no fades.

Typeface: Geist only. Weight 900 for big words, 600 to 800 for small labels (24 to 28 px, tracked 0.14 to 0.3 em).
Palette: paper cream #EDE6D5, blueprint blue #1B3ED2, hologram cyan #45F0DD, plus black #07080A, graphite #16161A and white. Each stage's accent is the next stage's colour: blue pencil on paper, cyan on the blueprint, white on the hologram.
Camera: locked and front-on for the whole film, like a drafting table. Objects turn; the camera never moves.
Empty border: nothing at rest within 150 px of the sides or 90 px of the top and bottom. Things travelling through may cross it.

Three inks. The same geometry is drawn in whichever ink is on screen:
- PAPER: a cream paper background (use my paper image if I give one, otherwise flat cream with fine drawn grain) with a 60 px blue grid at about 13% and every fifth line at 26%. Lines are pencil: resampled and pushed off true by slow sine waves whose phase changes 8 times a second, stroked twice (full width at 90%, half width at 40% with more wobble), with paper tooth knocked out of the strokes, then multiplied onto the paper. Fills are diagonal hatching drawn on one line at a time. Big type is hatching cut to the letter shapes, with a doubled outline.
- BLUEPRINT: flat blue with the same grid in white. Clean white lines 3 to 4 px, hidden edges dashed and thinner, fills are fine clean hatching.
- HOLOGRAM: black with the same grid in cyan. Cyan lines with a white core 30% of the line width. Fills are horizontal scan lines on an 8 px pitch whose thickness follows how lit the surface is. No blur halo anywhere: it reads as light through line density only.

Banned: particle bursts, glows, lens flares, camera shake, RGB split, crossfades, generic gradients, bouncy easing, holds longer than half a second, anything that looks like a template.
</direction>

<structure>
120 BPM, 60 beats, 15 bars of 2 seconds. Something happens on every beat. Moves start 0.05 s before their beat so they land on it.
Easing: a critically damped spring, 1 - (1 + w t) e^(-w t) with w between 12 and 40, so nothing ever passes its target; exponential ease-in and ease-out for wipes, presses and exits.
Scene changes: paper to blueprint by a shape that floods the frame with a hard edge; blueprint to hologram and hologram to paper by one horizontal scan line.
The last frame is the first frame, so it loops.
Two corner labels stay on all film: top left "FIG. 07 — GEAR" (bar number and name), bottom right "BEAT 27 / 60". Bar names: DRAFT, TYPE, CURVE, MORPH, TILE, SOLID, GEAR, PANEL, DATA, LIGHT, WAVE, GLOBE, DRUM, FORM, END.
</structure>
<mascot>

The creative director: a small box character. Body 76 x 54 units with rounded corners, two short arm stubs (24 x 16) at mid height, four straight legs (11 x 33), two tall rounded-rectangle eyes (8 x 14). Draw it about 250 px wide. Its right arm is raised 58 degrees holding a pencil.
On paper: graphite outline with sparse blue hatching and graphite eyes. In the hologram: cyan outline with scan-line fill and white eyes. It is never a fourth colour.
It runs with alternate leg pairs lifting, six steps a second, leaning 7 degrees into the run.
</mascot>
<storyboard>

Bar 1, HOOK, 0-2 s, paper.
Frame 0: CLAUDE in Geist 900, fitted to 1500 px wide, centred, pencil-hatched. INTRODUCING small above it, A MOTION DESIGNER small below. A pencil rail 1620 px wide sits 96 px above the letters. The mascot stands on the rail at x = 1560 with CREATIVE DIRECTOR lettered to its left.

0.0: the small lines un-type; the mascot runs off the right edge, accelerating.

0.36 to 0.5: the rail drops, accelerating, to 26 px below the baseline and presses the letters flat into itself.

1.0: the line rises to the middle, shortens to 1320 px and splits into two rails 140 px apart; 41 blue ruler ticks sweep along the top rail.

1.5: the rails open to 300 px; a blue height dimension draws at the right with a live number.

Bar 2, KINETIC TYPE, 2-4 s, paper. Words sit between the rails and are clipped to that slot; the rails move to fit each word.

2.0: INTRODUCING rises through the baseline letter by letter, then lifts out through the top.

2.5: A MOTION whips in from the left (1400 px in 0.2 s).

3.0: the rails clap shut on it and reopen, stretching DESIGNER out of the line; its letters then fly out sideways.

3.5: CLAUDE in blue pencil, letters dropping from above one every 0.05 s. At 4.0 the rails close and crush it into one line 1476 px long.

Bar 3, CURVES, 4-6 s, paper.

4.1: the line gets pen-tool handles (430 px long at 58 degrees, small squares at the ends, circles on the handle tips, the label EASE) and bends into an S.

4.5: the handles swing to the mirror angle; eight blue copies fan out 34 px apart, joined at both ends like a leaf.

5.0: handles retract; the ribbon becomes travelling sine waves (amplitude 92 px, 2.75 cycles, each line a little out of phase).

5.5: it gathers back into one flat line.

Bar 4, SHAPE MORPH, 6-8 s, paper.

6.1: the line curls into a circle of radius 235 (curvature grows, length stays). 6.5: triangle, turning 120 degrees as it changes. 7.0: square. 7.5: hexagon, point up, radius 270. Blue hatching builds inside, then cross-hatching.

Bar 5, TILING, 8-10 s, paper.

8.0: the hexagon shrinks to radius 96 and six more slide out around it. 8.5: twelve more, a honeycomb of

19. 9.0: dense hatching sweeps across until every cell is solid blue. 9.6 to 10.0: the centre cell's shape grows past the frame with a hard edge; inside it is the blueprint, with the honeycomb in white line.

Bar 6, 2D TO 3D, 10-12 s, blueprint.

10.0: three lines draw inside every hexagon, plus three dashed hidden ones: each is a cube seen corner-on. 

10.5: the eighteen outer cubes slide into the centre one, which grows to radius 270. 11.0: it turns a quarter and perspective switches on. 11.5: it faces front.

Bar 7, MECHANISM, 12-14 s, blueprint.

12.0: the cube flattens and its front square grows teeth: a 16-tooth gear, pitch radius 208. From 12.25 the train steps 45 degrees on every eighth note. 12.5: a 10-tooth gear grows out to the upper right, meshing. 13.0: a 12-tooth gear to the upper left. Each has a dashed pitch circle, a hub and a label (16T, 10T, 12T). 13.5: the small gears retract; the gear becomes a square again and the cube gets its depth back.
Bar 8, UNFOLD, 14-16 s, blueprint.

14.0: the cube unfolds on its hinges into a cross of six squares. 14.5: the squares slide and stretch into six panels: a header strip, a tall sidebar, a wide chart, two tiles, a timeline strip.

15.0: they fill in. Header: "CLAUDE — MOTION REEL", a BARS / RING switch, a LIGHT toggle. Chart: 30 bars, one per second of this film, heights 42 30 36 44 50 46 52 62 50 56 62 72 60 66 58 76 56 62 68 74 70 78 86 94 100 93 97 90 80 50. Timeline: the 15 bar names, a keyframe diamond on each.
15.5: counters roll up: 120 BPM, 60 BEATS, 1800 FRAMES, 0 CUTS.
Bar 9, DATA, 16-18 s, blueprint.

16.0: a graph line draws across the bar tops; a cyan playhead lands on the timeline at the real time. The current second's bar is solid cyan, earlier ones hatched, later ones outlined. A cursor arrives.
16.5: it clicks RING: the chart's baseline bends round into a circle of radius 110 with the ba
```
