# Phiếu QC 1 — Road v1.0

Lô được kiểm (học viên): (Vi Thanh Duc)    Người kiểm (học viên): Phạm Tiến Dũng  
Ngày: 2026-11-22    Phiên bản guideline: Road v1.0  
File được kiểm (tên + `revision` trong manifest): (điền khi có file của bạn được kiểm)  
Số ảnh kiểm: 6 (+ __ ảnh thêm, ghi riêng)   Số nhãn đã kiểm (shape + tag): (điền)  

## Tổng hợp theo mã
| Mã | Loại lỗi | Số mục kiểm | Số lỗi | Mức |
| --- | --- | ---: | ---: | --- |
| QC1-01 tag camera | sai thuộc tính / bỏ sót |  |  | nặng |
| QC1-02 đủ L1, R1 | bỏ sót |  |  | nặng |
| QC1-03 position | sai thuộc tính / thừa |  |  | nặng |
| QC1-04 tâm vạch, chiều, điểm dừng | sai phạm vi / bỏ sót |  |  | chính |
| QC1-05 vạch đứt, che | sai phạm vi / sai thuộc tính |  |  | chính |
| QC1-06 style, color, kind | sai thuộc tính |  |  | chính |
| QC1-07 vùng lái | sai phạm vi / bỏ sót / thừa |  |  | chính |
| QC1-08 đèn, màu | bỏ sót / sai phạm vi / sai thuộc tính |  |  | nặng / chính |
| QC1-09 facing, type, group, biển phụ | sai thuộc tính |  |  | chính |
| QC1-10 hình in, đủ biển | bỏ sót / sai phạm vi |  |  | chính |
| QC1-11 fisheye | sai phạm vi / sai thuộc tính |  |  | chính |
| QC1-12 file | lỗi file |  |  | nhẹ / nặng |

## Danh sách lỗi (mỗi lỗi một dòng)
| # | Mã | Ảnh | Nhãn (label, id) | Mức | Mô tả ngắn |
| --- | --- | --- | --- | --- | --- |
|  |  |  |  |  |  |

## Ca mơ hồ
Phần này ghi các ảnh của chính lô tôi gán (`PhamTienDung-front.zip`, revision 1) bị lint báo QC1-02 mức nặng nhưng thực tế không có vạch để gán. Theo CHECKPOINTS và đặc tả bàn giao, ca này được miễn khi coach đã nhìn và xác nhận.

| Ảnh | Câu hỏi cho lead | Lời đáp (nếu có) |
| --- | --- | --- |
| A05 | QC1-02 thiếu L1 và R1: đường phố không sơn vạch, xe đỗ hai bên, vỉa hè bên phải; không có vạch nào thấy được. Không vẽ lane. | Chờ coach xác nhận |
| A06 | QC1-02 thiếu L1 và R1: hai bên xe mình không có vạch sơn (chỉ có vạch ngựa vạn phía trước, vạch trắng ở góc phải dưới thuộc làn khác). Không vẽ lane. | Chờ coach xác nhận |
| A07 | QC1-02 thiếu L1: bên trái là dải bê tông chắn, không có vạch sơn; mép đã gán road_curb. Không vẽ lane. | Chờ coach xác nhận |
| A09 | QC1-02 thiếu R1: bên phải là vỉa hè, không có vạch sơn; mép đã gán road_curb. Không vẽ lane. | Chờ coach xác nhận |
| A12 | QC1-02 thiếu L1: các vạch bên trái nằm xa làn của xe mình, không có vạch sát bên trái. Không vẽ lane. | Chờ coach xác nhận |

## Quyết định
Lỗi nặng: __   Lỗi chính: __ / __ nhãn = __ %   Lỗi nhẹ: __   Ca chờ lead: 5 ảnh ở bảng trên (A05, A06, A07, A09, A12)  
Quyết định (Release / Hold / Rework):  
Lý do (theo luật của phiếu):  

Loại lỗi: bỏ sót = thiếu nhãn phải có; thừa = gán cái không phải đối tượng; sai phạm vi = hình lệch, sai chiều, dừng sai chỗ, tràn vùng. Ba loại này theo cách chia lỗi gán nhãn của ISO/IEC 5259-4 (mục 8.4.2); "sai thuộc tính" và "lỗi file" là khóa học thêm. Cách xếp mức: [thang mức lỗi](../docs/qc_severity_road_v1.0.md).
