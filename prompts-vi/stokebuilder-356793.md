# Video Opus 5.5 của @stokebuilder

[▶ Xem bản gốc và bản làm lại trực tiếp trên Skillry](https://skillry.dev/ai-videos/opus-5-5/stokebuilder-356793?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos) · [Bài đăng gốc](https://x.com/stokebuilder/status/2103896101120356793)

- **Danh mục:** Video giải thích
- **Bản làm lại dùng:** Canvas · SVG
- **Tác giả:** [@stokebuilder](https://x.com/stokebuilder)

> Tác giả không công bố đầy đủ prompt. Dưới đây là nội dung bài đăng gốc của họ.

Trang gốc (chưa dịch): [prompts/stokebuilder-356793.md](../prompts/stokebuilder-356793.md)

## Prompt (tiếng Việt)

```text
Tôi đã dùng Opus 5.5 để tạo 50 animation cho podcast về những khái niệm cực kỳ khó hình dung như Jev for Legal.  Hoàn toàn choáng ngợp.

Chúng ta sắp chứng kiến một cơn bùng nổ podcast có hình ảnh, toàn bộ loại hình này sắp thay đổi

Chia sẻ prompt của tôi bên dưới.

【Ghi chú sản xuất bổ sung của tác giả】
Hãy đi qua toàn bộ bản dựng [episode] và thêm animation cùng đồ họa toàn màn hình ở bất cứ chỗ nào chúng có ích. Hãy mạnh tay và thà thừa còn hơn thiếu: 35–50 khoảnh khắc, ít nhất 2 cho mỗi chương. Mục tiêu là lấp đầy những đoạn trống chỉ có người nói, giải thích ý tưởng, và tạo visual hook.

Phong cách. Chọn một thẩm mỹ thật sự thú vị và cực kỳ ngầu, xây bằng JavaScript với HyperFrames và lắp ráp trong Tesseract. Cảm hứng (tất cả là JS, không có asset hình ảnh):

https://x.com/Voxyz_ai/status/2102531681450119426: giấy, nhãn băng máy đánh chữ, nét vẽ tay
https://x.com/donaldjewkes/status/2102801274173587569: halftone, manga và in pixel, chữ dữ liệu kinetic

Giữ trong brand LegalQuants (đọc brands/legalquants/): chỉ than chì, trắng và đen, Arial, và lockup được cung cấp ở góc trên bên phải, đứng yên. Hãy viết một style bible chung và một bộ component trước, để mọi animation trông như cùng một chương trình.

Những khoảnh khắc tôi chắc chắn muốn có:

[LIST]

Quy tắc

Bất cứ khi nào có thứ gì lên toàn màn hình (animation, chia sẻ màn hình hay ảnh tĩnh), một trong hai chúng tôi nằm ở góc dạng picture-in-picture, dưới cùng bên phải, đi theo người đang nói.
Không punch-in hay zoom vào camera. Giữ mỗi người nói tương đối ở giữa.
Chữ phải đúng nguyên văn hoặc trung thành với những gì được nói. Không bao giờ bịa sự kiện, con số hay trích dẫn.
Đồng bộ các nhịp của mỗi animation với lời nói.
Giữ mỗi đồ họa nằm trong một đoạn âm thanh liền mạch không cắt, và chừa vài giây hình mặt người giữa các đồ họa.

Quy trình

Một agent Opus 5.5 ở mức effort extra-high tìm mọi timestamp nơi animation có thể lấp chỗ trống và móc người xem, kèm một ý tưởng cho mỗi chỗ.
Opus 5.5 ở mức effort medium dựng từng animation.
Opus 5.5 ở mức effort extra-high chấm mỗi cái một lần về độ nhất quán brand với các cái khác, độ hấp dẫn thị giác, mức liên quan tới mạch kể và óc phán đoán sáng tạo.
Chỉ những cue mà giám khảo cho là tệ hết mức mới quay lại để sửa. Không có vòng lặp làm lại hàng loạt.
Lắp ráp toàn bộ bản dựng với PiP được gắn cứng vào mọi hình ảnh toàn màn hình, và đưa tôi một thư mục chứa từng animation riêng lẻ.
```

## Prompt gốc

```text
I used Opus 5.5 to generate 50 podcast animations for extremely hard to visualize concepts like Jev for Legal.  Absolutely blown away. 

We're about to see an explosion of visual podcasts, this entire medium is about to shift 

Sharing my prompt below.

【作者补充制作说明】
Go through the entire [episode] cut and add full-screen animations and graphics wherever they help. Be aggressive and over-inclusive: 35–50 moments, at least 2 per chapter. The goal is to fill empty talking-head time, explain ideas, and create visual hooks.

Style. Pick an aesthetic that's genuinely interesting and very, very cool, built in JavaScript with HyperFrames and assembled in Tesseract. Inspiration (all JS, no image assets):

https://x.com/Voxyz_ai/status/2102531681450119426: paper, typewriter-tape labels, hand-drawn marks
https://x.com/donaldjewkes/status/2102801274173587569: halftone, manga and pixel print, kinetic data type

Stay inside the LegalQuants brand (read brands/legalquants/): charcoal, white and black only, Arial, and the supplied lockup top-right, static. Write a shared style bible and a component kit first, so every animation looks like the same show.

Moments I definitely want:

[LIST]

Rules

Whenever anything goes full-screen (animation, screen share or still), one of us is in a corner picture-in-picture, bottom-right, following whoever is talking.
No punch-ins or zooming on the cameras. Keep each speaker relatively centered.
Copy must be verbatim or faithful to what's said. Never invent facts, numbers or quotes.
Sync each animation's beats to the spoken words.
Keep each graphic inside one uncut stretch of audio, and leave a few seconds of faces between graphics.

Process

An Opus 5.5 agent at extra-high effort finds every timestamp where an animation could fill space and hook the viewer, with a concept for each.
Opus 5.5 at medium effort builds each animation.
Opus 5.5 at extra-high effort judges each one once on brand consistency with the others, visual interest, relevance to the narrative and creative judgment.
Only cues the judge considers egregiously bad go back for a fix. No blanket redo loops.
Assemble the full cut with PiP baked into every full-screen visual, and give me a folder of the individual animations.
```
