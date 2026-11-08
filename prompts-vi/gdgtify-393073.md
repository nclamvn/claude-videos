# Chứng minh của Euclid bằng chữ chuyển động

_Euclid's Proof Kinetic Typography_

Video Opus 5.5 của [@Gdgtify](https://x.com/Gdgtify) · [Bài đăng gốc kèm video](https://x.com/Gdgtify/status/2107054188836393073)

- **Danh mục:** Motion graphics
- **Tác giả:** [@Gdgtify](https://x.com/Gdgtify)

Thêm video Opus 5.5, mỗi video kèm bản làm lại trực tiếp: [skillry.dev/ai-videos/opus-5-5](https://skillry.dev/ai-videos/opus-5-5?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos)

Trang gốc (chưa dịch): [prompts/gdgtify-393073.md](../prompts/gdgtify-393073.md)

## Prompt (tiếng Việt)

```text
Hãy tạo một chứng minh toán học động học có tiêu đề “THERE IS NO LAST PRIME.”
Dàn dựng lập luận của Euclid như một hệ thống kiểm định cơ khí tuyệt đẹp. Chữ trở thành các bánh số khắc chìm, băng chuyền phép nhân và đồng hồ chỉ số dư.
Cơ cấu phải chứng minh định lý, chứ không phải trang trí cho một lời giải thích thuyết minh.
SẢN PHẨM GIAO
Một file HTML tự chứa.
1080×1080.
Loop 20.00 giây.
Render tất định 60fps.
Dùng SVG và/hoặc Canvas.
Không có tài nguyên runtime bên ngoài.
BẢNG MÀU
Sứ trắng # F0EEE6.
Than chì #222522.
Xanh công nghiệp # 416B53.
Cam cảnh báo # E78636.
CHỮ
Monospace dạng bảng (tabular) cho mọi phép tính.
Grotesque hình học nét dày cho các câu khẳng định.
Serif kỹ thuật cỡ nhỏ cho mệnh đề logic cuối cùng.
Dùng khoảng cách chặt chẽ và chữ số lớn, dễ đọc.
CHỮ CỐ ĐỊNH
SUPPOSE THE LIST ENDS.
MULTIPLY EVERY PRIME ON IT.
ADD ONE.
EVERY LISTED PRIME LEAVES REMAINDER 1.
A PRIME FACTOR IS MISSING.
THERE IS NO LAST PRIME.
VÍ DỤ TRUNG TÂM
Danh sách giả định:
2, 3, 5, 7, 11, 13
Tích:
30030
Tích cộng một:
30031
Phân tích thừa số:
30031 = 59 × 509
Cả hai thừa số đều không có trong danh sách giả định.
LOGIC QUAN TRỌNG
Không khẳng định rằng nhân các số nguyên tố rồi cộng một luôn cho ra số nguyên tố.
Số được dựng ra có thể là hợp số.
Các thừa số nguyên tố của nó không thể là bất kỳ số nguyên tố nào trong danh sách được giả định là đầy đủ.
Ví dụ bằng số minh họa cho mâu thuẫn tổng quát.
STORYBOARD
0.00–3.00
SUPPOSE THE LIST ENDS.
Sáu bánh số nguyên tố khắc chìm khóa vào một giá kiểm định hữu hạn.
Một chốt chặn vật lý đóng lại sau số 13.
Chốt chặn làm cho tuyên bố về tính đầy đủ trở nên nhìn thấy được.
3.00–6.50
MULTIPLY EVERY PRIME ON IT.
Một băng chuyền nối cả sáu bánh.
Hiển thị một biểu thức nhân dễ đọc:
2 × 3 × 5 × 7 × 11 × 13 = 30030.
Chỉ dùng chữ số cuộn trong lúc chuyển động; giá trị cuối dừng lại sắc nét.
6.50–8.50
ADD ONE.
Một đơn vị màu cam duy nhất đi vào cơ cấu.
Nó đẩy đầu ra từ 30030 lên 30031.
Biến thay đổi một đơn vị này thành sự kiện thị giác quyết định.
8.50–12.50
EVERY LISTED PRIME LEAVES REMAINDER 1.
Đầu ra đi qua sáu cổng chia.
Mỗi cổng được gắn nhãn số nguyên tố của nó.
Mỗi cổng cho ra cùng một số dư nhìn thấy được: 1.
Sắp xếp sáu kết quả hoàn chỉnh để khán giả có thể so sánh chúng cùng lúc.
12.50–15.50
Đầu ra mở ra như một vỏ cơ khí có gắn nhãn.
Bên trong, hé lộ:
59 × 509.
Các thừa số này không thể nằm vừa trong giá được cho là đầy đủ.
Chốt chặn bị các thẻ thừa số mới đẩy bật ra ngoài.
15.50–18.00
A PRIME FACTOR IS MISSING.
Sau đó:
THERE IS NO LAST PRIME.
Giữ mệnh đề tổng quát phía trên giá đã mở.
Kèm dạng tổng quát gọn:
N = p₁p₂…pₖ + 1.
N mod pᵢ = 1.
18.00–20.00
Một tấm kiểm định mới trượt phủ lên cơ cấu.
Mép khắc của nó trở thành chốt chặn ban đầu.
Reset các bánh bị che khuất.
Hé lộ giá mở đầu ở đúng vị trí ban đầu.
CHUYỂN ĐỘNG BẮT BUỘC
Mọi thao tác cơ khí phải tương ứng với một phép toán trong chứng minh.
Dùng các chuyển động xoay liên kết
```

## Prompt gốc

```text
Create a kinetic mathematical proof titled “THERE IS NO LAST PRIME.”
Stage Euclid’s argument as a beautiful mechanical inspection system. Typography becomes engraved number wheels, multiplication belts, and remainder indicators.
The mechanism must demonstrate the proof rather than decorate a narrated explanation.
DELIVERABLE
One self-contained HTML file.
1080×1080.
20.00-second loop.
Deterministic 60fps rendering.
Use SVG and/or Canvas.
No external runtime assets.
PALETTE
Porcelain # F0EEE6.
Graphite #222522.
Industrial green # 416B53.
Warning orange # E78636.
TYPE
Tabular monospace for all calculations.
Heavy geometric grotesque for declarations.
Small technical serif for the final logical statement.
Use disciplined spacing and large, readable numerals.
LOCKED COPY
SUPPOSE THE LIST ENDS.
MULTIPLY EVERY PRIME ON IT.
ADD ONE.
EVERY LISTED PRIME LEAVES REMAINDER 1.
A PRIME FACTOR IS MISSING.
THERE IS NO LAST PRIME.
CENTRAL EXAMPLE
Assumed list:
2, 3, 5, 7, 11, 13
Product:
30030
Product plus one:
30031
Factorization:
30031 = 59 × 509
Both factors are absent from the assumed list.
IMPORTANT LOGIC
Do not claim that multiplying primes and adding one always produces a prime.
The constructed number may be composite.
Its prime factors cannot be any prime on the assumed complete list.
The numerical example illustrates the general contradiction.
STORYBOARD
0.00–3.00
SUPPOSE THE LIST ENDS.
Six engraved prime wheels lock into a finite inspection rack.
A physical end-stop closes after 13.
The end-stop makes the claim of completeness visible.
3.00–6.50
MULTIPLY EVERY PRIME ON IT.
A belt couples all six wheels.
Show a readable multiplication expression:
2 × 3 × 5 × 7 × 11 × 13 = 30030.
Use rolling numerals only during movement; settle the final value sharply.
6.50–8.50
ADD ONE.
A single orange unit enters the mechanism.
It advances the output from 30030 to 30031.
Make this one-unit change the decisive visual event.
8.50–12.50
EVERY LISTED PRIME LEAVES REMAINDER 1.
The output passes through six division gates.
Each gate is labelled with its prime.
Each produces the same visible remainder: 1.
Arrange the six completed results so the audience can compare them simultaneously.
12.50–15.50
The output opens as a labelled mechanical casing.
Inside, reveal:
59 × 509.
These factors cannot fit into the supposedly complete rack.
The end-stop is forced outward by the new factor cards.
15.50–18.00
A PRIME FACTOR IS MISSING.
Then:
THERE IS NO LAST PRIME.
Hold the general statement above the opened rack.
Include the compact general form:
N = p₁p₂…pₖ + 1.
N mod pᵢ = 1.
18.00–20.00
A fresh inspection plate slides over the mechanism.
Its engraved edge becomes the original end-stop.
Reset the hidden wheels.
Reveal the opening rack at the exact initial position.
REQUIRED MOTION
Every mechanical action must correspond to an operation in the proof.
Use linked rota
```
