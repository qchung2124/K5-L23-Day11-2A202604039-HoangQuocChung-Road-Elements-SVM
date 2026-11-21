# Báo cáo cá nhân — Ngày 11
Họ tên: Hoàng Quốc Chung               Mã học viên: 2A202604039 
Phiên bản CVAT (Help → About): 2.81.0 
Guideline: Road v1.0    Lần nộp (`revision` trong manifest): 2  
Thời điểm export (ngày giờ trên CVAT): 2026-11-21 09:15    Số lần nộp lại sau Rework: 1  

## 1. Kiểm project
| Mục | Đúng như guideline Road v1.0? | Ghi chú |
| --- | --- | --- |
| 6 label, đúng kiểu | Đúng | Đủ 6 label: `lane` (polyline), `road_curb` (polyline), `crosswalk` (polygon), `drivable` (polygon), `traffic_light` (rectangle), `traffic_sign` (rectangle). |
| Thuộc tính và giá trị | Đúng | Đầy đủ thuộc tính và giá trị chuẩn theo Guideline Road v1.0 (`position`, `style`, `color`, `kind`, `area_type`, `facing`, `type`, `group`, `edge_zone`, `occluded`). |
| 4 tag ảnh | Đúng | Đủ 4 tag toàn ảnh: `camera`, `timeofday`, `weather`, `source`. |

Cách kết thúc polyline trên bản CVAT này: Nhấn phím `N` hoặc bấm nút **Done** trên thanh công cụ (hoặc double-click tại điểm cuối cùng).  
Cách đặt tag ảnh trên bản CVAT này: Mở bảng **Tags** ở góc phải màn hình $\rightarrow$ chọn tên tag $\rightarrow$ chọn giá trị thuộc tính tương ứng $\rightarrow$ bấm **Add tag** (gắn đủ 4 tag cho mỗi ảnh).  

## 2. Số lượng đã gán
| Task | Ảnh | lane | road_curb | crosswalk | drivable | traffic_light | traffic_sign |
| --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| front | 12 | 29 | 2 | 7 | 27 | 17 | 13 |
| front-extra (đã làm 0 / 4) | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| fisheye | 8 | 8 | 10 | 8 | 12 | 1 | 2 |
| fisheye-extra (đã làm 0 / 4) | 0 | 0 | 0 | 0 | 0 | 0 | 0 |

## 3. Bảng ca khó
| Ảnh | Nhãn | Phân vân giữa | Đã chọn | Lý do |
| --- | --- | --- | --- | --- |
| `A05`, `A06`, `A09` | `lane` | Vẽ bổ sung `R1`/`L1` để hết cảnh báo `lint` hay để trống | Không vẽ bịa (giữ trống `R1`/`L1` ở phía không có vạch) | Thực tế không có vạch sơn kẻ làn; đã được người kiểm lô (`PhamHuuMinh`) mở ảnh đối chiếu và xác nhận thuộc ca được miễn lỗi `QC1-02`. |
| `A06_b8c66e31-37045eec.jpg` | `lane` | Kéo dài vệt vàng mờ dài 39 px tại `(440,416)` hay xóa hẳn | Xóa đoạn polyline ngắn 39 px | Vệt sơn quá mờ và đứt đoạn sát mép vỉa, không đủ căn cứ xác định biên trái làn đường; xóa bỏ để tránh sai phạm vi `QC1-04`. |
| `A08`, `A12` | `crosswalk` | Gộp thành 1 polygon lớn hay tách theo từng lối sang đường | Tách theo từng lối sang đường độc lập | Mỗi cụm vạch ngựa vằn phục vụ một nhánh băng qua đường riêng biệt tại nút giao nên tách riêng từng polygon. |
| `B02`, `B03`, `B04` | `traffic_light`, `traffic_sign` | Bật hay tắt cờ `edge_zone` ở vùng rìa ảnh fisheye | Bật `edge_zone` | Tâm bounding box nằm ngoài 80% bán kính vòng ảnh fisheye, đối tượng bị biến dạng quang học mạnh nên bật `edge_zone` theo quy tắc Task 2. |
| `B06`, `B07` | `lane` | Đặt `position` là `L1`/`R1` hay `other` trên camera hai bên (`MVL`, `MVR`) | `position = other` | Camera hông quan sát ngang thân xe, không xác định theo hướng tiến/lùi của làn xe chủ nên gán `position = other`. |

