# Video Opus 5.5 của @iamtanzil_

[▶ Xem bản gốc và bản làm lại trực tiếp trên Skillry](https://skillry.dev/ai-videos/opus-5-5/iamtanzil-120030?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos) · [Bài đăng gốc](https://x.com/iamtanzil_/status/2103459843831120030)

- **Danh mục:** Motion graphics
- **Bản làm lại dùng:** Canvas · CSS
- **Tác giả:** [@iamtanzil_](https://x.com/iamtanzil_)

Trang gốc (chưa dịch): [prompts/iamtanzil-120030.md](../prompts/iamtanzil-120030.md)

## Prompt (tiếng Việt)

````text
# OBLT E-bike Header

Một header sản phẩm xe đạp điện toàn màn hình (full-viewport), nền tối, phong cách điện ảnh cho thương hiệu **OBLT**, dựng bằng React (client component) với CSS thuần và hiệu ứng spotlight "x-ray" tương tác bám theo con trỏ: di chuột sẽ xoá dần ảnh ngoại thất của chiếc xe để lộ cấu trúc carbon/hộp số bên trong. Chỉ dùng React (không dùng thư viện animation nào).

## Tech stack (các thư viện thực sự được import)
- Chỉ React: `useRef`, `useState` và kiểu `MouseEvent`. Không framer-motion, không GSAP, không thư viện icon. Toàn bộ animation là CSS keyframes viết tay cộng với `mask-image` CSS inline.
- Icon SVG (mũi tên của nút CTA) được viết inline bằng tay, không lấy từ thư viện.

## Font và style toàn cục
- Một Google font duy nhất, import bên trong một khối `<style>`:
  ```
  @import url('https://fonts.googleapis.com/css2?family=Almarai:wght@300;400;700;800&display=swap');
  ```
- Font stack: `"Almarai","Helvetica Neue",Helvetica,Arial,sans-serif`.
- `-webkit-font-smoothing: antialiased`. `box-sizing: border-box` áp cho phần tử gốc và mọi phần tử con (giới hạn trong `.vt-header`, không bao giờ áp toàn cục).

## Container của section
- Phần tử gốc `<header className="vt-header">` là phần tử theo dõi chuột (handler: `onMouseEnter`, `onMouseMove`, `onMouseLeave`).
- Style: `position: relative; display: flex; flex-direction: column; min-height: 100vh; overflow: hidden; padding: 32px 56px 44px; background-color: #272727; color: #fff;`.
- Luồng dọc bên trong: nav trên cùng, rồi một "stage" spacer co giãn (flex-grow), rồi phần nội dung dưới cùng ghim sát đáy.

## Cấu trúc, từng phần một

### 1. Nền reveal (`.vt-bg`, absolute inset:0, z-index 0, pointer-events:none)
Ba lớp xếp chồng:
- **Ảnh ngoại thất nền** (`.vt-bg-img`): ảnh ngoại thất đầy đủ của chiếc xe, `object-fit: cover; object-position: center;`, phủ kín lớp. `user-select:none`, `-webkit-user-drag:none`, `referrerPolicy="no-referrer"`.
- **Lớp x-ray** (`.vt-bg-xray`, z-index 1): chứa ảnh x-ray/bên trong của xe (cùng kiểu cover/center). Lớp này được mask bằng một radial gradient điều khiển theo vị trí con trỏ (xem phần Animation). `will-change: -webkit-mask-image, mask-image;` và `transition: -webkit-mask-image .12s linear, mask-image .12s linear;`.
- **Lớp phủ tối (veil)** (`.vt-bg-veil`, z-index 2): gradient làm tối theo chiều dọc để chữ ở trên và dưới luôn dễ đọc:
  ```
  linear-gradient(180deg, rgba(39,38,38,.62) 0%, rgba(39,38,38,.10) 26%, rgba(39,38,38,.10) 60%, rgba(39,38,38,.82) 100%)
  ```

### 2. Nav trên cùng (`.vt-nav`, z-index 30)
- `display: grid; grid-template-columns: 1fr auto 1fr; align-items: center; gap: 24px;`.
- **Logo** (bên trái, `.vt-logo`): chữ `OBLT` theo sau là một span `.`. `font-size: 28px; font-weight: 700; letter-spacing: 0.5px; color: #E0E1CC;` (dấu chấm cũng là `#E0E1CC`).
- **Menu giữa** (`.vt-menu`, gap 40px): ba link `E-bikes`, `Features`, `Connect`. Mỗi link: `font-size: 16px; font-weight: 400; letter-spacing: .3px; color: #E0E1CC; opacity: .85; transition: opacity .2s ease;` khi hover → opacity 1.
- **Cụm bên phải** (`.vt-nav-right`, gap 18px): một link explore viết hoa cộng với nút hamburger.
  - Link `.vt-explore` có chữ `Explore the bike`: `font-size: 14px; font-weight: 700; letter-spacing: 1.5px; text-transform: uppercase; color: #E0E1CC;` khi hover → opacity .65.
  - **Hamburger** (`.vt-burger`, ẩn trên desktop): 34×34px, ba thanh `#E0E1CC` kích thước 22×2px, radius 2px, gap 5px. Khi `.open`: thanh 1 `translateY(7px) rotate(45deg)`, thanh 2 `opacity:0`, thanh 3 `translateY(-7px) rotate(-45deg)`. Transition `transform .25s ease, opacity .2s ease`.
- **Dropdown mobile** (`.vt-mobile-menu`, chỉ render khi `menuOpen`): định vị absolute ngay dưới nav (`top:100%; margin-top:16px; z-index:40`), `background: rgba(20,19,19,.97); backdrop-filter: blur(10px); border: 1px solid rgba(255,255,255,.1); border-radius: 16px; padding: 8px 18px;`. Các link (`E-bikes`, `Features`, `Connect`, `Explore the bike`): `color:#E0E1CC; font-size:18px; padding:14px 4px; border-bottom:1px solid rgba(255,255,255,.08)`; link cuối `border-bottom:none; font-weight:700`. Bấm vào link nào cũng đóng menu.

### 3. Stage spacer (`.vt-stage`, z-index 30, `flex: 1 1 0%`)
- `display: flex; align-items: flex-start; justify-content: flex-end; padding-top: 22px;`. Trong markup hiện tại, đây là một spacer `aria-hidden` rỗng (style chấm nhấp nháy `.vt-hint` có trong CSS nhưng phần tử hint không được render).
- (Tham khảo: `.vt-hint` được style thành nhãn viết hoa 11px/600 kèm một chấm tròn 36px, `border:1px solid rgba(46,211,176,.5); color:#2ed3b1;` chạy `vtPulse 1.8s ease-in-out infinite`.)

### 4. Nội dung dưới cùng (`.vt-bottom`, z-index 30)
Grid 12 cột: `grid-template-columns: repeat(12, 1fr); align-items: end; gap: 18px 32px;`.
- **Headline** (`.vt-headline`, `grid-column: 1 / span 8`): một `<h1>` chứa component hiện chữ so le theo từng từ. Style của h1: `color: #E0E1CC; font-weight: 500; font-size: clamp(36px, 7vw, 116px); line-height: 0.85; letter-spacing: -0.07em; white-space: nowrap; margin:0;`. Nội dung: **Ready For The Ride**.
- **Khối bên phải** (`.vt-right`, `grid-column: 9 / span 4; align-self: end; transform: translateY(22px);`):
  - Đoạn văn (giữ nguyên văn): `An integrated gearbox, battery, and motor engineered in carbon and built to be seen. Every system, in the open.` Style: `font-size: 16px; line-height: 1.2; color: rgba(225,224,204,.7);` xuất hiện bằng `vtFadeUp .8s cubic-bezier(.16,1,.3,1) both` với `animation-delay: .5s`.
  - **Nút CTA** (`.vt-cta`): nhãn **Reserve yours** cộng với một mũi tên trong hình tròn. Dạng viên thuốc (pill): `color:#000; background:#E0E1CC; border:none; border-radius:9999px; padding:6px 6px 6px 22px; font-size: clamp(14px, 1vw, 16px); font-weight:500; display:inline-flex; align-items:center; gap:10px;`. Xuất hiện bằng `vtFadeUp .8s cubic-bezier(.16,1,.3,1) both`, `animation-delay: .7s`. Hover → `gap: 14px`. Hình tròn bên trong `.circ`: 40×40px, `border-radius:50%; background:#000;` chứa SVG (stroke `#E0E1CC`); khi hover nút, `.circ` phóng to lên `1.1` (`transition: transform .25s ease`).

## Asset (mọi URL)
- Ảnh ngoại thất (lớp nền): `https://cdn.jiro.build/ARS/OBLT%20E%20Bike/bike-exterior.png`
- Ảnh x-ray / bên trong (lớp được hé lộ): `https://cdn.jiro.build/ARS/OBLT%20E%20Bike/bike-xray-original.png`
- Icon mũi tên CTA: SVG inline, 16×16, `viewBox="0 0 24 24"`, `stroke="currentColor"`, `stroke-width="2.2"`, đầu nét và góc nối bo tròn, path:
  ```
  M5 12h14M13 6l6 6-6 6
  ```

## Animation

### Spotlight "x-ray" theo con trỏ (tương tác đặc trưng)
- State: `hovering` (bool) và `pos` ({x,y} tính bằng px, tương đối so với bounding rect của section). `handleMove` tính `e.clientX - rect.left`, `e.clientY - http://rect.top`.
- Hằng số: `RADIUS = 165` px (bán kính spotlight), `FEATHER = 45` px (viền mềm). Bán kính phần trong suốt hoàn toàn = `RADIUS - FEATHER` = 120px.
- `maskImage` / `WebkitMaskImage` của lớp x-ray được đặt inline. Khi đang hover:
  ```
  radial-gradient(circle 165px at {x}px {y}px, #000 0, #000 120px, transparent 165px)
  ```
  Khi không hover (thu về bằng không):
  ```
  radial-gradient(circle 0px at 50% 50%, transparent 0, transparent 0)
  ```
- Mask chuyển đổi với `.12s linear` để vùng hé lộ bám theo con trỏ một cách mượt mà. LƯU Ý: trong CSS `mask`, vùng đục (`#000`) GIỮ LẠI lớp đó, nên vòng tròn hé lộ ảnh x-ray còn phần còn lại của lớp bị ẩn (để lộ ảnh ngoại thất bên dưới).

### Headline kéo lên theo từng từ (component `WordsPullUp`)
- Tách headline theo dấu cách; mỗi từ là một span `inline-block` (`margin-right: 0.22em`, từ cuối là 0). Mỗi từ chạy animation `wpuUp` với `cubic-bezier(.16,1,.3,1) both`, mặc định `duration = 0.6s`, so le theo `delayStep = 0.08s` (`animationDelay: i * 0.08s`).
- Keyframes:
  ```
  @keyframes wpuUp { from { transform: translateY(20px); opacity: 0; } to { transform: translateY(0); opacity: 1; } }
  ```
- Dấu sao chỉ số trên tuỳ chọn (`.wpu-ast`, `font-size:0.31em; vertical-align:top; top:0.15em; left:-0.05em;`): không bật ở đây (`asterisk` mặc định là false).
- Tôn trọng `@media (prefers-reduced-motion: reduce)` → `.wpu-word { animation: none; }`.

### Fade-up cho khối bên phải (`vtFadeUp`)
```
@keyframes vtFadeUp { from { transform: translateY(20px); opacity: 0; } to { transform: translateY(0); opacity: 1; } }
```
Đoạn văn delay `.5s`, CTA delay `.7s`; cả hai đều `.8s cubic-bezier(.16,1,.3,1) both`.

### Pulse (định nghĩa cho chấm hint)
```
@keyframes vtPulse { 0%,100%{transform:scale(1);opacity:.7} 50%{transform:scale(1.12);opacity:1} }
```
Áp dụng `vtPulse 1.8s ease-in-out infinite`.

## Responsive
- **≤1000px**: padding `24px 28px 32px`; nav chuyển thành `1fr auto` (logo + cụm phải); ẩn `.vt-menu` ở giữa và `.vt-explore`; hiện hamburger; `.vt-bottom` gộp thành một cột (`gap:16px`); headline và khối phải chiếm toàn bộ chiều ngang; `.vt-right` `transform:none; align-self:start; margin-top:4px; max-width:520px`.
- **≤600px**: padding `18px 20px 26px`; logo `font-size:22px`; headline `white-space:normal; font-size: clamp(40px, 13vw, 72px); line-height:0.92`; đoạn văn `font-size:15px; margin-bottom:16px`; CTA `font-size:14px; padding:5px 5px 5px 20px`; `.circ` 36×36px.

## Nguyên tắc thiết kế chính
- Sân khấu tối (`#272727`) với một màu nhấn kem ấm duy nhất (`#E0E1CC`) và một màu nhấn teal (`#2ed3b1`) dành riêng cho hint nhấp nháy (tuỳ chọn).
- Việc hé lộ sản phẩm CHÍNH LÀ hero: con trỏ đóng vai đèn pin x-ray soi qua cặp ảnh xếp lớp.
- Headline cỡ lớn kiểu tạp chí (line-height 0.85, tracking sát `-0.07em`) neo ở góc dưới bên trái; nội dung phụ + CTA ở góc dưới bên phải.
- Hiệu ứng xuất hiện so le, có easing (`cubic-bezier(.16,1,.3,1)`) để tạo thứ bậc.

## Những lỗi thường gặp cần tránh
- Đừng đảo ngược logic mask: vùng đục `#000` trong radial gradient HÉ LỘ lớp x-ray; vòng trong suốt thì ẩn nó. Làm ngược sẽ khiến phần bên trong hiện ở khắp nơi trừ chỗ dưới con trỏ.
- Giữ `RADIUS - FEATHER` (120px) làm điểm dừng đặc bên trong và `RADIUS` (165px) làm điểm dừng trong suốt; dải 45px đó chính là viền mềm.
- Toạ độ chuột phải tương đối so với rect của section (`getBoundingClientRect`), không phải so với viewport.
- Transition của mask chỉ là `.12s linear`; transition dài hơn hoặc có easing sẽ khiến spotlight có cảm giác bị trễ.
- `white-space: nowrap` trên headline là cố ý ở desktop; chỉ chuyển sang `normal` ở ≤600px.
- Giới hạn mọi reset và `@import` font Almarai trong component; không động vào `body`/`html` toàn cục.

## Tiêu đề trang
OBLT — Ready For The Ride

## Tích hợp (an toàn khi build, không được bỏ qua)
- Thêm section này dưới dạng một file component **mới** với tên duy nhất. Không sửa hay ghi đè bất kỳ file hiện có nào, trừ việc thêm import và render nó.
- Render nó **sau** tất cả các section hiện có; giữ nguyên mọi section đã dựng trước đó, không bao giờ thay thế hay xoá chúng.
- Nếu chưa có project, hãy tạo một app React + Tailwind tối giản; nếu đã có, dùng nguyên trạng, không scaffold lại hay thay đổi config hoặc phiên bản Tailwind/build.
- Giữ nó tự đóng gói: giới hạn font và mọi reset trong section này; không bao giờ đặt style toàn cục cho `body`/`html`/`*` hay font toàn cục.
- Chỉ cài những thư viện mà section này nêu tên.
````

## Prompt gốc

````text
# OBLT E-bike Header

A full-viewport, dark, cinematic e-bike product header for the brand **OBLT**, built in React (client component) with pure CSS and an interactive cursor-following "x-ray" spotlight reveal — moving the mouse wipes away the bike's exterior photo to expose its internal carbon/gearbox structure underneath. Built with React only (no animation libraries).

## Tech stack (libraries actually imported)
- React only — `useRef`, `useState`, and the `MouseEvent` type. No framer-motion, no GSAP, no icon library. All animation is hand-written CSS keyframes + an inline CSS `mask-image`.
- SVG icon (the CTA arrow) is hand-inlined, not from a library.

## Fonts & global styles
- Single Google font, imported inside a `<style>` block:
  ```
  @import url('https://fonts.googleapis.com/css2?family=Almarai:wght@300;400;700;800&display=swap');
  ```
- Font stack: `"Almarai","Helvetica Neue",Helvetica,Arial,sans-serif`.
- `-webkit-font-smoothing: antialiased`. `box-sizing: border-box` applied to the root and all descendants (scoped to `.vt-header`, never global).

## Section container
- Root `<header className="vt-header">` is the mouse-tracking element (handlers: `onMouseEnter`, `onMouseMove`, `onMouseLeave`).
- Styles: `position: relative; display: flex; flex-direction: column; min-height: 100vh; overflow: hidden; padding: 32px 56px 44px; background-color: #272727; color: #fff;`.
- Internal vertical flow: top nav, then a flex-grow spacer "stage", then bottom content pinned to the base.

## Structure, section by section

### 1. Reveal background (`.vt-bg`, absolute inset:0, z-index 0, pointer-events:none)
Three stacked layers:
- **Base exterior image** (`.vt-bg-img`): the full bike exterior photo, `object-fit: cover; object-position: center;`, fills the layer. `user-select:none`, `-webkit-user-drag:none`, `referrerPolicy="no-referrer"`.
- **X-ray layer** (`.vt-bg-xray`, z-index 1): contains the bike x-ray/internal image (same cover/center sizing). This layer is masked by a radial gradient driven by cursor position (see Animations). `will-change: -webkit-mask-image, mask-image;` and `transition: -webkit-mask-image .12s linear, mask-image .12s linear;`.
- **Veil overlay** (`.vt-bg-veil`, z-index 2): a vertical darkening gradient so text stays legible top & bottom:
  ```
  linear-gradient(180deg, rgba(39,38,38,.62) 0%, rgba(39,38,38,.10) 26%, rgba(39,38,38,.10) 60%, rgba(39,38,38,.82) 100%)
  ```

### 2. Top nav (`.vt-nav`, z-index 30)
- `display: grid; grid-template-columns: 1fr auto 1fr; align-items: center; gap: 24px;`.
- **Logo** (left, `.vt-logo`): text `OBLT` followed by a `.` span. `font-size: 28px; font-weight: 700; letter-spacing: 0.5px; color: #E0E1CC;` (dot is also `#E0E1CC`).
- **Center menu** (`.vt-menu`, gap 40px): three links — `E-bikes`, `Features`, `Connect`. Each: `font-size: 16px; font-weight: 400; letter-spacing: .3px; color: #E0E1CC; opacity: .85; transition: opacity .2s ease;` hover → opacity 1.
- **Right cluster** (`.vt-nav-right`, gap 18px): an uppercase explore link plus a hamburger button.
  - `.vt-explore` link text: `Explore the bike` — `font-size: 14px; font-weight: 700; letter-spacing: 1.5px; text-transform: uppercase; color: #E0E1CC;` hover → opacity .65.
  - **Hamburger** (`.vt-burger`, hidden on desktop): 34×34px, three `#E0E1CC` bars 22×2px, radius 2px, gap 5px. On `.open`: bar 1 `translateY(7px) rotate(45deg)`, bar 2 `opacity:0`, bar 3 `translateY(-7px) rotate(-45deg)`. Transition `transform .25s ease, opacity .2s ease`.
- **Mobile dropdown** (`.vt-mobile-menu`, rendered only when `menuOpen`): absolutely positioned below the nav (`top:100%; margin-top:16px; z-index:40`), `background: rgba(20,19,19,.97); backdrop-filter: blur(10px); border: 1px solid rgba(255,255,255,.1); border-radius: 16px; padding: 8px 18px;`. Links (`E-bikes`, `Features`, `Connect`, `Explore the bike`): `color:#E0E1CC; font-size:18px; padding:14px 4px; border-bottom:1px solid rgba(255,255,255,.08)`; last link `border-bottom:none; font-weight:700`. Each link closes the menu on click.

### 3. Stage spacer (`.vt-stage`, z-index 30, `flex: 1 1 0%`)
- `display: flex; align-items: flex-start; justify-content: flex-end; padding-top: 22px;`. In the current markup it is an empty `aria-hidden` spacer (the `.vt-hint` pulsing-dot styles exist in CSS but the hint element is not rendered).
- (Reference: `.vt-hint` styled as an uppercase 11px/600 label with a 36px circle dot, `border:1px solid rgba(46,211,176,.5); color:#2ed3b1;` running `vtPulse 1.8s ease-in-out infinite`.)

### 4. Bottom content (`.vt-bottom`, z-index 30)
12-column grid: `grid-template-columns: repeat(12, 1fr); align-items: end; gap: 18px 32px;`.
- **Headline** (`.vt-headline`, `grid-column: 1 / span 8`): `<h1>` containing the word-stagger component. h1 style: `color: #E0E1CC; font-weight: 500; font-size: clamp(36px, 7vw, 116px); line-height: 0.85; letter-spacing: -0.07em; white-space: nowrap; margin:0;`. Text: **Ready For The Ride**.
- **Right block** (`.vt-right`, `grid-column: 9 / span 4; align-self: end; transform: translateY(22px);`):
  - Paragraph (verbatim): `An integrated gearbox, battery, and motor engineered in carbon and built to be seen. Every system, in the open.` Style: `font-size: 16px; line-height: 1.2; color: rgba(225,224,204,.7);` animates in via `vtFadeUp .8s cubic-bezier(.16,1,.3,1) both` with `animation-delay: .5s`.
  - **CTA button** (`.vt-cta`): label **Reserve yours** plus a circular arrow. Pill: `color:#000; background:#E0E1CC; border:none; border-radius:9999px; padding:6px 6px 6px 22px; font-size: clamp(14px, 1vw, 16px); font-weight:500; display:inline-flex; align-items:center; gap:10px;`. Animates via `vtFadeUp .8s cubic-bezier(.16,1,.3,1) both`, `animation-delay: .7s`. Hover → `gap: 14px`. Inner circle `.circ`: 40×40px, `border-radius:50%; background:#000;` containing the SVG (stroke `#E0E1CC`); on button hover `.circ` scales to `1.1` (`transition: transform .25s ease`).

## Assets (every URL)
- Exterior photo (base layer): `https://cdn.jiro.build/ARS/OBLT%20E%20Bike/bike-exterior.png`
- X-ray / internals photo (revealed layer): `https://cdn.jiro.build/ARS/OBLT%20E%20Bike/bike-xray-original.png`
- CTA arrow icon: inline SVG, 16×16, `viewBox="0 0 24 24"`, `stroke="currentColor"`, `stroke-width="2.2"`, round caps/joins, path:
  ```
  M5 12h14M13 6l6 6-6 6
  ```

## Animations

### Cursor "x-ray" spotlight (signature interaction)
- State: `hovering` (bool) and `pos` ({x,y} in px relative to the section's bounding rect). `handleMove` computes `e.clientX - rect.left`, `e.clientY - http://rect.top`.
- Constants: `RADIUS = 165` px (spotlight radius), `FEATHER = 45` px (soft edge). Inner fully-clear radius = `RADIUS - FEATHER` = 120px.
- The x-ray layer's `maskImage` / `WebkitMaskImage` is set inline. When hovering:
  ```
  radial-gradient(circle 165px at {x}px {y}px, #000 0, #000 120px, transparent 165px)
  ```
  When not hovering (collapsed to nothing):
  ```
  radial-gradient(circle 0px at 50% 50%, transparent 0, transparent 0)
  ```
- Mask transitions at `.12s linear` so the reveal trails the cursor smoothly. NOTE: in CSS `mask`, opaque (`#000`) areas KEEP the layer — so the circle reveals the x-ray image while the rest of that layer is hidden (showing the exterior beneath).

### Headline word pull-up (`WordsPullUp` component)
- Splits the headline on spaces; each word is an `inline-block` span (`margin-right: 0.22em`, last word 0). Each word animates `wpuUp` with `cubic-bezier(.16,1,.3,1) both`, default `duration = 0.6s`, staggered by `delayStep = 0.08s` (`animationDelay: i * 0.08s`).
- Keyframes:
  ```
  @keyframes wpuUp { from { transform: translateY(20px); opacity: 0; } to { transform: translateY(0); opacity: 1; } }
  ```
- Optional superscript asterisk (`.wpu-ast`, `font-size:0.31em; vertical-align:top; top:0.15em; left:-0.05em;`) — not enabled here (`asterisk` defaults false).
- Respects `@media (prefers-reduced-motion: reduce)` → `.wpu-word { animation: none; }`.

### Fade-up for right block (`vtFadeUp`)
```
@keyframes vtFadeUp { from { transform: translateY(20px); opacity: 0; } to { transform: translateY(0); opacity: 1; } }
```
Paragraph delay `.5s`, CTA delay `.7s`; both `.8s cubic-bezier(.16,1,.3,1) both`.

### Pulse (defined for hint dot)
```
@keyframes vtPulse { 0%,100%{transform:scale(1);opacity:.7} 50%{transform:scale(1.12);opacity:1} }
```
Applied `vtPulse 1.8s ease-in-out infinite`.

## Responsive
- **≤1000px**: padding `24px 28px 32px`; nav becomes `1fr auto` (logo + right); center `.vt-menu` and `.vt-explore` hidden; hamburger shown; `.vt-bottom` collapses to single column (`gap:16px`); headline & right span full width; `.vt-right` `transform:none; align-self:start; margin-top:4px; max-width:520px`.
- **≤600px**: padding `18px 20px 26px`; logo `font-size:22px`; headline `white-space:normal; font-size: clamp(40px, 13vw, 72px); line-height:0.92`; paragraph `font-size:15px; margin-bottom:16px`; CTA `font-size:14px; padding:5px 5px 5px 20px`; `.circ` 36×36px.

## Key design principles
- Dark stage (`#272727`) with a single warm-cream accent (`#E0E1CC`) and a teal accent (`#2ed3b1`) reserved for the (optional) pulse hint.
- The product reveal IS the hero: cursor acts as an x-ray torch over a layered photo pair.
- Editorial oversized headline (line-height 0.85, tight `-0.07em` tracking) anchored bottom-left; supporting copy + CTA bottom-right.
- Staggered, eased (`cubic-bezier(.16,1,.3,1)`) entrance for hierarchy.

## Common mistakes to avoid
- Don't invert the mask logic: opaque `#000` in the radial gradient REVEALS the x-ray layer; the transparent ring hides it. Getting this backwards shows internals everywhere except under the cursor.
- Keep `RADIUS - FEATHER` (120px) as the inner solid stop and `RADIUS` (165px) as the transparent stop — that 45px band is the soft feather.
- Mouse coordinates must be relative to the section rect (`getBoundingClientRect`), not the viewport.
- Mask transition is `.12s linear` only — a longer/eased transition makes the spotlight feel laggy.
- `white-space: nowrap` on the headline is intentional on desktop; only switch to `normal` at ≤600px.
- Scope all resets and the Almarai `@import` to the component; do not touch global `body`/`html`.

## Page title
OBLT — Ready For The Ride

## Integration (build-safety — do not skip)
- Add this section as a **new** component file with a unique name. Don't edit or overwrite any existing file except to add its import and render it.
- Render it **after** all existing sections; keep every previously built section exactly as-is — never replace or remove them.
- If no project exists, create a minimal React + Tailwind app; if one exists, use it as-is — don't re-scaffold or change the Tailwind/build config or version.
- Keep it self-contained: scope its fonts and any resets to this section; never set global `body`/`html`/`*` styles or a global font.
- Install only the libraries this section names.
````
