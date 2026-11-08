# Video Opus 5.5 của @DemitiyaGeekzen

[▶ Xem bản gốc và bản làm lại trực tiếp trên Skillry](https://skillry.dev/ai-videos/opus-5-5/demitiyageekzen-818523?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos) · [Bài đăng gốc](https://x.com/DemitiyaGeekzen/status/2103517910274818523)

- **Danh mục:** Cảnh 3D
- **Bản làm lại dùng:** GLSL · WebGL · Canvas · Web Audio
- **Tác giả:** [@DemitiyaGeekzen](https://x.com/DemitiyaGeekzen)

> Tác giả không công bố đầy đủ prompt. Dưới đây là nội dung bài đăng gốc của họ.

Trang gốc (chưa dịch): [prompts/demitiyageekzen-818523.md](../prompts/demitiyageekzen-818523.md)

## Prompt (tiếng Việt)

```text
opus5.5 hơi bị mạnh, tôi để nó tự chọn chủ đề làm trang tương tác và video,
Prompt: Hãy dùng tư duy và năng lực mạnh nhất của bạn, dựa trên những gì bạn hiểu về tôi, tự tìm một chủ đề tôi có thể thích, làm một video 30s cùng một trang html tương tác, thể hiện năng lực front-end của bạn nhiều nhất có thể!
Hướng chọn đề tài của nó: Đằng Vương Các · đêm Trung thu. Hôm nay (2026-09-25) đúng là ngày rằm tháng Tám năm Bính Ngọ. Nên tôi chọn câu giàu hình ảnh nhất trong 《Đằng Vương Các tự》: "落霞与孤鹜齐飞，秋水共长天一色". Đoạn phim nhìn từ trên thuyền: lúc hoàng hôn một con cò lẻ bay ngang mặt trời, trên trời là mây vảy cá, rồi sông trời một sắc, lầu gác lên đèn từ dưới lên trên, trăng tròn mọc từ phía đông, trên mặt sông thả đèn hoa đăng, câu thơ xuất hiện dưới dạng phụ đề thư pháp viết dọc kèm con dấu.

Phần front-end còn đỉnh hơn, nhưng ở đây không đăng lên được!
Hình ảnh: toàn bộ khung hình được một shader WebGL2 tính từng pixel, không dùng bất kỳ hình ảnh nào. Bao gồm các tầng màu hoàng hôn của bầu trời, quỹ đạo mặt trời mặt trăng tính theo vĩ độ Nam Xương, mây vảy cá sinh procedural, bóng phản chiếu mặt sông chồng 9 nhóm sóng, và mặt đứng Đằng Vương Các vẽ bằng Canvas 2D.
Âm thanh: toàn bộ tổng hợp thời gian thực bằng WebAudio, không có một đoạn thu âm nào. Đàn tranh dùng mô hình dao động dây Karplus-Strong, có kỹ thuật nhấn luyến và rung dây; ngoài ra có tiêu, tiếng nước sông, tiếng côn trùng và reverb.
Chế độ ngắm tự do: có thể kéo để nhìn quanh và thu phóng, kéo timeline để đổi giờ trong ngày; bấm vào mặt sông để thả đèn hoa đăng, sẽ hiện ra một câu thơ và vang lên một tiếng đàn tranh; bấm vào mặt trăng để vào cận cảnh bề mặt trăng; còn có thể chuyển sang xem các lớp render, hoặc quay video ngay trong trang web.
```

## Prompt gốc

```text
opus5.5有点强，我让它自由选题做交互页面和视频，
提示词：用你最强的思维和能力，根据对我的了解，自行寻找我可能喜欢的主题，制作一个30s的视频还有互动html，尽可能的展示你的前端能力！
它的选题思路：滕王阁·中秋夜。 今天（2026-09-25）正好是丙午年八月十五。所以我选了《滕王阁序》里最有画面感的那句："落霞与孤鹜齐飞，秋水共长天一色"。短片是船上视角：落日时一只孤鹜飞过太阳，天上是鱼鳞云，然后江天一色，楼阁由下往上亮起灯，满月从东边升起，江面上漂着河灯，诗句以竖排书法字幕配印章出现。

前端做的更牛，但是这里没法放！
画面：整幅画面由一个 WebGL2 着色器逐像素算出来，没有用任何图片。包括天空的暮色层次、按南昌纬度推算的日月轨迹、程序生成的鱼鳞云、9 组波浪叠加的江面倒影，以及用 Canvas 2D 画出来的滕王阁立面。
声音：全部用 WebAudio 实时合成，没有一段录音。古筝用 Karplus-Strong 弦振动模型，带按滑和揉弦；另有箫、江水声、虫鸣和混响。
自由观赏模式：可以拖动环视和缩放，拖时间轴改变时辰；点江面放河灯，会弹出一句诗、响一声古筝；点月亮进入月面特写；还能切换查看渲染图层，或者在网页里直接录制视频。
```
