# Video Opus 5.5 của @majidmanzarpour

[▶ Xem bản gốc và bản làm lại trực tiếp trên Skillry](https://skillry.dev/ai-videos/opus-5-5/majidmanzarpour-927543?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos) · [Bài đăng gốc](https://x.com/majidmanzarpour/status/2102476258948927543)

- **Danh mục:** Motion graphics
- **Bản làm lại dùng:** Canvas
- **Tác giả:** [@majidmanzarpour](https://x.com/majidmanzarpour)

Trang gốc (chưa dịch): [prompts/majidmanzarpour-927543.md](../prompts/majidmanzarpour-927543.md)

## Prompt (tiếng Việt)

```text
Hãy tạo một file HTML tự chứa duy nhất render một phù thủy pixel art có animation đang niệm phép, dùng vanilla JavaScript và Canvas 2D. Không tài nguyên bên ngoài, không thư viện, không request mạng.

RENDERING
- Vẽ mọi thứ lên một offscreen canvas ở độ phân giải logic cố định 128x96, rồi blit lên một canvas hiển thị toàn màn hình, scale theo hệ số nguyên lớn nhất vừa với cửa sổ, căn giữa, với imageSmoothingEnabled = false và CSS image-rendering: pixelated.
- Mọi thao tác vẽ đều bám vào tọa độ nguyên trên canvas logic. Không vị trí sub-pixel, không khử răng cưa, không gradient, không shadowBlur.
- Bảng màu cố định khoảng 24 mã màu hex: xanh lam/tím đậm cho bầu trời đêm, tông ấm cho áo choàng, 3-4 màu phép thuật sáng. Mọi pixel đều lấy từ bảng màu này.

NHÂN VẬT
- Dựng phù thủy theo kiểu procedural từ các hình chữ nhật tô đầy và các dải pixel, khoảng 24x32 pixel logic: mũ nhọn có chỗ gập, râu dài, áo choàng hai sắc độ với viền tối hơn, cây gậy có viên đá quý ở đầu.
- Tham số hóa tư thế (góc gậy, độ giơ tay, độ nghiêng đầu, độ đung đưa áo choàng). Animate các tham số một cách mượt, rồi lượng tử hóa về lưới pixel mỗi khung hình để chuyển động mang cảm giác animation pixel 8-12 fps dù vòng lặp chạy ở 60fps.

ANIMATION
- State machine lặp: IDLE (nhún 2 khung hình, râu đung đưa) -> CHARGE (gậy giơ lên, viên đá chập chờn, tia lửa xoắn ốc vào trong) -> CAST (bùng sáng, đạn phép bắn ngang qua cảnh, rung màn hình 1-2 pixel) -> RECOVER (trở về trạng thái nghỉ). Ease các tham số tư thế giữa các keyframe.
- Hệ thống hạt dùng pool, không cấp phát: cấp phát trước và tái sử dụng. Tia lửa quay quanh viên đá trong CHARGE, nổ tung ra ngoài khi CAST, mỗi hạt bước chỉ số bảng màu từ trắng sang màu phép thuật sang tối trước khi biến mất. Bám vị trí hạt vào lưới khi vẽ.
- Update theo bước thời gian cố định 60hz, render bằng rAF. Không cấp phát object nào bên trong vòng lặp.

CẢNH
- Nền tối giản: bầu trời tối, vài ngôi sao 1px lấp lánh, mặt trăng, đường nền đá. Hình bóng nhân vật phải đọc rõ ràng.
- Rim light 1px tinh tế trên phù thủy phát ra từ viên đá, sáng dần lên trong CHARGE và CAST.

CHUẨN CHẤT LƯỢNG
- Pixel sắc nét ở mọi kích thước cửa sổ, lặp liền mạch, 60fps ổn định, hình bóng dễ đọc. Phải trông như một sprite animation 16-bit được trau chuốt, không phải hình vector bị thu nhỏ.
```

## Prompt gốc

```text
Create a single self-contained HTML file that renders an animated pixel art wizard casting a spell, using vanilla JavaScript and Canvas 2D. No external assets, libraries, or network requests.

RENDERING
- Draw everything to an offscreen canvas at a fixed logical resolution of 128x96, then blit to a fullscreen display canvas scaled by the largest integer factor that fits the window, centered, with imageSmoothingEnabled = false and CSS image-rendering: pixelated.
- All drawing snaps to integer coordinates on the logical canvas. No sub-pixel positions, anti-aliasing, gradients, or shadowBlur.
- Fixed palette of ~24 hex colors: deep blues/purples for night sky, warm robe tones, 3-4 bright magic colors. Every pixel comes from this palette.

CHARACTER
- Build the wizard procedurally from filled rects and pixel runs, ~24x32 logical pixels: pointed hat with a bend, long beard, two-shade robe with darker outline, staff with a gem at the tip.
- Parameterize the pose (staff angle, arm raise, head tilt, robe sway). Animate parameters smoothly, then quantize to the pixel grid each frame so motion reads at an 8-12 fps pixel animation feel even though the loop runs at 60fps.

ANIMATION
- Looping state machine: IDLE (2-frame bob, beard sway) -> CHARGE (staff raises, gem flickers, sparks spiral inward) -> CAST (bright burst, projectile fires across the scene, 1-2 pixel screen shake) -> RECOVER (settle back). Ease pose parameters between keyframes.
- Pooled allocation-free particle system: preallocate and reuse. Sparks orbit the gem during CHARGE, explode outward on CAST, each particle stepping its palette index from white to magic color to dark before despawn. Snap particle positions to the grid when drawing.
- Fixed 60hz timestep update with rAF rendering. Zero object allocation inside the loop.

SCENE
- Minimal background: dark sky, a few twinkling 1px stars, moon, stone floor line. Character silhouette must read clearly.
- Subtle 1px rim light on the wizard from the gem, brightening during CHARGE and CAST.

QUALITY BAR
- Crisp pixels at any window size, seamless loop, stable 60fps, readable silhouette. Should look like a polished 16-bit sprite animation, not vector shapes scaled down.
```
