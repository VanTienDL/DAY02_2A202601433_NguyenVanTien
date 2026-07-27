# 01 — Individual Problem Scan

## Scan rộng

Tôi đã scan 7 problems từ các bối cảnh khác nhau, vượt mức tối thiểu 5 problems.

## Bảng scan

| # | Lăng kính | Problem quan sát được | Ai chịu ảnh hưởng? | Dấu hiệu thật |
|---|---|---|---|---|
| 1 | AI có thể tốt hơn | Sales không có thông tin quá cá nhân hóa về khách hàng | Sales, khách hàng mua xe | Phải tư vấn kiểu chung chung làm mất khách đòi cá nhân hóa; mỗi lần phải tìm riêng lộ tuyến sạc |
| 2 | Tốn thời gian | Khách hàng tốn rất nhiều thời gian tra cứu lộ tuyến và so sánh chi phí | Khách hàng có ý định mua xe | Mỗi lần tìm thông tin mất 30-45 phút; nhiều khách bỏ cuộc vì kiệt sức |
| 3 | Tốn thời gian | Cán bộ phòng ban tốn thời gian tra cứu quy chế, quy định vì số lượng quá nhiều | Cán bộ, công chức | Làm việc thiếu hiệu quả; hay tìm sai quy định; mỗi lần tra cứu mất 15-20 phút |
| 4 | Lặp lại | HR phải lặp lại việc trả lời các câu hỏi chung về quy định nhân sự | HR staff, nhân viên | Lặp lại 10-15 lần/tháng; mỗi câu trả lời mất 5-10 phút; HR cảm thấy công việc nhàm chán |
| 5 | Lặp lại | Sinh viên mới liên tục hỏi lên diễn đàn những câu hỏi đã được trả lời trước đó | Sinh viên mới, mentor | Mỗi tuần có 20-30 câu hỏi giống nhau; mentor mất công repost câu trả lời cũ; diễn đàn rối vì duplicate |
| 6 | Pain từ người khác | Mentor khó theo dõi progress của sinh viên vì phải log vào nhiều nơi khác nhau | Mentor, sinh viên | Không có central dashboard; phải check Discord, email, Jira; dễ bỏ sót ai chưa nộp bài |
| 7 | Tốn thời gian | Sinh viên mất thời gian search từ trước đó xem đã nộp bài hay chưa | Sinh viên | Phải check nhiều tool khác nhau; dễ nhầm deadline; nộp trễ vì không biết chính xác deadline của mình |

## Top 3 Problems

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---|---|---|---|
| 1 | Sales không có thông tin quá cá nhân hóa về khách hàng | Có nhu cầu tư vấn chuyên sâu/cá nhân hóa thực tế, dữ liệu lộ tuyến & chi phí phức tạp, AI giúp hỗ trợ rất tốt ở khâu tổng hợp thông tin | Mức độ sẵn có của dữ liệu lịch sử/nhu cầu khách |
| 2 | Khách hàng tốn rất nhiều thời gian tra cứu lộ tuyến và so sánh chi phí | Bottleneck về thời gian cực lớn (30-45 phút/lần), pain điểm chạm trực tiếp tới quyết định mua xe | Khả năng thu thập data và so sánh |
| 3 | Cán bộ phòng ban tốn thời gian tra cứu quy chế, quy định vì số lượng quá nhiều | Quy mô tài liệu quy định quá đồ sộ, tần suất tra cứu cao, tác động trực tiếp tới hiệu suất công việc hành chính | Độ chuẩn xác bắt buộc phải 100% |

---

## Problem Card #1 — Sales không có thông tin cá nhân hóa về khách hàng

**Problem 1 câu:**
Sales tư vấn xe điện không có sẵn thông tin cá nhân hóa (lộ tuyến di chuyển, trạm sạc, chi phí thực tế) theo đúng nhu cầu từng khách, nên tư vấn theo kịch bản chung và dễ mất khách đang cần một câu trả lời cụ thể.

