# Phiếu QC 1 — Road v1.0

Lô được kiểm (học viên): Phạm Hữu Minh        Người kiểm (học viên): Hoàng Quốc Chung
Ngày: 2026-11-21                           Phiên bản guideline: Road v1.0  
File được kiểm (tên + `revision` trong manifest): PhamHuuMinh-front.zip, PhamHuuMinh-fisheye.zip (revision: 1)  
Số ảnh kiểm: 6 (+ 6 ảnh thêm, ghi riêng)   Số nhãn đã kiểm (shape + tag): 107 (59 shape + 48 tag)  

## Tổng hợp theo mã
| Mã | Loại lỗi | Số mục kiểm | Số lỗi | Mức |
| --- | --- | ---: | ---: | --- |
| QC1-01 tag camera | sai thuộc tính / bỏ sót | 12 | 0 | nặng |
| QC1-02 đủ L1, R1 | bỏ sót | 12 | 9 | nặng |
| QC1-03 position | sai thuộc tính / thừa | 12 | 1 | nặng |
| QC1-04 tâm vạch, chiều, điểm dừng | sai phạm vi / bỏ sót | 12 | 4 | chính |
| QC1-05 vạch đứt, che | sai phạm vi / sai thuộc tính | 7 | 0 | chính |
| QC1-06 style, color, kind | sai thuộc tính | 7 | 0 | chính |
| QC1-07 vùng lái | sai phạm vi / bỏ sót / thừa | 20 | 12 | chính |
| QC1-08 đèn, màu | bỏ sót / sai phạm vi / sai thuộc tính | 12 | 0 | nặng / chính |
| QC1-09 facing, type, group, biển phụ | sai thuộc tính | 27 | 0 | chính |
| QC1-10 hình in, đủ biển | bỏ sót / sai phạm vi | 12 | 2 | chính |
| QC1-11 fisheye | sai phạm vi / sai thuộc tính | 6 | 4 | chính |
| QC1-12 file | lỗi file | 2 | 0 | nhẹ / nặng |

