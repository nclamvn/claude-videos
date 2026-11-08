# Video Opus 5.5 của @AstroTheWizard

[▶ Xem bản gốc và bản làm lại trực tiếp trên Skillry](https://skillry.dev/ai-videos/opus-5-5/astrothewizard-618782?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos) · [Bài đăng gốc](https://x.com/AstroTheWizard/status/2103629247751618782)

- **Danh mục:** Video giải thích
- **Bản làm lại dùng:** Canvas
- **Tác giả:** [@AstroTheWizard](https://x.com/AstroTheWizard)

Trang gốc (chưa dịch): [prompts/astrothewizard-618782.md](../prompts/astrothewizard-618782.md)

## Prompt (tiếng Việt)

```text
Tôi muốn bạn làm một video giải thích hoạt hình hoàn chỉnh dài 60 giây, từ đầu đến cuối, hoàn toàn tự lực. Tôi sắp rời khỏi máy tính, nên hãy làm việc tự chủ cho đến khi xong. Đừng dừng lại để hỏi tôi; hãy tự quyết định và cuối cùng cho tôi biết bạn đã quyết định những gì.

Chủ đề: hành trình của các photon

Phong cách: kỳ thú, đáng yêu, như sách truyện. Hãy cho photon một tính cách. Nó phải có cảm giác như do một studio motion design chuyên nghiệp làm, không phải "video AI". Toàn bộ phải là một animation JavaScript thuần, render từ code từng khung hình một. Đừng dùng các công cụ tạo video bằng AI cho phần hình ảnh. Tôi đã thấy những video mọi người đăng từ Opus 5.5 (các reel kinetic typography, zoom vô tận liền mạch, video giải thích dựa trên dữ liệu kiểu The Pudding hay 3Blue1Brown), và điều làm chúng tuyệt vời là chúng được render bằng code: sắc nét, chính xác, có một hệ thống thiết kế nhất quán và một ý tưởng hình thức mạnh cho mỗi cảnh. Hãy nhắm đến mức đó hoặc cao hơn.

Hãy làm cho nó thật sự mang tính giáo dục và chính xác. Khi có thể, hãy mô phỏng thứ thật: bước ngẫu nhiên phải là một bước ngẫu nhiên thật sự, không phải hình vẽ về nó. Đưa vào các con số thật (nhiệt độ lõi, khoảng cách, thời gian di chuyển, số năm ở bên trong Mặt Trời) và trung thực về độ bất định của các ước tính. Dùng sự hài hước và các gag hình ảnh để giữ sự chú ý: từ tượng thanh, những nhân vật nhỏ, các chi tiết gọi lại. Đặt những gì đang diễn ra trên Trái Đất trong suốt 100,000 năm đó song song với dòng thời gian của photon.

Sản phẩm giao: 1920x1080 ở 60fps, đúng 60 giây, kèm:
- Một kịch bản lồng tiếng do bạn tự viết, đọc bằng mô hình text-to-speech chất lượng cao nhất bạn có thể truy cập
- Phụ đề gắn cứng vào hình, vì hầu hết mọi người xem trên X khi tắt tiếng
- Một bản nhạc nền gốc hợp với tông kỳ thú và thay đổi theo từng cảnh
- Thiết kế âm thanh đồng bộ chính xác với hành động trên màn hình (mọi cú nảy, tiếng bụp, tiếng vút và tiếng ding)
- Một bản mix chuyên nghiệp: nhạc tự hạ xuống dưới giọng đọc, master đạt độ lớn chuẩn streaming

Bạn viết kịch bản, thiết kế nhân vật, chọn typography và bảng màu, soạn nhạc và xây dựng engine animation. Dùng bất kỳ công cụ và tài nguyên nào bạn có thể truy cập: font mở, thư viện sample, mô hình mã nguồn mở. Dùng bất cứ thứ gì hiệu quả.

Chất lượng là trên hết. Hãy xây dựng các vòng kiểm tra: render ảnh tĩnh của mọi cảnh và soát xét chúng một cách khắt khe, kiểm tra từng khung hình ở các chuyển cảnh, đo bản mix âm thanh bằng số liệu, sửa chỗ yếu và render lại. Đừng đưa tôi bản nháp đầu tiên. Hãy đưa tôi thứ mà bạn dám ký tên vào. Đồng thời đưa tôi mã nguồn để có thể tái tạo lại
```

## Prompt gốc

```text
I want you to make a 60-second, fully animated explainer video, end to end, completely on your own. I'm stepping away from my computer, so work autonomously until it's done. Don't stop to ask me questions; make the calls yourself and tell me what you decided at the end.

Topic: the journey of photons 

Style: whimsical, charming, storybook. Give the photon a personality. It should feel like a professional motion-design studio made it, not "AI video". The whole thing should be a pure JavaScript animation, rendered from code frame by frame. Don't use AI video generators for the visuals. I've seen the videos people are posting from Opus 5.5 (kinetic typography reels, continuous infinite zooms, data-driven explainers like The Pudding or 3Blue1Brown), and what makes them great is that they're code-rendered: crisp, precise, with a coherent design system and one strong formal idea per scene. Aim for that bar or above.

Make it genuinely educational and accurate. Where you can, simulate the real thing: the random walk should be an actual random walk, not a drawing of one. Include real numbers (core temperature, distance, travel time, years inside the Sun) and be honest about uncertainty in the estimates. Use humor and visual gags to keep attention: onomatopoeia, little characters, callbacks. Put what was happening on Earth during those 100,000 years alongside the photon's timeline.

Deliverable: 1920x1080 at 60fps, exactly 60 seconds, with:
- A voiceover script you write yourself, voiced with the highest-quality text-to-speech model you can access
- Burned-in captions, since most people watch on X with the sound off
- An original music score that fits the whimsical tone and changes with each scene
- Sound design synced exactly to the on-screen action (every bounce, pop, whoosh and ding)
- A professional mix: music ducks under the voice, mastered to streaming loudness

You write the script, design the characters, pick the typography and palette, compose the music, and build the animation engine. Use any tools and resources you can find access to: open fonts, sample libraries, open-source models. Use whatever works.

Quality is paramount. Build verification loops: render stills of every scene and review them critically, check transitions frame by frame, measure the audio mix numerically, fix what's weak and re-render. Don't hand me a first draft. Hand me something you'd put your name on. Also give me the source code so it's reproducible
```
