# Video Opus 5.5 của @froessell

[▶ Xem bản gốc và bản làm lại trực tiếp trên Skillry](https://skillry.dev/ai-videos/opus-5-5/froessell-562325?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos) · [Bài đăng gốc](https://x.com/froessell/status/2103789415323562325)

- **Danh mục:** Game & tương tác
- **Bản làm lại dùng:** Three.js · Canvas · Vật lý · Chơi được
- **Tác giả:** [@froessell](https://x.com/froessell)

Trang gốc (chưa dịch): [prompts/froessell-562325.md](../prompts/froessell-562325.md)

## Prompt (tiếng Việt)

```text
PRD — Game arcade rượt đuổi cảnh sát

Tên tạm: Heatwave
Nền tảng: iOS + Android
Engine: Unity
Thể loại: Game arcade rượt đuổi / sinh tồn 3D góc nhìn từ trên xuống (top-down)
Hướng màn hình: Dọc
Điều khiển: Cảm ứng một ngón cái
Mô hình kinh doanh: Chưa quyết — thiết kế MVP xoay quanh gameplay trước
Mục tiêu chính: Dựng một bản prototype chơi được và thực sự vui trước khi thêm hệ thống tiến trình hay kiếm tiền.
⸻
Tầm nhìn sản phẩm
Một game arcade di động nhanh, hỗn loạn, trong đó người chơi liên tục bị cảnh sát truy đuổi ngày càng hung hăng.
Người chơi không thể tấn công trực tiếp.
Thay vào đó, họ sống sót bằng cách lái xe liều lĩnh, drift vòng qua chướng ngại vật, bẻ lái đột ngột và lừa cảnh sát đang truy đuổi đâm vào chướng ngại vật và đâm vào nhau.
Cảm giác cốt lõi là:
Bạn không mạnh hơn cảnh sát. Bạn khó bắt hơn.

Mỗi lượt chơi phải liên tục tạo ra những pha suýt va chạm, va chạm dây chuyền và những khoảnh khắc người chơi thoát khỏi một tình huống tưởng như không thể.

Hãy nghĩ theo hướng:

điều khiển dễ + truy đuổi hung hăng + hỗn loạn vật lý + áp lực leo thang.

⸻

Vòng lặp gameplay cốt lõi

BẮT ĐẦU LƯỢT
↓
LÁI / DRIFT
↓
CẢNH SÁT TRUY ĐUỔI
↓
NHỬ CẢNH SÁT
↓
NÉ
↓
CẢNH SÁT ĐÂM XE
↓
ĐƯỢC ĐIỂM
↓
MỨC TRUY NÃ TĂNG
↓
CẢNH SÁT NHIỀU HƠN / MẠNH HƠN
↓
SỐNG SÓT
↓
CUỐI CÙNG BỊ BẮT
↓
ĐIỂM / CHƠI LẠI

Thời lượng mục tiêu mỗi lượt:

2–5 phút.

Chơi lại phải mất dưới 2 giây.

⸻

Nguyên tắc thiết kế

3.1 Chơi được bằng một ngón cái

Người chơi phải hiểu cách điều khiển chỉ trong vài giây.
Không có chân ga.
Không có chân phanh.
Không có vô lăng ảo.
Xe tự động chạy.
Người chơi chỉ điều khiển hướng.

(Tôi đã bỏ cách này sau lần thử đầu tiên và thêm joystick trên màn hình)

3.2 Vật lý arcade, không phải mô phỏng
Xe phải:
drift
trượt
nảy
xoay vòng
va chạm thật kịch tính
hồi lại nhanh
Độ vui được ưu tiên hơn độ chính xác vật lý.

3.3 Kẻ truy đuổi chính là vũ khí
Cảnh sát thực chất là cơ chế tấn công của người chơi.
Người chơi cần học được:
“Nếu mình rẽ ở đây, ông cảnh sát kia sẽ lao thẳng vào bức tường đó.”
3.4 Hỗn loạn nhưng vẫn phải dễ đọc

Kể cả khi có hơn 10 xe trên màn hình, người chơi vẫn phải hiểu ngay lập tức:
mình đang ở đâu
mình đang đi về hướng nào

cảnh sát đang đến từ đâu

thứ gì có thể giết mình

3.5 Thua phải thấy công bằng

Cái chết nhìn chung nên đến từ một sai lầm mà người chơi hiểu được, chứ không phải từ vật lý khó đoán.

⸻

Phạm vi MVP

Không làm hệ thống tiến trình, nâng cấp, nhiệm vụ hay kiếm tiền cho mốc đầu tiên.

Phiên bản đầu tiên gồm:

1 xe của người chơi

1 đấu trường

1 xe cảnh sát

1 biến thể cảnh sát tinh nhuệ

5 mức truy nã

va chạm vật lý

chướng ngại vật môi trường
tính điểm
máu của người chơi
phá hủy xe cảnh sát
VFX cơ bản
âm thanh cơ bản

màn hình game over

chơi lại tức thì

Chừng đó là đủ để xác định game có đáng phát triển tiếp hay không.

⸻

Xe của người chơi

Chuyển động

Xe của người chơi dùng bộ điều khiển arcade dựa trên Rigidbody.

Không phụ thuộc nhiều vào WheelCollider kiểu thực tế.
Các biến cốt lõi phải được hiển thị trong Unity Inspector:
Acceleration
Maximum Speed
Turn Speed
Turn Curve
Lateral Grip
Drift Factor
Vehicle Mass
Collision Force
Drag
Angular Drag
Recovery Speed
Những thông số này phải cực kỳ dễ tinh chỉnh.

⸻

Điều khiển

Cách triển khai đầu tiên được đề xuất:

Lái bằng kéo (drag steering)

Người chơi chạm vào bất kỳ đâu ở nửa dưới màn hình.

Kéo theo chiều ngang để lái.

← kéo          rẽ trái
→ kéo          rẽ phải
Xe tự động tăng tốc.
Lái theo kiểu tương đối thay vì tuyệt đối.
Người chơi có thể nhấc ngón tay lên mà không mất kiểm soát ngay.
Phương án thay thế để làm prototype
Thử:
Giữ nửa trái/phải màn hình = lái trái/phải.
Chưa chốt cho tới khi đã thử cả hai trên điện thoại thật.
⸻
Hệ thống drift
Drift phải xảy ra tự nhiên khi rẽ ở tốc độ cao.
Không có nút drift riêng.
Ở tốc độ thấp:
độ bám cao

Ở tốc độ cao:

giảm độ bám ngang

Điều này tạo ra những cú trượt có kiểm soát.

Drift dài có thể (tùy chọn) được cộng điểm.

Ví dụ:

DRIFT
+120
LONG DRIFT
+340

Nhưng điểm drift chỉ là phụ so với việc phá hủy xe cảnh sát.

⸻
AI cảnh sát
Cảnh sát phải tạo cảm giác:
hung hăng, dễ đoán và hơi ngốc.
Chúng không được chỉ đơn giản đi theo vị trí hiện tại của người chơi.
Thay vào đó, hãy tính một điểm chặn đầu dựa trên vận tốc của người chơi.
Về mặt ý tưởng:
target =
playerPosition
+
playerVelocity * predictionTime
Nhờ vậy cảnh sát sẽ cố chặn đầu người chơi.
⸻
Trí khôn của cảnh sát

Cảnh sát được cố ý cho khả năng né chướng ngại vật hạn chế.

Điều này rất quan trọng.

Điều hướng hoàn hảo sẽ khiến game kém vui.

Cảnh sát phải:

truy đuổi hung hăng

cố chặn đầu

né các chướng ngại vật tĩnh dễ thấy

ít để ý đến các xe cảnh sát khác
ôm cua quá đà

đâm vào nhau

thỉnh thoảng đi những đường nguy hiểm

Điều này tạo cơ hội cho người chơi.

⸻

Phá hủy xe cảnh sát

Xe cảnh sát có thể bị phá hủy khi:

va chạm chướng ngại vật ở tốc độ cao

đâm vào một xe cảnh sát khác

va chạm dây chuyền

mối nguy từ môi trường

Người chơi không có vũ khí.

Ví dụ tính điểm:

COP SMASHED
+250
DOUBLE SMASH
+600
TRIPLE SMASH
+1,000
PILEUP!
+2,000

Va chạm dây chuyền phải được thưởng thật lớn.

⸻

Hệ thống truy nã

Mức truy nã điều khiển độ khó.

★☆☆☆☆
★★☆☆☆
★★★☆☆
★★★★☆
★★★★★

Mức truy nã tăng chủ yếu dựa trên thời gian sống sót và điểm số.
Mức 1
2 cảnh sát.
Chậm và dễ dãi.

Mức 2

3–4 cảnh sát.

Nhanh hơn một chút.

Mức 3

5–6 cảnh sát.

Chặn đầu hung hăng hơn.

Mức 4

7–9 cảnh sát.

Xuất hiện cảnh sát tinh nhuệ.
Mức 5
Hỗn loạn tối đa.
Hơn 10 cảnh sát tùy theo hiệu năng thiết bị.

Đơn vị tinh nhuệ xuất hiện thường xuyên.

Cuối cùng game phải trở nên gần như không thể sống sót.

Đó là chủ đích.

⸻

Cảnh sát tinh nhuệ

MVP chỉ cần một loại cảnh sát đặc biệt.

Interceptor

Xe có ngoại hình khác biệt rõ.
Đặc điểm:
nhanh hơn cảnh sát thường
khối lượng nhẹ hơn
dự đoán hung hăng hơn
bẻ lái gắt
dễ bị phá hủy hơn khi va chạm

Điều này tạo ra một kẻ truy đuổi kiểu "pháo thủy tinh" (glass cannon): mạnh nhưng mỏng manh.

⸻

Máu của người chơi

Dùng một thanh máu đơn giản.

Ví dụ:
HULL
██████░░░░
Va chạm nhẹ:
mất ít máu.

Va chạm mạnh:

mất nhiều máu.

Va chạm ở tốc độ cực cao:
có thể bị phá hủy ngay lập tức.
Chỉ chạm vào cảnh sát thôi thì không nên giết người chơi ngay.
Điều này cho phép những pha giằng co hỗn loạn.
⸻
Đấu trường
Đấu trường đầu tiên nên nhỏ gọn.
Đại khái tương đương thế này:

ROCK

┌─────────────┐
│             │
│   ROCK      │
│             │
│       ███   │
│             │
│ ROCK        │
│         ROCK│
└─────────────┘

Giữa các chướng ngại vật phải có đủ khoảng trống để di chuyển ở tốc độ cao.

Ban đầu tránh sinh màn chơi theo kiểu procedural.

Hãy tự tay thiết kế một đấu trường thật tốt.
⸻
Môi trường
Với chủ đề hình ảnh đầu tiên, tôi muốn dùng thứ gì đó khác nước để không sao chép bản tham khảo quá sát.
Tôi thích:

Rượt đuổi kẻ ngoài vòng pháp luật trên sa mạc

Người chơi là một kẻ ngoài vòng pháp luật đang chạy trốn qua một môi trường sa mạc cách điệu.

Môi trường gồm:

khối đá

xương rồng

rào chắn

xe bị bỏ hoang

dốc nhảy

hàng rào

nhà nhỏ

bụi

đạo cụ phá hủy được

Nó cũng hợp với ngôn ngữ hình ảnh khối mập mạp mà bạn đang thử nghiệm với Bolt Pit.

⸻

Camera

Camera phối cảnh nhìn từ trên xuống.

Không hoàn toàn thẳng đứng.

Khoảng chừng:

góc nhìn xuống 55–70°.

Camera bám theo người chơi có làm mượt.

Camera nên nhìn hơi lệch về phía trước theo hướng di chuyển của người chơi.

Ở tốc độ cao:

camera lùi ra một chút.

Ở tốc độ thấp:

camera tiến lại gần hơn.

⸻
Hiệu ứng camera (camera juice)
Những hiệu ứng camera nhỏ tạo ra khác biệt lớn.
Va chạm nhẹ
Rung rất nhẹ.

Va chạm mạnh

Rung mạnh trong thời gian ngắn.

Phá hủy xe cảnh sát

Rung + đứng hình rất ngắn (freeze frame).

Ví dụ:

hit stop 50–100 ms.
Pileup lớn

Zoom giật nhẹ + rung + hạt.

Đừng lạm dụng rung liên tục.

⸻

Phong cách hình ảnh

3D cách điệu khối mập mạp.

Đặc điểm:

hình khối đơn giản hóa

tỉ lệ cường điệu

xe sáng màu, dễ nhận ra

ánh sáng dịu

ít texture

hình bóng (silhouette) rõ nét

hạt cường điệu
Tránh tỉ lệ xe thực tế.
Xe phải trông gần như đồ chơi.
⸻
VFX
Hiệu ứng tối thiểu cho MVP:
Người chơi
vệt bụi
vết lốp/vết trượt
khói drift

tia lửa va chạm

Cảnh sát

đèn còi hụ

khói khi bị hư hại

vụ nổ khi bị phá hủy

mảnh vỡ

Môi trường

bụi

vật thể phá hủy được

hạt khi va chạm

⸻
Phản hồi va chạm
Mọi va chạm đáng kể phải kết hợp:
vật lý + hạt + âm thanh + phản ứng camera.
Phá hủy xe cảnh sát lớn:
IMPACT
→ xung lực vật lý
→ mảnh xe/mảnh vỡ
→ tia lửa
→ khói
→ rung camera
→ hit stop
→ âm thanh
→ popup điểm
Tương tác này là một trong những nguồn khoái cảm chính của game.
⸻
Hệ thống điểm

Điểm đến từ:

Hành độngVí dụ
Sống sót+10/giây
Phá hủy cảnh sát+250
Driftthay đổi
Suýt va chạm+100
Va chạm đôi+600
Va chạm ba+1,000
Pileup lớn+2,000

Giá trị cụ thể phải luôn cấu hình được.

⸻

Suýt va chạm (near miss)

Tùy chọn cho MVP nhưng có thể rất có giá trị.

Phát hiện khi một xe cảnh sát lướt qua cực sát người chơi với vận tốc tương đối cao.

Hiển thị:

CLOSE CALL! +100

Điều này thưởng cho lối lái liều lĩnh.

⸻

UI

Trong lúc chơi, giữ UI cực kỳ tối giản.

SCORE                          COINS
13,590                          14
★★★☆☆
WANTED
GAME
HULL
████████░░

Ban đầu không có minimap.

Cảnh sát ngoài màn hình có thể dùng các chỉ báo kín đáo ở mép màn hình.

⸻

Game over

Khi HULL về 0:

slow motion ngắn.

Người chơi đâm xe.

Sau đó:

BUSTED
SCORE
24,850
BEST
31,220
[ AGAIN ]

Chạm vào bất kỳ đâu có thể chơi lại.

Tránh các menu không cần thiết giữa các lượt.

⸻

Âm thanh

Âm thanh phải bán được cảm giác tốc độ và va chạm.

Bắt buộc:

động cơ

tiếng rít lốp

còi hụ cảnh sát
va đập
tiếng kim loại bẹp
mảnh vỡ
phá hủy
âm thanh điểm trên UI
tăng mức truy nã

Còi hụ phải ngày càng hỗn loạn khi mức truy nã tăng.

⸻

Kiến trúc kỹ thuật

Cấu trúc Unity gợi ý:

GameManager
Player
├── PlayerController
├── VehiclePhysics
├── PlayerHealth
└── PlayerEffects
Police
├── PoliceController
├── PoliceAI
├── VehiclePhysics
├── PoliceHealth
└── PoliceEffects
Systems
├── SpawnManager
├── WantedManager
├── ScoreManager
├── AudioManager
├── CameraManager
└── PoolManager
UI
├── HUD
├── WantedUI
├── ScoreUI
├── HealthUI
└── GameOverUI

Tránh dựng một framework cầu kỳ.

⸻
Object pooling
Cảnh sát, hạt và mảnh vỡ phải dùng object pooling.
Tránh gọi thường xuyên:

Instantiate()
Destroy()

trong lúc chơi.
Hiệu năng trên di động phải được tính đến ngay từ đầu.
⸻
Mục tiêu hiệu năng

Mục tiêu:

60 FPS
trên một thiết bị iPhone/Android tầm trung đời mới.
Giới hạn ban đầu:

~12 xe đang hoạt động

~100 mảnh vỡ/hạt đơn giản

bóng đổ đơn giản

hạn chế đèn real-time

Hiệu năng phải được test trên thiết bị thật từ sớm.

⸻
Các mốc phát triển
Mốc 1 — Lái xe greybox
Dựng:
đấu trường trống
người chơi dạng khối hộp
lái bằng cảm ứng
tăng tốc
drift

camera

Tiêu chí thành công:

Chạy vòng quanh một đấu trường trống đã thấy đã tay.

Chưa đạt thì không làm tiếp.

⸻
Mốc 2 — Cuộc rượt đuổi
Thêm:
một xe cảnh sát
AI truy đuổi
chặn đầu
va chạm
Tiêu chí thành công:

Né một xe cảnh sát đã thấy thú vị.

⸻

Mốc 3 — Hỗn loạn tự phát (emergent chaos)

Thêm:

nhiều cảnh sát

va chạm cảnh sát–cảnh sát

chướng ngại vật

phá hủy

tính điểm

Tiêu chí thành công:

Người chơi có thể chủ động gây ra va chạm:

cảnh sát → cảnh sát
và
cảnh sát → môi trường
Đây là mốc quan trọng nhất.
⸻
Mốc 4 — Leo thang

Thêm:

mức truy nã

spawn xe

tăng độ khó

interceptor

Giờ một lượt chơi đã có diễn tiến:

bình yên
↓
áp lực
↓
hỗn loạn
↓
hoảng loạn
↓
chết

⸻

Mốc 5 — Juice
Thêm:
hạt
rung camera
hit stop
vết trượt

bụi

còi hụ

âm thanh va chạm

popup điểm

⸻

Mốc 6 — Bản build di động

Build cho thiết bị thật.
Test:
điều khiển
hiệu năng
độ dễ đọc
pin/nhiệt độ máy
các tỉ lệ màn hình khác nhau
⸻
Mốc 7 — Quyết định có làm tiếp hay không

Đến đây, tạm dừng phát triển.

Đừng vội làm ngay một gara với 37 xe mở khóa.

Đưa bản build cho mọi người chơi thử.

Những câu hỏi quan trọng là:

Mọi người có hiểu ngay không?
Họ có chơi lại sau khi chết không?
Họ có chủ động tìm cách khiến cảnh sát đâm xe không?
Cảm giác “thêm một lượt nữa” có tự nhiên xuất hiện không?
Nếu không, hãy làm tiếp vòng lặp cốt lõi thay vì thêm nội dung.
⸻
Giai đoạn 2 — chỉ sau khi đã kiểm chứng
Nếu prototype ổn, mở rộng thành:
Xe
↓
Xu
↓
Mở khóa
↓
Thử thách
↓
Đấu trường mới
↓
Cảnh sát đặc biệt
↓
Nâng cấp
↓
Thử thách hằng ngày
↓
Bảng xếp hạng
Các môi trường tiềm năng:
sa mạc
thành phố
bến cảng
tuyết
bãi công nghiệp
sân bay
công trường
căn cứ quân sự
Và còn nhiều đất cho những đơn vị cảnh sát lố bịch: SUV, xe tải bọc thép, trực thăng thả rào chắn, v.v.

Tôi đã mở một project @[Unity CLI installation] để chúng ta làm việc trong đó. Phong cách hình ảnh của game phải vui nhộn, kiểu hoạt hình, và hành động cũng phải cường điệu hết cỡ.
Tôi cũng đã import Topdown engine vào project để chúng ta dùng:
https://topdown-engine.moremountains.com/

Tôi muốn game được tối ưu cho di động, nhưng vẫn chạy được trên desktop trong lúc test.
```

## Prompt gốc

```text
PRD — Police Chase Arcade Game

Working title: Heatwave
Platform: iOS + Android
Engine: Unity
Genre: Top-down 3D arcade chase / survival
Orientation: Portrait
Input: One-thumb touch controls
Business model: TBD — design MVP around gameplay first
Primary goal: Build a genuinely fun playable prototype before adding progression or monetization.
⸻
Product vision
A fast, chaotic mobile arcade game where the player is constantly being pursued by increasingly aggressive police.
The player cannot directly attack.
Instead, they survive by driving aggressively, drifting around obstacles, making sudden turns and tricking pursuing police into crashing into obstacles and each other.
The fantasy is:
You’re not stronger than the police. You’re harder to catch.

Runs should produce constant near-misses, chain collisions and moments where the player escapes a seemingly impossible situation.

Think:

easy controls + aggressive pursuit + physics chaos + escalating pressure.

⸻

Core gameplay loop

START RUN
↓
DRIVE / DRIFT
↓
POLICE PURSUE
↓
BAIT POLICE
↓
DODGE
↓
POLICE CRASH
↓
GAIN SCORE
↓
WANTED LEVEL INCREASES
↓
MORE / HARDER POLICE
↓
SURVIVE
↓
EVENTUALLY GET CAUGHT
↓
SCORE / RESTART

Target run duration:

2–5 minutes.

Restart should take less than 2 seconds.

⸻

Design principles

3.1 One-thumb playable

The player should be able to understand the controls within seconds.
No accelerator.
No brake pedal.
No virtual steering wheel.
The vehicle moves automatically.
The player controls only direction.

(I moved away from this after testing it the first time and added the onscreen joystick)

3.2 Arcade physics, not simulation
Vehicles should:
drift
slide
bounce
spin
collide dramatically
recover quickly
Fun takes priority over physical accuracy.

3.3 Pursuers are weapons
Police are effectively the player’s offensive mechanic.
The player should learn:
“If I turn here, that cop is going straight into that wall.”
3.4 Chaos should remain readable

Even with 10+ vehicles on screen, the player must immediately understand:
where they are
where they’re moving

where police are coming from

what can kill them

3.5 Failure should feel fair

Death should generally result from a mistake the player understands rather than unpredictable physics.

⸻

MVP scope

Do not build progression, upgrades, missions or monetization for the first milestone.

The first version contains:

1 player vehicle

1 arena

1 police vehicle

1 elite police variant

5 wanted levels

physics collisions

environmental obstacles
scoring
player health
police destruction
basic VFX
basic audio

game-over screen

instant restart

That’s enough to determine whether the game deserves further development.

⸻

Player vehicle

Movement

Player vehicle uses a Rigidbody-based arcade controller.

Do not rely heavily on realistic WheelColliders.
Core variables should be exposed in the Unity Inspector:
Acceleration
Maximum Speed
Turn Speed
Turn Curve
Lateral Grip
Drift Factor
Vehicle Mass
Collision Force
Drag
Angular Drag
Recovery Speed
These need to be extremely easy to tune.

⸻

Controls

Recommended first implementation:

Drag steering

Player touches anywhere on the lower portion of the screen.

Dragging horizontally controls steering.

← drag          turn left
→ drag          turn right
Vehicle accelerates automatically.
Steering should be relative rather than absolute.
The player should be able to lift their finger without immediately losing control.
Alternative to prototype
Test:
Hold left/right side of screen = steer left/right.
Don’t commit until both have been tested on a physical phone.
⸻
Drift system
Drifting should happen naturally when turning at speed.
No dedicated drift button.
At low speed:
high traction

At high speed:

reduced lateral traction

This produces controlled sliding.

Long drifts can optionally award score.

Example:

DRIFT
+120
LONG DRIFT
+340

But drift scoring is secondary to police destruction.

⸻
Police AI
Police should feel:
aggressive, predictable and slightly stupid.
They should not simply follow the player’s current position.
Instead, calculate an interception target based on player velocity.
Conceptually:
target =
playerPosition
+
playerVelocity * predictionTime
Police therefore try to cut the player off.
⸻
Police intelligence

Police intentionally have limited obstacle avoidance.

This is important.

Perfect navigation would make the game less fun.

Police should:

pursue aggressively

attempt interception

avoid obvious static obstacles

poorly account for other police
overshoot turns

collide with each other

occasionally take dangerous routes

This creates opportunities for the player.

⸻

Police destruction

Police can be destroyed by:

high-speed obstacle collisions

hitting another police vehicle

chain collisions

environmental hazards

The player does not have weapons.

Example scoring:

COP SMASHED
+250
DOUBLE SMASH
+600
TRIPLE SMASH
+1,000
PILEUP!
+2,000

Chain collisions should be heavily rewarded.

⸻

Wanted system

Wanted level controls difficulty.

★☆☆☆☆
★★☆☆☆
★★★☆☆
★★★★☆
★★★★★

Wanted level increases based primarily on survival time and score.
Level 1
2 police.
Slow and forgiving.

Level 2

3–4 police.

Slightly faster.

Level 3

5–6 police.

More aggressive interception.

Level 4

7–9 police.

Elite police introduced.
Level 5
Maximum chaos.
10+ police depending on device performance.

Elite units appear frequently.

The game should eventually become effectively impossible.

That’s intentional.

⸻

Elite police

The MVP only needs one special police type.

Interceptor

Visually distinct vehicle.
Characteristics:
faster than standard police
lower mass
aggressive prediction
sharp steering
easier to destroy in collisions

This creates a glass-cannon pursuer.

⸻

Player health

Use a simple health bar.

Example:
HULL
██████░░░░
Minor impacts:
small damage.

Heavy impacts:

large damage.

Extremely high-speed impacts:
potential instant destruction.
Police contact alone shouldn’t immediately kill the player.
This allows chaotic scrambles.
⸻
Arena
First arena should be compact.
Something roughly equivalent to:

ROCK

┌─────────────┐
│             │
│   ROCK      │
│             │
│       ███   │
│             │
│ ROCK        │
│         ROCK│
└─────────────┘

Obstacles need enough space between them for high-speed movement.

Avoid procedural generation initially.

Hand-design one good arena.
⸻
Environment
For the first visual theme, I’d use something other than water so we’re not cloning the reference too closely.
My preference:

Desert outlaw chase

Player is an outlaw escaping through a stylized desert environment.

Environment contains:

rock formations

cacti

barriers

abandoned vehicles

ramps

fences

small buildings

dust

destructible props

It also fits the chunky visual language you’re already exploring with Bolt Pit.

⸻

Camera

Top-down perspective camera.

Not completely vertical.

Something approximately:

55–70° downward angle.

Camera follows player with smoothing.

Camera should look slightly ahead in the player’s travel direction.

At high speed:

camera pulls back slightly.

At low speed:

camera moves closer.

⸻
Camera juice
Small camera effects make a large difference.
Light collision
Tiny shake.

Heavy collision

Strong short shake.

Police destruction

Shake + tiny freeze frame.

Example:

50–100 ms hit stop.
Large pileup

Slight zoom impulse + shake + particles.

Don’t overdo continuous shaking.

⸻

Visual style

Chunky stylized 3D.

Characteristics:

simplified geometry

exaggerated proportions

bright readable vehicles

soft lighting

minimal textures

strong silhouettes

exaggerated particles
Avoid realistic vehicle proportions.
Cars should feel almost toy-like.
⸻
VFX
Minimum MVP effects:
Player
dust trail
tire/skid marks
drift smoke

impact sparks

Police

siren lights

smoke when damaged

destruction explosion

debris

Environment

dust

destructible objects

impact particles

⸻
Collision feedback
Every significant collision should combine:
physics + particles + audio + camera response.
Major police destruction:
IMPACT
→ physics impulse
→ vehicle fragments/debris
→ sparks
→ smoke
→ camera shake
→ hit stop
→ sound
→ score popup
This interaction is one of the game’s main sources of satisfaction.
⸻
Score system

Score comes from:

ActionExample
Surviving+10/sec
Police destroyed+250
Driftvariable
Near miss+100
Double collision+600
Triple collision+1,000
Large pileup+2,000

Exact values should remain configurable.

⸻

Near misses

Optional for MVP but potentially valuable.

Detect when a police vehicle passes extremely close to the player at high relative velocity.

Display:

CLOSE CALL! +100

This rewards risky driving.

⸻

UI

During gameplay keep UI extremely minimal.

SCORE                          COINS
13,590                          14
★★★☆☆
WANTED
GAME
HULL
████████░░

No minimap initially.

Off-screen police can use subtle edge indicators.

⸻

Game over

When hull reaches zero:

brief slow motion.

Player crashes.

Then:

BUSTED
SCORE
24,850
BEST
31,220
[ AGAIN ]

Tapping anywhere could restart.

Avoid unnecessary menus between runs.

⸻

Audio

The soundscape should sell speed and collisions.

Required:

engine

tire squeal

police sirens
impact
metal crunch
debris
destruction
UI score sounds
wanted level increase

Sirens should become increasingly chaotic as wanted level increases.

⸻

Technical architecture

Suggested Unity structure:

GameManager
Player
├── PlayerController
├── VehiclePhysics
├── PlayerHealth
└── PlayerEffects
Police
├── PoliceController
├── PoliceAI
├── VehiclePhysics
├── PoliceHealth
└── PoliceEffects
Systems
├── SpawnManager
├── WantedManager
├── ScoreManager
├── AudioManager
├── CameraManager
└── PoolManager
UI
├── HUD
├── WantedUI
├── ScoreUI
├── HealthUI
└── GameOverUI

Avoid building an elaborate framework.

⸻
Object pooling
Police, particles and debris should use object pooling.
Avoid frequent:

Instantiate()
Destroy()

during gameplay.
Mobile performance should be considered from the beginning.
⸻
Performance target

Target:

60 FPS
on a mid-range modern iPhone/Android device.
Initial limits:

~12 active vehicles

~100 simple debris/particles

simple shadows

limited real-time lights

Performance should be tested on device early.

⸻
Development milestones
Milestone 1 — Greybox driving
Build:
empty arena
cube player
touch steering
acceleration
drifting

camera

Success criterion:

Driving around an empty arena feels satisfying.

Do not continue until it does.

⸻
Milestone 2 — The chase
Add:
one police vehicle
pursuit AI
interception
collisions
Success criterion:

Dodging one police car is entertaining.

⸻

Milestone 3 — Emergent chaos

Add:

multiple police

police-police collisions

obstacles

destruction

scoring

Success criterion:

Player can intentionally cause:

police → police
and
police → environment
collisions.
This is the critical milestone.
⸻
Milestone 4 — Escalation

Add:

wanted levels

spawning

difficulty scaling

interceptor

Now a run has an arc:

calm
↓
pressure
↓
chaos
↓
panic
↓
death

⸻

Milestone 5 — Juice
Add:
particles
camera shake
hit stop
skid marks

dust

sirens

collision sounds

score popups

⸻

Milestone 6 — Mobile build

Build for real devices.
Test:
controls
performance
readability
battery/thermal behaviour
different screen ratios
⸻
Milestone 7 — Decide whether to continue

At this point, stop development temporarily.

Don’t immediately build a garage and 37 unlockable cars.

Put the build in front of people.

The important questions are:

Do people immediately understand it?
Do they restart after dying?
Do they intentionally try to make cops crash?
Does “one more run” happen naturally?
If not, work on the core loop rather than adding content.
⸻
Phase 2 — only after validation
If the prototype works, then expand into:
Cars
↓
Coins
↓
Unlocks
↓
Challenges
↓
New arenas
↓
Special police
↓
Upgrades
↓
Daily challenges
↓
Leaderboards
Potential environments:
desert
city
docks
snow
industrial yard
airport
construction site
military base
And then there’s room for ridiculous police units: SUVs, armored vans, helicopters dropping roadblocks, etc.

I have opened a @[Unity CLI installation] project which we can work in. The art style of the game should be fun and cartoony and the action also over the top.
I have imported the Topdown engine into the project as well that we can use:
https://topdown-engine.moremountains.com/

I want the game to be optimized for mobile, but should work on desktop while testing.
```
