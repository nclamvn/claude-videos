# Tech demo fractal kiểu demoscene

_Demoscene Fractal Tech Demo_

Video Opus 5.5 của [@Xanares](https://x.com/Xanares) · [Bài đăng gốc kèm video](https://x.com/Xanares/status/2105770390924738984)

- **Danh mục:** Cảnh 3D
- **Tác giả:** [@Xanares](https://x.com/Xanares)

Thêm video Opus 5.5, mỗi video kèm bản làm lại trực tiếp: [skillry.dev/ai-videos/opus-5-5](https://skillry.dev/ai-videos/opus-5-5?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos)

Trang gốc (chưa dịch): [prompts/xanares-738984.md](../prompts/xanares-738984.md)

## Prompt (tiếng Việt)

```text
Hãy làm một tech demo kiểu demoscene dài 37 giây cho bản nhạc ~/Downloads/(filename).mp3.
Mục tiêu là đồ họa chưa ai từng thấy. Như một tuyên ngôn cho một nền demoscene AI mới.

Câu chuyện, trong một cảnh quay liên tục không cắt:
- Một quả cầu chrome lơ lửng trong sương mù tối. Mỗi cú hit trong bản nhạc, nó có thêm một cấp fractal Mandelbox.
- Ở đoạn drop, vật thể lớn dần cho đến khi mặt trên của nó là một vùng địa hình. Bay sát trên đó lúc hoàng hôn, rồi lao xuống khỏi mép của nó.
- Ở cuối, fractal sụp lại thành các chữ vàng 3D của tiêu đề. Khắc các chữ từ chính fractal đó và chiếu sáng chúng bằng cùng nguồn sáng đó.

Diện mạo: chất lượng path-traced. Bóng mềm, ambient occlusion, phản chiếu bóng loáng, sương mù có tia sáng xuyên qua, depth of field, motion blur, bloom.

Đồng bộ: phân tích bản nhạc trước. Lưu một beat map JSON với các hit, break, và onset của kick, snare và hat. Kick làm ánh sáng đập nhịp. Hat thêm chi tiết bề mặt.

Kỹ thuật:
- Một raymarcher fragment shader WebGL2. Một trang HTML vừa là trình phát trực tiếp vừa là nguồn render.
- Trực tiếp: 60 fps trên Chrome.
- Offline: 1920x1080 ở 60 fps với 16 mẫu mỗi pixel. Render bằng headless Chrome trên GPU của Mac, pipe các khung hình PNG sang ffmpeg, và dùng file MP3 làm âm thanh.
- Không dùng công cụ tạo ảnh hay video bằng AI.
- Kiểm tra contact sheet các ảnh tĩnh trước khi render toàn bộ.
```

## Prompt gốc

```text
Make a 37-second demoscene tech demo for the track ~/Downloads/(filename).mp3.
The goal is graphics nobody has seen before. Like it's a statement for a new AI demoscene.

Story, in one continuous shot with no cuts:
- A chrome sphere floats in dark fog. On each hit in the track, it gains one Mandelbox fractal level.
- In the drop, the object grows until its top face is a landscape. Fly low over it at sunset, then dive off its edge.
- At the end, the fractal collapses into 3D gold letters of the title. Carve the letters from the same fractal and light them with the same light.

Look: path-traced quality. Soft shadows, ambient occlusion, glossy reflections, fog with light shafts, depth of field, motion blur, bloom.

Sync: analyse the track first. Save a JSON beat map with hits, breaks, and kick, snare and hat onsets. Kicks pulse the light. Hats add surface detail.

Tech:
- One WebGL2 fragment-shader raymarcher. One HTML page is both the live player and the render source.
- Live: 60 fps in Chrome.
- Offline: 1920x1080 at 60 fps with 16 samples per pixel. Render it in headless Chrome on the Mac GPU, pipe the PNG frames to ffmpeg, and use the MP3 as the audio.
- Do not use AI image or video generators.
- Check contact sheets of stills before the full render.
```
