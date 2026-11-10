# Báo cáo cá nhân — Ngày 2 Object Detection

Đổi tên file theo `MSSV_HoTen.md`, ví dụ `20241234_NguyenVanAn.md`. Điền kết quả thật, xóa dòng hướng dẫn khi nộp. Xem [quy định nộp](../../SUBMISSION.md).

## 1. Thông tin học viên

- Họ tên: Nguyễn Thị Ngọc Mai
- MSSV: 2A202603188
- Email: 26ai.maintn2@vinuni.edu.vn
- Lớp: L2A
- Link repo bài làm: https://github.com/maimmmrrr77/K5-L2-Day02-NguyenThiNgocMai-2A202603188-ObjectDetection
- Link Colab đã chạy: https://colab.research.google.com/drive/1Fu0vbPfJo_WdO5N5vXYf3xDbzStUNnVO#scrollTo=CpcicVc4RzdV

## 2. Schema và mini guideline

Dẫn tới [GUIDELINE_MINI.md](../../GUIDELINE_MINI.md). Tóm tắt ba ca mơ hồ đã quyết định, cách áp dụng schema và phần cần giảng viên làm rõ.

## 3. Annotation và self-QC

- Số file nhãn train: 50
- Kết quả checker và lỗi đã xử lý:
- Danh sách ít nhất 10 ảnh đã rà bằng mắt:
- Lỗi bỏ sót/box/class phát hiện khi rà và cách sửa:
- Commit khóa nhãn ban đầu:

## 4. Gold QC và rework

Không có rewwork

| Chỉ số | Trước sửa | Sau sửa nếu có |
|---|---:|---:|
| TP |369| |
| FP |338| |
| FN |284| |
| Precision |0.5219| |
| Recall |0.5651| |
| F1 |0.5426| |
| mean_iou_of_matches |0.827| |
| passed |fasle| |

Dẫn tới `outputs/annotation_evaluation.json` trong repo. Nếu rework, ghi ảnh, lỗi đã kiểm, quyết định sửa/giữ và lý do. Không suy nguyên nhân chỉ từ FP/FN. Không có rework thì ghi rõ.

## 5. Kết quả YOLO

- Runtime, GPU/CPU, phiên bản Ultralytics và Torch: Ultralytics: 8.4.208, Torch 2.14.1, CPU (Intel Xeon CPU @ 2.20GHz)
- Các tham số thay đổi so với notebook nếu có và lý do:
- Đường dẫn best checkpoint trong phiên chạy: /content/Day2-Lab/outputs/yolo26_runs/vehicle_annotation/weights/best.pt

| Chỉ số trên 10 ảnh eval | Giá trị |
|---|---:|
| Precision |0.4105453698519763 |
| Recall |0.23026854853628678|
| mAP50 |0.27225886498171903|
| mAP50–95 |0.20168300309748077|

Đặt cả 2 folder `assets/eval_predictions/` và `assets/yolo26_runs/` (giải nén từ `day2_colab_outputs.zip`) cạnh báo cáo và dẫn link tương đối. Không chỉ ghi số; chỉ ra ít nhất một ảnh và vật thể cụ thể.

Trả lời bốn câu hỏi cuối notebook:

1. Lớp nào recall thấp nhất? Ảnh nào minh họa? lớp bus có recall thấp nhất
2. Nếu mAP50 cao nhưng mAP50–95 thấp, cần kiểm điều gì trên box? độ chính xác viền khung, kích thước đối tượng, mức độ chồng lấp
3. Lỗi class nào có thể liên quan guideline? Dữ kiện nào hỗ trợ nhận xét? 
4. Vì sao không dùng 10 ảnh eval để train? Vai trò validation của chúng trong notebook là gì? không dùng eval để train vì tránh học vẹt. vai trò: đánh giá khách quan, trực quan hóa lỗi dự đoán, theo dõi và chọn checkpoint.

## 6. Khó khăn và cách xử lý

| Bước/thời điểm | Lỗi quan sát | Cách đã thử | Kết quả/còn thiếu |
|---|---|---|---|
|| | | |

## 7. Tự đánh giá theo rubric

Đối chiếu [RUBRIC.md](../../RUBRIC.md): phần nào đã có kết quả, phần nào còn thiếu hoặc chưa kiểm được. Đã làm được:
- Không tự nhận hoàn thành bước chưa chạy.
- Hoàn thành và định dạng YOLO
- bám sát và hình học box 
- Mini guideline và quyết định mơ hồ
- Pipeline YOLO và phân tích
Chưa làm được:
- Gold-set annotation QC: F1 >= 0.80  và mean IoU >= 0.70
- Đầy đủ vật thể: gán đủ xe thuộc schema, kể cả xe che/cắt khung có thể nhận diện

## 8. Công cụ AI và tài liệu tham khảo

Ghi công cụ đã dùng, dùng ở bước nào và phần đã tự kiểm tra; không dùng thì ghi rõ. Liệt kê nguồn ngoài repo được sử dụng. Không ghi mật khẩu/token hoặc đính kèm gold train.
không dùng