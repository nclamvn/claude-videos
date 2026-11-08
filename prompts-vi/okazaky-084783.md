# Quy trình engine 3D làm lyric MV

_Lyric MV 3D Engine Workflow_

Video Opus 5.5 của [@okazaky](https://x.com/okazaky) · [Bài đăng gốc kèm video](https://x.com/okazaky/status/2107826563786084783)

- **Danh mục:** Cảnh 3D
- **Tác giả:** [@okazaky](https://x.com/okazaky)

Thêm video Opus 5.5, mỗi video kèm bản làm lại trực tiếp: [skillry.dev/ai-videos/opus-5-5](https://skillry.dev/ai-videos/opus-5-5?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos)

Trang gốc (chưa dịch): [prompts/okazaky-084783.md](../prompts/okazaky-084783.md)

## Prompt (tiếng Việt)

```text
Hãy tạo một music video khổ dọc dài 50 giây bằng cách render theo lập trình (Three.js) thay vì dùng AI sinh video.
1. Tạo bài hát bằng Suno. Trích lời bài hát từ metadata nhúng trong file.
2. Tách stem bằng Demucs (vocals, drums, bass, other).
3. Chép lời phần vocal bằng mlx_whisper. Căn khớp với lời chính thức để tạo kịch bản theo nguyên tắc '1 dòng lời = 1 cảnh'.
4. Viết storyboard: định nghĩa 'Thể hiện gì bằng 3D', 'Camera', 'Từ khoá chính' cho mỗi dòng lời.
5. Cho 4 sub-agent Opus chạy song song viết chương trình cho các cảnh.
6. Xuất contact sheet 16 khung hình để kiểm tra bằng mắt.
7. Render bằng headless Chrome ở 1080x1920, 60fps.
8. Chuẩn hoá âm lượng về -14 LUFS.
Phong cách: nét vẽ kiểu tranh khắc, màu giới hạn ở Đen, Màu xương (Bone), Cam.
```

## Prompt gốc

```text
Create a 50-second vertical music video using programmatic rendering (Three.js) instead of native video AI.
1. Generate song with Suno. Extract lyrics from embedded metadata.
2. Separate stems with Demucs (vocals, drums, bass, other).
3. Transcribe vocals with mlx_whisper. Align with official lyrics to create script where '1 lyric line = 1 scene'.
4. Write storyboard: define 'What to show in 3D', 'Camera', 'Main word' for each lyric line.
5. Have 4 parallel Opus sub-agents write scene programs.
6. Export 16-frame contact sheet for visual verification.
7. Render headless Chrome at 1080x1920, 60fps.
8. Normalize volume to -14 LUFS.
Style: Engraving-like lines, colors limited to Black, Bone, Orange.
```
