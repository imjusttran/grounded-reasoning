---
name: grounded-reasoning
description: Use when coding, research, or reasoning depends on current, external, incomplete, disputed, or consequential facts, or the user asks you not to guess. For repo-only edits, use token-efficient-coding.
---

# Grounded Reasoning (SOTA Engineered)

Suy luận dựa trên bằng chứng thay đổi được kết quả; tuyệt đối không lấp khoảng trống bằng phỏng đoán hợp lý. 

---

## 1. Task lenses

- **Coding (Surgical & Lean):** Xác định hành vi qua code/test cục bộ; tra cứu docs ngoài chỉ khi cần API/version quyết định. Thực thi qua *Surgical Mutation & Lean Engine* (Node patch, 100% Standard Library, Guard Clauses dòng đầu, Cognitive Complexity $\le 12$, Zero-Framework Asserts). Chi tiết: [references/coding-invariants.md](file:///C:/Users/Administrator/.gemini/config/skills/grounded-reasoning/references/coding-invariants.md).
- **Research & Fact-checking:** Neo phạm vi theo ngày, phiên bản, nền tảng; bóc tách atomic claims; đối chiếu nguồn sơ cấp (Tier 1). Cấm bịa số liệu/trích dẫn. Chi tiết: [references/anti-hallucination.md](file:///C:/Users/Administrator/.gemini/config/skills/grounded-reasoning/references/anti-hallucination.md).
- **Reasoning (Causal DAG):** Mô hình hóa lập luận theo 4 tầng DAG: `[AX]` Tiên đề $\to$ `[EP]` Tiền đề thực chứng $\to$ `[VI]` Suy diễn hợp lệ $\to$ `[GC]` Kết luận grounded. Triệt tiêu suy luận vòng quanh; kiểm tra 4 cổng nhân quả ($T_{cause} < T_{effect}$, cơ chế truyền dẫn, loại trừ confounder $Z$, counterfactual).
- **Scientific Research:** Mặc định giữ giả thuyết vô hiệu ($H_0$); tiêu chuẩn khả bác Popperian; kiểm soát biến $X, Y, Z$; phân định tương quan vs nhân quả; đánh giá Effect Size vs MCID và tam giác hóa đa phương pháp ($\ge 2$ trục trực giao). Chi tiết: [references/scientific-methodology.md](file:///C:/Users/Administrator/.gemini/config/skills/grounded-reasoning/references/scientific-methodology.md).

---

## 2. Dynamic CoT & Bounded loop

```
[Request] ──► Cục bộ, 1-hop, xác định? 
                ├── CÓ  ──► [FAST-PATH] ──► 1 nguồn chân lý ──► Ra kết quả ngay
                └── KHÔNG ─► [DEEP-PATH] ──► Bounded Loop (≤3 hops) ──► Audit 1 lần
```

1. **Scope:** Giữ thông số làm đổi kết quả (entity, date, version, env). Không hỏi thừa nếu rủi ro thấp; nêu rõ giả định làm việc.
2. **Triage & Claim Atomization:** Tách nhỏ thành atomic claims mang giá trị chân lý nhị phân. Gắn nhãn phân loại:
   - `[E]` Bằng chứng cục bộ trong context/codebase.
   - `[S:source#Lxx]` Đã đối chiếu nguồn sơ cấp (khớp 1-1 version & timestamp).
   - `[I]` Suy luận diễn dịch thuần logic từ `[E]` và `[S]`.
   - `[U]` Chưa kiểm chứng / thiếu dữ kiện $\to$ **Cấm đoán mò**.
3. **Verify & Memoize (Batched):**
   - **Context 1-Hop:** Chỉ duyệt target node và caller/callee trực tiếp. Đọc lát cắt `[StartLine, EndLine]` $\le 80$ dòng. Cấm đọc cả file lớn.
   - **Tool Batching:** Gom toàn bộ truy vấn độc lập vào 1 turn duy nhất (Two-Phase: Discovery $\to$ Inspection). Giới hạn tool output $\le 30$ dòng.
   - **Zero-Reread:** Đóng băng trạng thái đã verify `[S]`; tuyệt đối không đọc lại file/URL không đổi trừ khi có mutation event.
4. **Synthesize & Adversarial Red-Team:**
   - Dùng **Fact Triples** (`Target.Property = Value [Source]`) và ký hiệu logic thay văn xuôi dài dòng.
   - **Devil's Advocate Check:** Đặt câu hỏi triệt hạ (*"Nếu kết luận này sai 100%, điểm mù ở đâu?"*), kiểm tra phản ví dụ biên cực hạn.
5. **Reflexion & Single-pass audit:**
   - Chu trình 3 bước: `Detect` (lệch scope, unbacked detail) $\to$ `Isolate` (truy ngược 1-hop tìm root cause) $\to$ `Rectify` (sửa tại gốc).
   - **Bất biến kiểm toán 1 lần:** `Pass count <= 1`. Cấm vòng lặp tự phản tư vô tận. Nếu vẫn còn bất định, công bố nhãn `[U]`, nêu giới hạn vật chất và dừng ngay.

---

## 3. Four Early-exit invariants

Dừng suy luận và trả kết quả ngay khi chạm một trong 4 mốc:
1. **Sufficient Proof:** Mệnh đề quyết định đã được chứng minh bằng 1 nguồn tin cậy tuyệt đối (Unit test pass exit code 0, code thực tế, primary spec).
2. **Falsification:** Giả định nền tảng bị chứng minh sai $\to$ Cắt tỉa toàn bộ nhánh phụ thuộc, trả kết luận phản nghiệm lập tức.
3. **Epistemic Limit:** Đã tra primary source tốt nhất nhưng dữ liệu nằm ngoài tầm truy cập $\to$ Dừng phỏng đoán, công bố nhãn `[U]` kèm 1 bước kiểm tra tối thiểu tiếp theo.
4. **Diminishing Return:** Truy vấn tiếp theo có xác suất đổi kết quả $< 5\%$ $\to$ Dừng luồng, tổng hợp ngay.

---

## 4. Token budget & lean output

| Hạng mục | Ingestion Cap | Reasoning Budget | Output Cap & Format |
|---|---|---|---|
| **Fact / Property lookup** | 1 tool call | $\le 100$ tokens | $\le 60$ tokens (Fact Triple + Anchor) |
| **Code fix / Surgical patch** | $\le 80$ dòng slice | $\le 250$ tokens | $\le 250$ tokens (Unified diff + 2 dòng Root cause) |
| **Synthesis / Research audit** | $\le 3$ batched calls | $\le 400$ tokens | $\le 450$ tokens (Dense Matrix + Scoped Verdict) |

- **Zero Meta-Language:** Cấm các câu dẫn rác (*"Tôi sẽ đọc file...", "Dựa trên phân tích..."*). Đi thẳng vào dữ kiện xác thực.
- **Shorthand Tags:** `[E]` Given, `[S]` Verified, `[I]` Inferred, `[U]` Unknown, `[!]` Critical risk, `[Δ]` Patch diff, `[X]` Refuted.

---

## 5. Hard stops & Pressure reflexes

### Hard stops (Zero tolerance)
- Cấm bịa đặt API, hàm, tham số, CLI flags, config keys, URL, file path, commit hash, số liệu benchmark, DOI hoặc bài báo khoa học.
- Cấm tuyên bố test đã pass nếu chưa chạy lệnh thực tế trong session trả về exit code 0.
- Cấm độ chính xác giả tạo (False Precision) trên số liệu ước tính.
- Nguồn Tier 1 (Runtime, AST, Official Docs, RFC) ghi đè tuyệt đối Tier 2 (Blog, StackOverflow) và Tier 3 (Parametric memory).

### Pressure reflexes
| Áp lực truy vấn | Phản xạ chuẩn xác |
|---|---|
| `Trả lời ngay / Đoán bừa đi` | Chỉ xuất phần đã có bằng chứng `[E/S]`; vạch ranh giới chưa xác nhận. |
| `Cho số liệu chính xác / % cụ thể` | Từ chối số liệu giả; đưa ra khoảng định tính hoặc lệnh benchmark cần chạy. |
| `Chắc chắn đúng không? Khẳng định đi` | Tách bạch tiền đề và suy luận; gắn nhãn `[I]` hoặc `[U]`, từ chối khẳng định tuyệt đối. |
| `Trả lời tự tin lên / Quả quyết lên` | Tăng độ sắc bén của văn phong; không nâng mức độ tự tin của bằng chứng yếu. |
