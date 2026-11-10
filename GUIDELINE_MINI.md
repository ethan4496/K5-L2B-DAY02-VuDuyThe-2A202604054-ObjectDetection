# Mini guideline — bài làm cá nhân

> Điền nội dung này trước khi bắt đầu gán nhãn. Giữ lại các quyết định sau khi self-QC.

## Định nghĩa lớp

| Lớp | Định nghĩa của bạn | Ví dụ/điểm phân biệt |
| --- | --- | --- |
| `car` | Xe chở người cỡ nhỏ (khoảng 4–7 chỗ): sedan, hatchback, SUV, crossover, taxi. Thân thấp hoặc vừa, có nắp capo rõ, thường có cốp tách riêng hoặc đuôi dốc. | Taxi vàng (`drive_003`), sedan bạc (`drive_008`), SUV đen (`drive_002`). Khác `van`: mui thấp hơn, đầu xe dài, không có thân hộp vuông. SUV to vẫn là `car`. |
| `truck` | Xe chuyên chở hàng: cabin tách riêng với thùng hàng hoặc khung chở hàng phía sau. Gồm xe ben, xe tải thùng, xe bồn, đầu kéo, bán tải chở hàng. | Xe ben đỏ chở đất (`drive_008`), bán tải trắng (`drive_005`). Khác `van`: cabin và thùng hàng là hai khối riêng. Khác `bus`: không có dãy cửa sổ khách dọc thân. |
| `bus` | Xe khách cỡ lớn chở nhiều người. Thân dài hình hộp, có dãy cửa sổ đều dọc thân, nhiều cửa lên xuống. Gồm buýt thành phố, buýt nối toa, xe khách du lịch. | Buýt nối toa vàng-xanh (`drive_008`), xe khách trắng (`drive_002`). Khác `van`: dài hơn hẳn (thường gấp khoảng 2 lần xe con trở lên), có từ 2 cửa khách và nhiều ô kính. Buýt nối toa vẫn là 1 box. |
| `van` | Xe một khối, thân hộp cao, mui cao. Đầu xe ngắn hoặc gần như không có capo, thường có cửa trượt bên hông. Gồm minivan, van chở khách hoặc chở hàng, microbus cỡ nhỏ. | Minivan trắng (`drive_002` mép phải, `drive_008` giữa ảnh), minivan xanh có giá nóc (`drive_006`). Khác `car`: mui cao vuông, đầu ngắn. Khác `truck`: khoang hàng liền khối với cabin. Khác `bus`: ngắn, chỉ cỡ xe con đến khoảng 1,5 lần. |

Thứ tự phân biệt nhanh:
1. Cabin tách khỏi thùng hàng → `truck`.
2. Thân dài cỡ khoảng 2 xe con trở lên, nhiều cửa sổ khách → `bus`.
3. Một khối hộp, mui cao, đầu ngắn → `van`.
4. Còn lại → `car`.

Nếu xe lưng chừng giữa `van` và `car` hoặc `bus`: không tự chọn, ghi case ID và hỏi giảng viên.

## Quy tắc chung

- Box bám sát vật thể nghĩa là: ...
- Vật thể bị che khuất: ...
- Vật thể bị cắt bởi rìa ảnh: ...
- Vật thể rất nhỏ/mơ hồ: ...

## Ghi lại quyết định cho ít nhất ba ca mơ hồ

| Ảnh | Tình huống | Quyết định cuối | Lý do theo schema |
| --- | --- | --- | --- |
| `drive_006` | Minivan nhỏ màu xanh ngọc có giá nóc ở góc phải dưới. Thân cao, dạng hộp giống `van`, nhưng kích thước chỉ cỡ xe con nên dễ nhầm với `car`. | Tạm gán `van` (3), đánh dấu để hỏi giảng viên. | Phân lớp theo hình dáng thân xe (một khối, mui cao, đầu ngắn, có cửa trượt), không theo kích thước. GUIDE yêu cầu ca van/minivan mơ hồ với `car` phải ghi case ID và hỏi, không tự chọn. |
| `drive_005` | Bán tải trắng chở hàng trên thùng, ở giữa ảnh. Đầu xe giống xe con nhưng phía sau có thùng hở, nên mơ hồ giữa `truck` và `car`. | Gán `truck` (1). Box chỉ ôm thân xe, không lấy phần hàng thò ra ngoài. | Cabin tách riêng với thùng chở hàng phía sau, khớp định nghĩa `truck`. `car` chỉ dành cho xe chở người. |
| `drive_003` | Dòng xe ở xa sát chân trời dưới cầu vượt. Xe rất nhỏ (dưới khoảng 15 px), dính vào nhau, không phân biệt được `car`, `van` hay `bus`. | Không gán những xe không xác định chắc được lớp. Xe nào đủ rõ thì vẽ box riêng từng chiếc. | GUIDE ghi: vật thể quá nhỏ, không xác định chắc lớp thì không tự đoán. Không gộp nhiều xe vào một box. |
