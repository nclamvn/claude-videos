# Trực quan hoá bài phát biểu bằng chữ chuyển động

_Kinetic Typography Speech Visualization_

Video Opus 5.5 của [@Gdgtify](https://x.com/Gdgtify) · [Bài đăng gốc kèm video](https://x.com/Gdgtify/status/2105570411870130294)

- **Danh mục:** Video giải thích
- **Tác giả:** [@Gdgtify](https://x.com/Gdgtify)

Thêm video Opus 5.5, mỗi video kèm bản làm lại trực tiếp: [skillry.dev/ai-videos/opus-5-5](https://skillry.dev/ai-videos/opus-5-5?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos)

Trang gốc (chưa dịch): [prompts/gdgtify-130294.md](../prompts/gdgtify-130294.md)

## Prompt (tiếng Việt)

```text
Hãy tạo một phim spoken-word kinetic dài 20.00 giây có tựa đề "BUILD THE FLOOR."
Hãy coi đây là một bài diễn văn thu nhỏ nguyên bản được dàn dựng bên trong một trường chữ. Mỗi dòng sắp xếp lại trường của khung hình. Lời tuyên bố cuối cùng phải đứng trên một trường cuối cùng đã nằm phẳng.
Bàn giao một file HTML tự chứa, 1080×1080, nhắm 60fps, dùng SVG và/hoặc Canvas. Nhúng mọi asset cần thiết.
CHỈ ĐẠO NGHỆ THUẬT
Nền #102820. Chữ # F4E9D5. Đường sức và mạt sắt # F2B544. Một thế giới tượng đài từ trường: đường dòng, từ thông, sự tĩnh lặng tại điểm không. Chữ luôn sắc nét; hạt chỉ là không khí. Serif tương phản cao cho bài diễn văn, grotesque đậm cho các từ chịu lực, monospace tiết chế cho các đồng hồ đo từ thông. Không nam châm móng ngựa, tia sét, sơ đồ electron hay các vòng cung sci-fi.
BÀI DIỄN VĂN NGUYÊN BẢN — ĐÚNG TỪNG CHỮ, ĐÚNG THỨ TỰ
"We were told to wait."
"So we learned the weight of waiting."
"Then one voice made room."
"Then another."
"Now the floor belongs to us."
Không gán những lời này cho bất kỳ người thật nào. Không thêm khẩu hiệu nào khác. Toàn bộ bài diễn văn phải hiểu được mà không cần âm thanh.
QUY TẮC HÌNH ẢNH TRUNG TÂM
Các từ được gán vai trò trong trường. WAIT là một bản đẩy; các chữ nghiêng tránh xa nó, khoảng cách chữ bị nén. WAITING là các đường sức võng xuống dưới tải trong khi mạt sắt chảy về phía thấp. VOICE là một cực bị đảo ngược; trường tự sắp xếp lại và các chữ đứng thẳng dọc theo nó. ROOM là một điểm không, một con mắt tĩnh bên trong trường. FLOOR là trường được làm phẳng thành một mặt phẳng nằm ngang. Những vai trò này phải nảy sinh từ chính các chữ phản ứng với trường, không phải từ hình minh họa.
STORYBOARD
0.00–3.00 — "We were told to wait." Câu nghiêng tránh xa bản WAIT; các đường dòng bị nén ép vào nó. Không gian khả dụng bị bóp lại ở phía bản; câu vẫn đọc được, bị ép nhưng còn nguyên vẹn.
3.00–6.50 — "So we learned the weight of waiting." Hiện theo từng cụm từ. Đường sức võng sâu hơn với mỗi cụm. Mạt sắt — tất định, seed bằng hash theo id và thời gian — trôi dọc các đường dòng về phía thấp và tụ lại. Chữ WAITING treo nghiêng trong trường như một vật tải lơ lửng.
6.50–10.00 — "Then one voice made room." VOICE xuất hiện; một cực đảo ngược. Trường tự sắp xếp lại: các đường dòng cũ rút lại bằng dash-offset trong khi các đường mới được vẽ vào. Các chữ xoay thẳng đứng dọc theo trường mới — xoay giải tích toàn bộ glyph, không bao giờ morph path. ROOM mở ra như một điểm không, một con mắt tĩnh; lòng chữ O trong ROOM là tâm của nó, và bố cục kế tiếp nằm yên bên trong đó.
10.00–12.50 — "Then another." Một cực thứ hai xoay. Trường trở nên đối xứng; mọi chữ đứng thẳng đứng. Đường chân chữ cân bằng lại thành đường nằm ngang hoàn hảo đầu tiên trong phim. Giữ tĩnh lặng tuyệt đối ít nhất 400ms — kể cả mạt sắt cũng dừng lại.
12.50–16.00 — "Now the floor belongs to us." Trường phẳng dần thành một mặt nằm ng
```

## Prompt gốc

```text
Create a 20.00-second kinetic spoken-word film titled “BUILD THE FLOOR.”
Treat this as an original miniature speech staged inside a typographic field. Every line reorganizes the field of the frame. The final declaration must stand on a field that finally lies flat.
Deliver one self-contained HTML file, 1080×1080, targeting 60fps, using SVG and/or Canvas. Embed all required assets.
ART DIRECTION
Background #102820. Letterforms # F4E9D5. Field lines and filings # F2B544. A magnetic-monument world: streamlines, flux, stillness at the null. Typography stays crisp; particles are atmosphere only. High-contrast serif for the speech, heavy grotesque for load-bearing words, restrained monospace for flux gauges. No horseshoe magnets, lightning, electron diagrams, or sci-fi arcs.
ORIGINAL SPEECH — EXACT WORDS, EXACT ORDER
“We were told to wait.”
“So we learned the weight of waiting.”
“Then one voice made room.”
“Then another.”
“Now the floor belongs to us.”
Do not attribute these words to any real person. No extra slogans. The complete speech must be understandable without audio.
CENTRAL VISUAL RULE
Words have assigned field roles. WAIT is a repelling plate; letterforms lean away from it, kerning compressed. WAITING is field lines sagging under load while filings stream toward the low side. VOICE is one pole reversed; the field reorganizes and letters stand upright along it. ROOM is a null point, a still eye inside the field. FLOOR is the field flattened into a horizontal plane. These roles must emerge from the actual letterforms responding to the field, not from illustrations.
STORYBOARD
0.00–3.00 — “We were told to wait.” The sentence leans away from the WAIT plate; streamlines compress against it. Available space pinches on the plate side; the sentence remains readable, pressed but intact.
3.00–6.50 — “So we learned the weight of waiting.” Reveal in phrase groups. Field lines sag deeper with each phrase. Filings — deterministic, hash-seeded per id and time — drift along the streamlines toward the low side and gather. The WAITING glyph hangs tilted inside the field as a suspended load.
6.50–10.00 — “Then one voice made room.” VOICE enters; one pole reverses. The field reorganizes: old streamlines retract by dash-offset while new ones draw in. Letters rotate upright along the new field — analytic rotation of whole glyphs, never path morphing. ROOM opens as a null point, a still eye; the counter of the O in ROOM is its center, and the next composition sits calm inside it.
10.00–12.50 — “Then another.” A second pole turns. The field becomes symmetric; every letter stands vertical. The baseline levels into the first perfect horizontal in the film. Hold absolute stillness for at least 400ms — even the filings pause.
12.50–16.00 — “Now the floor belongs to us.” The field flattens into a hor
```
