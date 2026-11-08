# Video Opus 5.5 của @ik_builds

[▶ Xem bản gốc và bản làm lại trực tiếp trên Skillry](https://skillry.dev/ai-videos/opus-5-5/ik-builds-585923?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos) · [Bài đăng gốc](https://x.com/ik_builds/status/2103890476885585923)

- **Danh mục:** Motion graphics
- **Bản làm lại dùng:** Canvas · SVG
- **Tác giả:** [@ik_builds](https://x.com/ik_builds)

> Tác giả không công bố đầy đủ prompt. Dưới đây là nội dung bài đăng gốc của họ.

Trang gốc (chưa dịch): [prompts/ik-builds-585923.md](../prompts/ik-builds-585923.md)

## Prompt (tiếng Việt)

```text
TÔI ĐƯỢC BÁO GIÁ $3000 CHO CÁI NÀY!!!

Thế là tôi nhờ Opus 5.5 (medium) làm một video ra mắt bằng Motion Graphics cho chúng tôi.

đây là prompt one-shot ra nó:

"Hãy tạo một phim motion graphics 15s giải thích {{PRODUCT}}. HyperFrames + GSAP, không voiceover, không footage.
Phong cách: canvas sáng như giấy, ghi chú bút dạ tự vẽ ra, vật lý thật, kinetic type cực lớn,
chuyển sáng/tối gắt, một ý mới mỗi 1.5–2 s, một âm thanh trên mỗi cú hit.

COPY: đọc {{POSITIONING_DOCS}} trước. {{ONE_LINER}} Dành cho {{AUDIENCE}}. {{WHAT_IT_DOES}}
Gọi tên thứ sản phẩm học được, không bao giờ nói khái niệm trừu tượng.

QUY TẮC
- Không chrome (scrubber, timecode, fps, header). Không thuật ngữ animator trên màn hình
  ("squash", "stagger", "easing"...). Mọi chữ đều nói với người mua.
- Không bịa kết quả: không %, hệ số nhân, tên khách hàng hay số liệu.
- Không bao giờ dùng: {{BANNED_WORDS}}.
- Logo: mark thật {{LOGO_FILE}} + "{{PRODUCT}}" bằng {{WORDMARK_FONT}}; không bao giờ dùng file logo đóng khung.

CRAFT
- Màu {{COLOR_CANVAS}} / {{COLOR_INK}} / {{COLOR_ACCENT_1}} / {{COLOR_ACCENT_2}}; ghi chú dùng các
  màu nhấn; nền tối = màu than khớp với bảng màu.
- Font {{BRAND_FONTS}}; Anton cho kinetic type; chữ viết tay Caveat qua stroke-dashoffset.
- Easing thật, squash/stretch, stagger, overlap, onion skin, smear, follow-through. Kiểm tra
  registry HyperFrames trước. Đặt mọi from-state tại t=0 (an toàn khi seek); không bao giờ che một exit.
  Mỗi chuyển cảnh một chuyển động chính; không push/slide/rotate-swing chung chung.
- Nhạc chia đoạn: trống tắt ở cú chuyển sang tối và khi quả bóng đang bay, đập trở lại
  ở phần chữ và logo. SFX: tiếng pop, tiếng bút cào, whoosh, sub-hit cho logo. Chỉ dùng CC0 hoặc tự tạo;
  ghi lại nguồn. Master -14 LUFS, -2 dBTP, đo lại sau khi encode AAC."
```

## Prompt gốc

```text
I WAS QUOTED $3000 FOR THIS!!!

So I asked Opus 5.5 (medium) to create a launch video using Motion Graphics for us.

here's the prompt that one-shots it:

"Create a 15s motion-graphics film explaining {{PRODUCT}}. HyperFrames + GSAP, no voiceover, no footage.
Style: paper-light canvas, marker notes that draw on, real physics, huge kinetic type,
hard light/dark switches, a new idea every 1.5–2 s, a sound on every hit.

COPY: read {{POSITIONING_DOCS}} first. {{ONE_LINER}} For {{AUDIENCE}}. {{WHAT_IT_DOES}}
Name what the product learns, never the abstraction.

RULES
- No chrome (scrubber, timecode, fps, headers). No animator jargon on screen
  ("squash", "stagger", "easing"...). Every word speaks to the buyer.
- No invented results: no %, multipliers, customer names or figures.
- Never use: {{BANNED_WORDS}}.
- Logo: real mark {{LOGO_FILE}} + "{{PRODUCT}}" in {{WORDMARK_FONT}}; never a boxed logo file.

CRAFT
- Colours {{COLOR_CANVAS}} / {{COLOR_INK}} / {{COLOR_ACCENT_1}} / {{COLOR_ACCENT_2}}; notes in the
  accents; dark mode = charcoal matching the palette.
- Fonts {{BRAND_FONTS}}; Anton for kinetic type; Caveat handwriting via stroke-dashoffset.
- Real easing, squash/stretch, stagger, overlap, onion skin, smear, follow-through. Check the
  HyperFrames registry first. Set every from-state at t=0 (seek-safe); never cover an exit.
  One primary move per transition; no generic push/slide/rotate-swing.
- Music in sections: drums drop on the dark switch and while the ball is airborne, slam back
  on the type and the logo. SFX: pops, pen scribbles, whooshes, logo sub-hit. CC0 or generated
  only; log sources. Master -14 LUFS, -2 dBTP, re-measured after AAC encode."
```