**Actor:**
Nhân viên sales tại showroom, chịu trách nhiệm tư vấn cho khách hàng có ý định mua xe điện.

**Thời điểm / bối cảnh:**
Khi khách hàng đến showroom hoặc liên hệ tư vấn, thường hỏi những câu rất cụ thể theo hoàn cảnh của họ: "Nhà tôi ở A, hay đi B, xe này chạy có đủ không, sạc ở đâu, tốn bao nhiêu tiền?"

**Current workflow:**

```text
1. Khách hàng chia sẻ nhu cầu: khu vực sống, lộ trình hay đi, tần suất di chuyển
2. Sales hỏi thêm thông tin cơ bản (ngân sách, dòng xe quan tâm)
3. Sales tư vấn theo kịch bản chung: thông số xe, giá bán, ưu đãi
4. Khách hỏi sâu hơn về lộ tuyến/trạm sạc/chi phí thực tế theo tuyến của họ
5. Sales không có sẵn dữ liệu, phải tự tra cứu riêng (bản đồ trạm sạc, hỏi đồng nghiệp, ước lượng tay) hoặc hẹn trả lời sau
6. Khách hàng chờ, mất hứng vì tư vấn chưa đủ cụ thể, có thể rời đi tham khảo hãng khác
```

**Bottleneck:**
Bước 5 — sales phải tự tra cứu riêng cho từng khách vì không có công cụ tổng hợp sẵn dữ liệu lộ tuyến/trạm sạc/chi phí; mỗi lần tra cứu mất nhiều thời gian và không nhất quán giữa các sales.

**Impact:**
- Khách hàng: Không nhận được câu trả lời cá nhân hóa ngay tại chỗ, dễ mất niềm tin vào quyết định mua, có thể bỏ đi tham khảo nơi khác.
- Sales: Mất thời gian tra cứu thủ công cho từng khách, khó chốt sale ngay trong buổi tư vấn đầu.
- Showroom/hãng xe: Giảm tỷ lệ chuyển đổi từ tư vấn sang mua hàng.

**Success metric:**
- Giảm thời gian sales cần để trả lời câu hỏi cá nhân hóa (lộ tuyến, trạm sạc, chi phí) từ mức hiện tại xuống dưới vài phút ngay trong buổi tư vấn.
- Tăng tỷ lệ khách hàng nhận được câu trả lời cụ thể ngay tại chỗ thay vì phải hẹn lại.
- Không giảm độ chính xác thông tin so với sales tự tra cứu tay.

**Non-AI alternative:**
- Tài liệu tĩnh liệt kê trạm sạc theo khu vực: không cập nhật kịp, không tính theo lộ trình cụ thể của từng khách.
- Đào tạo sales thuộc lòng thông tin trạm sạc phổ biến: không khả thi vì số lượng tuyến đường/trạm sạc quá lớn và luôn thay đổi.

**AI hypothesis:**
Xây công cụ cho sales nhập điểm đi/điểm đến hoặc khu vực sinh sống của khách → AI tổng hợp lộ trình phù hợp, trạm sạc gần tuyến, ước tính chi phí sạc so với xăng, giúp sales tư vấn cá nhân hóa ngay tại chỗ.

**Quick gut:**
Workflow (có thể cần Agent nếu phải tính toán lộ trình nhiều điểm dừng phức tạp).

---

### Draft current workflow

```text
CURRENT STATE — không xác định trước, xử lý ngoài luồng khi khách hỏi sâu

[1 Khách chia sẻ nhu cầu: 2-3']
→ [2 Sales hỏi thêm thông tin: 2']
→ [3 Sales tư vấn theo kịch bản chung: 5']
→ [4 Khách hỏi sâu về lộ tuyến/sạc/chi phí: 1']
→ [5 Sales tự tra cứu riêng: 10-20'] ← bottleneck ← không nhất quán giữa các sales
→ [6 Khách chờ hoặc hẹn trả lời sau: variable] ← rủi ro mất khách

Risk: Khách rời đi tham khảo nơi khác trong lúc chờ.
```