## 4. Phiếu QC 1 nhận được
Bạn kiểm lô của tôi: Phạm Hữu Minh — 2A202603330  Quyết định nhận được: Rework  
| Mã lỗi | Số lỗi | Đồng ý? | Đã sửa? |
| --- | ---: | --- | --- |
| QC1-03 | 1 | Đồng ý (đổi thuộc tính `position` của vạch liền lề phải tại `A04` từ `R1` sang `R2`) | Đã sửa |
| QC1-04 | 1 | Đồng ý (xóa đoạn `lane` `L1` dài 39 px tại `A06`) | Đã sửa |
| QC1-07 | 3 | Đồng ý (kéo biên vùng lái xuyên qua xe phía trước tại `A08`, `A10` và toàn lô `front`; thu gọn vùng lái ra khỏi dải gạch đỏ làn xe đạp và vỉa hè tại `B07`) | Đã sửa |
| QC1-08 | 1 | Đồng ý (bổ sung hộp `traffic_light` cho đèn người đi bộ tại `A12`) | Đã sửa |
| QC1-10 | 3 | Đồng ý (bổ sung 4 biển cột trái tại `A10`, 2 biển tại `A12`, 1 biển xanh cột đèn trái tại `A04` và rà lại toàn bộ ảnh `front`) | Đã sửa |
| QC1-11 | 1 | Đồng ý (vẽ lại polyline `lane` theo cung cong vạch sơn tại `B07`) | Đã sửa |
| QC1-12 | 1 | Đồng ý (1 điểm trùng liền kề trên `drivable` tại `A02`) | Chưa sửa (lỗi mức nhẹ, không làm sai lệch hình dạng vùng lái) |

## 5. Kiểm file export
| File | Mở lại được? | Số shape ảnh 1 (job / file) | Số shape ảnh 2 (job / file) | Tag camera có trong XML? |
| --- | --- | --- | --- | --- |
| `HoangQuocChung-front.zip` | Có | `A01`: 9 / 9 | `A02`: 6 / 6 | Có (`camera=front`) |
| `HoangQuocChung-fisheye.zip` | Có | `B01`: 2 / 2 | `B02`: 5 / 5 | Có (`camera=fisheye_front`) |

## 6. Ảnh chụp màn hình
1. Tab Labels của project: `images/1_label.png`
2. Một ảnh camera trước đã gán đủ (làn, vùng lái, đèn/biển):   `images/2_front.png`
3. Một ảnh fisheye đã gán, phóng to đoạn polyline cong: `images/3_fisheye.png`
4. Một đoạn XML có `<polyline label="lane">`: `images/4_lane.png`

## 7. Tự đánh giá
Lỗi bạn mắc nhiều nhất hôm nay (theo mã QC1-xx), và cách tránh ở Ngày 20:  
Hai nhóm lỗi mắc nhiều nhất qua kết quả QC 1 là **`QC1-07`** (vẽ biên polygon `drivable` khoét lỗ vòng quanh xe phía trước ở `A08`, `A10` hoặc tràn nhẹ sang làn xe đạp/vỉa hè trên ảnh fisheye `B07`) và **`QC1-10`** (bỏ sót biển báo cao $\ge 8\text{ px}$ ở lề đường như `A04`, `A10`, `A12`), kèm theo lỗi nhầm thuộc tính `R1`/`R2` (`QC1-03`). Cách tránh ở Ngày 20: khi vẽ `drivable`, luôn áp dụng nguyên tắc "mặt đường trống" bằng cách kéo thẳng cạnh polygon xuyên qua các phương tiện đang lưu thông/đỗ phía trước và kiểm tra kỹ ranh giới bó vỉa; trước khi kết thúc mỗi ảnh, phóng to dọc hai bên cột đèn/lề đường để gán đủ mọi biển báo cao $\ge 8\text{ px}$, đồng thời kiểm tra lại thuộc tính `position` cho từng vạch kẻ làn (`L1`, `L2`, `R1`, `R2`, `other`) trước khi chuyển frame.  

