# HỆ THỐNG TIÊU CHÍ GIAO DỊCH SCALPING FOREX (M1 – M3 – M5 – M15)
### Tổng hợp & phân tích từ chuỗi bài "Tinh Túy RSI & MACD" và "Xây dựng hệ thống giao dịch"

> Tài liệu này **tổng hợp lại** các nguyên tắc cốt lõi từ 4 nguồn transcript được cung cấp, chuyển hóa thành một **bộ tiêu chí giao dịch cụ thể, có thể áp dụng ngay** cho phong cách scalping Forex đa khung thời gian M1/M3/M5/M15. Đây **không phải là chén thánh** — đây là khung sườn để bạn tự backtest, điều chỉnh và biến thành hệ thống của riêng mình (đúng tinh thần "phải tự xây dựng, tự trải nghiệm ít nhất ~100 lệnh" mà nguồn gốc nhấn mạnh).

---

## 1. NGUYÊN TẮC NỀN TẢNG (rút ra từ 4 tài liệu gốc)

| # | Nguyên tắc | Nguồn ý tưởng |
|---|---|---|
| 1 | **Không ai vào lệnh thay bạn được** — quyết định vào lệnh phải dựa trên bộ tiêu chí của chính bạn, không dựa vào cảm tính hay hỏi người khác từng lệnh một | Xây dựng hệ thống tiêu chí giao dịch |
| 2 | Chỉ báo (RSI, MACD...) luôn **đi sau giá** — chúng phản ánh quá khứ, không phải công cụ tiên tri | Bài 1 |
| 3 | Không có công cụ nào "mạnh nhất" — công cụ tốt là công cụ **bạn luyện tới mức thuần thục** (tinh thần "luyện 10.000 lần một cú đá") | Bài 1 |
| 4 | Phân tích kỹ thuật chỉ chiếm ~20–30% thành công; **tư duy, kỷ luật, quản trị vốn** chiếm 70–80% | Bài 1 |
| 5 | **Càng nhiều tiêu chí → xác suất thắng càng cao, nhưng cơ hội vào lệnh càng ít.** Không có bộ tiêu chí nào loại bỏ hoàn toàn xác suất thua | Xây dựng hệ thống tiêu chí giao dịch |
| 6 | Phải backtest/forward-test tối thiểu **~100 lệnh có ghi chép** mới đúc kết được tiêu chí thật sự phù hợp với bản thân | Xây dựng hệ thống tiêu chí giao dịch |
| 7 | **Phân kỳ (Divergence)** = giá tạo đỉnh sau cao hơn đỉnh trước nhưng chỉ báo (RSI/MACD) tạo đỉnh sau **thấp hơn** → lực mua suy yếu → cảnh báo đảo chiều giảm | Bài 1, 2, 3 |
| 8 | **Hội tụ (Convergence)** = giá tạo đáy sau thấp hơn đáy trước nhưng chỉ báo tạo đáy sau **cao hơn** → lực bán suy yếu → cảnh báo đảo chiều tăng | Bài 1, 2, 3 |
| 9 | **Không bắt đáy / không đu đỉnh mù quáng.** Chờ nến xác nhận sau khi có tín hiệu hội tụ/phân kỳ rồi mới vào lệnh, thay vì đoán đỉnh/đáy chính xác | Bài 1 |
| 10 | Phải xem **đa khung thời gian (multi-timeframe)** — tín hiệu ở khung nhỏ chỉ đáng tin khi có sự đồng thuận từ khung lớn hơn | Bài 1, 2, 3 |
| 11 | Quản lý lệnh linh hoạt: chốt một phần, dời SL về hòa vốn/giữ lời khi thấy dấu hiệu suy yếu, không tham lam giữ 100% vị thế đến cùng | Bài 3 |
| 12 | Luôn có **Stop Loss (SL)** rõ ràng cho mọi lệnh — không có ngoại lệ | Bài 3, Xây dựng hệ thống |

---

## 2. VÌ SAO PHẢI CÓ "ĐIỀU KIỆN ĐỦ" THAY VÌ "ĐIỀU KIỆN HOÀN HẢO"

Đúng như tài liệu gốc cảnh báo: nếu bạn yêu cầu **tất cả** tiêu chí (đồng thuận 4 khung + phân kỳ/hội tụ rõ + MACD cắt + volume + tin tức...) phải khớp **cùng lúc**, có thể **cả ngày không có nổi 1 lệnh** — đặc biệt với scalping M1/M3 vốn cần tần suất giao dịch nhất định.

**Giải pháp:** Tách tiêu chí thành 2 nhóm:

- **NHÓM BẮT BUỘC (điều kiện đủ / cần có tối thiểu)** — thiếu 1 trong nhóm này thì **không vào lệnh**, không có ngoại lệ.
- **NHÓM CỘNG ĐIỂM (điều kiện lý tưởng)** — không bắt buộc, nhưng có càng nhiều thì xác suất thắng càng cao và bạn có thể vào khối lượng (lot) lớn hơn một chút.

