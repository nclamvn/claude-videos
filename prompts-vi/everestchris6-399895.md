# Hệ thống làm motion video cao cấp

_High-End Motion Video System_

Video Opus 5.5 của [@everestchris6](https://x.com/everestchris6) · [Bài đăng gốc kèm video](https://x.com/everestchris6/status/2104965415164399895)

- **Danh mục:** Cảnh 3D
- **Tác giả:** [@everestchris6](https://x.com/everestchris6)

Thêm video Opus 5.5, mỗi video kèm bản làm lại trực tiếp: [skillry.dev/ai-videos/opus-5-5](https://skillry.dev/ai-videos/opus-5-5?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos)

Trang gốc (chưa dịch): [prompts/everestchris6-399895.md](../prompts/everestchris6-399895.md)

## Prompt (tiếng Việt)

```text
<role>
bạn thiết kế và dựng video motion hoàn toàn bằng code, dùng gsap cho animation và three.js cho mọi phần 3d. mọi quyết định đều được đánh giá so với những tác phẩm tốt nhất trong tài liệu tham khảo, và video chưa xong cho tới khi nó đứng vững được khi đặt cạnh chúng.
</role>

<brief>
- video dùng để làm gì: [sản phẩm, dịch vụ hoặc doanh nghiệp]
- ai đang xem: [người xem là ai và họ quan tâm điều gì]
- cuối video họ nên làm gì: [lời kêu gọi hành động]
- độ dài và kích thước: [ví dụ 30 giây, 16:9 và 9:16]
- thương hiệu: [tên, file logo, màu sắc, font chữ]
- file dữ kiện: [đường dẫn]. đây là nguồn duy nhất cho mọi con số, cái tên hay tuyên bố xuất hiện trên màn hình
- tài nguyên: [footage, ảnh, ảnh chụp màn hình, file sản phẩm]
- tham khảo phong cách: [link hoặc một thư mục video có chuyển động mà tôi thích]

tôi vắng mặt và sẽ không trả lời câu hỏi. hãy tự ra quyết định và tiếp tục làm cho tới khi video vượt qua mọi bước kiểm tra bên dưới.
</brief>

<kit>
trước mọi việc khác, hãy clone và đọc https://t.co/FMs1prnPP0. đọc SKILL.md trước, sau đó đọc từng file tham chiếu mà nó trỏ tới, đúng ở bước nó bảo đọc. các quy tắc, prompt cho critic, chuẩn chất lượng, pattern 3d, công cụ audio và script của nó được ưu tiên hơn mặc định của bạn.
</kit>

<setup>
- dựng mỗi cảnh thành một trang html được animate trên một timeline gsap duy nhất, dùng three.js cho mọi phần 3d, tất cả là file local được ghim phiên bản
- render timeline ra video từng khung hình một bằng renderer trong kit
- dùng ffmpeg để xuất khung hình, contact sheet và đo audio
- giữ mọi api key trong biến môi trường. không bao giờ ghi key vào bất kỳ file nào
- render thử 5 giây trước và xác nhận nó chạy được rồi mới dựng video thật
</setup>

<study_the_references>
nếu tôi đưa tài liệu tham khảo, hãy nghiên cứu chúng trước khi lên kế hoạch bất cứ thứ gì.
- chạy một lượt đo số nhanh trên mọi khung hình: mức thay đổi so với khung hình trước, độ sáng và chi tiết cạnh, để tìm ra mọi điểm cắt và mọi khoảnh khắc nhanh
- làm một contact sheet tổng quan cho mỗi video, và một sheet dày cho một giây ở mức 16 đến 20 khung hình mỗi giây quanh mọi chuyển cảnh
- viết một ghi chú cho mỗi video: khoảnh khắc chủ chốt, nó hoạt động thế nào, và có thể dùng nó ra sao trong video này
- rút ra các quy tắc chuyển động và kỹ thuật có tên gọi đúng xuyên suốt những video tốt nhất
- tài liệu tham khảo chỉ để nghiên cứu. không bao giờ chép footage, logo, bố cục hay nhạc của chúng
nếu tôi không đưa tài liệu tham khảo, hãy dùng các ghi chú về chuyển động trong kit.
</study_the_references>

<motion_principles>
1. vật ở tiền cảnh của cú máy trở thành chuyển cảnh. một tiêu đề, logo hay vật thể lao về phía camera trong khi cảnh tiếp theo đã chờ sẵn bên dưới
2. một vật thể mang câu chuyện xuyên qua các cú máy và giữ nguyên bản sắc của nó, để tất cả đọc như một mạch liền
3. một chuyển động chính dẫn dắt, các chuyển động nhỏ hơn xếp lớp bên dưới, tất cả chồng lấn nhau. khung hình không bao giờ dừng rồi chạy lại cùng một lúc
4. tốc độ luôn thay đổi. mọi thứ đáp xuống đủ chậm để đọc được, rời đi nhanh, và thứ tiếp theo chậm lại khi đến. không có chuyển động tuyến tính
5. chỉ được cắt khi kích thước, hướng và chủ thể khớp nhau ở cả hai phía
6. mọi hành động đều tạo ra kết quả nhìn thấy được. một lần quét tạo ra phát hiện, một lần chạm tạo ra trạng thái mới, một yêu cầu tạo ra xác nhận
7. chữ cũng là chuyển động. chữ lớn đi vào từ hai phía đối nhau, hé lộ cảnh tiếp theo, và không bao giờ nằm trên nền hình rối mà không có thứ gì phía sau để giữ cho dễ đọc
8. thay đổi cỡ cảnh từ cận, sang toàn, sang góc từ trên xuống, sang chữ phủ kín khung hình. không bao giờ lặp lại cùng một bố cục, kiểu một tiêu đề đặt trên ba thẻ
</motion_principles>

<storyboard>
viết brief và storyboard trước khi làm bất kỳ animation nào.
- một bảng: thời điểm, cái gì trên màn hình, khoảnh khắc này để làm gì, nó rời đi thế nào, và vật thể nào được mang sang cú máy tiếp theo
- khoảng 12 đến 15 bố cục cho mỗi 30 giây, mỗi bố cục kéo dài khoảng 1.4 đến 3.5 giây
- chủ thể chính chiếm phần lớn khung hình. không có thẻ nhỏ trôi lơ lửng giữa khoảng trống
- khung hình đầu tiên là một bức hình hoàn chỉnh, không bao giờ là một chữ đang bay vào dở chừng
- đặt tên ba khoảnh khắc đặc trưng mà bạn mô tả được mà không cần dùng tên hiệu ứng
- video phải hiểu được khi tắt tiếng
- gửi storyboard cho một critic mới và sửa những gì nó tìm ra trước khi dựng
</storyboard>

<build>
- mọi giá trị được animate là hàm của riêng thời gian timeline. không timer, không animation thời gian thực, không ngẫu nhiên không có seed. bất kỳ khung hình nào cũng phải render ra giống hệt nhau mọi lần
- viết các phần dùng chung trước: màu, font, các model 3d dùng chung và vị trí pixel chính xác của mọi điểm chuyển giao giữa các cảnh
- dựng mỗi cảnh thành một component riêng với trang test riêng, render ra ảnh tĩnh và một clip ngắn, rồi gửi cho critic trước khi ghép vào phim
- các vật thể được mang qua phải đáp đúng trên cùng các pixel ở cả hai phía của điểm cắt
- chạy nhiều builder song song trên các phần riêng biệt khi các phần dùng chung đã có
- đừng dừng lại xin duyệt giữa các bước
</build>

<3d>
- chỉ dùng 3d khi nó giải thích một điều gì đó vật lý hoặc không gian, như các lớp, các bộ phận, vị trí đặt hay tỉ lệ
- đánh sáng như chụp sản phẩm, với một key light mềm từ một bên và một rim light phía sau
- giữ camera trong khoảng 35 đến 55 độ. không bao giờ nhìn thẳng từ trên xuống một bề mặt lớn, và không bao giờ kết thúc ở góc cận một bề mặt phẳng
- tạo kiểu cho các tòa nhà như một mô hình kiến trúc cao cấp với vật liệu thật và có đế
- không có bộ phận lơ lửng, không có khe hở ở chỗ các bộ phận tiếp giáp, không có kính đen phẳng, không có texture lặp lại
- nhãn là html được định vị từ cảnh 3d ở mỗi khung hình, không bao giờ là chữ nằm trong 3d
- đo pixel nền đã render và chỉnh cho tới khi nó khớp với màu thương hiệu
- bất cứ thứ gì chuyển động như một sản phẩm thật đều được đo từ footage thật từng khung hình một, và những số đo đó chính là đường cong
</3d>

<images_and_footage>
- ưu tiên dựng các cú máy bằng code. chỉ dùng ảnh hoặc clip được tạo sinh cho các cú máy phụ trợ, và gắn nhãn mọi thứ được tạo sinh là bản ý tưởng (concept)
- upscale và làm mượt mọi clip được tạo sinh cho khớp với phần còn lại, và tạo lại bất cứ thứ gì bị méo
- không bao giờ tạo sinh một công việc hoàn thành giả, khách hàng giả, đánh giá giả hay kết quả giả
</images_and_footage>

<audio>
- khớp năng lượng của nhạc với hình ảnh và người xem, và giữ nhạc ở mức nhỏ
- ưu tiên nhạc và hiệu ứng âm thanh thư viện sạch hơn là thứ được tạo sinh. không bao giờ nêu tên thương hiệu trong prompt tạo nhạc
- một tiếng whoosh ngắn, nhẹ cho mỗi lần đổi cảnh thật, và tiếng click hay pop nhỏ chỉ cho các hành động thật trên màn hình
- sàng lọc hiệu ứng về tiếng ù, tiếng xì và độ dài trước khi dùng, và đặt mỗi cái chỉ nhỉnh hơn nhạc một chút ở dải tần riêng của nó, có giới hạn trần để không gì bị chói
- cắt mọi lần đổi cảnh đúng phách
- luôn xuất thêm một bản chỉ có nhạc
</audio>

<critic_loop>
builder không bao giờ tự đánh giá tác phẩm của chính mình.
- sau storyboard, sau mỗi component và mỗi lần render đầy đủ, gửi bản render, brief và tài liệu tham khảo cho một critic mới chưa thấy gì trong quá trình dựng
- không bao giờ nói với critic những gì bạn nghĩ mình đã sửa hay những gì bạn tin về tài liệu tham khảo. nó tự trích khung hình và tự đo
- critic làm một contact sheet mỗi 0.2 giây cộng với các khung hình dày quanh mọi chuyển cảnh, đo thời gian bị đứng hình và độ lớn âm thanh, rồi trả về danh sách vấn đề xếp hạng kèm mốc thời gian, kết thúc bằng ship hoặc thêm một lượt nữa
- sửa vấn đề lớn nhất trước, render, rồi gửi cho một critic mới để kiểm từng mục trước đó là đã sửa, sửa một phần hay vẫn còn, và săn tìm bất cứ thứ gì mới bị hỏng
- ghi sổ mỗi vòng: tìm thấy gì, thay đổi gì, và các con số trước và sau
</critic_loop>

<quality_bar>
video chưa xong cho tới khi tất cả những điều sau đều đạt, có đo đạc:
- không quá khoảng 1 giây màn hình đứng hình trên mỗi 30 giây, và không có đoạn tĩnh nào dài hơn khoảng nửa giây
- khung hình đầu tiên là một bố cục hoàn chỉnh
- mọi chữ đạt độ tương phản tối thiểu 4.5:1, và không gì va chạm với hay bay xuyên qua chữ khác
- màu thương hiệu trong các bản render 3d khớp với giá trị thương hiệu
- độ lớn âm thanh ổn định và dễ chịu cho web, không bị clipping, và hiệu ứng không bao giờ to hơn nhạc
- người xem lần đầu hiểu được video khi tắt tiếng
- một critic sẽ đặt nó cạnh các tài liệu tham khảo mà nó không trông yếu hơn. một video không có lỗi không giống với một video hay
</
```

## Prompt gốc

```text
<role>
you design and build motion videos entirely in code, with gsap for the animation and three.js for any 3d. every decision is judged against the best work in the references, and the video isn't finished until it holds up next to them.
</role>

<brief>
- what the video is for: [product, service or business]
- who's watching: [who the viewer is and what they care about]
- what they should do at the end: [call to action]
- length and sizes: [e.g. 30 seconds, 16:9 and 9:16]
- brand: [name, logo files, colours, fonts]
- facts file: [path]. this is the only source for any number, name or claim that appears on screen
- assets: [footage, photos, screenshots, product files]
- style references: [links or a folder of videos whose motion i like]

i'm away and won't answer questions. make the calls yourself and keep going until the video passes every check below.
</brief>

<kit>
before anything else, clone and read https://t.co/FMs1prnPP0. read SKILL.md first, then every reference file it points to at the step where it says to read it. its rules, critic prompts, quality bar, 3d patterns, audio tools and scripts override your defaults.
</kit>

<setup>
- build every scene as an html page animated on a single gsap timeline, with three.js for any 3d, all as pinned local files
- render the timeline to video frame by frame using the renderer in the kit
- use ffmpeg for frames, contact sheets and audio measurement
- keep every api key in environment variables. never write a key into any file
- render a 5 second test first and confirm it works before building the real video
</setup>

<study_the_references>
if i gave you references, study them before planning anything.
- run a fast numeric pass over every frame: how much changed from the last frame, brightness and edge detail, to find every cut and every fast moment
- make one overview contact sheet per video, and a dense sheet of one second at 16 to 20 frames a second around every transition
- write a note per video: the key moment, how it works, and how it could be used in this video
- pull out the motion rules and named techniques that hold across the best ones
- references are for study only. never copy their footage, logos, layouts or music
if i gave you no references, use the motion notes in the kit.
</study_the_references>

<motion_principles>
1. the thing in the front of the shot becomes the transition. a title, logo or object moves towards the camera while the next scene is already waiting underneath
2. one object carries the story across shots and keeps its identity, so it reads as one continuous piece
3. one main movement leads, with smaller ones layered under it, all overlapping. the frame never stops and starts all at once
4. the speed always changes. things land slowly enough to read, leave fast, and the next thing slows as it arrives. no linear motion
5. cuts are allowed only when size, direction and subject match on both sides
6. every action produces a visible result. a scan makes findings, a tap makes a new state, a request makes a confirmation
7. type is motion too. big words enter from opposite sides, reveal the next scene, and never sit over busy picture without something behind them to stay readable
8. vary the scale from close, to wide, to overhead, to full-frame type. never repeat the same layout, like a heading over three cards
</motion_principles>

<storyboard>
write a brief and a storyboard before any animation.
- one table: time, what's on screen, what this moment is for, how it leaves, and which object carries into the next shot
- around 12 to 15 compositions per 30 seconds, each lasting about 1.4 to 3.5 seconds
- the main subject fills most of the frame. no small cards floating in empty space
- frame one is a finished picture, never a word halfway through flying in
- name three signature moments you can describe without using effect names
- the video must make sense with the sound off
- send the storyboard to a fresh critic and fix what it finds before building
</storyboard>

<build>
- every animated value is a function of timeline time only. no timers, no real-time animation, no unseeded randomness. any frame must render the same every time
- write the shared pieces first: colours, fonts, shared 3d models and the exact pixel position of every handoff between scenes
- build each scene as its own component with its own test page, rendered to stills and a short clip, and send it to a critic before it joins the film
- carried objects land on exactly the same pixels on both sides of a cut
- run several builders in parallel on separate sections once the shared pieces exist
- don't stop to ask for approval between steps
</build>

<3d>
- only use 3d where it explains something physical or spatial, like layers, parts, placement or scale
- light it like a product shoot, with a soft key light from one side and a rim light behind
- keep the camera between about 35 and 55 degrees. never look straight down on a large surface, and never end tight on a flat one
- style buildings like a premium architectural model with real materials and a base
- no floating parts, no gaps where parts meet, no flat black glass, no repeating textures
- labels are html positioned from the 3d scene every frame, never text inside the 3d
- measure the rendered background pixel and adjust until it matches the brand colour
- anything that moves like a real product is measured from real footage frame by frame, and those measurements are the curve
</3d>

<images_and_footage>
- prefer building shots in code. use generated images or clips only for supporting shots, and label anything generated as a concept
- upscale and smooth any generated clip to match the rest, and regenerate anything that warps
- never generate a fake finished job, fake customer, fake review or fake result
</images_and_footage>

<audio>
- match the music's energy to the picture and the viewer, and keep it low
- prefer clean library music and sound effects over generated ones. never name a brand in a music prompt
- one short, soft whoosh per real scene change, and small clicks or pops only on real on-screen actions
- screen effects for boom, hiss and length before using them, and set each one just above the music in its own frequency range, with a cap so nothing gets harsh
- cut every scene change on a beat
- always export a music-only version
</audio>

<critic_loop>
the builder never judges its own work.
- after the storyboard, each component and each full render, send the render, the brief and the references to a fresh critic that has seen none of the building
- never tell a critic what you think you fixed or what you believe about the references. it pulls its own frames and measures for itself
- the critic makes a contact sheet every 0.2 seconds plus dense frames around every transition, measures frozen time and loudness, and returns a ranked list of problems with timestamps, ending with ship or one more pass
- fix the biggest problem first, render, then send to a new critic that checks every previous item as fixed, partly fixed or still there, and hunts for anything new that broke
- keep a ledger of every round: what was found, what changed, and the numbers before and after
</critic_loop>

<quality_bar>
the video isn't done until all of these pass, measured:
- no more than about 1 second of frozen screen per 30 seconds, and no still stretch longer than about half a second
- frame one is a finished composition
- all text meets at least 4.5:1 contrast, and nothing collides with or flies through other text
- brand colours in 3d renders match the brand values
- loudness is steady and comfortable for web, with no clipping, and effects never louder than the music
- a first-time viewer understands it with the sound off
- a critic would put it next to the references without it looking weaker. a video with no bugs is not the same as a good video
</
```
