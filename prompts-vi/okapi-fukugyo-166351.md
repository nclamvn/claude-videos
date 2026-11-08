# Hoạt hình UI motion design

_UI Motion Design Animation_

Video Opus 5.5 của [@okapi_fukugyo](https://x.com/okapi_fukugyo) · [Bài đăng gốc kèm video](https://x.com/okapi_fukugyo/status/2103586082336166351)

- **Danh mục:** Motion graphics
- **Tác giả:** [@okapi_fukugyo](https://x.com/okapi_fukugyo)

Thêm video Opus 5.5, mỗi video kèm bản làm lại trực tiếp: [skillry.dev/ai-videos/opus-5-5](https://skillry.dev/ai-videos/opus-5-5?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos)

Trang gốc (chưa dịch): [prompts/okapi-fukugyo-166351.md](../prompts/okapi-fukugyo-166351.md)

## Prompt (tiếng Việt)

```text
<inputs>
Hãy hỏi tôi 3 điều sau: 8–12 thành phần giao diện mà hình khối sẽ biến hình qua (ví dụ: nút bấm, chỉ báo đang tải, trình phát nhạc, thanh trượt âm lượng, công tắc bật/tắt, tab, biểu đồ, ô tìm kiếm mở bằng ⌘K, thông báo hiện thoáng qua), màu sắc là đen trắng hoàn toàn hay có thêm 1 màu nhấn, và một bản nhạc miễn phí bản quyền khoảng 120BPM (tempo 120 phách mỗi phút) (ví dụ: Mixkit, miễn phí cho mục đích thương mại).
</inputs>

<direction>
Chuyển động giao diện tinh tế, đạt mức có thể đăng lên "Dribbble", trang portfolio dành cho designer. Chỉ có 1 hình khối duy nhất, tuyệt đối không chuyển cảnh. Mọi trạng thái đều được thể hiện bằng chuyển động của cùng 1 hình khối đó thay đổi hình dạng trong khi đổi kích thước, độ bo góc và màu sắc, còn nội dung bên trong được hoán đổi qua một nhịp blur ngắn. Con trỏ gây ra mọi thay đổi bằng những cú click và kéo thật. Nền màu xám sáng có chút ấm, thành phần màu trắng và đen, chữ trên màn hình là tiếng Nhật, font tiếng Nhật là Noto Sans JP, chữ số Latin và ký hiệu dùng Geist (1 font duy nhất). Mọi chuyển động đều là chuyển động tự nhiên như "lò xo", độ vượt đích (nảy ngược lại) chỉ ở mức rất nhỏ. Camera zoom để mỗi trạng thái lấp đầy màn hình. Khung hình cuối giống hệt khung hình đầu để tạo vòng lặp.
Cấm: chuyển động nảy tưng tưng, hiệu ứng hạt bắn tung tóe, quầng sáng nhòe, gradient trên thành phần, icon có độ dày nét không đồng đều, khoảng lặng vô ích không có gì xảy ra, và nói chung bất cứ thứ gì trông như template.
</direction>

<structure>
120BPM, 7 ô nhịp (khoảng 14 giây), phách nào cũng có gì đó xảy ra.
Nút bấm → chỉ báo đang tải → dấu tích → khối hiển thị kiểu Dynamic Island của iPhone → trình phát nhạc với biểu tượng phát/tạm dừng chuyển đổi mượt mà → kéo núm của thanh phát để dời vị trí phát → biến hình thành thanh trượt âm lượng (kéo vượt mức tối đa thì giãn ra như cao su) → công tắc bật/tắt chuyển theo phách → núm công tắc trở thành chỉ báo chọn tab chuyển động như chất lỏng → tab mở ra thành một biểu đồ tự vẽ đường của nó (rê con trỏ lên thì hiện tooltip) → gập lại thành ô tìm kiếm ⌘K → gõ chữ để lọc dần gợi ý → Enter → thông báo hiện thoáng qua → quay lại nút bấm.
</structure>

<build>
1. Một file HTML duy nhất, hình vuông 1440x1440. Mọi thứ hiển thị đều được tính từ thời gian bên trong seek(t) (hàm nhận thời gian t và xác định màn hình tại đúng khoảnh khắc đó). Không dùng CSS transition (tính năng animation tự động) hay timer, không mang trạng thái từ khung hình này sang khung hình khác.
2. Chuyển động "lò xo" phải ở dạng tính trực tiếp bằng công thức (đáp ứng bước dạng closed-form). Với giá trị đổi đích nhiều lần, cộng dồn các chuyển động tính riêng cho từng lần đổi. Như vậy, giá trị luôn được xác định chỉ bằng thời gian ở bất kỳ lúc nào.
3. Chỉ báo chọn tab: cho mép trái và mép phải chuyển động bằng hai lò xo riêng, sao cho đầu phía hướng di chuyển giãn ra trước phía sau. Núm công tắc cũng dùng cùng kỹ thuật này.
4. Kéo là thao tác trực tiếp: trong lúc con trỏ đang nhấn giữ, giá trị được tính từ vị trí con trỏ. Khi thả ra, nó trở về bằng lò xo từ vị trí đó.
5. Phân tích bản nhạc bằng numpy (công cụ tính toán) để xác định vị trí các phách, bắt đầu từ phách đầu ô nhịp. Âm thanh thao tác được đặt đúng vị trí đỉnh âm đã đo.
6. Render bằng Playwright (công cụ tự động điều khiển trình duyệt và xuất màn hình ra ảnh). Xuất 4 khung con cho mỗi khung hình, chồng chúng lại bằng tmix của ffmpeg (công cụ tạo video) để có motion blur (vệt nhòe chuyển động), ra 60fps.
7. Trước khi xuất toàn bộ, xuất mỗi phách đúng 1 khung hình để kiểm tra. Sửa những gì lệch phách, chật chội hoặc khó đọc.
</build>

<gotchas>
Tuyệt đối không gắn will-change (thiết lập render của trình duyệt) cho các phần tử được camera phóng to thu nhỏ. Gắn vào thì chữ sẽ bị mờ. Chữ hoán đổi bên trong cái hộp đang biến hình phải có thời điểm vào/ra riêng của từng chữ (để tránh chồng lên nhau). Khung hình cuối phải khớp hoàn toàn với khung hình đầu, kể cả vị trí và vận tốc của con trỏ. Nếu không, vòng lặp sẽ bị giật.
</gotchas>

<start>
Trước tiên hãy hỏi tôi các thông tin đầu vào, và trước khi viết code, cho tôi xem danh sách trạng thái theo từng phách.
</start>
```

## Prompt gốc

```text
<inputs>
次の3つを私に質問すること：図形が変身する8〜12個の画面部品（例：ボタン、読み込み中の表示、音楽プレーヤー、音量スライダー、オン/オフのスイッチ、タブ、グラフ、⌘Kで開く検索窓、一瞬出る通知）、色は完全な白黒か差し色1色か、そして120BPM（1分間に120拍のテンポ）前後の著作権フリーの曲（例：Mixkit、商用利用無料）。
</inputs>

<direction>
デザイナー向け作品サイト「Dribbble」に載るレベルの、洗練された画面の動き。図形は1つだけで、絶対に場面を切り替えない。すべての状態は、同じ1つの図形が大きさ・角の丸み・色を変えながら形を変えていく動きで表し、中身は短いぼかしをはさんで入れ替える。カーソルが本物のクリックとドラッグで、すべての変化を起こす。背景はあたたかみのある明るいグレー、部品は白と黒、画面の文字は日本語で、日本語フォントはNoto Sans JP、英数字と記号はGeist（1種類のフォント）。動きはすべて「ばね」のような自然な動きにし、行き過ぎ（跳ね返り）はごくわずかまで。カメラはズームして、各状態が画面いっぱいになるようにする。最後のフレームは最初のフレームと同じにして、ループさせる。
禁止：弾むような動き、粒が飛び散る演出、光るにじみ、部品へのグラデーション、線の太さが揃っていないアイコン、何も起きない無駄な間、テンプレっぽく見えるもの全般。
</direction>

<structure>
120BPM、7小節（約14秒）、毎拍なにかが起きる。
ボタン → 読み込み中の表示 → チェック → iPhoneのダイナミックアイランド風の表示 → 再生/一時停止のマークが滑らかに変わる音楽プレーヤー → 再生バーのつまみをドラッグして再生位置を動かす → 音量スライダーに変身（最大を超えてドラッグするとゴムのように伸びる） → オン/オフのスイッチが拍に合わせて切り替わる → スイッチのつまみが液体のように動くタブの選択表示になる → タブが開いて、自分で線を描いていくグラフに（カーソルを乗せると吹き出しが出る） → ⌘Kの検索窓に折りたたまれる → 入力して候補を絞り込む → Enter → 一瞬出る通知 → ボタンに戻る。
</structure>

<build>
1. HTMLファイル1つ、正方形1440x1440。すべての見た目は seek(t)（時間tを渡すと、その瞬間の画面が決まる関数）の中で、時間から計算する。CSSトランジション（自動アニメーション機能）もタイマーも使わず、フレーム間で状態を持ち越さない。
2. 「ばね」の動きは、式で直接求められる形（閉形式のステップ応答）にする。目標が何度も変わる値は、変化ごとに1つずつ計算した動きを足し合わせる。そうすれば、いつでも時間だけで値が決まる。
3. タブの選択表示は、左端と右端を別々のばねで動かし、進む方向の先端が後ろ側より先に伸びるようにする。スイッチのつまみも同じ手法。
4. ドラッグは直接操作：カーソルを押している間、値はカーソル位置から計算する。離したら、その位置からばねで戻る。
5. 曲はnumpy（計算用のツール）で解析して拍の位置を割り出し、小節の頭の拍から始める。操作音は、測定した音のピークの位置に置く。
6. Playwright（ブラウザを自動操作して画面を画像に書き出すツール）で描画する。1フレームあたり4コマ分を書き出して、ffmpeg（動画を作るツール）のtmixで重ねてモーションブラー（動きの残像）をかけ、60fpsにする。
7. 全編を書き出す前に、1拍ごとに1フレームだけ書き出して確認する。拍からズレているもの、窮屈なもの、読みにくいものを直す。
</build>

<gotchas>
カメラで拡大縮小される要素には will-change（ブラウザの描画設定）を絶対に付けない。付けると文字がぼやける。形が変わる箱の中で入れ替わる文字には、それぞれ専用の出入りのタイミングを持たせる（重なるのを防ぐ）。最後のフレームは、カーソルの位置と速度も含めて最初のフレームと完全に一致させる。そうしないと、ループがカクつく。
</gotchas>

<start>
まず入力内容を私に質問して、コードを書く前に、拍ごとの状態リストを見せて。
</start>
```