Cách chia này giải quyết đúng nghịch lý mà nguồn "Xây dựng hệ thống tiêu chí giao dịch" nêu ra: *"khắt khe quá thì cơ hội khó đến — nới lỏng tiêu chí thì cơ hội nhiều hơn nhưng tỷ lệ thắng giảm"*. Bạn chọn mức độ khắt khe phù hợp với khẩu vị rủi ro của mình sau khi đã backtest.

---

## 3. CẤU TRÚC ĐA KHUNG THỜI GIAN (TOP-DOWN: M15 → M5 → M3 → M1)

Nguyên tắc cốt lõi từ Bài 1–3: **xem khung lớn để định hướng, xem khung nhỏ để tìm điểm vào chính xác.**

| Khung | Vai trò | Câu hỏi cần trả lời |
|---|---|---|
| **M15** | Xác định xu hướng chính / bối cảnh thị trường | Đang trend tăng, trend giảm, hay sideway tích lũy? RSI M15 đang ở vùng nào (>70, <30, hay trung tính 40–60)? |
| **M5** | Xác nhận cấu trúc & sự đồng thuận với M15 | Cấu trúc đỉnh/đáy trên M5 có cùng hướng với M15 không? Có tín hiệu hội tụ/phân kỳ manh nha chưa? |
| **M3** | Tìm vùng giá cụ thể để chờ vào lệnh (entry zone) | Giá đã hồi về vùng hỗ trợ/kháng cự hợp lý chưa? Hội tụ/phân kỳ RSI-MACD đã rõ trên M3 chưa? |
| **M1** | Xác định điểm kích hoạt (trigger) chính xác | Có nến xác nhận (nến tăng/giảm rõ ràng, đóng cửa vượt qua vùng entry) chưa? |

![Đa khung thời gian](../images/04-da-khung-thoi-gian.svg)

**Quy tắc đồng thuận:** Chỉ vào lệnh khi **M15 và M5 cùng hướng** (đây là điều kiện bắt buộc). M3/M1 dùng để tinh chỉnh điểm vào — nếu M3/M1 chưa xác nhận, bạn **chờ**, không đuổi giá.

---

## 4. TÍNH CHẤT CỐT LÕI CỦA RSI VÀ MACD (rút ra từ Bài 1, 2, 3)

### 4.1. RSI — Phân kỳ (Divergence) & Hội tụ (Convergence)

**Phân kỳ giảm (Bearish Divergence):** Giá tạo đỉnh sau **cao hơn** đỉnh trước, nhưng RSI tạo đỉnh sau **thấp hơn** đỉnh trước → lực mua đang suy yếu dù giá vẫn tăng → cảnh báo khả năng đảo chiều giảm.

![Phân kỳ giảm RSI](../images/01-phan-ky-giam-rsi.svg)

**Hội tụ tăng (Bullish Convergence):** Giá tạo đáy sau **thấp hơn** đáy trước, nhưng RSI tạo đáy sau **cao hơn** đáy trước → lực bán đang suy yếu dù giá vẫn giảm → cảnh báo khả năng đảo chiều tăng.

![Hội tụ tăng RSI](../images/02-hoi-tu-tang-rsi.svg)

**Lưu ý quan trọng (theo đúng tinh thần Bài 1):**
- **Không mua chỉ vì RSI < 30, không bán chỉ vì RSI > 70.** Trong xu hướng mạnh, RSI có thể duy trì vùng quá mua/quá bán rất lâu.
- RSI > 70–80 = lực mua đang áp đảo, đây là **vùng "chờ mua khi hồi"**, không phải vùng để tìm lệnh bán ngay.
- RSI < 20–30 = lực bán đang áp đảo, đây là **vùng "chờ bán khi hồi"**, không phải vùng để bắt đáy ngay.
- Khi thấy hội tụ/phân kỳ, **đừng vào lệnh ngay tại đáy/đỉnh** — chờ một nến xác nhận (giá đã ngừng tạo đáy mới / đỉnh mới) rồi mới vào, để tránh bị "quét râu nến".

### 4.2. MACD — Cắt đường tín hiệu & Phân kỳ Histogram

- MACD cắt lên trên đường Signal (từ dưới lên) = tín hiệu mua; cắt xuống dưới = tín hiệu bán. **Nhưng dùng một mình tín hiệu cắt này rất dễ vào lệnh trễ / bị nhiễu** — cần kết hợp với histogram và RSI.
- **Phân kỳ Histogram**: giá tạo đỉnh mới cao hơn nhưng đỉnh cột histogram **thấp hơn** đỉnh trước → lực tăng không bền vững.

