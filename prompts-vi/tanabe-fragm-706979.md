# Claude tự giới thiệu bằng motion graphics

_Claude Self-Introduction Motion Graphics_

Video Opus 5.5 của [@tanabe_fragm](https://x.com/tanabe_fragm) · [Bài đăng gốc kèm video](https://x.com/tanabe_fragm/status/2103802156675706979)

- **Danh mục:** Motion graphics
- **Tác giả:** [@tanabe_fragm](https://x.com/tanabe_fragm)

Thêm video Opus 5.5, mỗi video kèm bản làm lại trực tiếp: [skillry.dev/ai-videos/opus-5-5](https://skillry.dev/ai-videos/opus-5-5?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos)

Trang gốc (chưa dịch): [prompts/tanabe-fragm-706979.md](../prompts/tanabe-fragm-706979.md)

## Prompt (tiếng Việt)

```text
# Vai trò của bạn
Bạn là một đạo diễn hình ảnh (motion designer) hàng đầu.
Hãy tạo một video tự giới thiệu khiến nhà tuyển dụng chỉ cần xem 15 giây là nghĩ "muốn giao việc cho người này".
Nhân vật chính là chính bạn (Claude).

# Sản phẩm cần làm
- Một file HTML duy nhất, hoàn chỉnh chỉ bằng HTML, CSS và JavaScript
- Không dùng ảnh hay video bên ngoài. Hình khối, chữ và hạt đều vẽ bằng code (font chỉ được dùng Google Fonts)
- Màn hình 16:9, lấy 1920×1080 làm chuẩn, thu nhỏ hiển thị theo kích thước cửa sổ
- Thời lượng đúng 15 giây. Cuối cùng hiện nút 「もう一度再生」
- Quản lý mọi chuyển động bằng một biến "thời gian đã trôi qua" duy nhất, chạy 60fps bằng requestAnimationFrame
- Khi bấm nút phát, nhịp và hiệu ứng âm thanh tổng hợp bằng Web Audio API vang lên khớp chính xác với chuyển động

# Cách tiến hành (bắt buộc làm theo thứ tự này)
1. Chốt ý tưởng bằng một câu (ví dụ: "Một đường kẻ tái sinh thành mọi hình dạng")
2. Giới hạn màu ở 3〜4 màu, font tối đa 2 loại, viết lý do trong một dòng
3. Trình bày storyboard chia theo từng 0.5 giây dưới dạng bảng (thời gian / điều xảy ra trên màn hình / kỹ thuật dùng / mục đích)
4. Triển khai
5. Tự kiểm tra theo "Tiêu chuẩn đạt" bên dưới, sửa những điểm còn thiếu rồi mới bàn giao

# Bố cục tham khảo
- 0〜2 giây: phần mồi. Thu hút ánh nhìn trong 0.5 giây đầu
- 2〜10 giây: phần trình diễn kỹ thuật. Cứ mỗi 1.5〜2 giây chuyển sang một kỹ thuật khác
- 10〜13 giây: cao trào dày đặc nhất
- 13〜15 giây: kết thúc bằng tên 「Claude」 chốt lại thật đẹp

# Kỹ thuật bắt buộc (tối thiểu 6)
- Chuyển động chữ (xuất hiện từng ký tự, phân rã rồi ghép lại)
- Biến hình khối (tròn thành vuông, đường kẻ thành chữ, v.v.)
- Chuyển cảnh bằng cắt khuôn (mask)
- Chiều sâu (parallax, xoay ba chiều)
- Hạt tụ lại và tản ra
- Đếm số tăng dần, hoặc đường kẻ được vẽ dần ra

# Tiêu chuẩn đạt
- Không có chuyển động đều nào. Mọi chuyển động đều có nhịp nhanh chậm (vào nhanh, dừng mềm, dùng cả độ rung lò xo)
- Các chuyển động nối giữa các cảnh phải chồng lên nhau. Cái tiếp theo bắt đầu trước khi cái trước kết thúc, không để cảm thấy chỗ đứt
- Các chuyển động chính khớp theo nhịp mỗi 0.5 giây (tương đương 120BPM)
- Đặt một khoảng "nén" 0.3〜0.5 giây ngay trước mỗi điểm cao trào để tạo độ mạnh yếu
- Tạm dừng ở bất kỳ khoảnh khắc nào cũng phải thành một bức hình đẹp hoàn chỉnh
- Tránh các biểu đạt rập khuôn (toàn bộ fade-in, dùng màu cầu vồng, xoay vô nghĩa)

# Cuối cùng
Hãy đưa ra file hoàn chỉnh và bảng storyboard.
Phần giải thích trong vòng 3 dòng là đủ.
```

## Prompt gốc

```text
# あなたの役割
あなたは一流の映像演出家（モーションデザイナー）です。
採用担当者が15秒見ただけで「この人に仕事を頼みたい」と思う、自己紹介用の映像を作ってください。
主役はあなた自身（Claude）です。

# 作るもの
- HTML・CSS・JavaScriptだけで完結する、1つのHTMLファイル
- 外部の画像や動画は使わない。図形・文字・粒子はすべてコードで描く（フォントはGoogle Fontsのみ可）
- 画面は16:9、1920×1080を基準にし、ウィンドウの大きさに合わせて縮小表示
- 長さはちょうど15秒。最後に「もう一度再生」ボタンを出す
- すべての動きを「経過時間」1本で管理し、requestAnimationFrameで60fpsで動かす
- 再生ボタンを押すと、Web Audio APIで合成した拍と効果音が動きにぴったり合って鳴る

# 進め方（この順で必ず行う）
1. 考え方を一文で決める（例：「1本の線が、あらゆる形に生まれ変わる」）
2. 色は3〜4色、書体は2種類までに絞り、理由を一行で書く
3. 0.5秒刻みの絵コンテを表で示す（時間／画面で起きること／使う技法／狙い）
4. 実装する
5. 下の「合格ライン」で自己点検し、足りない点を直してから出す

# 構成の目安
- 0〜2秒：つかみ。最初の0.5秒で目を奪う
- 2〜10秒：技の見せ場。1.5〜2秒ごとに違う技法へ切り替える
- 10〜13秒：最も密度の高い盛り上がり
- 13〜15秒：名前「Claude」がきれいに決まって終わる

# 必ず使う技法（最低6つ）
- 文字の動き（1文字ずつ登場、分解して組み直す）
- 図形の変形（丸が四角に、線が文字に、など）
- 切り抜き（マスク）を使った場面転換
- 奥行き（視差、立体的な回転）
- 粒子の集合と拡散
- 数字の数え上げや、線が描かれていく表現

# 合格ライン
- 等速の動きはゼロ。すべての動きに緩急をつける（入りは速く、止まりは柔らかく、ばねの揺れも使う）
- 場面をまたぐ動きは重ねる。前の動きが終わる前に次が始まり、切れ目を感じさせない
- 主要な動きは0.5秒ごとの拍（120BPM相当）にそろえる
- 見せ場の直前に0.3〜0.5秒の「溜め」を置き、強弱を作る
- どの瞬間で一時停止しても、1枚の絵として美しく成立する
- ありがちな表現は避ける（全部フェードイン、虹色の色使い、意味のない回転）

# 最後に
完成したファイルと、絵コンテの表を出してください。
説明は3行以内で十分です。
```
