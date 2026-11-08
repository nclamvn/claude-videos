# Video Opus 5.5 của @daniel_haida

[▶ Xem bản gốc và bản làm lại trực tiếp trên Skillry](https://skillry.dev/ai-videos/opus-5-5/daniel-haida-636937?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos) · [Bài đăng gốc](https://x.com/daniel_haida/status/2104139720829636937)

- **Danh mục:** Motion graphics
- **Bản làm lại dùng:** Canvas · SVG · CSS
- **Tác giả:** [@daniel_haida](https://x.com/daniel_haida)

> Tác giả không công bố đầy đủ prompt. Dưới đây là nội dung bài đăng gốc của họ.

Trang gốc (chưa dịch): [prompts/daniel-haida-636937.md](../prompts/daniel-haida-636937.md)

## Prompt (tiếng Việt)

```text
claude code (opus 5.5) đã làm phim sản phẩm cho taxtello, app kế toán sổ sách của tôi

mọi khung hình đều là code: react + remotion, 0 after effects
nhạc nền cũng là code, tổng hợp bằng python từ sóng sin và nhiễu

1 prompt và 2 vòng góp ý

prompt đầy đủ bên dưới, cứ lấy mà dùng ↓

Bạn là motion designer cấp cao, product designer và kỹ sư Remotion cho Taxtello.

Nhiệm vụ của bạn là tạo một phim sản phẩm thực sự cao cấp, đẳng cấp Apple cho Taxtello.

Đây KHÔNG phải một video giải thích SaaS chung chung.
Đây KHÔNG phải một bài đi qua từng tính năng.
Đây KHÔNG phải một animation template kiểu startup.

Tôi muốn một showreel thương hiệu/sản phẩm dài tối đa 15 giây, khiến Taxtello trông như một sản phẩm tài chính trưởng thành, đắt tiền, được thiết kế đẹp.

Hãy nghĩ tới:

phim ra mắt sản phẩm của Apple
× fintech cao cấp
× motion design kiểu tạp chí (editorial)
× cách trình bày sản phẩm tiết chế kiểu Stripe
× bản sắc thị giác riêng của Taxtello

Phản ứng mong muốn là:

“Wait, this is a German bookkeeping app?”

Bộ phim phải toát lên cảm giác đắt tiền.

────────────────────────────────────
REPO / NGUỒN SỰ THẬT DUY NHẤT
────────────────────────────────────

Trước khi thiết kế bất cứ thứ gì, hãy xem xét các repository thật trước.

Sản phẩm chính:
  /taxtello/main

Dự án Remotion hiện có:
  /taxtello/beta-motion

Các nguồn thương hiệu thật quan trọng:

  /taxtello/main/public/css/app/_00-tokens.css
  /taxtello/main/docs/design/TOKENS.md
  /taxtello/main/public/taxtello-wordmark.png
  /taxtello/main/public/icons.svg

Ảnh chụp màn hình sản phẩm hiện tại nằm trong:

  /taxtello/main/artifacts/smoke-ui-smoke/

Ưu tiên các ảnh chụp màn hình hợp lệ mới nhất/mã nguồn hiện tại hơn các artifact đã cũ.

Trong /taxtello/beta-motion đã có sẵn một hero animation Remotion dài 24 giây.

KHÔNG được thay thế nó.
KHÔNG được làm nó xuống cấp.
KHÔNG được ép mạch truyện AI-connections hiện tại của nó vào bộ phim mới này.

Hãy tạo một composition mới, độc lập cho nhiệm vụ này, ví dụ

  TaxtelloShowreel15

Bạn có thể tái sử dụng phần hạ tầng tốt, font, tiện ích render, các primitive chuyển động,
đường cong easing, cơ chế tải asset và hạ tầng QA từ beta-motion khi hữu ích.

Nhưng về mặt sáng tạo, đây phải là một bộ phim mới.

Trước khi triển khai, hãy xem xét UI Taxtello thật và hiểu sản phẩm.

Không bịa ra chức năng không tồn tại.

────────────────────────────────────
NGÔN NGỮ THỊ GIÁC THẬT CỦA TAXTELLO
────────────────────────────────────

Dùng design system thật.

Bảng màu cốt lõi:

Nền:
  #0c0f1a

Bề mặt nổi:
  #111525
  #131722
  #1a2032

Vàng thương hiệu chính:
  #e8b84b

Vàng highlight:
  #f5d07a

Vàng chiều sâu:
  #9b6d18

Chữ chính:
  #e8eaf2

Trắng ấm đậm:
  #f6f4eb

Chữ phụ:
  #8b93b5

Tích cực:
  #34d399

Tiêu cực/lỗi, chỉ dùng khi thực sự cần về mặt ngữ nghĩa:
  #f87171

Typography:
  Plus Jakarta Sans

Số / giá trị tài chính khi phù hợp:
  JetBrains Mono

Dùng wordmark Taxtello thật và/hoặc biểu tượng Taxtello thật.
Không vẽ lại hay làm phỏng logo.

Màu vàng của Taxtello phải giống một điểm nhấn quý giá, không phải một trận lụt UI màu vàng.

Hãy nghĩ tới:
kim loại tối
vàng ấm
kính
mực
độ chính xác
sự tự tin trầm lặng

KHÔNG PHẢI:
cyberpunk
crypto
neon
gaming
màu tím AI chung chung
gradient cầu vồng

────────────────────────────────────
CÁC QUY TẮC SÁNG TẠO CỐT LÕI
────────────────────────────────────

Tuân thủ các quy tắc này không khoan nhượng:

1. MỘT CẢNH QUAY = MỘT Ý TƯỞNG.

2. Mỗi cảnh cần có khoảng thở.

3. UI sản phẩm là nhân vật chính.

4. Đừng dán chữ giải thích khắp nơi.

5. Không dùng hard cut trừ khi có lý do chủ đích.

6. Ưu tiên chuyển cảnh dẫn dắt bằng vật thể:
   một card biến thành card kế tiếp,
   một đường biểu đồ trở thành một đường nối,
   một biên lai trở thành một bút toán,
   một con số trở thành một thành phần giao diện khác,
   camera di chuyển xuyên qua sản phẩm.

7. Dùng easing cao cấp.
   Không có chuyển động tuyến tính.

8. Chuyển động nên chồng lấn tự nhiên.
   Các thành phần không nên cùng bắt đầu và dừng ở đúng cùng một khung hình.

9. Dùng chiều sâu một cách tiết chế:
   phối cảnh,
   parallax nhẹ,
   tỉ lệ,
   tách tiền cảnh/hậu cảnh,
   depth of field có kiểm soát nếu làm được.

10. KHÔNG có hiệu ứng nào tồn tại chỉ vì trông nó ngầu.

11. Không spam hạt.

12. Không glassmorphism giả tạo ở khắp nơi.

13. Không blur quá mức.

14. Không có những card 3D xoay vô nghĩa.

15. Không zoom liên tục.

16. Không 20 phong cách animation khác nhau.

17. Không UI nảy tưng tưng.

18. Không đoạn văn marketing khổng lồ.

19. Không bắt chước từng cảnh quay của một quảng cáo Apple cụ thể.
    Hãy nắm lấy triết lý và chất lượng sản xuất thay vào đó.

Sự tự tin về thị giác phải đến từ sự tiết chế.

────────────────────────────────────
ĐỊNH DẠNG
────────────────────────────────────

Bản master chính:

1920 × 1080
60 fps
16:9
H.264
thời lượng tối đa: 15.0 giây

Thời lượng mục tiêu:
khoảng 14.0–15.0 giây.

Phim phải hoạt động được như một màn giới thiệu sản phẩm trên mạng xã hội ngay cả khi không có âm thanh.

Nếu khả thi SAU KHI bản master hoàn tất, hãy tạo thêm một phiên bản dọc/mạng xã hội được bố cục lại có chủ đích.

Đừng chỉ crop bố cục desktop.

Nhưng bản master desktop là ưu tiên.

────────────────────────────────────
CÂU CHUYỆN / MẠCH CẢM XÚC
────────────────────────────────────

Đừng biến phim này thành danh sách năm tính năng.

Nó phải giống một dòng suy nghĩ liên tục:

HỖN LOẠN → KIỂM SOÁT → RÕ RÀNG → TAXTELLO

1.5 giây đầu tiên phải trông cao cấp ngay.

Khoảnh khắc sản phẩm có ý nghĩa đầu tiên phải xuất hiện vào khoảng giây thứ ~2.

Không intro logo năm giây.

Hướng kể chuyện khả dĩ:

“Everything about your business, finally in one place.”

Nhưng hãy CHO THẤY điều này thay vì giải thích nó.

Tôi muốn khoảng bốn ý tưởng thị giác trong toàn bộ phim.

Dùng những bề mặt Taxtello THẬT mạnh nhất mà bạn tìm thấy trong repository.

Các ứng viên mạnh gồm:

• Finanzcockpit / Dashboard
• Rechnungen
• Belege
• Bank / matching
• Steuergesundheit / tổng quan thuế

Bạn KHÔNG cần thể hiện tất cả.

Chọn tổ hợp mạnh nhất về mặt thị giác.

────────────────────────────────────
STORYBOARD 15 GIÂY GỢI Ý
────────────────────────────────────

Hãy coi đây là một điểm xuất phát tốt, không phải template cứng nhắc.

0.00 – 1.20

ĐEN / XANH NAVY.

Một tia lóe vàng ấm nhỏ xuất hiện.

Tia lóe hé lộ một cách thanh lịch hoặc biểu tượng Taxtello, hoặc một mảnh của wordmark.

Không fade logo chung chung.

Hãy nghĩ tới độ chính xác của kim loại gia công.

Camera di chuyển xuyên qua hoặc lướt qua biểu tượng và UI bắt đầu hiện ra từ đó.

Rất ít hoặc không có chữ.

─────────────────

1.20 – 4.40

KIỂM SOÁT TÀI CHÍNH.

Hé lộ Cockpit Taxtello thật như một bề mặt sản phẩm có chiều sâu.

Không chỉ là một ảnh chụp màn hình đặt lên màn hình.

Dựng lại/crop/xếp lớp nó để từng vùng giao diện có thể animate riêng.

Con số tài chính chủ đạo hiện ra sắc nét.
Biểu đồ được vẽ dần vào.
Các chỉ số phụ ổn định muộn hơn một chút.

Dùng stagger tinh tế.

Có thể xuất hiện một dòng chữ duy nhất, ví dụ:

  “Alles im Blick.”

hoặc một cụm từ tiếng Đức ngắn tương đương nếu bạn tìm được cụm phù hợp hơn.

Tối đa ~3–4 từ.

Giao diện phải vẫn nhận ra được là sản phẩm thật.

─────────────────

4.40 – 7.50

BIẾN ĐỔI CHỨNG TỪ / SỔ SÁCH.

Dùng một vật thể thị giác từ cảnh trước làm chuyển cảnh.

Ví dụ:

Một điểm biểu đồ màu vàng nở ra thành góc của một biên lai/card.
Camera đi theo nó.
Một biên lai/chứng từ đi vào.
Taxtello nhận diện hoặc sắp xếp nó.
Chứng từ khớp vào đúng bút toán / bản ghi tài chính tương ứng một cách thanh lịch.

Dùng căn chỉnh kiểu hút nam châm và độ chính xác.

Không tia laser quét sến sẩm.

Không lốc xoáy giấy bay lơ lửng.

Micro-copy khả dĩ:

  “Belege. Erledigt.”

Chỉ khi nó làm cảnh tốt hơn.

─────────────────

7.50 – 10.70

TIỀN / HÓA ĐƠN.

Morph hoặc chuyển cảnh tự nhiên sang giao diện Rechnungen thật.

Dùng một khoảnh khắc mạnh:

trạng thái một hóa đơn thay đổi,
một khoản thanh toán được xử lý xong,
một số tiền di chuyển vào đúng chỗ,
hoặc màn tổng quan tự lắp ráp.

Các con số phải có cảm giác xúc giác và chính xác.

Dùng JetBrains Mono ở những chỗ khớp với sản phẩm thật.

Màu vàng làm nổi bật trạng thái đang active.

Màu xanh lá chỉ dùng cho trạng thái thực sự tích cực về mặt ngữ nghĩa.

Chữ khả dĩ:

  “Geld. Im Griff.”

Một lần nữa: tùy chọn và cực ngắn.

─────────────────

10.70 – 12.80

THUẾ / RÕ RÀNG.

Chuyển sang bề mặt sức khỏe thuế / hướng dẫn tài chính thật của Taxtello.

Không tuyên bố rằng Taxtello đảm bảo thuế đúng một cách thần kỳ.

Truyền tải sự minh bạch và quyền kiểm soát.

Ví dụ:

nhiều tín hiệu nhiễu loạn sụp lại thành một bản tổng quan thuế bình tĩnh, có cấu trúc.

Chữ khả dĩ:

  “Steuern im Blick.”

Cảnh này phải cho cảm giác bình tĩnh hơn cảnh trước.

Nhịp điệu chậm lại trong chốc lát.

─────────────────

12.80 – 15.00

CHỐT THƯƠNG HIỆU.

Kéo camera ra xa.

UI nén lại hoặc gập lại thành một vật thể / bề mặt sản phẩm Taxtello đẹp đẽ duy nhất.

Bóng tối trở lại bao quanh nó.

Wordmark Taxtello màu vàng hiện ra.

Một dòng thương hiệu ngắn bên dưới.

Hãy khám phá những câu kết mạnh như:

  “Dein Business. Klar.”

  “Buchhaltung. Unter Kontrolle.”

  “Einfach mehr Überblick.”

  “Alles fürs Business. An einem Ort.”

Chọn dựa trên định vị sản phẩm thực tế mà bạn tìm thấy trong repo.

Đừng dùng một câu chỉ vì tôi gợi ý nó.

Khung hình cuối phải có đủ độ tĩnh để người xem ghi nhận.

Kết thúc một cách tự tin.

Không CTA khổng lồ nảy tưng tưng.

────────────────────────────────────
CHUYỂN CẢNH
────────────────────────────────────

Đây là một trong những phần quan trọng nhất.

Tôi muốn những chuyển cảnh khiến người xem nghĩ:

“Of course the next scene came from that.”

Tốt:

đường biểu đồ → mép chứng từ
pill vàng → nút hóa đơn
con số tài chính → số tiền trong hóa đơn
mép card → bề mặt kế tiếp
camera đẩy xuyên qua thành phần giao diện
hình học dùng chung
mask reveal dùng chính các hình dạng thật của sản phẩm

Tệ:

crossfade
wipe ngẫu nhiên
chuyển cảnh xoay
glitch
whip-pan cứ hai giây một lần
slide-left kiểu SaaS chung chung
spam zoom-blur

Cắt thẳng chỉ được phép khi một cú nhấn nhịp có chủ đích mang lại lợi ích cho bộ phim.

────────────────────────────────────
CHUYỂN ĐỘNG
────────────────────────────────────

Chuyển động cần có trọng lượng.

Dùng các đường cong tương tự:

cubic-bezier(0.16, 1, 0.3, 1)

ở những chỗ phù hợp.

Các thành phần khác nhau nên có thời điểm xuất hiện lệch nhau tinh tế.

Ưu tiên:

anticipation (lấy đà)
overshoot dưới ~2%
settling (lắng lại)
chuyển động tiếp nối
vận tốc dùng chung giữa các cảnh

Tránh độ nảy kiểu hoạt hình.

Chuyển động camera phải giống một buổi quay macro sản phẩm cao cấp.

Hãy tưởng tượng chúng ta đang quay một vật thể vật lý cao cấp dù nó là phần mềm.

────────────────────────────────────
ÁNH SÁNG / CHẤT LIỆU
────────────────────────────────────

Dùng ánh sáng môi trường cực kỳ tinh tế.

Các cách xử lý khả dĩ:

• rim light vàng mềm
• vùng tối dần xanh navy
• bloom môi trường mờ nhạt
• specular highlight mềm lướt qua một bề mặt
• vignette tiết chế
• grain tinh tế nếu nó thực sự giúp ích

Giữ giao diện sắc nét.

KHÔNG làm mờ sản phẩm chỉ để trông điện ảnh.

Không phản chiếu bóng loáng giả tạo phá hỏng khả năng đọc.

────────────────────────────────────
TYPOGRAPHY
────────────────────────────────────

Dùng rất ít chữ.

Không câu nào được cạnh tranh với sản phẩm.

Tiêu đề nhìn chung nên vừa trên một dòng.

Dùng Plus Jakarta Sans.

Typography mạnh đôi khi có thể phóng rất lớn và tự trở thành một công cụ chuyển cảnh.

Tránh kiểu motion graphics chung chung trong đó từng chữ animate riêng lẻ.

Typography phải chuyển động như những vật thể được thiết kế.

────────────────────────────────────
ÂM THANH / NHỊP ĐIỆU
────────────────────────────────────

Thiết kế chuyển động như thể nó được cắt theo khoảng 115–120 BPM:
cao cấp, có động năng, tinh tế, không cuống cuồng.

Các khoảnh khắc quan trọng phải rơi đúng nhịp nhạc.

Ngôn ngữ âm thanh gợi ý:

• cú va trầm mềm cho màn hé lộ lớn
• tiếng click UI tiết chế, có cảm giác xúc giác
• tiếng tick âm sắc kim loại/thủy tinh tinh tế
• chuyển động tần số thấp nhẹ trong các chuyển cảnh camera
• một âm kết thanh lịch ở màn chốt logo

Tránh:

• tiếng boom trailer điện ảnh khổng lồ
• riser EDM
• tiếng whoosh to khắp nơi
• âm thanh “tech interface” stock
• beat rap
• bass hung hăng

Nếu trong dự án không có asset nhạc/âm thanh an toàn về pháp lý, KHÔNG được lấy âm thanh có bản quyền từ internet.

Hãy giao bản master hình ảnh không có nhạc bản quyền và tạo một cue sheet ngắn gọn mô tả nhạc/SFX nên rơi vào đâu.

Nếu có sẵn âm thanh cục bộ/an toàn phù hợp, hãy dùng nó.

────────────────────────────────────
CHỈ SẢN PHẨM THẬT
────────────────────────────────────

Điều này là tối quan trọng.

Xem xét main hiện tại.

Không bịa ra màn hình.

Không bịa ra các chỉ số ám chỉ dữ liệu khách hàng thật.

Dùng giá trị rõ ràng là tổng hợp/an toàn cho demo nếu cần.

Không vô tình làm lộ bất kỳ thông tin cá nhân, người dùng test hay production nào.

Tái sử dụng cấu trúc thị giác của UI Taxtello thật.

Nếu một màn hình cần được tách ra để animate, hãy dựng lại nó một cách trung thành bằng React từ design system thật thay vì chỉ phóng to một ảnh chụp màn hình khổng lồ.

Kết quả vẫn phải trông không thể nhầm lẫn là Taxtello.

────────────────────────────────────
KỲ VỌNG TRIỂN KHAI
────────────────────────────────────

Làm việc trực tiếp trong:

  /taxtello/beta-motion

Tạo composition mới bên cạnh composition hiện có.

Giữ các composition hiện có vẫn hoạt động.

Tổ chức phần việc mới một cách gọn gàng.

Ưu tiên các primitive tái sử dụng được cho:

• camera surface
• product frame
• chuyển cảnh có mask
• hiệu ứng hé lộ chữ
• hé lộ các vùng UI
• ánh sáng môi trường
• chuyển cảnh shared-element

Tránh một component 1.500 dòng.

Dùng animation Remotion tất định, điều khiển bằng frame/thời gian.

Không setTimeout.
Không animation phi tất định.

Đảm bảo 60 fps xuyên suốt.

Dùng interpolation/spring/easing một cách có chủ đích.

────────────────────────────────────
KHÔNG DỪNG LẠI SAU LẦN TRIỂN KHAI ĐẦU TIÊN
────────────────────────────────────

Đây là một nhiệm vụ thị giác.

Bạn BẮT BUỘC phải xem lại output đã render thực tế.

Quy trình bắt buộc:

1. Xem xét repository và thương hiệu/sản phẩm thật.

2. Viết một storyboard ngắn gọn với:
   - timestamp chính xác
   - hình ảnh chủ đạo
   - logic chuyển cảnh
   - chữ
   - nhịp cảm xúc dự định

3. Triển khai nó.

4. Chạy typecheck / các kiểm tra liên quan.

5. Render các khung hình đại diện vào khoảng:
   0.0 s
   1.0 s
   2.5 s
   4.5 s
   6.5 s
   8.5 s
   10.5 s
   12.5 s
   14.0 s
   14.8 s

6. KIỂM TRA BẰNG MẮT NHỮNG ẢNH ĐÓ.

Đừng chỉ xác nhận rằng render thành công.

Hãy tự hỏi:

Cái này có trông như một phim sản phẩm đẳng cấp Apple không?

Có chỗ nào trông giống template không?

Có quá nhiều thứ trên màn hình không?

Sản phẩm có đọc được rõ không?

Các chuyển cảnh có liên kết logic với nhau không?

Màu vàng Taxtello có tạo cảm giác cao cấp không?

Mọi khung hình có được bố cục chỉn chu không?

7. Sửa các điểm yếu về thị giác.

8. Render toàn bộ phim.

9. Kiểm tra nhiều khung hình được decode chính xác từ file MP4 cuối cùng, không chỉ ảnh chụp màn hình trình duyệt.

10. Lặp lại nếu cần.

Đừng tuyên bố thành công chỉ vì code biên dịch được.

Sản phẩm bàn giao là BỘ PHIM.

────────────────────────────────────
TIÊU CHUẨN CHẤT LƯỢNG
────────────────────────────────────

Hãy tự loại bỏ kết quả của mình nếu nó có cảm giác như:

• một template SaaS
• một animation PowerPoint
• một bản quay màn hình website
• một demo Remotion chung chung
• một quảng cáo crypto
• một template quảng bá do AI sinh ra
• năm ảnh chụp màn hình trượt qua trượt lại
• quá nhiều chữ marketing

Mọi khung hình quan trọng phải đủ tốt để dùng làm ảnh quảng cáo tĩnh.

Tôi thà có:

3 khoảnh khắc thị giác phi thường

còn hơn

10 animation tính năng tầm thường.

────────────────────────────────────
SẢN PHẨM BÀN GIAO CUỐI CÙNG
────────────────────────────────────

Cung cấp:

1. Storyboard cuối cùng
2. Mã nguồn composition Remotion mới
3. File MP4 cuối cùng 1920×1080 / 60fps
4. Poster/khung hình cuối
5. Contact sheet với các khung hình đại diện từ phim
6. Thời lượng chính xác
7. Danh sách các asset/màn hình Taxtello thật đã dùng
8. Giải thích ngắn gọn về ngôn ngữ chuyển động
9. Mọi điểm thỏa hiệp về thị giác còn tồn đọng
10. Các lệnh để tái tạo bản render

Lưu output trong một thư mục đặt tên rõ ràng, ví dụ:

  /taxtello/beta-motion/out/showreel-15/

Không deploy bất cứ thứ gì.
Không sửa dữ liệu production.
Không merge bất cứ thứ gì.

Hãy sáng tạo hết mức, nhưng tiết chế không khoan nhượng.

Hãy làm cho Taxtello trông đắt tiền.
```

## Prompt gốc

```text
claude code (opus 5.5) made the product film for taxtello, my bookkeeping app

every frame is code: react + remotion, 0 after effects
the soundtrack is code too, synthesized in python from sine waves and noise

1 prompt and 2 rounds of feedback

full prompt below, steal it ↓

You are the senior motion designer, product designer and Remotion engineer for Taxtello.

Your task is to create a genuinely premium, Apple-level product film for Taxtello.

This is NOT a generic SaaS explainer.
This is NOT a feature walkthrough.
This is NOT a startup template animation.

I want a maximum 15-second brand/product showreel that makes Taxtello look like a mature, expensive, beautifully designed financial product.

Think:

Apple product launch film
× premium fintech
× editorial motion design
× restrained Stripe-like product presentation
× Taxtello's own visual identity

The desired reaction is:

“Wait, this is a German bookkeeping app?”

The film should feel expensive.

────────────────────────────────────
REPO / SOURCE OF TRUTH
────────────────────────────────────

First inspect the real repositories before designing anything.

Main product:
  /taxtello/main

Existing Remotion project:
  /taxtello/beta-motion

Important real brand sources:

  /taxtello/main/public/css/app/_00-tokens.css
  /taxtello/main/docs/design/TOKENS.md
  /taxtello/main/public/taxtello-wordmark.png
  /taxtello/main/public/icons.svg

Existing current product screenshots can be found under:

  /taxtello/main/artifacts/smoke-ui-smoke/

Prefer the newest valid screenshots/current source over stale artifacts.

There is already an existing 24-second Remotion hero animation in
/taxtello/beta-motion.

DO NOT replace it.
DO NOT regress it.
DO NOT force its current AI-connections storyline into this new film.

Create a new independent composition for this task, e.g.

  TaxtelloShowreel15

You may reuse good infrastructure, fonts, rendering utilities, motion primitives,
easing curves, asset loading and QA infrastructure from beta-motion where useful.

But creatively this should be a new film.

Before implementation, inspect the actual Taxtello UI and understand the product.

Do not invent functionality that does not exist.

────────────────────────────────────
REAL TAXTELLO VISUAL LANGUAGE
────────────────────────────────────

Use the real design system.

Core palette:

Background:
  #0c0f1a

Elevated surfaces:
  #111525
  #131722
  #1a2032

Primary brand gold:
  #e8b84b

Gold highlight:
  #f5d07a

Gold depth:
  #9b6d18

Primary text:
  #e8eaf2

Strong warm white:
  #f6f4eb

Secondary text:
  #8b93b5

Positive:
  #34d399

Negative/error only where semantically necessary:
  #f87171

Typography:
  Plus Jakarta Sans

Numbers / financial values where appropriate:
  JetBrains Mono

Use the actual Taxtello wordmark and/or Taxtello mark.
Do not redraw or approximate the logo.

Taxtello's gold should feel like a precious accent, not a yellow UI flood.

Think:
dark metal
warm gold
glass
ink
precision
quiet confidence

NOT:
cyberpunk
crypto
neon
gaming
generic AI purple
rainbow gradients

────────────────────────────────────
CORE CREATIVE RULES
────────────────────────────────────

Follow these rules ruthlessly:

1. ONE SHOT = ONE IDEA.

2. Every scene needs room to breathe.

3. The product UI is the hero.

4. Do not plaster explanatory copy everywhere.

5. Do not use hard cuts unless there is a deliberate reason.

6. Prefer object-driven transitions:
   a card becomes the next card,
   a chart line becomes a connector,
   a receipt becomes a booking,
   a number becomes another interface element,
   the camera moves through the product.

7. Use premium easing.
   No linear movement.

8. Motion should overlap naturally.
   Elements should not all start and stop at exactly the same frame.

9. Use depth sparingly:
   perspective,
   soft parallax,
   scale,
   foreground/background separation,
   controlled depth of field if achievable.

10. NO effect exists simply because it looks cool.

11. No particle spam.

12. No fake glassmorphism everywhere.

13. No excessive blur.

14. No pointless 3D spinning cards.

15. No constant zooming.

16. No 20 different animation styles.

17. No bouncing UI.

18. No giant marketing paragraph.

19. Do not imitate a particular Apple commercial shot-for-shot.
    Capture the philosophy and production quality instead.

The visual confidence should come from restraint.

────────────────────────────────────
FORMAT
────────────────────────────────────

Primary master:

1920 × 1080
60 fps
16:9
H.264
maximum duration: 15.0 seconds

Target runtime:
approximately 14.0–15.0 seconds.

It must work as a social-media product reveal even without sound.

If practical AFTER the master is finished, also create a deliberately recomposed
vertical/social variant.

Do not merely crop the desktop composition.

But the desktop master is the priority.

────────────────────────────────────
STORY / EMOTIONAL ARC
────────────────────────────────────

Do not make this a list of five features.

It should feel like one continuous thought:

CHAOS → CONTROL → CLARITY → TAXTELLO

The first 1.5 seconds must already look premium.

The first meaningful product moment should happen by ~2 seconds.

No five-second logo intro.

Possible narrative direction:

“Everything about your business, finally in one place.”

But SHOW this instead of explaining it.

I want approximately four visual ideas across the whole film.

Use the strongest REAL Taxtello surfaces you find in the repository.

Strong candidates include:

• Finanzcockpit / Dashboard
• Rechnungen
• Belege
• Bank / matching
• Steuergesundheit / tax overview

You do NOT need to show all of them.

Choose the visually strongest combination.

────────────────────────────────────
SUGGESTED 15-SECOND STORYBOARD
────────────────────────────────────

Treat this as a strong starting point, not a rigid template.

0.00 – 1.20

BLACK / NAVY.

A tiny warm-gold glint appears.

The glint elegantly reveals either the Taxtello mark or a fragment of the
wordmark.

No generic logo fade.

Think machined precision.

The camera moves through or past the mark and the UI begins to emerge from it.

Very little or no copy.

─────────────────

1.20 – 4.40

FINANCIAL CONTROL.

Reveal the actual Taxtello Cockpit as a dimensional product surface.

Not just a screenshot placed on screen.

Reconstruct/crop/layer it so individual interface regions can animate.

The hero financial number resolves crisply.
The chart draws in.
Supporting metrics settle slightly later.

Use subtle stagger.

A single line of copy may appear, for example:

  “Alles im Blick.”

or another equally short German phrase if you find something more fitting.

Maximum ~3–4 words.

The interface must remain recognizable as the real product.

─────────────────

4.40 – 7.50

DOCUMENT / BOOKKEEPING TRANSFORMATION.

Use a visual object from the previous scene as the transition.

Example:

A gold chart point expands into the corner of a receipt/card.
The camera follows it.
A receipt/document enters.
Taxtello identifies or organizes it.
The document snaps elegantly into its corresponding booking / financial record.

Use magnetic alignment and precision.

No cheesy scanner laser.

No floating paper tornado.

Possible micro-copy:

  “Belege. Erledigt.”

Only if it improves the scene.

─────────────────

7.50 – 10.70

MONEY / INVOICES.

Morph or transition naturally into the real Rechnungen interface.

Use one strong moment:

an invoice status changes,
a payment resolves,
an amount moves into place,
or the overview assembles itself.

Numbers should feel tactile and precise.

Use JetBrains Mono where this matches the actual product.

Gold highlights the active state.

Green is used only for a genuinely positive semantic state.

Potential copy:

  “Geld. Im Griff.”

Again: optional and extremely short.

─────────────────

10.70 – 12.80

TAX / CLARITY.

Transition into the real Taxtello tax-health / financial guidance surface.

Do not claim that Taxtello magically guarantees correct taxes.

Communicate visibility and control.

Example:

multiple noisy signals collapse into one calm, structured tax overview.

Potential copy:

  “Steuern im Blick.”

This scene should feel calmer than the previous scene.

The rhythm briefly slows.

─────────────────

12.80 – 15.00

BRAND PAYOFF.

Pull the camera outward.

The UI compresses or folds into one beautiful Taxtello product object / surface.

Darkness returns around it.

The gold Taxtello wordmark resolves.

One short brand line underneath.

Explore strong final lines such as:

  “Dein Business. Klar.”

  “Buchhaltung. Unter Kontrolle.”

  “Einfach mehr Überblick.”

  “Alles fürs Business. An einem Ort.”

Choose based on the actual product positioning you find in the repo.

Do not use a line simply because I suggested it.

The final frame must have enough stillness to register.

End confidently.

No giant bouncing CTA.

────────────────────────────────────
TRANSITIONS
────────────────────────────────────

This is one of the most important parts.

I want transitions that make the viewer think:

“Of course the next scene came from that.”

Good:

chart line → document edge
gold pill → invoice button
financial number → amount in invoice
card edge → next surface
camera push through interface element
shared geometry
mask reveal using actual product shapes

Bad:

crossfade
random wipe
spin transition
glitch
whip-pan every two seconds
generic SaaS slide-left
zoom-blur spam

Direct cuts are allowed only when a deliberate rhythmic impact benefits the film.

────────────────────────────────────
MOTION
────────────────────────────────────

Motion needs weight.

Use curves comparable to:

cubic-bezier(0.16, 1, 0.3, 1)

where appropriate.

Different elements should have subtly different arrival times.

Prefer:

anticipation
overshoot below ~2%
settling
motion continuation
shared velocity between scenes

Avoid cartoon springiness.

Camera movement should feel like a high-end macro product shoot.

Imagine we are filming a physical premium object even though it is software.

────────────────────────────────────
LIGHTING / MATERIAL
────────────────────────────────────

Use extremely subtle environmental lighting.

Possible treatments:

• soft gold rim lighting
• dark navy falloff
• faint ambient bloom
• soft specular highlight passing across a surface
• restrained vignette
• subtle grain if it materially helps

Keep the interface crisp.

Do NOT blur the product just to look cinematic.

No fake glossy reflections that destroy legibility.

────────────────────────────────────
TYPOGRAPHY
────────────────────────────────────

Use very little copy.

No sentence should compete with the product.

Headlines should generally fit on one line.

Use Plus Jakarta Sans.

Strong typography may occasionally scale very large and become a transition
device itself.

Avoid generic motion-graphics behavior where every word animates independently.

Typography should move as designed objects.

────────────────────────────────────
SOUND / RHYTHM
────────────────────────────────────

Design the motion as if it were cut to approximately 115–120 BPM:
premium, kinetic, sophisticated, not frantic.

Important moments should land musically.

Suggested sound language:

• low soft impact for major reveal
• restrained tactile UI clicks
• subtle metallic/glass tonal tick
• soft low-frequency movement during camera transitions
• elegant resolved tone at the logo payoff

Avoid:

• huge cinematic trailer boom
• EDM risers
• loud whooshes everywhere
• stock “tech interface” sounds
• rap beat
• aggressive bass

If there is no legally safe music/audio asset in the project, DO NOT pull
copyrighted audio from the internet.

Deliver the visual master without copyrighted music and create a concise cue
sheet describing where music/SFX should hit.

If suitable safe/local audio exists, use it.

────────────────────────────────────
REAL PRODUCT ONLY
────────────────────────────────────

This is critical.

Inspect current main.

Do not invent screens.

Do not invent metrics that imply real customer data.

Use clearly synthetic/demo-safe values if required.

Do not accidentally expose any personal, test-user or production information.

Reuse the visual structure of the actual Taxtello UI.

If a screen needs to be motion-separated, recreate it faithfully in React from
the real design system instead of simply scaling a giant screenshot.

The result should still look unmistakably like Taxtello.

────────────────────────────────────
IMPLEMENTATION EXPECTATIONS
────────────────────────────────────

Work directly in:

  /taxtello/beta-motion

Create the new composition alongside the existing one.

Keep existing compositions working.

Structure the new work cleanly.

Prefer reusable primitives for:

• camera surface
• product frame
• masked transitions
• text reveals
• UI region reveals
• ambient lighting
• shared-element transitions

Avoid one 1,500-line component.

Use deterministic Remotion animation driven by frame/time.

No setTimeout.
No nondeterministic animations.

Respect 60 fps throughout.

Use interpolation/spring/easing deliberately.

────────────────────────────────────
DO NOT STOP AFTER FIRST IMPLEMENTATION
────────────────────────────────────

This is a visual task.

You MUST review the actual rendered output.

Required workflow:

1. Inspect repository and real brand/product.

2. Write a concise storyboard with:
   - exact timestamps
   - key visual
   - transition logic
   - copy
   - intended emotional rhythm

3. Implement it.

4. Run typecheck / relevant checks.

5. Render representative frames at roughly:
   0.0 s
   1.0 s
   2.5 s
   4.5 s
   6.5 s
   8.5 s
   10.5 s
   12.5 s
   14.0 s
   14.8 s

6. VISUALLY INSPECT THOSE IMAGES.

Do not merely confirm that rendering succeeded.

Ask:

Does this look like an Apple-tier product film?

Does anything look like a template?

Is there too much on screen?

Is the product legible?

Are transitions logically connected?

Does Taxtello gold feel premium?

Does every frame look composed?

7. Fix visual weaknesses.

8. Render the complete film.

9. Inspect multiple exact decoded frames from the final MP4, not only browser
   screenshots.

10. Iterate again if necessary.

Do not declare success because the code compiles.

The deliverable is the FILM.

────────────────────────────────────
QUALITY BAR
────────────────────────────────────

Reject your own result if it feels like:

• a SaaS template
• a PowerPoint animation
• a website screen recording
• a generic Remotion demo
• a crypto advertisement
• an AI-generated promo template
• five screenshots sliding around
• excessive marketing copy

Every important frame should be good enough to use as a still advertisement.

I would rather have:

3 extraordinary visual moments

than

10 mediocre feature animations.

────────────────────────────────────
FINAL DELIVERABLES
────────────────────────────────────

Provide:

1. Final storyboard
2. New Remotion composition source
3. 1920×1080 / 60fps final MP4
4. Poster/final frame
5. Contact sheet with representative frames from the film
6. Exact runtime
7. List of real Taxtello assets/screens used
8. Brief explanation of the motion language
9. Any remaining visual compromises
10. Commands to reproduce the render

Save outputs in a clearly named directory such as:

  /taxtello/beta-motion/out/showreel-15/

Do not deploy anything.
Do not modify production data.
Do not merge anything.

Go all out creatively, but exercise ruthless restraint.

Make Taxtello look expensive.
```
