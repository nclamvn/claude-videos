# Video Opus 5.5 của @aayush4soni

[▶ Xem bản gốc và bản làm lại trực tiếp trên Skillry](https://skillry.dev/ai-videos/opus-5-5/aayush4soni-644283?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos) · [Bài đăng gốc](https://x.com/aayush4soni/status/2104181266459644283)

- **Danh mục:** Cảnh 3D
- **Bản làm lại dùng:** Three.js · Canvas
- **Tác giả:** [@aayush4soni](https://x.com/aayush4soni)

> Tác giả không công bố đầy đủ prompt. Dưới đây là nội dung bài đăng gốc của họ.

Trang gốc (chưa dịch): [prompts/aayush4soni-644283.md](../prompts/aayush4soni-644283.md)

## Prompt (tiếng Việt)

```text
Gia đình tôi đang tính xây nhà, và thứ duy nhất chúng tôi có là bản vẽ mặt bằng. Tôi muốn thấy khi xây xong nó sẽ thực sự trông thế nào: màu sắc, bố cục và thiết kế nào hợp nhất.

Thế là tôi đưa bản vẽ cho Claude Opus 5.5 và nhờ nó dựng một bản xem 3D của ngôi nhà.

Đây là một trong những thứ hữu ích nhất tôi làm được gần đây. Giờ chúng tôi có thể đi xuyên qua ngôi nhà trước khi đặt viên gạch đầu tiên, và khi muốn thử một màu hay một bố cục khác, tôi chỉ cần yêu cầu thay đổi.

Trong video: phòng khách, phòng ngủ, và sân thượng lúc chạng vạng, tất cả ở tầm mắt.

Cách nó hoạt động:

• Tôi đưa cho nó file PDF bản vẽ mặt bằng 5 trang và một ảnh tham khảo mặt tiền ngôi nhà.
• Nó đọc bản vẽ và dựng lại từng tầng: tường, cửa đi, cửa sổ và cầu thang.
• Chỗ nào kích thước ghi trên bản vẽ không khớp với bức tường được vẽ, nó đánh dấu lại (15 chỗ) thay vì lặng lẽ đoán.
• Nó tự bày nội thất cho mọi phòng: hơn 500 món đồ nội thất, đồ trang trí và đèn.
• Mọi thứ chạy trên trình duyệt web bằng three.js. Không Blender, không game engine. Bạn có thể đi xuyên qua nhà như chơi game, dưới ánh sáng ban ngày hoặc buổi tối, và đèn thực sự chiếu sáng các phòng.
• Nó coi đây là một dự án phần mềm thật sự: ~37k dòng JavaScript, 185 unit test, 56 test trên trình duyệt, và quay video tất định (render cùng một khung hình hai lần, ra pixel y hệt nhau).
• Nó còn tự lần ra một bug của chính nó: ánh sáng của một phòng thay đổi tùy theo bạn đi vào từ phòng nào.
• Nó chia việc cho các sub-agent. Từ đầu đến cuối mất khoảng hai ngày.

Phần của tôi là các quyết định: mỗi phòng dùng để làm gì, phong cách, và những thay đổi tôi muốn.
```

## Prompt gốc

```text
My family is planning to build a house, and all we had was the floor plan. I wanted to see how it would really look once it's built: which colors, layout and design would suit it best.

So I gave the plan to Claude Opus 5.5 and asked it to create a 3D view of the house.

It's one of the most useful things I've created recently. We can now walk through the house before a single brick is laid, and when we want to try a different color or layout, I just ask for the change.

In the video: the hall, room, and the terrace at dusk, all at eye height.

How it worked:

• I gave it the 5-page floor-plan PDF and one reference image for the front of the house.
• It read the drawings and rebuilt every floor: walls, doors, windows and stairs.
• Where a printed size didn't match the drawn wall, it flagged it (15 places) instead of quietly guessing.
• It furnished every room itself: 500+ pieces of furniture, decor and lighting.
• Everything runs in a web browser with three.js. No Blender, no game engine. You can walk through it like a game, in daylight or evening light, and the lamps actually light the rooms.
• It treated it like a real software project: ~37k lines of JavaScript, 185 unit tests, 56 browser tests, and deterministic video capture (render the same frame twice, get identical pixels).
• It even tracked down a bug of its own: a room's lighting changed depending on which room you walked in from.
• It split the work across sub-agents. Start to finish took about two days.

My part was the decisions: what each room is for, the style, and the changes I wanted.
```
