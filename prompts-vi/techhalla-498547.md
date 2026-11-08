# Video Opus 5.5 của @techhalla

[▶ Xem bản gốc và bản làm lại trực tiếp trên Skillry](https://skillry.dev/ai-videos/opus-5-5/techhalla-498547?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos) · [Bài đăng gốc](https://x.com/techhalla/status/2103411244468498547)

- **Danh mục:** Motion graphics
- **Bản làm lại dùng:** Canvas
- **Tác giả:** [@techhalla](https://x.com/techhalla)

Trang gốc (chưa dịch): [prompts/techhalla-498547.md](../prompts/techhalla-498547.md)

## Prompt (tiếng Việt)

```text
Bạn là một motion designer đẳng cấp thế giới đang làm một đoạn bumper nhận diện động (kinetic identity) dài 20.00s cho TechHalla — một nhà sáng tạo AI nổi tiếng với những workflow ai cũng muốn "chôm", chứ không phải cảm hứng suông. Tác phẩm này phải có cảm giác như designer giỏi nhất trong phòng làm ra một tấm poster đường phố biết chuyển động. Đây là showreel định đoạt: nếu nó yếu, bạn không được tuyển.

THỜI LƯỢNG: đúng 20.00 giây. LẶP ĐƯỢC: khung hình 0 == khung hình cuối (vị trí, độ mờ đục, con trỏ nếu có).
ĐỊNH DẠNG: một file HTML, 1080×1080 (vuông, chuẩn X). 60fps.
BẢNG MÀU (nghiêm ngặt):
- nền # 0A0A0A
- magenta # FF2BD6
- xanh chanh acid # B8FF00
- trắng # F5F5F5 chỉ dùng cho chữ chính cần đọc khi thật cần
Không có sắc màu nào khác. Không gradient trên phần khung UI. Magenta/xanh được phép lệch màu in (offset kiểu in ấn) 2–4px, chỉ ở các khung hình va chạm.

HỆ THỐNG CHỮ (dùng cả ba; không bao giờ dùng một font cho mọi thứ):
1) Display / gào thét: Archivo Black (hoặc font đen siêu hẹp tương đương) — tối đa 1–4 từ
2) Grotesque đô thị: Syne ExtraBold — các nhịp phụ, các dòng xếp chồng
3) Mono / “prompt code”: IBM Plex Mono Medium — nhãn nhỏ, mốc thời gian, mẩu prompt giả
Giãn chữ: display −40 đến −80; mono +20. Kerning quang học. Không dùng font viết tay điệu đà.

THÔNG ĐIỆP (khóa cứng — không làm mềm, không thêm slogan độn):
Các nhịp xuất hiện theo đúng thứ tự này:
1. STOP SCROLLING
2. AI VIDEO ISN’T EXPENSIVE
3. BAD PROMPTING IS
4. WORKFLOWS > WISHES
5. STEAL THE PROMPT
6. @ TECHHALLA
Mẩu phụ trợ (mono, ≤18 ký tự, không bao giờ là câu hoàn chỉnh): JSON · H3 · SEEDANCE · 0 KEYFRAMES · MAGNIFIC · COPY/PASTE

MẠCH TRUYỆN (20s):
0.0–2.5s  COLD OPEN — “STOP SCROLLING” đập vào từ dưới lên với lò xo vượt đích; vệt nhòe magenta; các vạch đường chân màu xanh acid chạy ngang như một dạng sóng.
2.5–6.5s  LUẬN ĐIỂM A — “AI VIDEO ISN’T EXPENSIVE” khóa vào lưới poster (lưới đường chân chữ 8px). Các chữ cái xáo trộn (Fisher–Yates có seed cho từng glyph) rồi bật vào chỗ đúng phách.
6.5–10.5s LUẬN ĐIỂM B — “BAD PROMPTING IS” thay thế nó bằng mask wipe xuyên qua hình chữ (dòng chữ đang rời đi chính là mask). Tách kênh magenta/xanh ở cú chuyển.
10.5–14.5s CHỚP BẰNG CHỨNG — chồng chữ động dồn dập: WORKFLOWS > WISHES, rồi các mẩu mono quay quanh một khối trung tâm như một terminal. Một “khối prompt” giả gõ tối đa 3 dòng, rồi bị một đường gạch ngang xanh acid cắt qua, đường này biến thành gạch chân cho STEAL THE PROMPT.
14.5–17.5s KHÓA THƯƠNG HIỆU — @ TECHHALLA vào giữa; độ đậm display. Một thanh magenta dày và một đường kẻ xanh acid mảnh tạo thành dấu ngoặc chữ L (tự thiết kế, không tải logo về).
17.5–20.0s ỔN ĐỊNH / LẶP — giữ cụm lockup; nhịp thở nhỏ (scale 1.000→1.012→1.000); khung hình cuối == khung hình đầu, sẵn sàng để lặp.

KỸ THUẬT CỤ THỂ (bắt buộc — phải triển khai, không làm gần đúng):
1. seek(t) là hàm thuần của thời gian. Không CSS transition. Không setInterval. Không React state giữa các khung hình.
2. Lò xo = đáp ứng bước dạng closed-form. Xếp chồng một lò xo cho mỗi lần đổi đích để chuyển động luôn tất định.
3. Chữ động: lò xo theo từng glyph (y, độ mờ đục, blur). Độ trễ so le = nốt 1/16 ở 120 BPM (125ms).
4. Lệch màu in: chỉ trên các khung hình nhấn, nhân bản lớp chữ lệch (±2–4px) bằng magenta và xanh acid ở độ mờ đục 40%.
5. Mask reveal: chữ đích được hé lộ bằng cách animate một path mask lấy từ đường viền của từ đang rời đi.
6. Camera: một camera trực giao duy nhất; chỉ punch-in (1.0→1.08) và smash-pan ngang canh theo phách — không bao giờ trôi ngẫu nhiên.
7. Motion blur: render 4 khung phụ mỗi khung hình, rồi trộn (kiểu tmix).
8. Lưới phách: 120 BPM, phách mạnh tại t=0. Trong 16 phách đầu, phách nào cũng phải có gì đó chạm xuống; sau đó, cách một phách là được.
9. Bước kiểm trước: trước khi render toàn bộ, xuất một ảnh tĩnh cho mỗi nhịp chính (8 khung hình). Sửa chữ bị chật, từ mồ côi, độ tương phản thấp — rồi mới render.

CẤM:
Các sáo rỗng AI chung chung (não, robot, mạng nơ-ron, lấp lánh), gradient mềm, easing nảy kiểu hoạt hình, hạt nổ tung, “HUD tương lai” kiểu stock, đoạn văn dài, giọng thuyết minh kiểu tiểu luận, chất Canva-deck, slogan thừa ngoài thông điệp đã khóa, neon tím/xanh, glassmorphism.

Nếu Astra đã khiến chúng ta choáng váng… thì Opus 5.5 đúng là một con quái vật 😱
```

## Prompt gốc

```text
You are a world-class motion designer doing a 20.00s kinetic identity bumper for TechHalla — an AI creator known for stealable workflows, not vibes. This piece must feel like the best designer in the room made a street-poster that moves. Showreel stakes: if this is weak, you don’t get hired.

DURATION: exactly 20.00 seconds. LOOPABLE: frame 0 == frame last (position, opacity, cursor if any).
FORMAT: one HTML file, 1080×1080 (square, X-native). 60fps.
PALETTE (strict):
- bg # 0A0A0A
- magenta # FF2BD6
- acid green # B8FF00
- white # F5F5F5 only for primary readable type when needed
No other hues. No gradients on UI chrome. Magenta/green may misregister (print offset) by 2–4px on impact frames only.

TYPE SYSTEM (use all three; never one font for everything):
1) Display / scream: Archivo Black (or equivalent ultra-condensed black) — 1–4 words max
2) Urban grotesque: Syne ExtraBold — secondary hits, stacked lines
3) Mono / “prompt code”: IBM Plex Mono Medium — small labels, timestamps, fake prompt crumbs
Tracking: display −40 to −80; mono +20. Optical kerning. No cute script fonts.

MESSAGE (locked — do not soften, do not add filler slogans):
Beat hits in this exact order:
1. STOP SCROLLING
2. AI VIDEO ISN’T EXPENSIVE
3. BAD PROMPTING IS
4. WORKFLOWS > WISHES
5. STEAL THE PROMPT
6. @ TECHHALLA
Supporting crumbs (mono, ≤18 chars, never full sentences): JSON · H3 · SEEDANCE · 0 KEYFRAMES · MAGNIFIC · COPY/PASTE

NARRATIVE ARC (20s):
0.0–2.5s  COLD OPEN — “STOP SCROLLING” slams in from below with spring overshoot; magenta smear trail; acid green baseline ticks across like a waveform.
2.5–6.5s  THESIS A — “AI VIDEO ISN’T EXPENSIVE” locks to a poster grid (baseline grid 8px). Letters scramble (seeded Fisher–Yates per glyph) then snap on the beat.
6.5–10.5s THESIS B — “BAD PROMPTING IS” replaces it via mask wipe through the letterforms (the outgoing line is the mask). Magenta/green channel split on the cut.
10.5–14.5s PROOF FLASH — rapid kinetic stack: WORKFLOWS > WISHES, then mono crumbs orbit a central block like a terminal. One fake “prompt block” types 3 lines max, then gets crossed by an acid green strikethrough that becomes a underline for STEAL THE PROMPT.
14.5–17.5s BRAND LOCK — @ TECHHALLA centers; display weight. A thick magenta bar and a thin acid green rule form an L-bracket mark (custom, not a logo download).
17.5–20.0s SETTLE / LOOP — hold lockup; micro-breath (scale 1.000→1.012→1.000); last frame == first ready for loop.

CONCRETE TECHNIQUES (required — implement, don’t approximate):
1. seek(t) pure function of time. No CSS transitions. No setInterval. No React state across frames.
2. Springs = closed-form step responses. Stack one spring per target change so motion stays deterministic.
3. Kinetic type: per-glyph spring (y, opacity, blur). Stagger = 1/16 note at 120 BPM (125ms).
4. Print misregistration: on accent frames only, duplicate text layer offset (±2–4px) in magenta and acid green at 40% opacity.
5. Mask reveal: destination text revealed by animating a path mask derived from the outgoing word’s outlines.
6. Camera: one orthographic camera; only punch-in (1.0→1.08) and horizontal smash-pans timed to beats — never random drift.
7. Motion blur: render 4 subframes per frame, blend (tmix-style).
8. Beat grid: 120 BPM, downbeat at t=0. Something must land on every beat for the first 16 beats; after that, every other beat is ok.
9. Pre-pass: before full render, export one still per major beat (8 frames). Fix cramped type, orphan words, low contrast — then render.

BANNED:
Generic AI clichés (brains, robots, neural nets, sparkles), soft gradients, bouncy cartoon easing, particle explosions, stock “futuristic HUD”, long paragraphs, narrator essay energy, Canva-deck energy, extra slogans beyond the locked message, purple/blue neon, glassmorphism.

If Astra already blew our minds… Opus 5.5 is a monster 😱
```