![Phân kỳ MACD Histogram](../images/03-macd-histogram-phan-ky.svg)

- Khi histogram chuyển từ vùng dương sang vùng âm (hoặc ngược lại) trong lúc có phân kỳ/hội tụ RSI đồng thời → tín hiệu được củng cố mạnh hơn nhiều so với chỉ dùng 1 chỉ báo.

---

## 5. BỘ TIÊU CHÍ VÀO LỆNH SCALPING (M1/M3/M5/M15)

### 5.1. NHÓM BẮT BUỘC (thiếu 1 → KHÔNG vào lệnh)

**Cho lệnh BUY:**
1. ☐ M15 không trong xu hướng giảm mạnh (đang tăng hoặc sideway tích lũy)
2. ☐ M5 xác nhận cấu trúc đáy sau cao hơn đáy trước (Higher Low) HOẶC có tín hiệu hội tụ RSI rõ ràng
3. ☐ M3: RSI đã ra khỏi vùng quá bán (<30) và đang hướng lên, hoặc có hội tụ RSI/MACD rõ
4. ☐ M1 có nến xác nhận tăng (đóng cửa > mở cửa, thân nến rõ ràng, không phải doji)
5. ☐ Đã xác định được điểm đặt Stop Loss cụ thể (dưới đáy gần nhất) và tỷ lệ R:R tối thiểu 1:1.5

**Cho lệnh SELL:** đảo ngược tương ứng (M15 không tăng mạnh; M5 đỉnh sau thấp hơn đỉnh trước hoặc phân kỳ RSI; M3 RSI ra khỏi vùng quá mua và hướng xuống; M1 nến xác nhận giảm; có SL + R:R ≥ 1:1.5).

### 5.2. NHÓM CỘNG ĐIỂM (không bắt buộc, càng nhiều càng tốt)

- ☐ MACD Histogram trên M3/M1 cùng chiều xác nhận (dương & tăng dần cho BUY / âm & giảm dần cho SELL)
- ☐ Giá đang ở vùng hỗ trợ/kháng cự trước đó, hoặc vùng Fibonacci 0.5–0.618
- ☐ Không có tin tức kinh tế lớn (High Impact News) trong vòng 15–30 phút tới trên cặp tiền đang giao dịch
- ☐ Đang trong phiên giao dịch thanh khoản cao (London/New York overlap) — spread thấp, ít nhiễu giá
- ☐ Volume/độ biến động nến M1 gần đây không bất thường (không phải đang bị "quét" bởi tin tức)
- ☐ Đỉnh/đáy tạo phân kỳ hoặc hội tụ nằm gần vùng đảo chiều lịch sử (đã từng phản ứng trước đó)

**Cách dùng để tránh "cả ngày không có lệnh nào":**
- Nếu đủ **5/5 tiêu chí bắt buộc + từ 0–2 tiêu chí cộng điểm** → vào lệnh với khối lượng (lot) **tiêu chuẩn/thấp**.
- Nếu đủ **5/5 bắt buộc + từ 3 tiêu chí cộng điểm trở lên** → có thể cân nhắc vào khối lượng lớn hơn (theo % rủi ro đã định trước, xem mục 7).
- **Tuyệt đối không hạ tiêu chí ở NHÓM BẮT BUỘC** để có thêm lệnh — đây là ranh giới giữa có hệ thống và đánh bạc.

![Ví dụ setup vào lệnh đầy đủ](../images/05-vi-du-setup-vao-lenh.svg)

---

## 6. QUẢN LÝ LỆNH (Trade Management) — theo tinh thần Bài 3

Bài 3 nhấn mạnh: quản lý lệnh còn quan trọng hơn cả việc tìm điểm vào, vì **không ai biết chắc giá sẽ đi bao xa**.

1. **Chốt một phần khi có dấu hiệu suy yếu đầu tiên** (ví dụ RSI bắt đầu phân kỳ nhẹ dù chưa rõ ràng) — chốt 30–50% khối lượng, dời SL của phần còn lại về điểm hòa vốn.
2. **Không đặt target cố định quá xa dựa trên kỳ vọng chủ quan** ("nó sẽ lên tới X điểm") — quan sát từng vùng giá phản ứng, đi tới đâu đánh giá tới đó.
3. Khi phân kỳ/hội tụ xuất hiện **rõ ràng** trên khung đang giao dịch (M1/M3) → thoát toàn bộ vị thế, không cố "ăn thêm".
4. Nếu lệnh đi ngược hướng ngay khi vào và chạm SL → chấp nhận thua, **không dời SL ra xa hơn để "chờ giá quay lại"**.
5. Với scalping, thời gian giữ lệnh thường ngắn (vài phút đến vài chục phút) — nếu sau một khoảng thời gian hợp lý (ví dụ 15–20 phút trên M1/M3) mà giá vẫn đi ngang không theo đúng kịch bản, cân nhắc thoát sớm để tránh bị "gặm" bởi spread và biến động nhiễu.

