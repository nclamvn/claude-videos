# Video Opus 5.5 của @_nieGRAMotny_

[▶ Xem bản gốc và bản làm lại trực tiếp trên Skillry](https://skillry.dev/ai-videos/opus-5-5/niegramotny-197521?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos) · [Bài đăng gốc](https://x.com/_nieGRAMotny_/status/2103128800909197521)

- **Danh mục:** Game & tương tác
- **Bản làm lại dùng:** Three.js · GLSL · Canvas · Vật lý
- **Tác giả:** [@_nieGRAMotny_](https://x.com/_nieGRAMotny_)

Trang gốc (chưa dịch): [prompts/niegramotny-197521.md](../prompts/niegramotny-197521.md)

## Prompt (tiếng Việt)

```text
Hãy xây dựng một game đua xe lấy cảm hứng từ Ignition (1997): camera nhìn từ trên xuống theo góc nghiêng,
vật lý thiên về arcade, các xe có cá tính rất khác biệt. Đây phải là một game nguyên bản,
không phải bản sao. Dùng tên nguyên bản, đường đua nguyên bản và không dùng asset gốc nào.

## Stack
- Vite + TypeScript (strict), Three.js để render, không dùng UI framework
  (HUD bằng DOM/CSS thuần).
- Đồ hoạ low-poly sinh bằng code (BoxGeometry, CylinderGeometry, v.v.),
  không dùng model hay texture bên ngoài. Màu đặc và material đơn giản.
- Vật lý 2.5D tự viết, giản lược (di chuyển trên mặt phẳng XZ, độ cao lấy từ địa hình).
  Không dùng physics engine.

## Kiến trúc
- src/game/ (game loop với timestep cố định), src/vehicles/, src/track/, src/ai/,
  src/render/, src/ui/
- Xe được điều khiển bằng dữ liệu: khối lượng, công suất, tốc độ tối đa, độ bám, khả năng lái, khả năng chịu
  va chạm và các tham số boost (cường độ, thời lượng, thời gian nạp lại).
  Một class Vehicle, nhiều cấu hình khác nhau.
- Bất kỳ xe nào cũng có thể do người chơi hoặc AI điều khiển
  (giao diện điều khiển chung: ga, phanh, lái, boost).
- Đường đua dưới dạng dữ liệu: spline đường tâm + bề rộng + danh sách vùng
  (băng, đường tắt, chướng ngại vật). Sinh mesh mặt đường và waypoint cho AI từ đó.

## Xe (tên nguyên bản, không dùng thương hiệu)
Bốn xe. Người chơi chọn một xe ở màn hình chọn xe; 3 xe còn lại
do AI lái.
- Sedan cảnh sát kiểu thập niên 90 (đen trắng, có dàn đèn trên nóc): nặng, ổn định,
  húc mạnh khi va chạm.
- Muscle car mui trần: nhanh nhất trên đường thẳng, bị oversteer khi vào cua.
- Xe monster truck màu đỏ: chậm, nhưng phớt lờ ổ gà và húc văng mọi thứ khác.
- Xe van giao bưu phẩm: chậm, trọng tâm cao, lắc lư khi vào cua.
Khác biệt về cảm giác lái phải thấy rõ ràng. Cả bốn xe đều phải chơi được
và có sức cạnh tranh. Xe chậm hơn được bù lại bằng, chẳng hạn, khả năng chịu va chạm,
khả năng xử lý địa hình, hoặc boost mạnh hơn hay thường xuyên hơn.

## Boost
- Xe nào cũng có boost: một cú tăng tốc ngắn, rõ rệt, vượt quá
  tốc độ tối đa bình thường của xe.
- Boost tự động nạp từ 0 đến 100%. Chỉ dùng được khi đạt 100%.
  Sau khi dùng, thanh đo tụt về 0 và bắt đầu nạp lại.
- Cường độ, thời lượng và thời gian nạp lại là riêng cho từng xe
  (ví dụ muscle car: ngắn và rất mạnh; van: yếu hơn nhưng nạp nhanh;
  monster truck: kéo dài nhưng nạp chậm).
- Hiệu ứng hình ảnh khi boost: lửa ống xả hoặc vệt đuôi, camera hơi
  lùi ra sau.
- AI cũng dùng boost, một cách hợp lý: trên đường thẳng, không dùng trước khúc cua gắt
  hay trên băng.

## Đường đua
Một thị trấn miền núi mang không khí Canada, mùa đông đang chuyển sang lúc băng tan đầu xuân:
- vòng khép kín, mỗi vòng khoảng 60–90 giây
- một thác nước nhìn thấy được từ đường đua và một cây cầu gỗ bắc qua sông
- một chỗ giao cắt đường sắt với đoàn tàu chạy qua định kỳ
  (va chạm = bị hất văng mạnh, không phải game over)
- các mảng băng làm giảm độ bám
- một đường tắt (hẹp, mạo hiểm); trang trí: cây vân sam, nhà gỗ, tuyết
- rào chắn hoặc chướng ngại tự nhiên để xe không bị kẹt ngoài đường đua.
  Cơ chế an toàn: nếu một xe (kể cả bot) bị kẹt quá ~4 s,
  tự động đưa nó về đường đua tại checkpoint gần nhất.

## Gameplay
- 3 vòng, xuất phát đứng yên trên lưới, đếm ngược 3-2-1
- AI đi theo waypoint với phong cách lái tuỳ theo xe,
  rubber-banding nhẹ, tránh chướng ngại vật, không dịch chuyển tức thời (trừ
  cơ chế an toàn đưa về đường đua nói ở trên)
- Trượt hoàn toàn do vật lý (độ bám, tốc độ, băng), không có phanh tay
- Camera: nhìn từ trên xuống ở góc ~50°, bám theo người chơi và hơi nhìn trước
  theo hướng di chuyển
- Điều khiển: phím mũi tên/WASD (ga, phanh/lùi, lái), space = boost
- Các màn hình: bắt đầu → chọn xe (xem trước model + thanh chỉ số, có cả
  boost) → đua → kết quả → chơi lại (có tuỳ chọn đổi xe)

## HUD
- Thứ hạng, vòng, thời gian vòng, vòng nhanh nhất, minimap.
- Thanh boost được tạo kiểu như một bình ắc quy ô tô: vỏ hình chữ nhật với hai cực
  (+/−) ở trên, mức đầy dâng lên khi nạp. Màu chuyển từ đỏ qua
  vàng sang xanh lá. Ở 100%, ắc quy báo hiệu sẵn sàng thật rõ (nhấp nháy hoặc
  phát sáng, nhãn "BOOST" hoặc biểu tượng tia sét). Khi đang boost, thanh đo
  cạn nhanh.

## Ngoài phạm vi của v1
Âm thanh, menu tuỳ chọn, nhiều đường đua, multiplayer, lưu trạng thái.

## Quy trình làm việc
1. Trước tiên đề xuất kế hoạch và cấu trúc file, rồi triển khai theo từng giai đoạn:
   (a) game loop + một xe trên mặt phẳng, có cả boost,
   (b) đường đua, (c) các xe còn lại và AI, (d) chướng ngại vật và tàu,
   (e) chọn xe, HUD với thanh đo ắc quy, và các màn hình.
2. Sau mỗi giai đoạn chạy `npm run build` và sửa lỗi kiểu.
3. Thêm unit test (Vitest) cho vật lý xe, logic boost (nạp,
   khoá khi dưới 100%, reset sau khi dùng) và logic vòng/thứ hạng.
4. Cuối cùng: một README mô tả cách điều khiển và cách thêm đường đua
   hoặc xe mới.

## Tiêu chí nghiệm thu
`npm install && npm run dev` khởi chạy được game. Có thể chọn bất kỳ xe nào trong 4
xe và hoàn thành 3 vòng đấu với 3 bot. Mỗi xe có cảm giác lái khác nhau
và boost khác nhau rõ rệt. Boost chỉ hoạt động khi ắc quy đầy, và bot
cũng dùng boost. Tàu và băng hoạt động. Kết quả hiển thị đúng thứ tự.
Ổn định 60 FPS trên một laptop trung bình.
```

## Prompt gốc

```text
Build a racing game inspired by Ignition (1997): angled top-down camera, arcade-leaning
physics, vehicles with very distinct personalities. This must be an original game,
not a copy. Use an original name, an original track, and zero original assets.

## Stack
- Vite + TypeScript (strict), Three.js for rendering, no UI framework
  (HUD in plain DOM/CSS).
- Low-poly graphics generated in code (BoxGeometry, CylinderGeometry, etc.),
  no external models or textures. Solid colors and simple materials.
- Custom simplified 2.5D physics (movement on the XZ plane, height from terrain).
  No physics engine.

## Architecture
- src/game/ (game loop with fixed timestep), src/vehicles/, src/track/, src/ai/,
  src/render/, src/ui/
- Vehicles are data-driven: mass, power, top speed, grip, steering, collision
  resistance, and boost parameters (strength, duration, recharge time).
  One Vehicle class, different configurations.
- Any vehicle can be controlled by either the player or the AI
  (shared control interface: throttle, brake, steer, boost).
- Track as data: centerline spline + width + list of zones
  (ice, shortcut, obstacle). Generate the road mesh and AI waypoints from it.

## Vehicles (original names, no brands)
Four vehicles. The player picks one on the selection screen; the remaining 3
are driven by the AI.
- 90s-style police sedan (black and white, light bar): heavy, stable,
  pushes hard in collisions.
- Muscle car convertible: fastest on straights, oversteers in corners.
- Red monster truck: slow, but ignores bumps and rams everything else.
- Postal delivery van: slow, high center of gravity, sways in corners.
The handling differences must be clearly noticeable. All four must be playable
and competitive. Slower vehicles compensate with e.g. collision resistance,
terrain handling, or a stronger or more frequent boost.

## Boost
- Every vehicle has a boost: a short, pronounced acceleration beyond its
  normal top speed.
- Boost charges automatically from 0 to 100%. It can only be used at 100%.
  After use, the meter drops to 0 and starts charging again.
- Strength, duration and recharge time are unique to each vehicle
  (e.g. muscle car: short and very strong; van: weaker but recharges fast;
  monster truck: long but slow to recharge).
- Visual effect while boosting: exhaust flame or trail, slight camera
  pull-back.
- The AI also uses boost, sensibly: on straights, not before sharp corners
  or on ice.

## Track
A mountain town with a Canadian feel, winter turning into spring thaw:
- closed loop, roughly 60–90 seconds per lap
- a waterfall visible from the track and a wooden bridge over a river
- a railroad crossing with a train passing periodically
  (collision = strong knockback, not game over)
- ice patches with reduced grip
- one shortcut (tight, risky); decorations: spruce trees, wooden houses, snow
- barriers or natural obstacles so vehicles can't get stuck off the track.
  Failsafe: if a vehicle (including bots) is stuck for more than ~4 s,
  automatically return it to the track at the last checkpoint.

## Gameplay
- 3 laps, standing grid start, 3-2-1 countdown
- AI follows waypoints with a driving style that depends on the vehicle,
  light rubber-banding, avoids obstacles, no teleporting (except the
  failsafe track return described above)
- Sliding comes purely from physics (grip, speed, ice), no handbrake
- Camera: top-down at ~50°, follows the player with a slight look-ahead
  in the direction of travel
- Controls: arrows/WASD (throttle, brake/reverse, steering), space = boost
- Screens: start → vehicle selection (model preview + stat bars, including
  boost) → race → results → restart (with option to change vehicle)

## HUD
- Position, lap, lap time, best lap, minimap.
- Boost meter styled as a car battery: rectangular casing with two terminals
  (+/−) on top, fill level rises as it charges. Color shifts from red through
  yellow to green. At 100% the battery clearly signals readiness (pulsing or
  glow, "BOOST" label or lightning bolt icon). While boosting, the meter
  drains quickly.

## Out of scope for v1
Sound, options menu, multiple tracks, multiplayer, save state.

## Workflow
1. First propose a plan and file structure, then implement in stages:
   (a) game loop + one vehicle on a flat plane, including boost,
   (b) track, (c) remaining vehicles and AI, (d) obstacles and train,
   (e) vehicle selection, HUD with battery meter, and screens.
2. After each stage run `npm run build` and fix type errors.
3. Add unit tests (Vitest) for vehicle physics, boost logic (charging,
   lockout below 100%, reset after use), and lap/position logic.
4. Finally: a README describing the controls and how to add a new track
   or vehicle.

## Acceptance criteria
`npm install && npm run dev` launches the game. You can pick any of the 4
vehicles and complete 3 laps against 3 bots. Each vehicle handles differently
and has a noticeably different boost. Boost only works with a full battery,
and bots use it too. The train and ice work. Results show the correct order.
Stable 60 FPS on an average laptop.
```