### Draft future workflow

```text
FUTURE STATE — trả lời ngay trong buổi tư vấn

[1 Khách chia sẻ nhu cầu: 2-3']
→ [2 Sales nhập điểm đi/đến + nhu cầu vào công cụ AI: 1']
→ [3 AI tổng hợp lộ trình, trạm sạc, chi phí ước tính: instant]
→ [4 Sales trình bày kết quả cho khách, giải thích thêm: 3-5']
→ [5 Sales chốt bước tiếp theo với khách: 2']

Total: dưới 10 phút, xử lý ngay tại chỗ thay vì hẹn lại.

Fallback: Nếu AI thiếu dữ liệu trạm sạc ở khu vực đó → sales báo rõ với khách và hẹn xác nhận lại, không tự bịa thông tin.
```

---

## Problem Card #2 — Khách hàng tốn thời gian tra cứu lộ tuyến và so sánh chi phí

**Problem 1 câu:**
Khách hàng có ý định mua xe điện phải tự tra cứu lộ tuyến, trạm sạc và so sánh chi phí từ nhiều nguồn rời rạc trước khi quyết định mua, mất 30-45 phút mỗi lần và nhiều người bỏ cuộc giữa chừng.

**Actor:**
Khách hàng đang cân nhắc mua xe điện, tự tìm hiểu trước hoặc sau khi gặp sales.

**Thời điểm / bối cảnh:**
Trong giai đoạn cân nhắc mua xe, khách tự tra cứu online (thường vào buổi tối, ngoài giờ gặp sales) để kiểm tra xem xe có phù hợp với lộ trình di chuyển hằng ngày của họ không.

**Current workflow:**

```text
1. Khách tìm tuyến đường quen thuộc trên Google Maps
2. Khách tìm trạm sạc dọc tuyến bằng app riêng (thường phải dùng nhiều app khác nhau)
3. Khách tính toán thời gian sạc và số lần cần dừng
4. Khách ước tính chi phí sạc, so sánh với chi phí xăng của xe hiện tại
5. Khách so sánh giữa nhiều dòng xe/hãng khác nhau (lặp lại bước 1-4 cho từng xe)
6. Nếu chưa chắc, khách hỏi thêm trên hội nhóm/diễn đàn xe điện
7. Khách ra quyết định tiếp tục tìm hiểu hoặc bỏ cuộc vì quá mất công
```

**Bottleneck:**
Bước 2-5 — phải dùng nhiều nguồn rời rạc (bản đồ, app trạm sạc, tính tay chi phí) và lặp lại cho từng dòng xe muốn so sánh; mỗi lần tra cứu mất 30-45 phút.

**Impact:**
- Khách hàng: Mất nhiều thời gian và công sức, một số khách bỏ cuộc vì kiệt sức trước khi ra quyết định mua.
- Hãng xe/showroom: Mất khách hàng tiềm năng ở chính giai đoạn cân nhắc, trước khi kịp gặp sales tư vấn thêm.
- Thị trường xe điện nói chung: Rào cản thông tin làm chậm quá trình chuyển đổi từ xe xăng sang xe điện.

**Success metric:**
- Giảm thời gian khách cần để tra cứu lộ tuyến + so sánh chi phí từ 30-45 phút xuống dưới 10 phút cho một lần tra cứu.
- Tăng tỷ lệ khách hoàn thành so sánh (không bỏ cuộc giữa chừng).
- Khách có thể so sánh nhiều dòng xe trong cùng một lần tra cứu thay vì lặp lại thủ công từng xe.