## Danh sách lỗi (mỗi lỗi một dòng)
| # | Mã | Ảnh | Nhãn (label, id) | Mức | Mô tả ngắn |
| --- | --- | --- | --- | --- | --- |
| 1 | QC1-07 | B02_03177_FV.png | drivable | chính | Vùng lái tràn qua mép bó vỉa lên vỉa hè bên phải dưới chân người đi bộ |
| 2 | QC1-10 | B02_03177_FV.png | traffic_light | chính | Bỏ sót cụm đèn tín hiệu lớn (>= 8 px) ở góc trên bên phải ảnh |
| 3 | QC1-02 | B03_04267_RV.png | lane | nặng | Bỏ sót vạch trắng nét đứt phân làn giữa đường (L1/R1) |
| 4 | QC1-11 | B03_04267_RV.png | road_curb, lane | chính | road_curb trái nối thẳng lệch cung > 5 px và tràn vào viền tối; lane phải gấp khúc |
| 5 | QC1-07 | B03_04267_RV.png | drivable | chính | Vùng lái tràn lên vỉa hè trái, tràn qua trụ chắn phải và thiếu vùng alternative |
| 6 | QC1-02 | B04_05535_RV.png | lane | nặng | Bỏ trống hoàn toàn lane, thiếu vạch trắng nét đứt phân làn giữa đường (L1/R1) |
| 7 | QC1-07 | B04_05535_RV.png | drivable, crosswalk | chính | drivable gộp chung làn đang đi với làn buýt bên trái và tràn vỉa hè phải; crosswalk thiếu góc trái |
| 8 | QC1-11 | B06_04068_MVL.png | drivable, road_curb | chính | drivable vẽ đè lên thân xe mình; road_curb vẽ thành đường thẳng cắt chéo giữa lòng đường |
| 9 | QC1-07 | B06_04068_MVL.png | drivable, crosswalk | chính | drivable tràn qua dải phân cách cứng sang đường bên kia; crosswalk thiếu gần một nửa vạch |
| 10 | QC1-04 | B06_04068_MVL.png | lane | chính | Bỏ sót các vạch kẻ làn (position = other) trên mặt đường camera trái |
| 11 | QC1-11 | B07_01216_MVR.png | drivable, road_curb | chính | drivable vẽ đè lên thân xe mình; road_curb bên trái nối thẳng lệch cung cong > 5 px |
| 12 | QC1-07 | B07_01216_MVR.png | drivable, crosswalk | chính | drivable tràn lên vỉa hè góc trên bên trái; bỏ sót crosswalk thứ hai phía xa |
| 13 | QC1-04 | B07_01216_MVR.png | lane | chính | Bỏ sót các vạch kẻ làn nét đứt (position = other) bên phải đường |
| 14 | QC1-11 | B08_05783_MVR.png | drivable, crosswalk | chính | drivable và crosswalk vẽ đè lên phần thân xe của mình ở cạnh dưới bên phải |
| 15 | QC1-07 | B08_05783_MVR.png | drivable, crosswalk | chính | drivable tràn qua hàng rào xanh bên trái và lên vỉa hè trên; crosswalk thiếu vạch dưới cùng |
| 16 | QC1-04 | B08_05783_MVR.png | lane | chính | Bỏ sót vạch kẻ làn (position = other) ở góc dưới bên trái |
| 17 | QC1-02 | A03_b1c66a42-6f7d68ca.jpg | lane | nặng | Thiếu vạch R1 (vạch trắng nét đứt phân làn ngay bên phải xe) |
| 18 | QC1-04 | A03_b1c66a42-6f7d68ca.jpg | lane | chính | Polyline L1 dừng quá sớm ngay mép dưới chữ SCHOOL dù phía trước vạch vẫn rõ |
| 19 | QC1-07 | A03_b1c66a42-6f7d68ca.jpg | drivable | chính | Vùng lái dừng quá sớm ngay mép dưới chữ SCHOOL trong khi đường phía trước trống |
| 20 | QC1-10 | A03_b1c66a42-6f7d68ca.jpg | traffic_sign | chính | Bỏ sót các biển báo cảnh báo hình thoi (>= 8 px) ở lề phải |
| 21 | QC1-02 | A06_b8c66e31-37045eec.jpg | lane | nặng | Thiếu vạch L1 phân làn bên trái sát hàng cột phân cách |
| 22 | QC1-07 | A06_b8c66e31-37045eec.jpg | drivable | chính | Vùng lái kéo tràn qua hàng cột phân cách sang làn xe chạy ngược chiều bên trái |
| 23 | QC1-02 | A07_b41ace08-c8468690.jpg | lane | nặng | Thiếu vạch L1 (vạch sơn vàng mép trái sát dải phân cách bê tông) |
| 24 | QC1-03 | A07_b41ace08-c8468690.jpg | road_curb | nặng | Vẽ nhầm vạch sơn vàng mép trái (lane L1) thành road_curb |
| 25 | QC1-07 | A07_b41ace08-c8468690.jpg | drivable | chính | Vùng lái cắt vòng theo đuôi xe con phía trước thay vì vẽ xuyên qua xe; thiếu alternative |
| 26 | QC1-02 | A08_c0deebc1-16cfa791.jpg | lane | nặng | Thiếu vạch L1 (vạch trắng nét đứt ngay bên trái làn xe đang chạy) |
| 27 | QC1-07 | A08_c0deebc1-16cfa791.jpg | drivable | chính | Gộp chung làn đang đi (direct) và làn cùng chiều bên trái (alternative) thành một vùng |
| 28 | QC1-02 | A10_b6ff1331-f6d3fba8.jpg | lane | nặng | Thiếu vạch R1 phân chia làn đang đi với làn bên phải |
| 29 | QC1-07 | A10_b6ff1331-f6d3fba8.jpg | drivable | chính | Vùng lái cắt vòng quanh đuôi xe SUV phía trước thay vì vẽ xuyên qua xe; thiếu alternative |
| 30 | QC1-02 | A12_c0f978fa-9b4e623f.jpg | lane | nặng | Thiếu vạch L1 (bỏ trống toàn bộ lane phía sau vạch ngựa vạn) |
| 31 | QC1-02 | A12_c0f978fa-9b4e623f.jpg | lane | nặng | Thiếu vạch R1 (bỏ trống toàn bộ lane phía sau vạch ngựa vạn) |
| 32 | QC1-07 | A12_c0f978fa-9b4e623f.jpg | drivable | chính | Gộp chung các làn cùng chiều (direct và alternative) thành một đa giác duy nhất |

## Ca mơ hồ
| Ảnh | Câu hỏi cho lead | Lời đáp (nếu có) |
| --- | --- | --- |
| A07_b41ace08-c8468690.jpg | Vạch sơn vàng sát dải phân cách bê tông bên trái nên tính đồng thời lỗi thiếu L1 (QC1-02) và vẽ nhầm road_curb (QC1-03) hay gộp một lỗi? Đã xếp mức nặng theo nguyên tắc chọn mức cao hơn khi phân vân. | |
| B02_03177_FV.png, B04_05535_RV.png | Các hộp đèn/biển sát rìa vòng ảnh fisheye có tâm nằm gần ngưỡng 80% bán kính cần đối chiếu lại cờ `edge_zone` trong XML. | |

## Quyết định
Lỗi nặng: 10   Lỗi chính: 22 / 107 nhãn = 20.56 %   Lỗi nhẹ: 0   Ca chờ lead: 0  
Quyết định (Release / Hold / Rework): Rework  
Lý do (theo luật của phiếu): Có 10 lỗi mức nặng (>= 1 lỗi nặng: bỏ sót L1/R1 khi nhìn thấy rõ trên đường và gán nhầm vạch sơn thành road_curb) và tỉ lệ lỗi chính đạt 20,56 % (vượt ngưỡng cho phép 5 % trên tổng 107 nhãn đã kiểm).  

Loại lỗi: bỏ sót = thiếu nhãn phải có; thừa = gán cái không phải đối tượng; sai phạm vi = hình lệch, sai chiều, dừng sai chỗ, tràn vùng. Ba loại này theo cách chia lỗi gán nhãn của ISO/IEC 5259-4 (mục 8.4.2); "sai thuộc tính" và "lỗi file" là khóa học thêm. Cách xếp mức: [thang mức lỗi](../docs/qc_severity_road_v1.0.md).