# Phim ngắn "Yohaku"

_Yohaku Short Film_

Video Opus 5.5 của [@AGIOyaZ](https://x.com/AGIOyaZ) · [Bài đăng gốc kèm video](https://x.com/AGIOyaZ/status/2103145567945986461)

- **Danh mục:** Cảnh 3D
- **Tác giả:** [@AGIOyaZ](https://x.com/AGIOyaZ)

Thêm video Opus 5.5, mỗi video kèm bản làm lại trực tiếp: [skillry.dev/ai-videos/opus-5-5](https://skillry.dev/ai-videos/opus-5-5?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos)

Trang gốc (chưa dịch): [prompts/agioyaz-986461.md](../prompts/agioyaz-986461.md)

## Prompt (tiếng Việt)

```text
Hãy dùng three.js để làm một đoạn phim ngắn khổ dọc 1080×1920, 30 khung hình/giây, dài khoảng 36 giây.

【Tên tác phẩm】
余白

【Trải nghiệm muốn truyền tải】
Một video cho người xem cảm nhận được cảm giác đánh mất thời gian khi bị cuốn theo việc tối ưu hiệu suất, và cảm giác cuộc đời ngập tràn ánh sáng phong phú ngay khoảnh khắc có được khoảng trống, mà không hề xuất hiện bất kỳ nhân vật nào. Mục tiêu là đến cuối, ánh sáng kính màu hiện lên phủ khắp mặt sàn khiến người xem bất giác nín thở.

【Bối cảnh】
・Bên trong một nhà thờ lớn bằng đá tranh tối tranh sáng. Trên bức tường chính diện chỉ có một ô cửa sổ vòm nhọn cao 15m, rộng 10m
・Từ bên ngoài cửa sổ, một luồng sáng mạnh chiếu xiên một góc 45 độ, đổ lên sàn đá một vệt sáng mang hình ô cửa sổ
・Cửa sổ được lắp kính màu (stained glass): Đức Mẹ ở chính giữa, hai bên là hai thiên thần dang cánh, phía trên là một ô cửa sổ hoa hồng. Thiết kế phải là bản gốc, không mô phỏng tác phẩm có sẵn, và có bố cục đối xứng trái phải

【Cấu trúc thời gian】
0–3 giây: Ánh sáng chiếu qua cửa sổ vẫn là ánh sáng trắng chưa có màu. Trên sàn là hình vệt sáng trắng dịu
3–11 giây: Các khối lập phương màu xám có khắc những chữ như "忙しい", "効率化", "至急", "締切" lần lượt bay tới từ phía trước căn phòng và lấp dần cửa sổ. Nhịp bay tới ngày càng nhanh, cửa sổ càng bị lấp thì căn phòng càng tối
11–14 giây: Cửa sổ bị bịt kín hoàn toàn, chỉ còn bóng tối và tĩnh lặng
14–19 giây: Chỉ một khối "忙しい" rời khỏi cửa sổ, rơi xuống, hoá thành những hạt sáng rồi tan biến. Từ lỗ trống vừa mở, một tia sáng màu rực rỡ chiếu vào
19–26 giây: Lấy lỗ trống đầu tiên làm tâm, các khối lần lượt rời ra theo kiểu dây chuyền. Mỗi khi có thêm lỗ trống, các cột sáng đủ màu sắc lại nhiều thêm, và tấm kính màu bị che khuất dần dần lộ diện
26–33 giây: Mọi khối đều biến mất, camera xuyên qua các cột sáng, bay lên và nhìn thẳng từ trên xuống sàn. Trên khắp mặt sàn, hình kính màu Đức Mẹ và thiên thần được chiếu lên thành ánh sáng rực rỡ sắc màu
33–36 giây: Toàn bộ màn hình chìm trong ánh sáng chói loà, dòng chữ cuối cùng hiện lên, và video lặng lẽ kết thúc

【Chữ (font Mincho, khẽ hiện lên rồi tan đi một cách tiết chế)】
・「毎日、もっと速く。」
・「もっと、効率よく。」
・「気づけば、光が入らなくなっていた。」
・「ひとつ、手放してみる。」
・「空いたところから、光が入る。」
・「その光は、前より豊かだった。」
・Cuối cùng, hiện thật lớn: 「豊かさは余白に宿る」

【Ánh sáng và chất liệu】
・Các cột sáng nhuốm đúng màu của kính màu tại vị trí đó, bụi trong không khí lấp lánh
・Hình chiếu trên sàn phản ánh chính xác những lỗ nào trên cửa sổ đang mở (chỗ còn khối thì thành bóng tối)
・Các khối mang màu xám mờ (matte) vô cơ. Chữ được khắc màu trắng
・Nửa đầu lạnh lẽo và không màu, nửa sau là đỏ, xanh lam, vàng kim như đá quý. Dùng sự tương phản màu sắc này để kể rằng "cuộc sống đã trở nên phong phú"

【Điều kiện kỹ thuật】
・Hoạ tiết kính màu được sinh ra dưới dạng ảnh, và ánh sáng trên sàn, các cột sáng, phần hiển thị cửa sổ đều được tính từ cùng một hoạ tiết đó để khớp nhau
・Tiến thời gian chính xác từng 1/30 giây, xuất ra từng khung hình một, rồi ghép thành MP4

【Hoàn thiện】
Hãy thực sự render từng cảnh để kiểm tra, sửa cho tới khi hoạ tiết kính màu trên sàn đọc ra được là Đức Mẹ và thiên thần, chữ đọc được, chuyển động không đột ngột, rồi mới giao cho tôi.
```

## Prompt gốc

```text
three.jsで、縦長1080×1920・30コマ/秒・約36秒の短編映像を作ってください。

【作品名】
余白

【見せたい体験】
効率化に追われて時間を失っていく感覚と、余白を手に入れた瞬間に人生が豊かな光で満たされていく感覚を、人物を一切登場させずに体感させる映像です。最後に床一面に浮かび上がるステンドグラスの光で、見た人が思わず息をのむことを目指します。

【舞台】
・薄暗い石造りの大聖堂の内部。正面の壁に、高さ15m・幅10mの尖頭アーチ型の窓が一つだけある
・窓の外からは、斜め45度の角度で強い光が差し込み、石の床に窓の形の光を落としている
・窓には、中央に聖母、両脇に翼を広げた二人の天使、上部にバラ窓を配したステンドグラスがはまっている。デザインは既存の作品を模さずオリジナルで、左右対称の構図にする

【時間の構成】
0〜3秒：窓から差す光は、まだ色のない白い光。床にやわらかな白い光の形
3〜11秒：「忙しい」「効率化」「至急」「締切」などの言葉が刻まれた灰色の立方体が、部屋の手前から次々と飛んできて窓を埋めていく。飛来のペースはどんどん加速し、窓が埋まるほど部屋は暗くなる
11〜14秒：窓は完全にふさがれ、闇と静寂
14〜19秒：「忙しい」のブロックが一つだけ窓から外れて落ち、光の粒になって消える。空いた穴から、鮮やかな色の一筋の光が差し込む
19〜26秒：最初の穴を中心に、ブロックが連鎖的に外れていく。穴が増えるたびに色とりどりの光の柱が増え、隠れていたステンドグラスが少しずつ姿を現す
26〜33秒：すべてのブロックが消え、カメラは光の柱をくぐり抜けて上昇し、真上から床を見下ろす。床一面に、聖母と天使のステンドグラスが色鮮やかな光として映し出されている
33〜36秒：画面全体がまばゆい光に包まれ、最後の言葉が浮かび、静かに終わる

【言葉（明朝体、控えめに浮かんでは消える）】
・「毎日、もっと速く。」
・「もっと、効率よく。」
・「気づけば、光が入らなくなっていた。」
・「ひとつ、手放してみる。」
・「空いたところから、光が入る。」
・「その光は、前より豊かだった。」
・最後に大きく：「豊かさは余白に宿る」

【光と質感】
・光の柱は、ステンドグラスのその場所の色に染まり、空中の塵がきらめく
・床の投影は、窓のどの穴が空いているかを正確に反映する（ブロックがある場所は影になる）
・ブロックは無機質なマットグレー。言葉は白く刻印されている
・前半は冷たく無彩色、後半は宝石のような赤・青・金。この色の対比で「豊かになった」ことを語る

【技術条件】
・ステンドグラスの絵柄は画像として生成し、床の光・光の柱・窓の表示はすべて同じ絵柄から計算して一致させる
・時間を1/30秒ずつ正確に進めて1コマずつ書き出し、MP4にする

【仕上げ】
各場面を実際に描画して確認し、ステンドグラスの絵柄が床の上で聖母と天使として読み取れるか、言葉が読めるか、動きが唐突でないかを直してから渡してください。
```
