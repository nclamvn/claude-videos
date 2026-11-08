# Quy trình làm video hiệu ứng hạt

_Particle Effect Video Workflow_

Video Opus 5.5 của [@Pluvio9yte](https://x.com/Pluvio9yte) · [Bài đăng gốc kèm video](https://x.com/Pluvio9yte/status/2107087191738662953)

- **Danh mục:** Motion graphics
- **Tác giả:** [@Pluvio9yte](https://x.com/Pluvio9yte)

Thêm video Opus 5.5, mỗi video kèm bản làm lại trực tiếp: [skillry.dev/ai-videos/opus-5-5](https://skillry.dev/ai-videos/opus-5-5?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos)

Trang gốc (chưa dịch): [prompts/pluvio9yte-662953.md](../prompts/pluvio9yte-662953.md)

## Prompt (tiếng Việt)

```text
Công khai quy trình làm của tôi, gửi cho Opus5.5 là dùng được ngay

  1. Chọn tư liệu

  Ba tiêu chí, quyết định thẳng thành bại:

  - Chủ thể trọn vẹn: người hoặc vật lọt hết toàn thân vào khung. Chi tiết sẽ mất trong quá trình xử lý, người xem nhận ra đồ vật nhờ đường viền, cảnh cận sẽ biến thành một cục.
  - Nền sạch: màu trơn, nền tuyết, bầu trời đều được, chủ thể dễ tách khỏi nền.
  - Có khoảnh khắc hành động rõ ràng: cú đánh, bật nhảy, tiếp đất, xoay người. Đây là điểm tựa để làm hiệu ứng về sau.

  Nguồn có thể là tự quay, do model video sinh ra, hoặc đoạn phim có sẵn đã được cấp phép.

  2. Tách tư liệu

  Từ mỗi khung hình, trích xuất ba loại thông tin:

  - Màu sắc: hình gốc.
  - Xa gần: mỗi vị trí cách camera bao xa, tính bằng model ước lượng độ sâu có sẵn.
  - Phạm vi chủ thể: đâu là chủ thể, đâu là nền.

  Ngoài ra, tìm ra những thời điểm xảy ra chuyển cảnh quay. Điểm mấu chốt của bước này là giữ ổn định: xa gần và phạm vi chủ thể phải được xử lý thống nhất trong cùng một cảnh quay, nếu không khi phát sẽ bị rung.

  3. Định "hạt" và "kiểu"

  Trước hết, quyết định dùng thứ gì để dựng lại hình ảnh: chấm tròn, ô vuông, chữ, đường kẻ đều được.

  Sau đó thiết kế vài kiểu. Mỗi kiểu thực chất chỉ là một tổ hợp khác nhau của ba quy tắc:

  - Đặt ở đâu: rải khắp khung hình, hay chỉ đặt trên chủ thể.
  - Lớn cỡ nào: cùng một cỡ, hay thay đổi theo sáng tối, xa gần.
  - Màu gì: dùng màu của hình gốc, hay thống nhất một hai màu.

  Thêm một công tắc nữa: trải phẳng trên một mặt, hay đẩy vào không gian ba chiều theo xa gần. Đẩy vào rồi thì camera mới bay vòng quanh được.

  Chuẩn bị bốn đến sáu kiểu khác biệt rõ rệt là đủ dùng. Độ dày thưa của hạt cần tự nhìn mà chỉnh: quá to thì không nhận ra nội dung, quá nhỏ thì lại chẳng khác gì phim gốc.

  4. Tìm nhịp

  - Định tốc độ: chọn tempo của nhạc, chia thời gian thành các ô nhỏ bằng nhau. Cho mỗi ô đúng bằng một số nguyên khung hình, mọi chuyển đổi về sau đều dễ căn khớp.
  - Tìm khoảnh khắc hành động: kết hợp hai tín hiệu "âm thanh đột ngột to lên" và "hình ảnh đột ngột biến động" để tìm ra các điểm nhấn trong tư liệu.
  - Chuẩn bị nhạc: có thể dùng bản nhạc có sẵn và phân tích ra nhịp của nó, cũng có thể tổng hợp một đoạn theo tempo đã định và thêm trọng âm ở các điểm nhấn.

  5. Dàn dựng

  Làm một bảng thời gian, ghi rõ mỗi ô dùng kiểu nào, phối màu gì, camera ở đâu. Bảng này lưu riêng, sau này chỉnh nhịp chỉ cần sửa nó.

  Bốn nguyên tắc dàn dựng:

  - Mở đầu phải cho thấy sự biến đổi: đưa hình gốc trước, rồi mới chuyển sang hạt, để người xem hiểu chuyện gì đang diễn ra.
  - Nhanh chậm xen kẽ: nhanh mãi sẽ chai cảm giác, ở giữa phải có một đoạn chậm lại rõ rệt.
  - Phối màu phải đối chọi: màu sắc và kiểu của hai ô liền kề càng tương phản, chuyển đổi càng mạnh.
  - Kết thúc phải có điểm khép lại: ví dụ hạt to dần cho tới khi thành các mảng màu, hoặc quay về hình gốc.

  6. Phản hồi ở khoảnh khắc then chốt

  Tại các điểm nhấn, chồng thêm những phản ứng ngắn gọn, phân cấp theo độ mạnh nhẹ:

  - Phản hồi nhẹ, lần nào cũng có: hạt biến dạng một chút, camera giật nhẹ một cái.
  - Phản hồi trung bình, chỉ khi mạnh hơn: một phần hạt bật văng về phía camera.
  - Phản hồi lớn, chỉ dùng cho một hai lần mạnh nhất: thời gian ngưng đọng, camera bay vòng quanh.

  Nguyên tắc là yếu và ngắn. Chỉ động vào một phần hạt, kết thúc trong vài khung hình, nếu không hình ảnh sẽ nổ tung thành một mảng, người xem không còn thấy rõ chủ thể đang làm gì.

  Phương pháp làm việc xuyên suốt

  - Làm mẫu nhỏ trước rồi mới tới cả phim: làm xong mỗi khâu, render vài khung hình xem hiệu quả trước, xác nhận rồi mới làm tiếp. Cả phim chỉ render ở bước cuối cùng.
  - Tham số nào chưa chắc thì cho ra một loạt: ví dụ độ dày thưa, bảo AI cùng lúc xuất năm sáu mức đặt cạnh nhau, bạn tự chọn.
  - Sửa chỗ nào render chỗ đó: khi chỉnh một đoạn nào thì chỉ render lại đoạn đó.
  - Bắt AI tự xem hình: mỗi bước đều yêu cầu nó mở kết quả render ra xem một lượt rồi mới báo cáo.
  - Cố định mọi yếu tố ngẫu nhiên: đảm bảo cùng một thiết lập thì lần render nào cũng cho kết quả giống nhau, nếu không sẽ không thể sửa dần từng bước.
```

## Prompt gốc

```text
公开我的制作方案，发给Opus5.5就能用

  1. 选素材

  三个标准，直接决定成败：

  - 主体完整：人物或物体全身入画。细节会在加工中丢失，观众靠轮廓认东西，特写会变成一团。
  - 背景干净：纯色、雪地、天空都行，主体和背景容易分开。
  - 有明确的动作瞬间：打击、起跳、落地、转身。这些是后面做特效的支点。

  来源可以是自己拍的、视频模型生成的，或有授权的现成片段。

  2. 拆素材

  从每一帧提取三类信息：

  - 颜色：原画面。
  - 远近：每个位置离镜头多远，用现成的深度估计模型算。
  - 主体范围：哪里是主体、哪里是背景。

  另外找出镜头切换发生在哪些时刻。这一步的要点是保持稳定：远近和主体范围要在同一个镜头内统一处理，否则播放起来会抖。

  3. 定"粒子"和"样式"

  先决定用什么东西来重建画面：圆点、方块、文字、线条都可以。

  然后设计几种样式。每种样式其实只是三条规则的不同组合：

  - 放在哪：整个画面都放，还是只放在主体上。
  - 多大：统一大小，还是跟着明暗、远近变化。
  - 什么颜色：用原画的颜色，还是统一用一两种颜色。

  再加一个开关：是平铺在一个面上，还是按远近推进三维空间。推进去之后镜头才能环绕。

  准备四到六种差异明显的样式就够用。粒子的疏密需要自己看着调：太大认不出内容，太小又和原片没区别。

  4. 找节奏

  - 定速度：选定音乐的速度，把时间切成等长的小格。让一格正好是整数帧，后面所有切换都好对齐。
  - 找动作瞬间：结合"声音突然变响"和"画面突然变动"两个信号，找出素材里的打击点。
  - 准备音乐：可以用现成的曲子并分析出它的拍子，也可以按定好的速度合成一段，并在打击点上加重音。

  5. 编排

  做一张时间表，写明每一格用哪种样式、什么配色、镜头在哪。这张表单独存放，以后调节奏只改它。

  编排的四条原则：

  - 开头交代变化：先给原画面，再过渡到粒子，让观众看懂发生了什么。
  - 快慢交替：一直快会麻木，中间要有一段明显慢下来的部分。
  - 配色要撞：相邻两格的颜色和样式反差越大，切换越有力。
  - 结尾要有收束：比如粒子越来越大直到变成色块，或者回到原画面。

  6. 关键时刻的反馈

  在打击点上叠加短促的反应，按轻重分级：

  - 每一次都有的轻反馈：粒子变形一下、镜头顶一下。
  - 较重时才有的中反馈：一部分粒子朝镜头弹开。
  - 最重的一两次才用的大反馈：时间静止，镜头环绕。

  原则是弱而短。只动一部分粒子，几帧内结束，否则画面炸成一片，观众就看不清主体在做什么了。

  贯穿全程的工作方法

  - 先小样后全片：每做完一个环节，先渲染几帧看效果，确认了再往下。全片只在最后渲染。
  - 拿不准的参数一次出一排：比如疏密，让 AI 同时出五六个档位并排放，你来挑。
  - 改哪里渲哪里：调整某一段时只重新渲染那一段。
  - 让 AI 自己看图：每一步都要求它把渲染结果打开看一遍再汇报。
  - 所有随机都固定：保证同样的设置每次渲染结果一致，否则没法逐步修改。
```