Nhãn của bạn đi vào model ở đâu? Chọn một lỗi đã sửa và nói nó làm model học sai thế nào:  
Dữ liệu nhãn xuất từ CVAT (`annotations.xml`) được chuyển đổi thành tập dữ liệu chuẩn (ground-truth) gồm mặt nạ phân vùng pixel (`drivable`, `crosswalk`), chuỗi tọa độ hình học (`lane`, `road_curb`) và hộp giới hạn kèm thuộc tính (`traffic_light`, `traffic_sign`) để huấn luyện các mô hình nhận thức môi trường (Perception) trong hệ thống hỗ trợ lái nâng cao ADAS / xe tự hành như phân vùng vùng lái an toàn, giữ làn đường (LKA) và nhận diện biển báo. Ví dụ lỗi **`QC1-07`** đã sửa (khoét lỗ biên polygon `drivable` vòng quanh các xe phía trước tại `A08`, `A10`): nếu giữ nguyên nhãn bị khoét lỗ, mô hình phân vùng mặt đường sẽ hiểu nhầm rằng phần mặt đường bị thân xe khác che khuất là "vùng không thể lái" (non-drivable) thay vì mặt đường hợp lệ bị vật cản động che tạm thời, khiến hệ thống hoạch định quỹ đạo dự đoán sai cấu trúc mặt đường phía trước khi xe kia di chuyển.  

## 8. (Tùy chọn, buffer) Từ polyline đến đích row-anchor
| y | 720 | 680 | 640 | 600 | 560 |
| --- | ---: | ---: | ---: | ---: | ---: |
| x của chúng tôi | [Tùy chọn] | [Tùy chọn] | [Tùy chọn] | [Tùy chọn] | [Tùy chọn] |
| x của bạn kia | [Tùy chọn] | [Tùy chọn] | [Tùy chọn] | [Tùy chọn] | [Tùy chọn] |

Trả lời 3 câu:

1. Năm số x đó chính là đích mà một model row-anchor học cho vạch này. Nếu bạn dừng polyline sớm 40 px, hàng nào đổi thành "không có làn"?  
Các hàng quét (row-anchor) nằm phía trên điểm dừng mới của polyline (tức các hàng có tọa độ $y$ nhỏ hơn điểm kết thúc mới trong đoạn $40\text{ px}$ phía xa bị cắt bớt) sẽ mất giao điểm với polyline và đổi nhãn thành "không có làn" (ví dụ: nếu ban đầu polyline kéo tới $y = 560$ mà dừng sớm $40\text{ px}$ tại $y = 600$ thì hàng **$y = 560$** sẽ chuyển thành "không có làn").

2. So với bạn được kiểm (cùng ảnh): ở hàng 720 và hàng 560, hai bạn lệch nhau bao nhiêu pixel? Lệch ở hàng nào ảnh hưởng LKA nhiều hơn (slide 25)?  
Độ lệch tại mỗi hàng bằng $|x_{\text{tôi}} - x_{\text{bạn}}|$ pixel. Sai lệch ở **hàng $y = 720$** (gần đầu xe nhất) ảnh hưởng đến hệ thống giữ làn **LKA (Lane Keeping Assist)** nhiều hơn, vì hàng $y = 720$ nằm ngay sát vị trí bánh xe hiện tại nên quyết định trực tiếp sai số lệch ngang (lateral offset) và góc hướng tức thời để bộ điều khiển đánh lái giữ xe ở tâm làn, trong khi hàng $y = 560$ ở xa chỉ đóng góp vào phần dự báo độ cong phía trước.

3. Nếu polyline vẽ từ xa về gần (ngược quy tắc 2), cách tính trên có đổi không? Script nào sẽ gặp khó?  
Về mặt hình học thuần túy, tập giao điểm $(x, y)$ với các hàng ngang $y$ không đổi nếu thuật toán chỉ lấy giao cắt đoạn thẳng, nhưng các script tiền xử lý chuỗi điểm — chẳng hạn script kiểm tra tính đơn điệu chiều vẽ từ gần ra xa ($y$ giảm dần từ đáy ảnh lên đỉnh ảnh), script nội suy row-anchor mặc định điểm đầu nằm ở gần xe, hoặc script tính véc-tơ hướng của làn đường — sẽ gặp lỗi thứ tự đỉnh, báo lỗi ngược chiều (`QC1-04`) hoặc loại bỏ/nội suy sai thực thể làn đường đó.