**Non-AI alternative:**
- Trang so sánh tĩnh theo các tuyến đường phổ biến có sẵn: không đáp ứng được lộ trình cá nhân của từng khách.
- Bảng giá/chi phí trung bình chung: không chính xác vì phụ thuộc vào tuyến đường và thói quen di chuyển thực tế.

**AI hypothesis:**
Xây công cụ cho khách tự nhập điểm đi/đến hoặc lộ trình quen thuộc → AI tự động tổng hợp trạm sạc dọc tuyến, ước tính thời gian/chi phí sạc, so sánh với chi phí xăng và giữa các dòng xe, trả kết quả trong một lần tra cứu duy nhất.

**Quick gut:**
Workflow hoặc Agent (vì cần tổng hợp từ nhiều nguồn dữ liệu và tính toán nhiều bước).

---

### Draft current workflow

```text
CURRENT STATE — 30-45 phút/lần

[1 Tìm tuyến đường trên Google Maps: 5-10']
→ [2 Tìm trạm sạc dọc tuyến bằng app riêng: 10-15'] ← bottleneck
→ [3 Tính thời gian/số lần sạc: 5']
→ [4 Ước tính chi phí, so sánh với xăng: 5-10'] ← bottleneck
→ [5 Lặp lại 1-4 cho từng dòng xe muốn so sánh: nhân lên nhiều lần]
→ [6 Hỏi thêm trên hội nhóm nếu chưa chắc: 5-10']

Risk: Khách kiệt sức, bỏ cuộc trước khi ra quyết định.
```

### Draft future workflow

```text
FUTURE STATE — dưới 10 phút/lần

[1 Khách nhập điểm đi/đến + dòng xe muốn so sánh: 1-2']
→ [2 AI tổng hợp trạm sạc dọc tuyến từ nhiều nguồn: instant]
→ [3 AI tính thời gian/chi phí sạc, so sánh với xăng: instant]
→ [4 AI hiển thị bảng so sánh nhiều dòng xe cùng lúc: instant]
→ [5 Khách xem kết quả, quyết định liên hệ sales hoặc tìm hiểu thêm: 3-5']

Total: dưới 10 phút cho một lần so sánh, kể cả nhiều dòng xe.

Fallback: Nếu dữ liệu trạm sạc ở khu vực đó chưa đủ tin cậy → hệ thống cảnh báo rõ và gợi ý khách xác nhận thêm với sales.
```

---

## Problem Card #3 — Cán bộ phòng ban tra cứu quy chế, quy định

**Problem 1 câu:**
Cán bộ phòng ban mất nhiều thời gian tra cứu quy chế, quy định nội bộ vì số lượng văn bản quá lớn, dễ áp dụng nhầm văn bản cũ đã hết hiệu lực.

**Actor:**
Cán bộ, công chức làm việc tại các phòng ban cần đối chiếu quy chế/quy định trước khi xử lý công việc hoặc ra quyết định hành chính.

**Thời điểm / bối cảnh:**
Trong quá trình xử lý công việc hằng ngày, khi gặp tình huống cần áp dụng đúng quy định (ví dụ: chế độ, quy trình phê duyệt, thẩm quyền), cán bộ phải tra lại văn bản quy chế liên quan.

**Current workflow:**

```text
1. Cán bộ phát sinh câu hỏi cần áp dụng quy định cụ thể
2. Cán bộ tìm trong hệ thống lưu trữ văn bản nội bộ (thư mục, cổng thông tin)
3. Cán bộ đọc lướt nhiều văn bản để tìm điều khoản liên quan
4. Cán bộ đối chiếu xem văn bản có phải bản mới nhất, còn hiệu lực hay không
5. Nếu chưa chắc, cán bộ hỏi thêm đồng nghiệp hoặc quản lý để xác nhận
6. Cán bộ áp dụng vào công việc
```

