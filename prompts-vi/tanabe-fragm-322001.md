# Prompt video quảng cáo ghép gạch mosaic cho Claude Opus 5.5

_Tile Mosaic Ad Video Prompt for Claude Opus 5.5_

Video Opus 5.5 của [@tanabe_fragm](https://x.com/tanabe_fragm) · [Bài đăng gốc kèm video](https://x.com/tanabe_fragm/status/2107644501372322001)

- **Danh mục:** Cảnh 3D
- **Tác giả:** [@tanabe_fragm](https://x.com/tanabe_fragm)

Thêm video Opus 5.5, mỗi video kèm bản làm lại trực tiếp: [skillry.dev/ai-videos/opus-5-5](https://skillry.dev/ai-videos/opus-5-5?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos)

Trang gốc (chưa dịch): [prompts/tanabe-fragm-322001.md](../prompts/tanabe-fragm-322001.md)

## Prompt (tiếng Việt)

```text
Hãy lấy ảnh đính kèm làm "màn hình cuối", rồi tạo một video quảng cáo 30 giây hoàn toàn bằng gạch ốp (có âm thanh, mp4).
Dựng trên trình duyệt (Three.js), xuất toàn bộ khung hình bằng Chrome, rồi ghép thành mp4 bằng ffmpeg.

# Mục tiêu
- Suốt 25 giây, người xem tưởng đây là video quá trình lát gạch. Trong vài giây cuối, họ mới nhận ra đó là ảnh đính kèm (một quảng cáo)
- Màn hình cuối gần như giống hệt ảnh đính kèm. Chữ đọc được. Gạch phủ kín toàn màn hình (không để lộ sàn)

# Đặc tả
- 1920×1080, 30fps, 30 giây. Một file HTML (Three.js, cài bằng npm rồi đóng gói thành một file bằng esbuild)
- Thiết kế sao cho khi truyền vào thời điểm t, cùng một t thì luôn ra cùng một hình (seek(t))
- Mỗi viên gạch là một instance riêng. Khoảng 190.000 viên trên lưới 16:9 (576×324)
- Thay đổi vị trí, hướng, độ dày, vát cạnh và màu cho từng viên. Mạch vữa (khe hở) để trống. Không vẽ đường kẻ
- Ảnh đính kèm chỉ dùng để lấy màu cho gạch (không dán làm texture)
- Khoảng 12 loại vật liệu (gốm men, đá phiến, xà cừ, sứ trắng, đất nung, thuỷ tinh...). Gán theo độ sáng và độ bão hoà của màu
- Ánh sáng là một mặt trời cứng duy nhất ở góc trên bên trái. Sàn là vữa trát. Phía xa có một đường phấn đỏ của thợ mộc, bị mờ ngoài tiêu cự
- Tự làm độ sâu trường ảnh (bokeh tròn) ở bước hậu kỳ. Khẩu độ ban đầu mở lớn, cuối cùng khép nhỏ

# Diễn biến (giây)
0〜3　 Một viên gạch tối màu trên sàn. Camera sát mặt sàn
3〜10　Từ [vị trí bắt đầu lát], gạch xoáy tròn rơi xuống. Tăng dần theo thứ tự viên đầu tiên → các viên xung quanh
10〜21 Lan rộng ra ngoài thật nhanh. Camera lùi ra và [hình muốn cho thấy] dần hiện ra
21〜24 Thấy được toàn cảnh. Những chỗ sẽ thành chữ vẫn giữ màu nhạt giống xung quanh
24〜26 Gạch của chữ, logo, nút bấm lần lượt lật lách cách từ trái sang để hiện ra
26〜30 Dừng ở bố cục nhìn thẳng từ trên xuống. Con trỏ click vào [nội dung nút bấm], viên gạch của nút lún xuống một chút

# Những chỗ dễ vướng (bắt buộc tuân thủ)
- Gạch sẽ thành chữ, ban đầu phải lát bằng màu nền xung quanh. Màu nền được xác định bằng cách tô loang từ ngoài vào trong. Viền chữ (viền trắng) cũng lật cùng lúc. Nếu không tuân thủ, hình dạng chữ sẽ lộ ra giữa chừng
- Camera nhìn từ trên xuống thì không đặt vị trí đúng chính xác thẳng trên đỉnh (hướng sẽ bị xoay 90°). Ở chỗ dừng, đưa đà chuyển động về 0 (nếu không, phần vượt quá của nội suy sẽ làm hình bị lật ngược)
- Màn hình cuối phải đặt cạnh ảnh gốc để so màu, chỉnh khớp phơi sáng, độ bão hoà và tông màu
- Nếu chữ quá nhỏ không đọc được, hãy tăng số lượng gạch
- Lớp nền tối bên dưới chỉ hiện ở những ô mà gạch đã đáp xuống

# Âm thanh
- Dùng hiệu ứng âm thanh của ElevenLabs để tạo tiếng đặt gạch, tiếng lật gạch và tiếng click chuột (mỗi cái 0.5 giây). Trước khi tạo, hãy thông báo lượng credit sẽ tiêu tốn
- Xếp và chồng các âm này khớp với thời điểm gạch đáp xuống và lật. Camera càng xa thì âm càng nhỏ, khi số lượng tăng lên thì gộp lại thành như tiếng mưa
- Đoạn lật lách cách ở giây 24〜26 phải nổi bật nhất. Âm lượng -16 LUFS

# Cách tiến hành
1. Trước tiên đưa ra kịch bản (cảnh theo từng giây) bằng tiếng Nhật, được đồng ý rồi mới làm
2. Tự xem và sửa các khung hình giữa chừng (viên gạch đầu tiên / lúc bắt đầu lát / lúc lùi camera / toàn cảnh / khoảnh khắc chữ hiện ra / cuối cùng)
3. Khi xuất, gọi seek(t) bằng Chrome (puppeteer-core) đủ cho 30fps, rồi pipe png vào ffmpeg
4. Bàn giao mp4 (chất lượng cao và bản để chia sẻ) cùng các ảnh đã kiểm tra

# Đầu vào
- Khung hình cuối: [đính kèm]
- Vị trí bắt đầu lát: [ví dụ: mắt của nhân vật]
- Hình muốn cho thấy khi lùi camera: [ví dụ: người phụ nữ đang cười]
- Nội dung nút bấm: [ví dụ: 無料体験はこちら]
```

## Prompt gốc

```text
添付の画像を「最後の画面」にして、全部タイルでできた30秒の広告動画（音つき・mp4）を作ってください。
ブラウザ（Three.js）で組み、Chromeで全コマを書き出し、ffmpegでmp4にします。

# ゴール
- 見る人は25秒、タイルの制作動画だと思って見る。最後の数秒で、添付画像（広告）だったと気づく
- 最後の画面は添付画像とほぼ同じ。文字が読める。画面いっぱいがタイル（床は見せない）

# 仕様
- 1920×1080、30fps、30秒。HTML1ファイル（Three.js。npmで入れてesbuildで1ファイルに固める）
- 時刻 t を渡すと、同じ t なら必ず同じ絵になる作りにする（seek(t)）
- タイルは1枚ずつ別のインスタンス。16:9の格子で約19万枚（576×324）
- 位置・向き・厚み・面取り・色を1枚ずつ変える。目地（隙間）は空き。線は引かない
- 添付画像は、タイルの色を取るためだけに使う（テクスチャとして貼らない）
- 素材は約12種（釉薬セラミック、スレート、真珠貝、白磁、テラコッタ、ガラスなど）。色の明るさと彩度で割り当てる
- 光は、左上の硬い太陽1つ。床は漆喰。奥に赤い大工のチョーク線がピンぼけで入る
- 被写界深度（円形ボケ）を後処理で自作する。しぼりは最初大きく、最後は小さく

# 流れ（秒）
0〜3　 床に暗いタイルが1枚。カメラは床すれすれ
3〜10　[組み始める場所]から、タイルが渦を巻いて落ちる。最初の1枚→周りの順に増える
10〜21 一気に外へ広がる。カメラが引いて[見せたい絵]が見えてくる
21〜24 全体が見える。文字になる場所は、周りと同じ淡い色のまま
24〜26 文字・ロゴ・ボタンのタイルが、左から順にパタパタ裏返って現れる
26〜30 真上からの構図で止まる。カーソルが[ボタンの文言]をクリックし、ボタンのタイルが少し沈む

# ハマりどころ（必ず守る）
- 文字になるタイルは、最初は周りの背景色で組む。背景色は、外側から内側へ塗り広げて決める。文字のふち（白ぶち）も一緒に裏返す。守らないと、途中で文字の形が見えてしまう
- 真上のカメラは、位置を真上ぴったりにしない（向きが90°回る）。止める所は、動きの勢いをゼロにする（補間のはみ出しで反転する）
- 最後の画面は、元画像と並べて色を比べ、露出・彩度・色味を合わせる
- 文字が小さくて読めないときは、タイル数を増やす
- 下地の暗い面は、タイルが着地したマスだけに出す

# 音
- ElevenLabsの効果音で、タイルを置く音・裏返す音・マウスのクリックを作る（各0.5秒）。作る前に、クレジットの消費を知らせる
- タイルの着地・裏返しの時刻に合わせて並べて重ねる。カメラが遠いほど小さく、数が増えたら雨のようにまとめる
- 24〜26秒のパタパタを、いちばん目立たせる。音量は -16 LUFS

# 進め方
1. 先に脚本（秒ごとの情景）を日本語で出し、OKをもらってから作る
2. 途中のコマ（最初のタイル／組み始め／引き／全景／文字が出る瞬間／最後）を自分で見て直す
3. 書き出しは Chrome（puppeteer-core）で seek(t) を30fpsぶん呼び、png を ffmpeg に流す
4. 納品は mp4（高画質と共有用）と、確認した画像

# 入力
- エンドフレーム: [添付]
- 組み始める場所: [例：人物の目]
- 引いたときに見せたい絵: [例：笑顔の女性]
- ボタンの文言: [例：無料体験はこちら]
```
