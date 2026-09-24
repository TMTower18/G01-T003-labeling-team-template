# Problem backlog

Những chỗ gặp trong lúc gán nhãn mà **guideline chưa trả lời được**, cộng các pain point về công cụ.

Ghi ngay khi gặp, kể cả lúc chưa biết xử lý thế nào. Một edge case không được ghi lại thì
mỗi người sẽ tự xử lý theo một kiểu — và đó là nguồn lớn nhất của nhãn không nhất quán.

## Danh sách

| Mã | Tóm tắt | Loại | Mục guideline | Trạng thái | Kết quả |
|---|---|---|---|---|---|
| [P-001](#p-001) | Dây điện xuất hiện trên vùng bầu trời | Guideline mơ hồ | §1 — Rule 03; §2 | 🟢 Đã chốt | → [QĐ-001](decision-log.md#qđ-001) |
| [P-002](#p-002) | Xe ở quá xa, không thể xác định rõ class | Guideline chưa nói rõ ngưỡng | §3 — OBJECT NHỎ/XA; §4; §6; §9 | 🟢 Đã chốt | → [QĐ-002](decision-log.md#qđ-002) |
| [P-003](#p-003) | Vạch trắng đôi đi kèm với vạch xương cá | Guideline chưa nói tới | §2; §4.2 | 🟢 Đã chốt | → [QĐ-003](decision-log.md#qđ-003) |
| [P-004](#p-004) | Biển chỉ dẫn lối ra có được gán traffic sign không | Guideline mơ hồ | §2 — Taxonomy | 🟢 Đã chốt | → [QĐ-004](decision-log.md#qđ-004) |
| [P-005](#p-005) | Mép dải đảo phân cách có được xem là road curb không | Guideline chưa nói tới | §2 — Lane Marking; §4.2 | 🟢 Đã chốt | → [QĐ-005](decision-log.md#qđ-005) |
| [P-006](#p-006) | Chưa rõ định nghĩa area/drivable và area/alternative | Guideline mơ hồ | §2; §4.1 | 🟢 Đã chốt | → [QĐ-008](decision-log.md#qđ-008) |
| [P-007](#p-007) | Object bị che khuất nhiều, không rõ có được suy đoán phần bị che | Guideline mơ hồ khi áp dụng thực tế | §3 — OCCLUSION; §6; §9 | 🟢 Đã chốt | → [QĐ-007](decision-log.md#qđ-007) |
| [P-008](#p-008) | Edge case tại BBOX Job #1338 — frame 7 | Guideline chưa nói tới | Chưa xác định | 🔴 Mở | ↗️ Hỏi BTC/Mentor |
| [P-009](#p-009) | Edge case tại Segmentation Job #1559 — frame 96 | Guideline chưa nói tới | Chưa xác định | 🔴 Mở | ↗️ Hỏi BTC/Mentor |

---

## P-001

**Dây điện xuất hiện trên vùng bầu trời**

- **Loại:** Guideline mơ hồ

- **Mục guideline:** §1 — Rule 03; §2

- **Người phát hiện:** [@TMTower18](https://github.com/TMTower18) · 16/09/2026

- **Link CVAT:** https://cvat.note.transformerlabs.ai/tasks/176/jobs/1554?frame=12

- **Mô tả:** Trong một số frame, dây điện chạy qua khu vực bầu trời. Dây điện không
  thuộc danh sách 19 class được quy định trong guideline, nhưng guideline chưa nói rõ
  cách xử lý pixel của dây điện khi nó nằm trên vùng `sky`.

- **Các cách hiểu:**

  1. Không tạo class riêng cho dây điện; phần nền xung quanh dây điện vẫn được gán
     theo semantic class tương ứng.

  2. Không ép pixel dây điện vào một trong 19 class và đưa case vào review.

- **Xử lý tạm trong lúc chờ:** Không tạo class mới và không tự gán dây điện vào
  một class khác.

- **Kết quả:** 🟢 Đã chốt → [QĐ-001](decision-log.md#qđ-001)


## P-002

**Xe ở quá xa, không thể xác định rõ class**

- **Loại:** Guideline chưa nói rõ ngưỡng

- **Mục guideline:** §3 — OBJECT NHỎ/XA; §4 — car vs truck vs bus; §6; §9

- **Người phát hiện:** [@TMTower18](https://github.com/TMTower18) · 17/09/2026

- **Link CVAT:** https://cvat.note.transformerlabs.ai/tasks/176/jobs/1554?frame=15

- **Mô tả:** Một số xe xuất hiện ở khoảng cách rất xa, kích thước rất nhỏ hoặc
  hình ảnh bị mờ khiến không thể xác định chắc chắn class của phương tiện.

- **Các cách hiểu:**

  1. Nếu vẫn nhận dạng được class thì annotate.

  2. Nếu quá nhỏ/mờ để xác định chắc chắn thì đưa review thay vì đoán.

- **Xử lý tạm trong lúc chờ:** Zoom để kiểm tra. Nếu vẫn không thể xác định
  chắc chắn class, tạo Issue/đưa reviewer theo quy trình escalation.

- **Kết quả:** 🟢 Đã chốt → [QĐ-002](decision-log.md#qđ-002)


## P-003

**Vạch trắng đôi đi kèm với vạch xương cá**

- **Loại:** Guideline chưa nói tới

- **Mục guideline:** §2; §4.2 — Polyline / Lane Marking

- **Người phát hiện:** [@minhducht239](https://github.com/minhducht239) · 17/09/2026

- **Link CVAT:** https://cvat.note.transformerlabs.ai/tasks/122/jobs/1340?frame=66&type=shape&serverID=57383

- **Mô tả:** Xuất hiện trường hợp vạch trắng đôi đi kèm với vạch xương cá.
  Guideline chưa nêu rõ cách xử lý khi hai dạng vạch xuất hiện liền nhau
  hoặc có phần giao nhau.

- **Các cách hiểu:**

  1. Annotate phần vạch trắng đôi bằng class hiện có; xử lý riêng phần xương cá.

  2. Xem cả hai là một cấu trúc liên kết và cần một rule riêng.

- **Xử lý tạm trong lúc chờ:** Annotate phần vạch trắng đôi theo quy định hiện có;
  không tự tạo class mới cho phần chưa có taxonomy phù hợp.

- **Kết quả:** 🟢 Đã chốt → [QĐ-003](decision-log.md#qđ-003)


## P-004

**Biển chỉ dẫn lối ra có được gán traffic sign không**

- **Loại:** Guideline mơ hồ

- **Mục guideline:** §2 — Taxonomy

- **Người phát hiện:** [@minhducht239](https://github.com/minhducht239) · 17/09/2026

- **Link CVAT:** https://cvat.note.transformerlabs.ai/tasks/122/jobs/1340?frame=68&type=shape&serverID=59452

- **Mô tả:** Xuất hiện một biển chỉ dẫn lối ra và chưa rõ có thuộc class
  `traffic_sign` hay không.

- **Các cách hiểu:**

  1. Annotate vào `traffic_sign` vì đây là biển chỉ dẫn giao thông.

  2. Không annotate nếu class `traffic_sign` chỉ áp dụng cho một số loại biển nhất định.

- **Xử lý tạm trong lúc chờ:** Annotate vào `traffic_sign` nếu xác định rõ đây là
  biển giao thông thực tế trong scene.

- **Kết quả:** 🟢 Đã chốt → [QĐ-004](decision-log.md#qđ-004)


## P-005

**Mép dải đảo phân cách có được xem là road curb không**

- **Loại:** Guideline chưa nói tới

- **Mục guideline:** §2 — Lane Marking; §4.2

- **Người phát hiện:** [@minhducht239](https://github.com/minhducht239) · 17/09/2026

- **Link CVAT:** https://cvat.note.transformerlabs.ai/tasks/122/jobs/1340?frame=68&type=shape&serverID=59636

- **Mô tả:** Khi annotate khu vực dải/đảo phân cách, chưa rõ phần mép có được
  xem là `lane/road curb` hay không.

- **Các cách hiểu:**

  1. Xem mép đảo phân cách là `lane/road curb` nếu quan sát rõ cấu trúc curb.

  2. Không gán `lane/road curb` nếu chỉ thấy boundary nhưng không đủ bằng chứng
     đó là curb vật lý.

- **Xử lý tạm trong lúc chờ:** Không suy đoán. Chỉ annotate khi có đủ bằng chứng
  hình ảnh.

- **Kết quả:** 🟢 Đã chốt → [QĐ-005](decision-log.md#qđ-005)


## P-006

**Chưa rõ định nghĩa area/drivable và area/alternative**

- **Loại:** Guideline mơ hồ

- **Mục guideline:** §2; §4.1 — Polygon / Drivable Area

- **Người phát hiện:** [@hoanghoang203205](https://github.com/hoanghoang203205) · 17/09/2026

- **Link CVAT:** https://cvat.note.transformerlabs.ai/tasks/122/jobs/1338?frame=20

- **Mô tả:** Chưa rõ ranh giới và định nghĩa chính xác của `area/drivable`
  và `area/alternative` khi vẽ polygon, đặc biệt ở đường giao nhau, làn phụ
  hoặc vùng có thể di chuyển nhưng không phải phần đường chính.

- **Các cách hiểu:**

  1. `area/drivable` là toàn bộ vùng phương tiện có thể di chuyển.

  2. `area/drivable` chỉ gồm phần đường chính; vùng phụ được xem xét theo
     `area/alternative`.

- **Xử lý tạm trong lúc chờ:** Bám theo boundary nhìn thấy; không tự đặt thêm
  định nghĩa ngoài rule đã được mentor/batch thống nhất.

- **Kết quả:** - **Kết quả:** 🟢 Đã chốt → [QĐ-008](decision-log.md#qđ-008)


## P-007

**Object bị che khuất nhiều, không rõ có được suy đoán phần bị che**

- **Loại:** Guideline mơ hồ khi áp dụng thực tế

- **Mục guideline:** §3 — OCCLUSION; §6; §9

- **Người phát hiện:** [@BachNguyen-hub](https://github.com/BachNguyen-hub) · 17/09/2026

- **Link CVAT:** https://cvat.note.transformerlabs.ai/tasks/122/jobs/1339?frame=31

- **Mô tả:** Một số object bị vật thể khác che khuất phần lớn diện tích,
  khiến ranh giới hoàn chỉnh của object không thể quan sát được.

- **Các cách hiểu:**

  1. Chỉ annotate phần pixel của object đang thực sự nhìn thấy.

  2. Suy đoán phần bị che dựa trên hình dạng của object.

- **Xử lý tạm trong lúc chờ:** Chỉ annotate phần nhìn thấy, không suy đoán
  phần bị che khuất.

- **Kết quả:** 🟢 Đã chốt → [QĐ-007](decision-log.md#qđ-007)

## P-008

**Đường đi vào cây xăng có được gán `area/drivable` không**

- **Loại:** Guideline chưa nói tới

- **Mục guideline:** §2; §4.1 — Polygon / Drivable Area

- **Người phát hiện:** [@hoanghoang203205](https://github.com/hoanghoang203205) · 20/09/2026

- **Link CVAT:** https://cvat.note.transformerlabs.ai/tasks/122/jobs/1338?frame=7

- **Task liên quan:** BBOX / Polygon — Task 122 · Job 1338 · Frame 7

- **Mô tả:** Trong frame xuất hiện một phần đường dẫn từ đường chính đi vào cây xăng. Phương tiện vẫn có thể di chuyển bình thường trên phần đường này để vào hoặc ra khỏi cây xăng, tuy nhiên đây không phải là làn lưu thông chính của tuyến đường. Chưa rõ khu vực này có nằm trong phạm vi cần annotate bằng `area/drivable` hay không.

- **Các cách hiểu:**

  1. Gán `area/drivable` vì đây là phần mặt đường mà phương tiện được phép và thực tế có thể di chuyển bình thường.

  2. Không gán `area/drivable` vì đây là đường dẫn vào khu vực dịch vụ/cây xăng, không thuộc phần đường lưu thông chính của tuyến.

- **Xử lý tạm trong lúc chờ:** Không tự suy đoán hoặc tự mở rộng phạm vi `area/drivable`. Giữ case ở trạng thái mở và đưa BTC/Mentor xác nhận đường ra/vào cây xăng có thuộc scope `area/drivable` hay không.

- **Kết quả:** 🔴 Mở — ↗️ Hỏi BTC/Mentor


## P-009

**`fence` nằm phía trên `wall` thì phân chia class như thế nào**

- **Loại:** Guideline mơ hồ khi áp dụng thực tế

- **Mục guideline:** §3 — KHÔNG CHỒNG LẤN; §4 — wall vs fence

- **Người phát hiện:** [@qungmnh-udev](https://github.com/qungmnh-udev) · 20/09/2026

- **Link CVAT:** https://cvat.note.transformerlabs.ai/tasks/176/jobs/1559?frame=96

- **Task liên quan:** Segmentation — Task 176 · Job 1559 · Frame 96

- **Mô tả:** Trong frame xuất hiện một hàng `fence` được đặt trực tiếp phía trên một phần `wall`. Hai cấu trúc nằm liền nhau và cùng tạo thành một ranh giới, nên chưa rõ cần tách riêng pixel của phần hàng rào phía trên thành `fence` và phần tường phía dưới thành `wall`, hay coi toàn bộ cấu trúc là một class duy nhất.

- **Các cách hiểu:**

  1. Tách riêng hai class: phần tường đặc phía dưới gán `wall`, còn phần thanh/lưới hàng rào nhìn thấy phía trên gán `fence`.

  2. Gán toàn bộ cấu trúc theo một class duy nhất nếu `fence` được xem là phần kéo dài hoặc phần bổ sung của `wall`.

- **Xử lý tạm trong lúc chờ:** Không để `fence` và `wall` chồng mask lên cùng một pixel. Giữ case ở trạng thái mở và đưa BTC/Mentor xác nhận cách phân chia class chính thức.

- **Kết quả:** 🔴 Mở — ↗️ Hỏi BTC/Mentor

## Mẫu để copy

```markdown
## P-NNN

**Tóm tắt một dòng**

- **Loại:** Guideline chưa nói tới | Guideline mơ hồ | Guideline mâu thuẫn | Pain point công cụ

- **Mục guideline:** §

- **Người phát hiện:** @ · dd/mm/yyyy

- **Link CVAT:** (bỏ trống nếu không có)

- **Mô tả:**

- **Các cách hiểu:**

  1.

  2.

- **Xử lý tạm trong lúc chờ:**

- **Kết quả:** 🔴 Mở