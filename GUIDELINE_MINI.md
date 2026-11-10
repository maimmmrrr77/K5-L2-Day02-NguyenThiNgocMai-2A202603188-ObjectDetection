# Mini guideline — bài làm cá nhân

> Điền nội dung này trước khi bắt đầu gán nhãn. Giữ lại các quyết định sau khi self-QC.

## Định nghĩa lớp

| Lớp | Định nghĩa của bạn | Ví dụ/điểm phân biệt |
| --- | --- | --- |
| `car` |Phương tiện ô tô con, thường có 4–5 chỗ ngồi.|Sedan, SUV, hatchback|
| `truck` |Phương tiện vận tải hàng hóa, thường có thùng hoặc khoang chở hàng lớn.|Xe tải nhỏ, xe tải lớn, xe ben.|
| `bus` |Phương tiện chở nhiều hành khách, có khoang hành khách lớn.|Xe buýt công cộng, xe khách, xe buýt trường học.|
| `van` |Xe có khoang thân kín, dùng để chở người hoặc hàng hóa, kích thước thường nhỏ hơn xe tải.|Xe van chở hàng, xe van chở khách.|

## Quy tắc chung

- Box bám sát vật thể nghĩa là: Vẽ Bounding Box bao quanh toàn bộ phần vật thể nhìn thấy, không lấy quá nhiều nền xung quanh
- Vật thể bị che khuất: Vẫn gán nhãn nếu nhận diện được phương tiện; box chỉ bao quanh phần nhìn thấy
- Vật thể bị cắt bởi rìa ảnh: Vẫn gán nhãn nếu xác định được đó là phương tiện; box kéo sát đến rìa ảnh
- Vật thể rất nhỏ/mơ hồ: Không gán nhãn nếu không thể xác định chắc chắn loại phương tiện

## Ghi lại quyết định cho ít nhất ba ca mơ hồ

| Ảnh | Tình huống | Quyết định cuối | Lý do theo schema |
| --- | --- | --- | --- |
| `drive_12` |Xe buýt bị một chiếc ô tô che khuất một phần.|Gán nhãn bus|Vẫn nhận diện được hình dáng.|
| `drive_11` |Một chiếc ô tô chỉ xuất hiện một phần ở mép ảnh.|Gán nhãn car|Vẫn đủ đặc điểm để nhận diện là ô tô con, box kéo đến mép ảnh|
| `drive_8` |Xe van chở người có hình dáng giống ô tô|Gán nhãn van |Vẫn đủ đặc điểm thân xe hình hộp vuông vức|
