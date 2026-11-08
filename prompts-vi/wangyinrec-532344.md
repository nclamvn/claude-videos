# Video phong cách bản thảo vạn vật học thời Phục Hưng

_Renaissance Naturalist Manuscript Style Video_

Video Opus 5.5 của [@wangyinrec](https://x.com/wangyinrec) · [Bài đăng gốc kèm video](https://x.com/wangyinrec/status/2103725737551532344)

- **Danh mục:** Motion graphics
- **Tác giả:** [@wangyinrec](https://x.com/wangyinrec)

Thêm video Opus 5.5, mỗi video kèm bản làm lại trực tiếp: [skillry.dev/ai-videos/opus-5-5](https://skillry.dev/ai-videos/opus-5-5?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos)

Trang gốc (chưa dịch): [prompts/wangyinrec-532344.md](../prompts/wangyinrec-532344.md)

## Prompt (tiếng Việt)

```text
Đề tài và phong cách là tôi chọn, tôi muốn cảm giác như bản thảo của một nhà vạn vật học thời Phục Hưng. Tra cứu tài liệu, viết phân cảnh, viết animation, soạn nhạc đều do Opus5.5 làm, phần hình vẽ là Codex vẽ theo tài liệu yêu cầu do Opus5.5 viết.
Thứ duy nhất làm tôi ngạc nhiên là âm nhạc. Đầu tiên nó dùng Python viết ra một bản tổng phổ MIDI, trong đó có vòng hòa âm, và cả hai giai điệu chính: sáo dọc thổi chủ đề của Claude, celesta chơi kiểu rải hợp âm vòng vòng của GPT. Ở đoạn các cái tên bay loạn xạ, tiếng harpsichord được tạo bằng bước đi ngẫu nhiên, mỗi ô nhịp lại dày hơn một chút, nghịch tai hơn một chút, cuối cùng giáng xuống một hợp âm nghịch dày đặc, rồi dừng hẳn. Đoạn nhanh mỗi ô nhịp 2 giây, các điểm chuyển then chốt đều khớp đúng vạch nhịp.

Sau đó dùng bộ tổng hợp mã nguồn mở FluidSynth cộng với một bộ thư viện âm sắc chuẩn miễn phí để "chơi" bản tổng phổ thành âm thanh. Các âm sắc lute, sáo dọc, organ đều lấy từ bộ thư viện này. Cuối cùng dùng ffmpeg chuẩn hóa độ lớn, làm fade out, rồi ghép với phần hình.
```

## Prompt gốc

```text
我定的选题、风格，我想要那种文艺复兴博物学家手稿的感觉，查资料、写分镜、写动画、作曲都是  Opus5.5 做的，画是 Codex 照着 Opus5.5 写的需求文档画的。  
唯一让我惊讶的是音乐。它先用 Python 写出一份 MIDI 乐谱，里面有和弦进行，也有两段主旋律：竖笛吹 Claude 的主题，钢片琴弹 GPT 那种绕圈的琶音。名字乱飞那段，羽管键琴的音是用随机走位生成的，每一小节更密一点、更不和谐一点，最后砸一个密集的不协和和弦，然后停住。快版一小节 2 秒，关键切换都卡在小节线上。  

然后用开源合成器 FluidSynth 加一套免费的标准音色库，把乐谱"演奏"成音频。鲁特琴、竖笛、管风琴这些音色都来自这套库。最后用 ffmpeg 统一响度、做淡出，再和画面合成。
```