---

## 7. QUẢN TRỊ VỐN & KỶ LUẬT (áp dụng riêng cho tài khoản Exness)

- **Rủi ro mỗi lệnh:** không quá 0.5–1% vốn tài khoản (scalping tần suất cao → rủi ro/lệnh phải thấp để tránh cháy tài khoản do chuỗi lệnh thua).
- **Giới hạn số lệnh thua liên tiếp:** nếu thua 3 lệnh liên tiếp trong phiên, dừng giao dịch trong ngày, xem lại tâm lý và bối cảnh thị trường.
- **Spread & giờ giao dịch trên Exness:** scalping M1/M3 rất nhạy với spread — ưu tiên giao dịch trong phiên Âu–Mỹ (khoảng 14h–23h giờ Việt Nam) khi spread các cặp chính (EURUSD, GBPUSD, XAUUSD...) thường thấp nhất; tránh giao dịch ngay trước/sau tin tức NFP, CPI, lãi suất FED.
- **Loại lệnh:** nên dùng lệnh Market kết hợp SL/TP đặt ngay khi khớp lệnh (Exness hỗ trợ đặt SL/TP cùng lúc mở lệnh) để tránh trượt giá khi thao tác tay trong lúc giá biến động nhanh.
- **Ghi nhật ký giao dịch bắt buộc** với mọi lệnh — dùng file tổng hợp lệnh đi kèm (xem mục 9) để sau ~100 lệnh, tự thống kê lại: bao nhiêu % tiêu chí nào cho tỷ lệ thắng cao nhất, từ đó **tinh chỉnh lại chính bộ tiêu chí này** cho phù hợp với phong cách cá nhân.

---

## 8. QUY TRÌNH RA QUYẾT ĐỊNH (Checklist thao tác nhanh)

```
BƯỚC 1 — Nhìn M15: Xu hướng chung là gì? (Tăng / Giảm / Sideway)
   └─ Nếu không rõ xu hướng & không phải sideway đẹp → ĐỨNG NGOÀI

BƯỚC 2 — Nhìn M5: Cấu trúc đáy/đỉnh có đồng thuận với M15 không?
   └─ Không đồng thuận → ĐỨNG NGOÀI

BƯỚC 3 — Nhìn M3: Có hội tụ/phân kỳ RSI-MACD rõ ràng tại vùng giá hợp lý không?
   └─ Chưa có → CHỜ, đặt cảnh báo giá (price alert), không đuổi theo

BƯỚC 4 — Nhìn M1: Đã có nến xác nhận chưa?
   └─ Chưa có nến xác nhận → CHỜ thêm 1-2 nến

BƯỚC 5 — Đủ 5/5 tiêu chí bắt buộc (mục 5.1)?
   └─ Thiếu 1 → KHÔNG VÀO LỆNH (không thương lượng)
   └─ Đủ → Xác định SL/TP, tính R:R, kiểm tra tin tức → VÀO LỆNH theo đúng % vốn quy định

BƯỚC 6 — Sau khi vào lệnh: theo dõi theo mục 6 (Quản lý lệnh)

BƯỚC 7 — Sau khi đóng lệnh: Ghi ngay vào Nhật ký giao dịch (mục 9)
```

---

## 9. FILE ĐI KÈM

- `templates/trade_journal_exness.xlsx` — File nhật ký/tổng hợp lệnh giao dịch dùng cho tài khoản Exness, có sẵn công thức tính Win Rate, R:R trung bình, tổng lãi/lỗ, và cột đối chiếu số tiêu chí đạt được trong bộ tiêu chí ở mục 5.
- `docs/02-checklist-nhanh.md` — Bản checklist rút gọn để in ra hoặc dán cạnh màn hình giao dịch.

---

## 10. GHI CHÚ QUAN TRỌNG / GIỚI HẠN

- Đây là bộ khung **tổng hợp lại từ các nguyên tắc chia sẻ trong 4 tài liệu nguồn**, không phải một hệ thống đã được backtest với dữ liệu Forex thực tế bởi người biên soạn. Bạn **bắt buộc phải tự backtest và forward-test** trên tài khoản demo trước khi dùng vốn thật, đúng như tinh thần "phải tự trải nghiệm ~100 lệnh" mà nguồn gốc nhấn mạnh.
- Không có bộ tiêu chí nào đảm bảo thắng 100% — mục tiêu là **tăng xác suất thắng và duy trì sự ổn định dài hạn**, không phải loại bỏ hoàn toàn rủi ro.
- Tài liệu này chỉ mang tính chất **giáo dục/tham khảo cá nhân**, không phải lời khuyên đầu tư/tài chính.