**Bottleneck:**
Bước 3-4 — do số lượng văn bản quy định quá nhiều và không có công cụ tìm kiếm theo ngữ nghĩa, cán bộ phải đọc lướt nhiều văn bản và tự đối chiếu hiệu lực; mỗi lần tra cứu mất 15-20 phút, đôi khi vẫn áp dụng nhầm quy định cũ.

**Impact:**
- Cán bộ: Làm việc kém hiệu quả, mất thời gian cho công việc chuyên môn khác.
- Phòng ban/tổ chức: Rủi ro áp dụng sai quy định dẫn đến quyết định hành chính không đúng, có thể ảnh hưởng đến quyền lợi của người liên quan hoặc gây khiếu nại.
- Người quản lý: Phải dành thời gian xác nhận lại quy định thay vì để cán bộ tự tra cứu chính xác ngay từ đầu.

**Success metric:**
- Giảm thời gian tra cứu quy định từ 15-20 phút xuống dưới 5 phút mỗi lần.
- Giảm tỷ lệ áp dụng nhầm văn bản đã hết hiệu lực xuống gần 0.
- Mỗi câu trả lời có trích dẫn rõ nguồn văn bản và tình trạng hiệu lực để cán bộ tự kiểm tra lại.

**Non-AI alternative:**
- Lập bảng chỉ mục (index) quy định theo chủ đề, cập nhật thủ công: giúp giảm thời gian tìm ban đầu, nhưng cần duy trì liên tục và dễ lỗi thời nếu quên cập nhật khi có văn bản mới.
- Tập huấn định kỳ về quy định mới: giúp cán bộ nắm được thay đổi lớn, nhưng không giải quyết được nhu cầu tra cứu chi tiết hằng ngày.

**AI hypothesis:**
Xây công cụ tìm kiếm quy định theo ngữ nghĩa (không chỉ theo từ khóa chính xác), trả lời kèm trích dẫn điều khoản và nguồn văn bản, đồng thời cảnh báo nếu văn bản đã bị thay thế/hết hiệu lực. Cán bộ vẫn là người xác nhận cuối cùng trước khi áp dụng.

**Quick gut:**
Workflow (độ chính xác phải rất cao nên cần trích dẫn nguồn rõ ràng và cán bộ tự xác nhận, chưa nên để AI tự quyết định áp dụng).

---

### Draft current workflow

```text
CURRENT STATE — 15-20 phút/lần

[1 Phát sinh câu hỏi quy định: instant]
→ [2 Tìm trong hệ thống lưu trữ văn bản: 5-8'] ← bottleneck
→ [3 Đọc lướt nhiều văn bản để tìm điều khoản: 5-8'] ← bottleneck
→ [4 Đối chiếu hiệu lực văn bản: 3-5'] ← rủi ro áp dụng sai
→ [5 Hỏi đồng nghiệp/quản lý nếu chưa chắc: 5-10'] (không phải lúc nào cũng cần)
→ [6 Áp dụng vào công việc: instant]

Risk: Áp dụng nhầm văn bản cũ đã hết hiệu lực.
```

### Draft future workflow

```text
FUTURE STATE — dưới 5 phút/lần

[1 Cán bộ hỏi công cụ AI bằng câu hỏi tự nhiên: 0.5']
→ [2 AI tìm kiếm theo ngữ nghĩa trong kho văn bản: instant]
→ [3 AI trả lời kèm trích dẫn điều khoản + nguồn + tình trạng hiệu lực: instant]
→ [4 Cán bộ đối chiếu nhanh trích dẫn, xác nhận trước khi áp dụng: 2-3'] ← human boundary
→ [5 Áp dụng vào công việc: instant]

Total: dưới 5 phút/lần, kể cả bước xác nhận của cán bộ.

Fallback: Nếu AI không chắc hoặc không tìm thấy văn bản phù hợp → báo rõ "chưa xác định được", cán bộ tra cứu thủ công hoặc hỏi quản lý như quy trình cũ, không tự suy diễn quy định.
```