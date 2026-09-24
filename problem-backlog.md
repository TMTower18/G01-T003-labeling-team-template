# Tuần 01 · 15/09 – 21/09/2026
# Problem backlog

Những chỗ gặp trong lúc gán nhãn mà **guideline chưa trả lời được**, cộng các pain point về công cụ.

Ghi ngay khi gặp, kể cả lúc chưa biết xử lý thế nào. Một edge case không được ghi lại thì
mỗi người sẽ tự xử lý theo một kiểu — và đó là nguồn lớn nhất của nhãn không nhất quán.

> Các mục bên dưới là **ví dụ**, tên và link CVAT đều giả. Mẫu trống để copy nằm cuối file.

## Danh sách

| Mã | Tóm tắt | Loại | Mục guideline | Trạng thái | Kết quả |
|---|---|---|---|---|---|
| [P-001](#p-001) | Người ngồi sau xe máy: box riêng hay gộp với người lái | Guideline mơ hồ | §3.2 | ✅ Đã chốt | [QĐ-001](so-quyet-dinh.md#qđ-001) |
| [P-002](#p-002) | Xe bị che khuất hơn một nửa | Guideline chưa nói tới | §3.4 | ↗️ Hỏi BTC | — |
| [P-003](#p-003) | Phải vẽ lại box y hệt qua nhiều frame liên tiếp | Pain point công cụ | — | 🗣️ Đang bàn | — |

**Loại**

| Loại | Nghĩa là |
|---|---|
| Guideline chưa nói tới | Tình huống không có trong guideline |
| Guideline mơ hồ | Đọc guideline ra được hai cách hiểu trở lên |
| Guideline mâu thuẫn | Hai mục trong guideline nói ngược nhau |
| Pain point công cụ | Guideline rõ, nhưng làm trên CVAT chậm hoặc dễ sai |

**Trạng thái:** 🔴 Mở · 🗣️ Đang bàn · ↗️ Hỏi BTC · ✅ Đã chốt (trỏ sang QĐ) · 🛠️ Làm tool (trỏ sang `source-tool/`) · ⚪ Bỏ (ghi lý do)

---

## P-002

**Không xác định được đúng số lượng vật thể cần vẽ**

- **Loại:** Guideline mơ hồ
- **Mục guideline:** §3.1 — Đủ vật thể
- **Người phát hiện:** @BachNguyen-hub · 17/09/2026
- **Link CVAT:**
  - https://cvat.note.transformerlabs.ai/tasks/122/jobs/1339
- **Mô tả:** Không rõ có nên gán nhãn vật thể không.
- **Xử lý tạm trong lúc chờ:** Gán nhãn các vật thể mình biết chắc chắn cần.
- **Kết quả:** 🔴 Mở

## P-003

**Phải vẽ lại box y hệt qua nhiều frame liên tiếp**

- **Loại:** Pain point công cụ
- **Mục guideline:** —
- **Người phát hiện:** @thanh-vien-d · 18/09/2026
- **Link CVAT:** https://cvat.example.com/tasks/12/jobs/105?frame=200 — frame 200–260, xe đỗ không di chuyển
- **Mô tả:** Ảnh chụp liên tiếp từ camera cố định. Xe đỗ bên đường xuất hiện y nguyên ở hàng chục
  frame, annotator phải vẽ lại ở từng frame. Ước tính chiếm ~40% thời gian job 105.
- **Hướng đang cân nhắc:**
  1. Dùng chế độ *Track* sẵn có của CVAT — cần thử xem có hợp với dữ liệu dạng ảnh rời không.
  2. Viết script đọc file export của CVAT, nhân box sang các frame kế tiếp, rồi import lại.
- **Kết quả:** 🗣️ Đang bàn. Nếu chọn hướng 2 thì đổi trạng thái sang 🛠️ và làm trong
  [`source-tool/`](source-tool/).

---

## Mẫu để copy

```markdown
## P-NNN

**Tóm tắt một dòng**

- **Loại:** Guideline chưa nói tới | Guideline mơ hồ | Guideline mâu thuẫn | Pain point công cụ
- **Mục guideline:** §
- **Người phát hiện:** @ · dd/mm/yyyy
- **Link CVAT:** (bỏ trống nếu không có)
  - https://…/tasks/<id>/jobs/<id>?frame=<n> — frame này có gì
- **Mô tả:**
- **Các cách hiểu:** (với pain point công cụ thì ghi **Hướng đang cân nhắc:**)
  1.
  2.
- **Xử lý tạm trong lúc chờ:**
- **Kết quả:** 🔴 Mở
```

Nhớ thêm một dòng vào bảng **Danh sách** ở đầu file.


## P-001

- **Loại:** Guideline chưa nói tới.
- **Mục guideline:** 2
- **Người phát hiện:** HoangTra@minhducht239 16/9/2026
- **Link CVAT:**  https://cvat.note.transformerlabs.ai/tasks/122/jobs/1340?frame=66&type=shape&serverID=57383
- **Mô tả:** vạch trắng đôi đi kèm với vạch xương cá
- **Các cách hiểu:**
  1. Annotate vạch trắng đôi theo quy định về vạch đôi, đồng thời annotate phần vạch xương cá theo class tương ứng.
  2. Xem vạch trắng đôi và vạch xương cá là một cấu trúc liên kết và cần có quy tắc annotate riêng.
- **Xử lý tạm trong lúc chờ:** Annotate vạch trắng đôi theo quy định về vạch đôi
- **Kết quả:** 🔴 Mở

## P-002

- **Loại:** Guideline mơ hồ 
- **Mục guideline:** 2
- **Người phát hiện:** HoangT@minhducht239 16/9/2026
- **Link CVAT:** https://cvat.note.transformerlabs.ai/tasks/122/jobs/1340?frame=68&type=shape&serverID=59452
- **Mô tả:** Phân vân có phải traffic sign hay không
- **Các cách hiểu:**
  1.  Annotate vào traffic sign vì đây là một loại biển báo/chỉ dẫn giao thông.
  2.  Không annotate traffic sign vì guideline chỉ áp dụng cho nhóm biển hiệu lệnh trên đường, trong khi đối tượng này là biển chỉ dẫn lối ra.
- **Xử lý tạm trong lúc chờ:** Annotate vào traffic sign
- **Kết quả:** 🔴 Mở

## P-003

- **Loại:** Guideline chưa nói tới.
- **Mục guideline:** 2
- **Người phát hiện:** @minhducht239 16/9/2026
- **Link CVAT:** https://cvat.note.transformerlabs.ai/tasks/122/jobs/1340?frame=68&type=shape&serverID=59636
- **Mô tả:** phân vân mép dải đảo phân cách có tính là road curb hay không
- **Các cách hiểu:**
  1.  Annotate mép dải đảo phân cách vào class road curb vì đây là phần mép/nâng cao phân tách khu vực mặt đường.
- **Xử lý tạm trong lúc chờ:** Annotate theo road curb
- **Kết quả:** 🔴 Mở

## P-004

**Có những class mà có trong cvat mà không có trong guideline**

- **Loại:** Guideline mơ hồ
- **Mục guideline:** §2. Taxonomy và loại shape bắt buộc

- **Người phát hiện:** @Vũ Huy Hoàng · 15/09/2026

- **Mô tả:** Có những class mà có trong cvat mà không có trong guideline
  
- **Hướng đang cân nhắc:** 
    Anotate các class chỉ có trong guideline
  
- **Xử lý tạm trong lúc chờ:** Anotate các class chỉ có trong guideline
- **Kết quả:** 🔴 Mở

## P-005

**Chưa rõ định nghĩa area/drivable và area/alternative khi vẽ polygon drivable area**

- **Loại:** Guideline mơ hồ
- **Mục guideline:** §2 (Taxonomy), §4.1 (Polygon – Drivable Area)
- **Người phát hiện:** @Vũ Huy Hoàng · 17/09/2026
- **Link CVAT:** (không có — vấn đề áp dụng cho toàn batch)
- **Mô tả:** §4.1 yêu cầu phân biệt area/drivable và area/alternative "theo định nghĩa đã được giảng viên/mentor chốt cho batch", nhưng guideline không ghi định nghĩa cụ thể. Vì vậy mỗi người có thể hiểu và gán nhãn khác nhau, gây thiếu nhất quán khi review và evaluate. Ví dụ trên đường một chiều có làn xe ego, làn hẹp bên cạnh (có thể là làn xe đạp) và làn đỗ xe hai bên, không rõ vùng nào là drivable, vùng nào là alternative, vùng nào không annotate.
- **Các cách hiểu:**
  1. Theo BDD100K gốc: area/drivable là làn xe ego (xe gắn camera) đang chạy và có quyền ưu tiên; area/alternative là mặt đường vẫn chạy được nhưng phải chuyển làn hoặc nhường xe (làn bên cạnh, phần đường sát xe đỗ). Vỉa hè, lề đất, bãi cỏ không annotate.
  2. area/drivable là toàn bộ mặt đường xe chạy được; area/alternative là vùng mặt đất không phải đường đi (vỉa hè, lề đất…).
  3. area/drivable là toàn bộ các làn xe chạy; area/alternative chỉ dành cho làn đỗ xe, làn xe đạp, lề đường có thể lấn tạm.
- **Xử lý tạm trong lúc chờ:** Tiếp tục vẽ polygon theo biên mặt đường quan sát được. Chưa sửa lại nhãn drivable/alternative ở các ảnh đã làm để tránh sửa hai lần. Ghi chú lại các ảnh có nhiều làn, làn đỗ xe hoặc làn xe đạp để rà soát lại sau khi mentor chốt định nghĩa.
- **Kết quả:** 🔴 Mở
