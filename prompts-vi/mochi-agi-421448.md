# Ga tàu kinh dị lúc nửa đêm

_Late Night Horror Station Animation_

Video Opus 5.5 của [@Mochi_AGI](https://x.com/Mochi_AGI) · [Bài đăng gốc kèm video](https://x.com/Mochi_AGI/status/2104757097850421448)

- **Danh mục:** Cảnh 3D
- **Tác giả:** [@Mochi_AGI](https://x.com/Mochi_AGI)

Thêm video Opus 5.5, mỗi video kèm bản làm lại trực tiếp: [skillry.dev/ai-videos/opus-5-5](https://skillry.dev/ai-videos/opus-5-5?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos)

Trang gốc (chưa dịch): [prompts/mochi-agi-421448.md](../prompts/mochi-agi-421448.md)

## Prompt (tiếng Việt)

```text
Lần này là để thử ElevenLabs v4: một đoạn phim kinh dị ngắn ở sân ga chuyến tàu cuối

Giọng nói: dùng v4 tạo đoạn đối đáp của 2 người chỉ trong 1 lần
Hình: chỉ là 9 ảnh tĩnh được thêm chiều sâu rồi cho chuyển động, không dùng AI tạo video

Vì giọng ban đầu chẳng đáng sợ chút nào
→ giữ nguyên lời thoại, chèn chỉ dẫn diễn xuất bằng tiếng Anh như [whispering] hay [laughs softly] vào giữa
→ stability 0.5 → 0.3
→ giọng nữ: nghe so sánh 3 người, chọn giọng trầm nhiều hơi thở
Người phụ nữ nói thầm đến tận cuối, không lộ mặt, chỉ có lưng và đôi môi

Phụ đề dùng font Mincho, chữ của người phụ nữ viết dọc, của người đàn ông viết ngang
Chữ của người phụ nữ hiện từng chữ một với tốc độ thì thầm, chữ của người đàn ông càng hét càng rung

Công cụ sử dụng
・Opus 5.5 trong Claude Code　lên ý tưởng, đạo diễn, code chuyển động và phụ đề, kiểm tra thành phẩm
・ElevenLabs v4　đoạn đối đáp giọng nói của 2 người, và âm thanh môi trường
・Tạo ảnh của Codex　9 ảnh tĩnh
・Three.js　thêm chiều sâu cho ảnh tĩnh và di chuyển camera
・しっぽり明朝 B1　font chữ phụ đề
・Playwright　xuất từng khung hình một trên trình duyệt
・ffmpeg　xuất video
```

## Prompt gốc

```text
今回は ElevenLabs v4 のお試しで、終電のホームの短いホラー

声は v4 で2人の掛け合いを1回で生成
画は静止画9枚に奥行きつけて動かしてるだけ、動画生成AIはなし

最初の声がぜんぜん怖くなかったので
→ 台詞はそのまま、途中に [whispering] とか [laughs softly] とか英語で演技の指示
→ stability 0.5 → 0.3
→ 女の声は3人聞き比べて、息の多い低い声に
女は最後まで小声、顔は出さずに背中と唇だけ

字幕は明朝体、女は縦書きで男は横書き
女の字はささやく速さで1字ずつ、男の字は叫ぶほど震える仕様

使用ツール
・Claude Code の Opus 5.5　企画、演出、動きと字幕のコード、仕上がりのチェック
・ElevenLabs v4　2人の声の掛け合いと、環境音
・Codex の画像生成　静止画9枚
・Three.js　静止画に奥行きをつけてカメラを動かす
・しっぽり明朝 B1　字幕の書体
・Playwright　ブラウザで1コマずつ書き出し
・ffmpeg　動画の書き出し
```
