# Báo cáo cá nhân — Ngày 11
Họ tên: Phạm Tiến Dũng    Mã học viên: 2A202603061  
Phiên bản CVAT (Help → About): 2.74.1  
Guideline: Road v1.0    Lần nộp (`revision` trong manifest): 1  
Thời điểm export (ngày giờ trên CVAT): 2026-11-22 (front ~04:24 UTC, fisheye ~04:18 UTC; manifest tạo 04:25 UTC)    Số lần nộp lại sau Rework: 0  

## 1. Kiểm project
| Mục | Đúng như guideline Road v1.0? | Ghi chú |
| --- | --- | --- |
| 6 label, đúng kiểu | Đúng | lane, road_curb: polyline; crosswalk, drivable: polygon; traffic_light, traffic_sign: rectangle |
| Thuộc tính và giá trị | Đúng | lane: position/style/color/kind; drivable: area_type direct/alternative; đèn: color/type/facing/edge_zone; biển: group/facing/edge_zone |
| 4 tag ảnh | Đúng | camera, timeofday, weather, source; mỗi tag có thuộc tính select `value` |
Cách kết thúc polyline trên bản CVAT này: vẽ polyline bằng cách bấm từng điểm trên ảnh, rồi nhấn phím N để kết thúc đường (có thể bấm lại điểm cuối cùng để đóng); điều chỉnh điểm sau bằng cách kéo điểm  
Cách đặt tag ảnh trên bản CVAT này: dùng nút Tag trên thanh công cụ bên trái của trang annotate, chọn label (camera, timeofday, weather, source) rồi chọn giá trị ở thuộc tính `value` và nhấn Tag  

## 2. Số lượng đã gán
| Task | Ảnh | lane | road_curb | crosswalk | drivable | traffic_light | traffic_sign |
| --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| front | 12 | 37 | 5 | 8 | 25 | 32 | 38 |
| front-extra (đã làm 4 / 4) | 4 | 13 | 0 | 2 | 8 | 7 | 14 |
| fisheye | 8 | 6 | 3 | 7 | 8 | 6 | 1 |
| fisheye-extra (đã làm 3 / 4) | 4 | 0 | 0 | 3 | 3 | 0 | 0 |

## 3. Bảng ca khó
| Ảnh | Nhãn | Phân vân giữa | Đã chọn | Lý do |
| --- | --- | --- | --- | --- |
| A05 | lane | vẽ L1/R1 hay không vẽ | không vẽ | đường không sơn vạch; chờ coach xác nhận QC1-02 |
| A06 | lane | L1, R1 | không vẽ | không có vạch sơn sát hai bên xe mình (chỉ có vạch ngựa vạn phía trước); chờ coach xác nhận |
| A07 | lane | L1 | không vẽ | bên trái là dải bê tông chắn, không có vạch sơn; đã có road_curb |
| A09 | lane | R1 | không vẽ | bên phải là vỉa hè, không có vạch sơn |
| A12 | lane | L1 | không vẽ | các vạch bên trái nằm xa làn xe mình |
| B11 | (chưa có shape) | gán lane/drivable hay bỏ trống | bỏ trống | ảnh chụp bãi đỗ xe: chỉ có vạch ô đỗ và ô xe người khuyết tật. Guideline mục 4: vạch ô đỗ không gán lane; ô đỗ nằm ngoài phạm vi Road v1.0; không có đèn, biển |

## 4. Phiếu QC 1 nhận được
Bạn kiểm lô của tôi: chưa nhận phiếu tại thời điểm viết  Quyết định nhận được: chưa có  
| Mã lỗi | Số lỗi | Đồng ý? | Đã sửa? |
| --- | ---: | --- | --- |
|  |  |  |  |

## 5. Kiểm file export
| File | Mở lại được? | Số shape ảnh 1 (job / file) | Số shape ảnh 2 (job / file) | Tag camera có trong XML? |
| --- | --- | --- | --- | --- |
| PhamTienDung-front.zip | Có (`road_check lint`, 16 ảnh) | A01: 9 / 9 | A02: 6 / 6 | Có, 16/16 ảnh |
| PhamTienDung-fisheye.zip | Có (`road_check lint`, 12 ảnh) | B01: 3 / 3 | B02: 6 / 6 | Có, 12/12 ảnh |

Manifest: `contains_images` = false; lint: 6 nặng (đều QC1-02, ảnh không thấy vạch, chờ coach xác nhận), 12 chính, 4 nhẹ.

## 6. Ảnh chụp màn hình
1. Tab Labels của project. (chèn ảnh chụp màn hình)
2. Một ảnh camera trước đã gán đủ (làn, vùng lái, đèn/biển). (chèn ảnh)
3. Một ảnh fisheye đã gán, phóng to đoạn polyline cong. (chèn ảnh)
4. Một đoạn XML có <polyline label="lane">. (chèn ảnh)

## 7. Tự đánh giá
Lỗi bạn mắc nhiều nhất hôm nay (theo mã QC1-xx), và cách tránh ở Ngày 20: QC1-05 (vạch đứt hoặc vạch đôi bị vẽ thành nhiều polyline cùng position; lint báo ở A01, A04, A08, A11, A12, A14) và QC1-11 (polyline fisheye chỉ 3 điểm ở B03, B04, B07). Ở Ngày 20 tôi sẽ vẽ mỗi vạch đứt hoặc vạch đôi thành đúng một polyline liên tục, và đặt điểm dày hơn theo cung trên fisheye, kiểm lint sau mỗi ảnh thay vì để cuối  
Nhãn đi vào bước huấn luyện của model phát hiện làn: mỗi polyline được đổi thành x tại các hàng ảnh cố định (row-anchor) làm đích học. Ví dụ lỗi QC1-05: nếu một vạch đứt bị tách thành hai polyline cùng position, cùng một hàng ảnh có thể có hai giá trị x đích cho một làn, hoặc đoạn giữa hai polyline bị coi là không có làn, nên model học dự đoán làn chập chờn ở đúng chỗ vạch đứt đó, ảnh hưởng tới giữ làn (LKA)  
