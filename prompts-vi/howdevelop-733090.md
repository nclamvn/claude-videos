# Video Opus 5.5 của @HowDevelop

[▶ Xem bản gốc và bản làm lại trực tiếp trên Skillry](https://skillry.dev/ai-videos/opus-5-5/howdevelop-733090?utm_source=github&utm_medium=readme&utm_campaign=awesome-opus5-5-videos) · [Bài đăng gốc](https://x.com/HowDevelop/status/2103840883812733090)

- **Danh mục:** Motion graphics
- **Bản làm lại dùng:** Canvas
- **Tác giả:** [@HowDevelop](https://x.com/HowDevelop)

Trang gốc (chưa dịch): [prompts/howdevelop-733090.md](../prompts/howdevelop-733090.md)

## Prompt (tiếng Việt)

```text
Hãy tạo và render một video motion graphics dài 15 giây giới thiệu TanStack AI. Làm cho nó mang cảm giác của một phim ra mắt công cụ cho lập trình viên cao cấp do Studio1 sản xuất: nhanh, chính xác, gây bất ngờ về thị giác, và đủ trau chuốt để mở màn một keynote hoặc dẫn đầu một chiến dịch mạng xã hội.

  Dùng thông tin tính năng TanStack AI dưới đây làm nguồn sự thật. Studio1 là đơn vị trình bày bộ phim; không được ngụ ý rằng
  Studio1 đã xây dựng TanStack AI.

  Định dạng và sản phẩm bàn giao
  - 1920×1080, 30 fps, đúng 15 giây; giữ nội dung quan trọng trong vùng trung tâm an toàn cho 9:16.
  - Bàn giao file MP4 đã render và project/mã nguồn có thể chỉnh sửa. Dùng Remotion hoặc một quy trình motion graphics dựa trên code khác nếu có.
  - Dùng chữ thật, chỉnh sửa được và đồ hoạ kiểu vector. Không dựa vào chữ do AI sinh ra bên trong hình ảnh.
  - Thêm phần thiết kế âm thanh điện tử nguyên bản: một nhịp đập mở đầu tiết chế, các cú hit chuyển cảnh đồng bộ chặt chẽ, đà tăng dần
  - Thêm phần thiết kế âm thanh điện tử nguyên bản: một nhịp đập mở đầu tiết chế, các cú hit chuyển cảnh đồng bộ chặt chẽ, đà tăng dần,
  và một đoạn kết thoả mãn. Câu chuyện cũng phải hiểu được khi tắt tiếng.

  Định hướng hình ảnh
  Nền graphite tối; gradient phát sáng và các chớp sáng có kiểm soát lấy cảm hứng từ nhận diện của TanStack. Chữ sắc nét,
  code chuyển động, các mảnh giao diện xếp lớp, dữ liệu chảy, các nhánh rẽ, và chuyển động camera mượt với chiều sâu
  thuyết phục. Độ tương phản cao và khoảng cách hoàn hảo. Mỗi chuyển cảnh phải minh hoạ trực quan một tính năng, thay vì
  chỉ thay một thẻ tiêu đề bằng một thẻ khác. Giữ mọi chữ trên màn hình ngắn gọn và dễ đọc. Tránh footage stock
  chung chung, logo xoay tròn, dashboard giả, hiệu ứng glitch quá đà, và code nhỏ xíu không ai đọc được.

  Trình tự chính xác 15 giây
  - 0:00–0:02 — Mồi câu: Một con trỏ nhập prompt nhấp nháy. Nó gửi đi một tín hiệu nở ra thành một mạng lưới
  khả năng. Trên màn hình: “What can one AI API become?”
  - 0:02–0:04 — Lõi và nhà cung cấp: Tín hiệu hội tụ thành chat(); các nút nhà cung cấp kết nối và hoán đổi nhanh mà không
  làm đứt luồng trung tâm. Trên màn hình: “chat() · 24 providers”
  - 0:04–0:06.5 — Đa phương thức: Một luồng liên tục biến đổi thành văn bản, dạng sóng âm, khung hình ảnh và timeline video.
  Trên màn hình: “One pattern. Every modality.”
  - 0:06.5–0:09 — Agent và công cụ: Luồng tách nhánh thành các lượt chạy agent trong sandbox, rồi chạm tới công cụ bên ngoài
  thông qua MCP. Thể hiện các lượt chạy riêng biệt tiến triển song song. Trên màn hình: “Agents · Sandboxes · MCP”
  - 0:09–0:11.5 — Độ tin cậy: Một luồng bị gián đoạn đứng hình, kết nối lại và tiếp tục từ đúng điểm cũ; một xác nhận
  type-check sạch sẽ khớp vào vị trí. Trên màn hình: “Persistent. Durable. Type-safe.”
  - 0:11.5–0:15 — Lộ diện: Mọi đường hội tụ vào một bố cục kết thúc đậm nét: “TanStack AI” rồi đến “Build what’s
  next.” Thêm một dòng ghi công nhỏ “A Studio1 film”, phụ về mặt thị giác so với TanStack AI. Giữ khung hình cuối đủ lâu
  để đọc.

  Rào chắn về độ chính xác
  Bài viết được cung cấp nói rằng TanStack AI đang ở giai đoạn release candidate, hỗ trợ 24 nhà cung cấp, dùng AG-UI, và
  cung cấp các primitive có thể kết hợp gồm chat(), tạo media, sandbox và agent-harness, MCP, type safety, persistence,
  và luồng có thể tiếp tục (resumable streams). Không gọi nó là bản phát hành v1 ổn định. Không trình bày các tính năng orchestration đang lên kế hoạch như thể đã
  phát hành.

  Hãy làm video, kiểm tra kết quả đã render, và sửa mọi chữ bị cắt, chuyển cảnh yếu, nhịp lệch thời điểm, hoặc
  khung hình khó đọc trước khi bàn giao. Mục tiêu là một showreel đáng nhớ, không phải một bài trình chiếu liệt kê tính năng.
```

## Prompt gốc

```text
Create and render a 15-second motion graphics video introducing TanStack AI. Make it feel like a premium            
  developer-tool launch film produced by Studio1: fast, precise, visually surprising, and polished enough to open a   
  keynote or lead a social campaign.                                                                                  
                                                                                                                      
  Use the TanStack AI feature details below as the source of truth. Studio1 is presenting the film; do not imply      
  Studio1 built TanStack AI.                                                                                          
                                                                                                                      
  Format and deliverables                                                                                             
  - 1920×1080, 30 fps, exactly 15 seconds; keep important content within a 9:16-safe central area.                    
  - Deliver the rendered MP4 and the editable project/source. Use Remotion or another code-based motion graphics      
  workflow if available.                                                                                              
  - Use real, editable typography and vector-style graphics. Do not rely on AI-generated text inside images.          
  - Add an original electronic sound design: a restrained opening pulse, tightly synchronized transition hits, rising 
  - Add an original electronic sound design: a restrained opening pulse, tightly synchronized transition hits, rising 
  momentum, and a satisfying final resolve. The story must also work muted.                                           
                                                                                                                      
  Visual direction                                                                                                    
  Dark graphite canvas; luminous gradients and controlled flashes inspired by TanStack’s identity. Crisp typography,  
  kinetic code, layered interface fragments, streaming data, branching paths, and smooth camera moves with convincing 
  depth. High contrast and immaculate spacing. Every transition should visually demonstrate a feature, rather than    
  simply replace one title card with another. Keep all on-screen wording brief and legible. Avoid generic stock       
  footage, spinning logos, fake dashboards, excessive glitch effects, and tiny code nobody can read.                  
                                                                                                                      
  Exact 15-second sequence                                                                                            
  - 0:00–0:02 — Hook: A single prompt cursor blinks. It sends one signal that expands into a network of               
  possibilities. On-screen: “What can one AI API become?”                                                             
  - 0:02–0:04 — Core and providers: The signal resolves into chat(); provider nodes connect and swap rapidly without  
  breaking the central flow. On-screen: “chat() · 24 providers”                                                       
  - 0:04–0:06.5 — Multimodal: One continuous stream transforms into text, waveform, image frame, and video timeline.  
  On-screen: “One pattern. Every modality.”                                                                           
  - 0:06.5–0:09 — Agents and tools: The stream branches into sandboxed agent runs, then reaches external tools        
  through MCP. Show distinct runs progressing in parallel. On-screen: “Agents · Sandboxes · MCP”                      
  - 0:09–0:11.5 — Reliability: An interrupted stream freezes, reconnects, and resumes from the same point; a clean    
  type-check confirmation snaps into place. On-screen: “Persistent. Durable. Type-safe.”                              
  - 0:11.5–0:15 — Reveal: All paths converge into a bold final composition: “TanStack AI” followed by “Build what’s   
  next.” Add a small “A Studio1 film” credit, visually subordinate to TanStack AI. Hold the final frame long enough   
  to read it.                                                                                                         
                                                                                                                      
  Accuracy guardrails                                                                                                 
  The supplied article says TanStack AI is in the release candidate phase, supports 24 providers, uses AG-UI, and     
  offers composable chat(), media generation, sandbox and agent-harness primitives, MCP, type safety, persistence,    
  and resumable streams. Do not call it a stable v1 release. Do not present planned orchestration features as already 
  shipped.                                                                                                            
                                                                                                                      
  Make the video, inspect the rendered result, and fix any clipped text, weak transitions, mistimed beats, or         
  unreadable frames before delivering it. The goal is a memorable showreel, not a slideshow of feature bullets.
```
