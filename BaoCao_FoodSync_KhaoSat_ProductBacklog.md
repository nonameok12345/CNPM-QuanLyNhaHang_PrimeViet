# BÁO CÁO DỰ ÁN: KHẢO SÁT NGƯỜI DÙNG VÀ XÂY DỰNG SẢN PHẨM WEB QUẢN LÝ QUÁN ĂN (FOODSYNC)

Từ nhu cầu người dùng đến User Story, Acceptance Criteria, Product Backlog và Kế hoạch kiểm thử · CMC University · 2026

## Mục lục

- [Thông tin chung](#thông-tin-chung)
- [Bước 1 – Khảo sát người dùng](#bước-1--khảo-sát-người-dùng)
- [Bước 2 – Xác định vấn đề](#bước-2--xác-định-vấn-đề)
- [Bước 3 – Các tình huống thực tế](#bước-3--các-tình-huống-thực-tế-micro-scenarios)
- [Bước 4 – Xây dựng Persona](#bước-4--xây-dựng-persona)
- [Bước 5 – Kịch bản xây dựng](#bước-5--kịch-bản-xây-dựng)
- [Bước 6 – User Story và thang MoSCoW](#bước-6--chuyển-thành-user-story-kèm-thang-ưu-tiên-moscow)
- [Bước 7 – Tiêu chí chấp nhận và quy tắc nghiệp vụ](#bước-7--tiêu-chí-chấp-nhận-và-quy-tắc-nghiệp-vụ)
- [Bước 8 – Từ User Story đến tính năng](#bước-8--từ-câu-chuyện-người-dùng-đến-tính-năng)
- [Bước 9 – Product Backlog và kế hoạch Sprint](#bước-9--product-backlog-và-kế-hoạch-sprint)
- [Bước 10 – Kế hoạch kiểm thử](#bước-10--kế-hoạch-kiểm-thử)
- [Kết luận](#kết-luận)

## Thông tin chung

| Hạng mục | Nội dung |
|---|---|
| Tên dự án | FoodSync – Website tổng hợp order và quản lý quán ăn |
| Nhóm thực hiện | Nhóm 1 |
| Thành viên | Phạm Tiến Sơn, Nguyễn Duy Anh, Nguyễn Nhật Tân, Đỗ Anh Tài |
| Môn học / Giảng viên | Công nghệ phần mềm – CMC University / Nguyễn Thị Vân Anh |
| Nền tảng kỹ thuật | ASP.NET Core MVC, Entity Framework Core, SQL Server (website quản lý nhà hàng của nhóm) |
| Thời gian thực hiện | 2026 |

## BƯỚC 1 – KHẢO SÁT NGƯỜI DÙNG

**Mục tiêu:** tìm hiểu cách quán ăn đang nhận order, quản lý thực đơn và giá món; xác định công cụ đang dùng, điểm bất tiện và nhu cầu cải thiện của chủ quán.

### 1.1. Kế hoạch khảo sát

| Nội dung | Mô tả |
|---|---|
| Đối tượng | Chủ quán/đại diện quán ăn thuộc nhiều loại hình khác nhau |
| Số mẫu thực tế | 4 phản hồi Google Forms |
| Phương pháp | Khảo sát trực tuyến qua Google Forms |
| Câu hỏi chính | Loại hình quán; thời gian hoạt động; cách nhận order; có muốn công cụ quản lý quán không; chức năng mong muốn; ý kiến tự do |
| Đầu ra | Bảng thống kê số liệu để xác định vấn đề và xếp ưu tiên chức năng |

**Hạn chế:** mẫu chỉ có 4 phản hồi nên các tỷ lệ chỉ phản ánh nhóm đã trả lời, chưa đại diện cho thị trường. Báo cáo này chỉ dùng số liệu của 4 phản hồi; những điều khảo sát chưa hỏi được ghi rõ là giả thuyết cần xác minh.

### 1.2. Kết quả khảo sát (thống kê)

- **Loại hình quán:** quán cơm bình dân 2 lượt chọn (50%); nhà hàng, quán ăn nhanh và quán bún phở mỗi loại 1 lượt (25%). Tổng 5 lượt chọn trên 4 phản hồi vì có quán chọn hai loại hình.
- **Thời gian hoạt động:** từ 1 đến 3 năm: 3/4 (75%); dưới 1 năm: 1/4 (25%); trên 3 năm: 0/4.
- **Cách nhận order:** dùng tất cả phương án 2/4 (50%); chỉ gọi món trực tiếp 1/4 (25%); chỉ qua app giao đồ ăn 1/4 (25%); chỉ qua Zalo 0/4.
- **Nhu cầu công cụ quản lý quán dễ dùng:** có 4/4 (100%); không hoặc đang cân nhắc: 0/4.
- **Chức năng mong muốn:** tổng hợp order từ nhiều nơi 2/4 (50%); quản lý thực đơn và giá món 1/4 (25%); “Khác” 1/4 (chưa nêu nội dung); quản lý doanh thu, nguyên liệu và kho, lịch làm việc nhân viên: 0/4.
- **Ý kiến tự do:** 3 câu trả lời, trong đó có mong muốn có “sản phẩm mà nhiều quán sử dụng được”.

### 1.3. Tổng hợp vấn đề và nhu cầu thực tế

| Nội dung | Số quán | Tỷ lệ | Ý nghĩa với sản phẩm |
|---|---|---|---|
| Nhận order bằng tất cả kênh (trực tiếp, Zalo, app giao đồ ăn) | 2/4 | 50% | Order nằm ở nhiều nơi, cần một danh sách chung |
| Chọn chức năng tổng hợp order từ nhiều nơi | 2/4 | 50% | Chức năng được chọn nhiều nhất, là trọng tâm của MVP |
| Chọn quản lý thực đơn và giá món | 1/4 | 25% | Dữ liệu nền để lập đơn |
| Muốn có công cụ quản lý quán dễ dùng | 4/4 | 100% | Nhu cầu chung của toàn bộ mẫu |
| Mong muốn sản phẩm nhiều quán dùng được | 1/4 | 25% | Ràng buộc thiết kế: thực đơn do từng quán tự nhập |

Không quán nào chọn quản lý doanh thu, kho hay lịch nhân viên (0/4). Vì vậy các module này không phải ưu tiên của MVP; website đã có sẵn nên nhóm chỉ đưa vào kiểm thử hồi quy ở Sprint 5.

## BƯỚC 2 – XÁC ĐỊNH VẤN ĐỀ

Dựa trên khảo sát (N = 4), nhóm xác định 3 vấn đề cần giải quyết ở phiên bản đầu tiên. Mã P01–P03 trùng với báo cáo Chương 3.

| Mã | Vấn đề | Số quán | Quyết định |
|---|---|---|---|
| I1 (P01) | **Ghi nhận và theo dõi order từ nhiều kênh.** Chủ quán khó nhận và theo dõi order vì order đến từ nhiều nơi nên phải nhìn nhiều chỗ. Hệ quả cụ thể (sót, nhầm, chậm order) khảo sát chưa ghi nhận, cần xác minh thêm. | 2/4 | Trọng tâm |
| I2 (P02) | **Quản lý thực đơn và giá món.** Cần một nơi sửa món và giá để dùng khi lập đơn. Khảo sát chưa ghi nhận nguyên nhân và hệ quả. | 1/4 | Hỗ trợ |
| I3 (P03) | **Dùng chung cho nhiều loại quán, có phân quyền.** Thực đơn do từng quán tự nhập; tài khoản chia vai trò Quản lý, Nhân viên, Khách hàng. Nhiều quán độc lập trên một hệ thống là phần mở rộng. | 1/4 | Ràng buộc thiết kế |
| P04 | Nhu cầu “Khác” chưa nêu cụ thể. | 1/4 | Để sau |

**Lý do chọn I1 làm trọng tâm:** (1) có từ 2/4 quán đề cập; (2) gắn trực tiếp với mục tiêu sản phẩm là gom order; (3) giải quyết được bằng phần mềm trong phạm vi đồ án.

## BƯỚC 3 – CÁC TÌNH HUỐNG THỰC TẾ (MICRO-SCENARIOS)

*Các tình huống dưới đây là minh họa dựng từ số liệu khảo sát, chưa phải trích dẫn phỏng vấn.*

- **Tình huống 1 (từ I1 – 50%):** vào giờ đông khách, quán vừa có khách gọi trực tiếp, vừa có đơn Zalo và đơn từ app giao đồ ăn. Order nằm ở sổ ghi, điện thoại và máy tính bảng riêng nên người bán phải nhìn nhiều nơi cùng lúc, dễ bỏ sót đơn.
- **Tình huống 2 (từ I2 – 25%):** quán thêm món mới hoặc đổi giá. Nếu thực đơn chỉ nằm trên giấy hoặc sổ, nhân viên có thể không biết giá mới khi ghi order.
- **Tình huống 3 (từ I3 – 25%):** một quán khác loại hình muốn dùng cùng phần mềm. Quán cần tự nhập thực đơn của mình, và mỗi nhân viên chỉ nên thấy các chức năng thuộc vai trò của họ.

## BƯỚC 4 – XÂY DỰNG PERSONA

| | Persona 1: Nhân viên thu ngân / phục vụ | Persona 2: Chủ quán / Quản lý |
|---|---|---|
| Căn cứ | Suy ra từ vai trò Nhân viên trong website; chưa phải đối tượng khảo sát | 4 phản hồi khảo sát (chủ quán, đại diện quán) |
| Mục tiêu | Lập đơn nhanh, đúng món, đúng giá; biết đơn nào đang chờ làm; thu tiền chính xác | Xem mọi order ở một nơi; giữ thực đơn và giá đúng; nắm số đơn và doanh thu |
| Khó khăn | Phải theo dõi order ở nhiều nơi; dễ nhầm món hoặc giá khi giờ đông | Order đến từ nhiều kênh (2/4 quán); chưa có một danh sách chung |
| Chức năng dùng chính | Màn hình lập đơn, danh sách thẻ đơn, trạng thái chế biến, thanh toán | Quản lý thực đơn, bảng điều khiển, thống kê theo nguồn, phân quyền |

Khách hàng là nhóm người dùng thứ ba (quét QR gọi món, đặt bàn trước) và tạo ra hai nguồn đơn của hệ thống. Nhóm chưa lập persona riêng vì khảo sát chưa hỏi đối tượng này.

## BƯỚC 5 – KỊCH BẢN XÂY DỰNG

- **Kịch bản 1 (lập đơn tại quầy):** Đăng nhập → mở màn hình lập đơn → chọn bàn → thêm món từ thực đơn và chỉnh số lượng → chọn nguồn đơn → hệ thống tự tính tổng tiền → lưu đơn.
- **Kịch bản 2 (khách gọi món bằng QR):** Khách quét mã QR tại bàn → chọn món và gửi → đơn có nguồn “QR tại bàn” xuất hiện trong danh sách thẻ đơn → nhân viên đổi trạng thái Mới → Đang làm → Đã xong.
- **Kịch bản 3 (thanh toán):** Thu ngân chọn đơn cần thanh toán → chọn tiền mặt hoặc chuyển khoản QR → nếu chuyển khoản thì xác nhận khi thấy tiền về → trả đủ thì hóa đơn chuyển sang “Đã thanh toán”.
- **Kịch bản 4 (theo dõi kinh doanh):** Quản lý mở bảng điều khiển → xem số đơn, doanh thu hôm nay và số đơn theo từng nguồn → mở danh sách đơn để lọc khi cần kiểm tra.

## BƯỚC 6 – CHUYỂN THÀNH USER STORY (KÈM THANG ƯU TIÊN MoSCoW)

| ID | Câu chuyện người dùng | Ưu tiên (MoSCoW) | Nhóm |
|---|---|---|---|
| US01 | Với vai trò chủ quán, tôi muốn đăng ký/đăng nhập bằng tài khoản riêng, khai báo thông tin quán và được phân quyền theo vai trò để mỗi người chỉ dùng đúng chức năng của mình. | Phải | Tài khoản |
| US02 | Với vai trò chủ quán, tôi muốn thêm, sửa, xóa món và giá để thực đơn luôn đúng khi lập đơn. | Phải | Thực đơn |
| US03 | Với vai trò nhân viên, tôi muốn lập đơn tại quầy trên một màn hình: chọn món, số lượng, nguồn đơn rồi thanh toán, để ghi nhận đúng đơn và tổng tiền. | Phải | Bán hàng |
| US04 | Với vai trò nhân viên, tôi muốn xem mọi đơn trên giao diện thẻ đơn và lọc theo nguồn, ngày, trạng thái thanh toán để biết đơn đến từ đâu và xử lý đúng đơn. | Phải | Quản lý đơn |
| US05 | Với vai trò nhân viên, tôi muốn cập nhật trạng thái chế biến của đơn hoặc từng món (Mới, Đang làm, Đã xong) để biết việc nào đang chờ. | Phải | Chế biến |
| US06 | Với vai trò quản lý, tôi muốn xem số đơn và doanh thu theo nguồn trong ngày để biết kênh nào tạo nhiều đơn và doanh thu. | Nên | Báo cáo |
| US07 | Với vai trò nhân viên, tôi muốn Check-in/Check-out để quản lý biết tôi đang Online hay Offline. | Nên | Nhân sự |
| US08 | Với vai trò khách hàng, tôi muốn quét QR tại bàn để gọi món mà không phải chờ nhân viên ghi order. | Nên | Khách hàng (đã có trong website) |
| US09 | Với vai trò khách hàng, tôi muốn đặt bàn trước để có chỗ khi đến quán. | Có thể | Khách hàng (đã có trong website) |

**Thang MoSCoW:** *Phải* – bắt buộc để MVP dùng được; *Nên* – giá trị cao nhưng làm sau luồng cốt lõi; *Có thể* – hữu ích, chưa làm cũng không ảnh hưởng MVP. Mức ưu tiên lấy theo Product Backlog Chương 2 (Cao → Phải, Trung bình → Nên). US05 và US06 là giả thuyết thiết kế: khảo sát chưa hỏi quán có cần theo dõi chế biến hay thống kê theo nguồn hay không, cần xác minh thêm.

## BƯỚC 7 – TIÊU CHÍ CHẤP NHẬN VÀ QUY TẮC NGHIỆP VỤ

- **US01:** Given chưa đăng nhập, When mở trang quản lý, Then được chuyển đến trang đăng nhập. Given đăng nhập bằng tài khoản Nhân viên, When mở trang chỉ dành cho Quản lý, Then hệ thống từ chối truy cập. Given email đã có tài khoản, When đăng ký lại, Then báo lỗi và không tạo trùng.
- **US02:** Given đã đăng nhập, When nhập tên món và giá hợp lệ rồi lưu, Then món xuất hiện trong thực đơn. Given tên trống hoặc giá âm, When lưu, Then báo lỗi và không lưu. Given giá món vừa đổi, Then hóa đơn cũ vẫn giữ giá tại lúc gọi.
- **US03:** Given thực đơn có món, When chọn nhiều món với số lượng từ 1 đến 99 cùng nguồn đơn rồi lưu, Then đơn lưu đủ món, đúng nguồn và tổng tiền do máy chủ tính từ giá chốt. Given chưa chọn món hoặc số lượng ngoài khoảng cho phép, Then báo lỗi và không lưu. Given thanh toán chuyển khoản, Then khoản đó ở trạng thái chờ xác nhận cho đến khi nhân viên xác nhận.
- **US04:** Given có đơn từ QR tại bàn, đặt bàn trước và tại quầy, When mở danh sách, Then mỗi thẻ đơn hiển thị đúng nguồn. When lọc theo nguồn, ngày hoặc trạng thái thanh toán, Then chỉ đơn khớp điều kiện xuất hiện. Given chưa có đơn, Then hiện trạng thái rỗng thay vì lỗi. Đơn cũ chưa có nguồn vẫn hiển thị với giá trị mặc định.
- **US05:** Given món ở trạng thái Mới, When chuyển sang Đang làm rồi Đã xong, Then trạng thái được lưu và vẫn đúng sau khi tải lại. Given mọi món của đơn đã xong, Then đơn hiển thị Đã xong. Khi lưu thất bại, hệ thống báo lỗi và không hiển thị trạng thái giả.
- **US06:** Given ngày có 10 đơn gồm 4 QR tại bàn, 3 đặt bàn trước và 3 tại quầy, When xem bảng điều khiển, Then số đơn hiển thị 4/3/3 và tổng doanh thu theo nguồn bằng doanh thu cả ngày. Given ngày chưa có đơn, Then hiện thông báo chưa có dữ liệu.
- **US07:** Given nhân viên đang Offline, When Check-in, Then trạng thái là Online và lưu giờ vào. Given đang Online, When Check-in lần nữa, Then báo lỗi và không tạo bản ghi trùng.

**Bảng quy tắc nghiệp vụ cốt lõi**

| Quy tắc | Nội dung | Tình trạng |
|---|---|---|
| Số lượng món | Mỗi dòng món có số lượng từ 1 đến 99; sửa về 0 là xóa món | Đã có trong website |
| Giá chốt | Đơn giá lấy từ thực đơn tại lúc gọi và lưu trong chi tiết hóa đơn; tổng tiền bằng tổng số lượng nhân đơn giá, tính ở máy chủ | Đã có trong website |
| Thanh toán | Chỉ có hai hình thức: tiền mặt hoặc chuyển khoản. Hóa đơn phải có tổng tiền lớn hơn 0; số tiền mỗi lần trả là số nguyên đồng từ 1 đến số còn lại | Đã có trong website |
| Chuyển khoản | Khoản khách báo đã chuyển ở trạng thái chờ xác nhận; nhân viên xác nhận hoặc từ chối | Đã có trong website |
| Đóng hóa đơn | Trả đủ thì hóa đơn chuyển sang “Đã thanh toán”, không sửa món hay thanh toán thêm; hệ thống trừ kho theo công thức món | Đã có trong website |
| Hủy hóa đơn | Chỉ hủy được hóa đơn chưa thu đồng nào; hóa đơn đã hủy không có khoản thu nên không vào doanh thu | Đã có trong website |
| Không giảm dưới số đã trả | Không được sửa món làm tổng tiền thấp hơn số khách đã trả | Đã có trong website |
| Một thu ngân tại một thời điểm | Mỗi lúc chỉ một người được sửa hoặc thanh toán hóa đơn để tránh thu thừa tiền | Đã có trong website |
| Đặt bàn | Nhận đặt từ 10:00 đến 21:00, mỗi 30 phút; giữ bàn 2 giờ; đặt trước ít nhất 30 phút và tối đa 30 ngày; tối đa 20 người; mỗi khách giữ tối đa 5 lịch | Đã có trong website |
| Nguồn đơn | Gồm Tại quầy, QR tại bàn, Đặt bàn trước; mọi luồng tạo đơn đều gán nguồn; đơn cũ không có nguồn hiển thị giá trị mặc định | Kế hoạch Sprint 3–4 |
| Trạng thái chế biến | Mới → Đang làm → Đã xong; đơn là Đã xong khi mọi món đã xong | Kế hoạch Sprint 4 |

## BƯỚC 8 – TỪ CÂU CHUYỆN NGƯỜI DÙNG ĐẾN TÍNH NĂNG

- **I1 (Order từ nhiều kênh):** liên kết US03, US04, US05, US06, US08 → màn hình lập đơn (POS) có cột nguồn đơn, danh sách thẻ đơn có bộ lọc theo nguồn, trạng thái chế biến, thống kê số đơn và doanh thu theo nguồn, đơn tự gán nguồn khi khách quét QR.
- **I2 (Thực đơn và giá):** liên kết US02 → quản lý thực đơn, danh mục và giá món; giá chốt trong chi tiết hóa đơn.
- **I3 (Dùng chung, có phân quyền):** liên kết US01, US09 → đăng nhập theo vai trò Quản lý, Nhân viên, Khách hàng; đặt bàn trước của khách tạo ra nguồn đơn “Đặt bàn trước”.
- **Ngoài ba vấn đề trên:** US07 (chấm công) hỗ trợ quản lý nhân sự, chưa có bằng chứng từ khảo sát nên xếp mức Nên và làm sau cùng.

## BƯỚC 9 – PRODUCT BACKLOG VÀ KẾ HOẠCH SPRINT

### 9.1. Phiên bản Product Backlog đầu tiên

| Thứ tự | ID | Hạng mục | Ưu tiên | Lý do | Dự kiến Sprint |
|---|---|---|---|---|---|
| 1 | US01 | Đăng ký, đăng nhập, thông tin quán, phân quyền | Phải | Nền tảng để mỗi vai trò dùng đúng chức năng và có dữ liệu riêng | Sprint 1 |
| 2 | US02 | Quản lý thực đơn và giá món | Phải | Không có món thì không lập được đơn | Sprint 2 |
| 3 | US03 | Màn hình lập đơn (POS), nguồn đơn và thanh toán | Phải | Giải quyết trực tiếp vấn đề I1 và là chức năng được chọn nhiều nhất (2/4) | Sprint 3 |
| 4 | US04 | Danh sách thẻ đơn và bộ lọc theo nguồn | Phải | Là chỗ “gom” order về một danh sách | Sprint 4 |
| 5 | US05 | Trạng thái chế biến | Phải | Biết đơn hoặc món nào còn phải làm | Sprint 4 |
| 6 | US06 | Thống kê đơn và doanh thu theo nguồn | Nên | Dùng lại dữ liệu đơn; cần xác minh nhu cầu | Sprint 5 |
| 7 | US07 | Chấm công Check-in/Check-out | Nên | Hỗ trợ quản lý nhân sự, không chặn chức năng khác | Sprint 5 |
| 8 | US08 | Khách quét QR gọi món tại bàn | Nên | Đã có trong website; Sprint 3–4 gán nguồn tự động, Sprint 5 kiểm thử hồi quy | Sprint 3–5 |
| 9 | US09 | Khách đặt bàn trước | Có thể | Đã có trong website; Sprint 4 gán nguồn “Đặt bàn trước”, Sprint 5 kiểm thử hồi quy | Sprint 4–5 |
| 10 | KT-01 | Sửa lỗi và kiểm thử hồi quy các luồng chính | Phải | Chỉ làm khi các chức năng nghiệp vụ đã ổn định | Sprint 5 |
| 11 | KT-02 | Hướng dẫn sử dụng và chuẩn bị bàn giao | Phải | Sản phẩm cần tài liệu để bàn giao và vấn đáp | Sprint 5 |

Chưa đưa vào Backlog: quản lý nguyên liệu, kho, công thức mở rộng và báo cáo nâng cao (0/4 quán chọn); tích hợp tự động với Zalo, Grab, ShopeeFood (chưa xác minh khả năng kết nối); nhu cầu “Khác” (1/4, chưa nêu nội dung). Ở bản MVP, order từ Zalo và app giao đồ ăn chưa có nguồn riêng; nếu cần, thêm hai nguồn này là phần mở rộng.

### 9.2. Kế hoạch phát triển sản phẩm (5 Sprint)

| Sprint | Phạm vi | Increment có thể kiểm tra |
|---|---|---|
| Sprint 1 | Tài khoản, phân quyền và dữ liệu quán (US01) | Đăng nhập theo vai trò; trang quản lý được bảo vệ; kiểm thử đúng/sai |
| Sprint 2 | Thực đơn và giá món (US02) | Thêm, sửa, xóa món; kiểm tra tên và giá; hóa đơn cũ giữ giá |
| Sprint 3 | Màn hình POS, nguồn đơn và thanh toán (US03, US08) | Lập đơn nhiều món trên một màn hình, lưu đúng nguồn và tổng tiền, thanh toán tiền mặt hoặc chuyển khoản QR |
| Sprint 4 | Danh sách thẻ đơn, bộ lọc nguồn và trạng thái chế biến (US04, US05, US09) | Xem mọi đơn trong một danh sách, lọc theo nguồn, đổi trạng thái chế biến và giữ nguyên sau khi tải lại |
| Sprint 5 | Thống kê, chấm công, kiểm thử và bàn giao (US06, US07, KT-01, KT-02) | Số đơn và doanh thu theo nguồn; trạng thái Online/Offline; biên bản kiểm thử hồi quy; hướng dẫn sử dụng |

### 9.3. Đối chiếu với website hiện có

| Khả năng | Tình trạng trong website | Việc còn lại |
|---|---|---|
| Đăng nhập, phân quyền Quản lý, Nhân viên, Khách hàng | Đã có | Cô lập dữ liệu nhiều quán chưa làm |
| Thực đơn và giá chốt trong chi tiết hóa đơn | Đã có | Kiểm thử theo tiêu chí US02 |
| Hóa đơn, thanh toán tiền mặt/chuyển khoản, xác nhận chuyển khoản, hủy, trừ kho | Đã có | Cần màn hình lập đơn một lần nhiều món (Sprint 3) |
| QR gọi món tại bàn, đặt bàn trước | Đã có | Gán nguồn tự động (Sprint 3–4) |
| Danh sách hóa đơn lọc theo ngày và trạng thái | Đã có | Thẻ đơn và lọc theo nguồn (Sprint 4) |
| Nguồn đơn, trạng thái chế biến | Chưa có | Sprint 3 và Sprint 4 |
| Thống kê theo nguồn, chấm công | Chưa có | Sprint 5 |
| Tích hợp tự động Zalo, Grab, ShopeeFood | Chưa có, ngoài phạm vi MVP | Xem lại sau khi xác minh khả năng kết nối |

## BƯỚC 10 – KẾ HOẠCH KIỂM THỬ

**Mục tiêu:** chứng minh mỗi User Story (US01–US09) đạt đúng Tiêu chí chấp nhận (Bước 7) và Quy tắc nghiệp vụ, trước khi bàn giao ở Sprint 5. Mỗi test case đều truy vết được về một User Story.

### 10.1. Phạm vi kiểm thử

| Nội dung | Mô tả |
|---|---|
| Trong phạm vi | US01–US09, các quy tắc nghiệp vụ ở Bước 7, kiểm thử hồi quy các luồng đã có (đăng nhập, thực đơn, hóa đơn, thanh toán, QR, đặt bàn) |
| Ngoài phạm vi | Tích hợp tự động Zalo, Grab, ShopeeFood; nguyên liệu/kho nâng cao; cô lập dữ liệu nhiều quán; kiểm thử tải lớn |
| Loại kiểm thử | Chức năng (hộp đen), kiểm thử giá trị biên, kiểm thử phân quyền, kiểm thử hồi quy |
| Môi trường | ASP.NET Core MVC, Entity Framework Core, SQL Server; trình duyệt Chrome (bản mới nhất); dữ liệu mẫu riêng, không dùng dữ liệu thật |
| Tài khoản mẫu | 1 Quản lý, 1 Nhân viên, 1 Khách hàng; thực đơn mẫu ≥ 5 món; ≥ 3 bàn |
| Người thực hiện | Các thành viên Nhóm 1; mỗi Sprint do thành viên không viết chức năng đó kiểm thử chéo |

### 10.2. Tiêu chí bắt đầu, kết thúc và mức độ lỗi

| Hạng mục | Quy định |
|---|---|
| Bắt đầu kiểm thử | Chức năng đã hoàn thành trong Sprint, chạy được trên môi trường kiểm thử, có dữ liệu mẫu |
| Kết thúc Sprint | 100% test case mức Cao ở trạng thái Pass; không còn lỗi Nghiêm trọng/Cao chưa sửa |
| Chấp nhận bàn giao | Tối thiểu 95% test case Pass; mọi lỗi tồn đọng có ghi chú và người phụ trách |
| Nghiêm trọng | Mất dữ liệu, sai tiền, vượt quyền truy cập, hệ thống không dùng được |
| Cao | Chức năng chính sai kết quả nhưng có cách khắc phục tạm |
| Trung bình | Sai thông báo, sai bộ lọc, lỗi hiển thị không ảnh hưởng dữ liệu |
| Thấp | Lỗi giao diện nhỏ, chính tả |

**Quy ước cột trong bảng test case**
- **Kết quả thực tế:** ghi lại những gì hệ thống làm. Các kết quả hiện có được lấy bằng **kiểm thử tĩnh**: đối chiếu từng test case với mã nguồn website (`test.zip`: controller, model, view). Chưa chạy trên trình duyệt và SQL Server, nên cần chạy lại các test case trước khi bàn giao.
- **Người kiểm thử:** thành viên chịu trách nhiệm chạy test case và ghi kết quả (xem phân công ở 10.3).
- **Trạng thái:** chỉ có hai giá trị: **Pass** (kết quả thực tế khớp kết quả mong đợi) hoặc **Chưa pass** (chưa chạy, hoặc chạy nhưng kết quả khác mong đợi). Mặc định là *Chưa pass*; chỉ đổi sang *Pass* sau khi đã điền kết quả thực tế. Nếu chạy mà sai, giữ *Chưa pass* và ghi mã lỗi ở mục 10.6.

### 10.3. Danh sách kịch bản kiểm thử (Test Scenario)

| Mã KB | Kịch bản | User Story | Sprint | Số TC |
|---|---|---|---|---|
| KB01 | Đăng ký, đăng nhập và phân quyền | US01 | 1 | 7 |
| KB02 | Quản lý thực đơn và giá món | US02 | 2 | 6 |
| KB03 | Lập đơn tại quầy (POS) | US03 | 3 | 6 |
| KB04 | Thanh toán và đóng/hủy hóa đơn | US03 | 3 | 10 |
| KB05 | Danh sách thẻ đơn và bộ lọc | US04 | 4 | 6 |
| KB06 | Trạng thái chế biến | US05 | 4 | 4 |
| KB07 | Thống kê đơn và doanh thu theo nguồn | US06 | 5 | 4 |
| KB08 | Chấm công Check-in/Check-out | US07 | 5 | 4 |
| KB09 | Khách quét QR gọi món | US08 | 3–5 | 3 |
| KB10 | Khách đặt bàn trước | US09 | 4–5 | 7 |
| | **Tổng** | | | **57** |

### 10.3b. Phân công người kiểm thử

Nguyên tắc: người kiểm thử **không phải người viết chức năng đó** (kiểm thử chéo) để tránh bỏ sót lỗi do quen tay. Bảng dưới là phân công mặc định chia đều 19 test case cho mỗi người; nếu thành viên nào viết chức năng được giao, hoán đổi với người khác trong nhóm.

| Người kiểm thử | Kịch bản phụ trách | Số TC | Tỷ lệ |
|---|---|---|---|
| Phạm Tiến Sơn | KB02 (Thực đơn), KB04 (Thanh toán), KB09 (QR gọi món) | 19 | 33,3% |
| Nguyễn Nhật Tân | KB01 (Tài khoản, phân quyền), KB03 (Lập đơn POS), KB05 (Thẻ đơn, bộ lọc) | 19 | 33,3% |
| Đỗ Anh Tài | KB06 (Chế biến), KB07 (Thống kê), KB08 (Chấm công), KB10 (Đặt bàn trước) | 19 | 33,3% |
| **Tổng** | | **57** | 100% |

### 10.4. Chi tiết test case

*Mức ưu tiên: C = Cao, TB = Trung bình, T = Thấp.*

#### KB01 – Đăng ký, đăng nhập và phân quyền (US01)
**Tiền điều kiện chung:** đã có tài khoản Quản lý, Nhân viên, Khách hàng trong cơ sở dữ liệu.

| Mã TC | Mô tả và dữ liệu | Các bước thực hiện | Kết quả mong đợi | Kết quả thực tế | Ưu tiên | Người kiểm thử | Trạng thái |
|---|---|---|---|---|---|---|---|
| TC01-01 | Đăng nhập đúng tài khoản Quản lý | 1. Mở trang đăng nhập<br>2. Nhập email, mật khẩu đúng<br>3. Bấm Đăng nhập | Vào được trang quản lý; hiển thị đúng tên và vai trò | Đăng nhập nhân viên/quản lý bằng tài khoản + mật khẩu đúng thì vào trang Quản trị (AccountController.Login); hiển thị đúng tên và vai trò (Quản lý), vai trò lấy từ chức vụ. | C | Tân | Pass |
| TC01-02 | Đăng nhập sai mật khẩu | 1. Nhập email đúng, mật khẩu sai<br>2. Bấm Đăng nhập | Báo lỗi đăng nhập; ở lại trang đăng nhập; không tiết lộ email hay mật khẩu sai | Báo “Sai tài khoản hoặc mật khẩu”, ở lại trang đăng nhập; dùng chung 1 thông báo nên không lộ tài khoản nào tồn tại. | C | Tân | Pass |
| TC01-06 | Đăng ký tài khoản hợp lệ | 1. Mở trang đăng ký<br>2. Nhập email chưa dùng, mật khẩu hợp lệ, thông tin quán<br>3. Bấm Đăng ký | Tạo tài khoản thành công; đăng nhập được bằng tài khoản vừa tạo | Khách hàng đăng ký bằng họ tên + SĐT + mật khẩu và tự đăng nhập. Chưa có đăng ký chủ quán bằng email và chưa có bước khai báo thông tin quán như US01 (xem BUG-01). | C | Tân | Chưa pass |
| TC01-07 | Đăng ký bằng email đã tồn tại | 1. Nhập email đã có tài khoản<br>2. Bấm Đăng ký | Báo lỗi email đã được dùng; không tạo tài khoản trùng | Hệ thống chỉ chặn trùng SĐT (“Số điện thoại này đã được đăng ký”); email không bị kiểm tra trùng (xem BUG-01). | C | Tân | Chưa pass |

#### KB02 – Quản lý thực đơn và giá món (US02)
**Tiền điều kiện:** đăng nhập bằng tài khoản Quản lý.

| Mã TC | Mô tả và dữ liệu | Các bước thực hiện | Kết quả mong đợi | Kết quả thực tế | Ưu tiên | Người kiểm thử | Trạng thái |
|---|---|---|---|---|---|---|---|
| TC02-01 | Thêm món hợp lệ: “Cơm gà”, 45.000 | 1. Mở Quản lý thực đơn<br>2. Bấm Thêm món<br>3. Nhập tên, giá, danh mục<br>4. Lưu | Món xuất hiện trong danh sách thực đơn với đúng tên và giá | hiển thị trong danh sách thực đơn (QuanLyThucDon.Create); món “Cơm gà” xuất hiện trong danh sách với đúng tên và đúng giá 45.000 đồng. | C | Sơn | Pass |
| TC02-02 | Thêm món với tên trống | 1. Bỏ trống tên món, nhập giá 30.000<br>2. Lưu | Báo lỗi “tên món bắt buộc”; không lưu món | Tên món là trường bắt buộc nên không lưu, hiện lỗi ngay dưới ô Tên món. | C | Sơn | Pass |
| TC02-03 | Thêm món với giá âm: -5.000 | 1. Nhập tên món, giá -5.000<br>2. Lưu | Báo lỗi giá không hợp lệ; không lưu món | Báo “Giá món phải lớn hơn 0.”; không lưu. | C | Sơn | Pass |
| TC02-04 | Thêm món với giá không phải số: “abc” | 1. Nhập giá “abc”<br>2. Lưu | Báo lỗi giá không hợp lệ; không lưu món | Ô giá nhập chữ bị lỗi định dạng ở bước đọc dữ liệu; báo lỗi giá không hợp lệ và không lưu món. | TB | Sơn | Pass |
| TC02-05 | Đổi giá món, hóa đơn cũ giữ giá | 1. Lập và lưu hóa đơn có món A giá 45.000<br>2. Đổi giá món A thành 50.000<br>3. Mở lại hóa đơn cũ | Hóa đơn cũ vẫn hiển thị 45.000; hóa đơn mới dùng 50.000 | Đơn giá được lưu riêng trong chi tiết hóa đơn (DonGia) lúc gọi, nên đổi giá món không làm đổi hóa đơn cũ: hóa đơn cũ vẫn hiển thị 45.000, hóa đơn mới dùng 50.000. | C | Sơn | Pass |
| TC02-06 | Xóa món | 1. Chọn món chưa dùng trong hóa đơn<br>2. Bấm Xóa, xác nhận | Món biến mất khỏi thực đơn; không còn chọn được khi lập đơn | Món chưa nằm trong hóa đơn được xóa và biến mất khỏi thực đơn; món đã có trong hóa đơn bị chặn kèm thông báo. | TB | Sơn | Pass |

#### KB03 – Lập đơn tại quầy (US03)
**Tiền điều kiện:** đăng nhập bằng Nhân viên; thực đơn có ≥ 3 món (A = 45.000, B = 30.000, C = 20.000); có ≥ 1 bàn.

| Mã TC | Mô tả và dữ liệu | Các bước thực hiện | Kết quả mong đợi | Kết quả thực tế | Ưu tiên | Người kiểm thử | Trạng thái |
|---|---|---|---|---|---|---|---|
| TC03-01 | Chức Năng Lập đơn nhiều món, nguồn “Tại quầy”: A×2, B×1 | 1. Mở màn hình lập đơn<br>2. Chọn bàn<br>3. Thêm A (SL 2), B (SL 1)<br>4. Chọn nguồn “Tại quầy”<br>5. Lưu | Đơn lưu đủ 2 món, đúng nguồn; tổng tiền = 2×45.000 + 30.000 = 120.000 | Thêm A×2, B×1 cho tổng đúng 120.000, nhưng không có ô chọn nguồn đơn “Tại quầy” và phải thêm từng món ở trang chi tiết, không phải một màn hình (xem BUG-02, BUG-03). | C | Tân | Chưa pass |
| TC03-02 | Lưu khi chưa chọn món | 1. Mở màn hình lập đơn<br>2. Không thêm món<br>3. Bấm Lưu | Báo lỗi chưa chọn món; không tạo đơn | Chọn bàn là tạo ngay hóa đơn rỗng (tổng 0); không có nút Lưu để chặn. Chỉ chặn ở bước thanh toán “Hóa đơn chưa có món” (xem BUG-03). | C | Tân | Chưa pass |
| TC03-03 | Số lượng nhỏ nhất và lớn nhất: 1 và 99 | 1. Thêm món A SL 1, lưu<br>2. Thêm món A SL 99, lưu | Cả hai đơn lưu được; tổng tiền lần lượt 45.000 và 4.455.000 | ThemMon nhận số lượng 1–99; cả hai đơn đều lưu được: A×1 cho tổng 45.000, A×99 cho tổng 4.455.000. | C | Tân | Pass |
| TC03-04 | Số lượng ngoài khoảng: 0, 100, -1 | 1. Nhập SL 100 rồi lưu<br>2. Nhập SL -1 rồi lưu | Báo lỗi số lượng phải từ 1 đến 99; không lưu | Số lượng 0, 100, -1 đều báo “Số lượng phải từ 1 đến 99.”; không lưu. | C | Tân | Pass |
| TC03-05 | Sửa số lượng về 0 thì xóa món | 1. Thêm A, B vào đơn<br>2. Sửa SL của B về 0 | Món B bị xóa khỏi đơn; tổng tiền tính lại chỉ còn món A | DoiSoLuong với 0 thì xóa dòng món và tính lại tổng tiền. | TB | Tân | Pass |
| TC03-06 | Tổng tiền do máy chủ tính | 1. Thêm món A SL 2<br>2. Dùng công cụ nhà phát triển (F12) sửa tổng tiền hiển thị thành 1.000<br>3. Lưu | Đơn lưu với tổng 90.000 (tính lại từ giá chốt), không lấy 1.000 | Tổng tiền luôn do máy chủ tính từ đơn giá trong cơ sở dữ liệu; không nhận tổng tiền từ trình duyệt; với A×2 đơn lưu tổng 90.000, không lấy 1.000. | C | Tân | Pass |

#### KB04 – Thanh toán và đóng/hủy hóa đơn (US03)
**Tiền điều kiện:** có hóa đơn H1 tổng 120.000, chưa thanh toán; đăng nhập bằng Nhân viên/Thu ngân.

| Mã TC | Mô tả và dữ liệu | Các bước thực hiện | Kết quả mong đợi | Kết quả thực tế | Ưu tiên | Người kiểm thử | Trạng thái |
|---|---|---|---|---|---|---|---|
| TC04-01 | Trả đủ bằng tiền mặt | 1. Mở H1<br>2. Chọn Tiền mặt, nhập 120.000<br>3. Xác nhận | H1 chuyển “Đã thanh toán”; kho được trừ theo công thức món; tính vào doanh thu | Trả đủ thì hóa đơn thành “Đã thanh toán”, trừ tồn kho theo công thức và tính vào doanh thu (cùng một lần lưu). | C | Sơn | Pass |
| TC04-02 | Trả một phần: 50.000 | 1. Chọn Tiền mặt, nhập 50.000 | H1 vẫn chưa đóng; còn lại 70.000; ghi nhận khoản 50.000 | Ghi nhận 50.000, hiện “Còn lại 70.000”; hóa đơn vẫn mở. | C | Sơn | Pass |
| TC04-03 | Số tiền ngoài khoảng cho phép: 0, vượt số còn lại, 1.500,5 | 1. Nhập 0, thử trả<br>2. Nhập 200.000 khi còn 120.000<br>3. Nhập 1.500,5 | Cả ba lần báo lỗi (phải là số nguyên đồng từ 1 đến số còn lại); không ghi nhận | Số tiền ≤ 0, lớn hơn số còn lại hoặc có phần lẻ đều bị từ chối kèm số tiền còn lại. | C | Sơn | Pass |
| TC04-04 | Chuyển khoản chờ xác nhận | 1. Chọn Chuyển khoản QR, nhập 120.000<br>2. Gửi | Khoản ở trạng thái “Chờ xác nhận”; H1 chưa chuyển “Đã thanh toán” | Khách bấm “Tôi đã chuyển khoản” thì tạo khoản “Chờ xác nhận” bằng đúng số còn lại, hóa đơn chưa đóng. Lưu ý: nhân viên tự nhập chuyển khoản thì được ghi nhận ngay, nên bước kiểm thử cần theo luồng của khách. | C | Sơn | Pass |
| TC04-05 | Xác nhận chuyển khoản | 1. Mở khoản đang chờ<br>2. Bấm Xác nhận | Khoản được tính; đủ tiền thì H1 chuyển “Đã thanh toán” | Xác nhận thì khoản thành công; đủ tiền thì hóa đơn chuyển “Đã thanh toán”. | C | Sơn | Pass |
| TC04-06 | Từ chối chuyển khoản | 1. Mở khoản đang chờ<br>2. Bấm Từ chối | Khoản không được tính; H1 giữ nguyên số còn lại | Từ chối thì khoản chuyển thành thất bại, không tính vào số đã trả; H1 giữ nguyên số còn lại. | C | Sơn | Pass |
| TC04-07 | Hóa đơn đã thanh toán không sửa được | 1. Mở hóa đơn “Đã thanh toán”<br>2. Thử thêm món hoặc thanh toán thêm | Hệ thống chặn và báo lỗi; hóa đơn không đổi | Mọi thao tác sửa/thanh toán đều chặn khi hóa đơn không còn ở trạng thái chưa thanh toán (“đã đóng, không thể thay đổi”); hóa đơn giữ nguyên. | C | Sơn | Pass |
| TC04-08 | Sửa món làm tổng thấp hơn số đã trả | 1. H1 đã trả 100.000<br>2. Xóa món để tổng còn 60.000<br>3. Lưu | Báo lỗi; không lưu thay đổi | Báo “Khách đã trả … nên tổng tiền không thể thấp hơn”; không lưu. | C | Sơn | Pass |
| TC04-09 | Hủy hóa đơn chưa thu đồng nào / đã thu | 1. Hủy hóa đơn chưa thu<br>2. Thử hủy hóa đơn đã thu 50.000 | (1) Hủy được, không vào doanh thu. (2) Báo lỗi, không hủy được | Hóa đơn chưa thu thì hủy được; hóa đơn đã có thanh toán bị chặn (“không hủy được”). | C | Sơn | Pass |
| TC04-10 | Hai thu ngân cùng thanh toán một hóa đơn | 1. Hai người dùng cùng mở H1<br>2. Cả hai nhập 120.000 và xác nhận gần như cùng lúc | Chỉ một giao dịch được ghi nhận; người còn lại nhận thông báo; tổng đã thu không vượt 120.000 | Các thao tác thanh toán chạy lần lượt qua khóa SemaphoreSlim; người thứ hai gặp hóa đơn đã đóng, bị chặn và nhận thông báo; chỉ một giao dịch được ghi nhận, tổng thu không vượt 120.000. Chỉ đúng khi web chạy một tiến trình. | C | Sơn | Pass |

#### KB05 – Danh sách thẻ đơn và bộ lọc (US04)
**Tiền điều kiện:** có đơn nguồn “QR tại bàn”, “Đặt bàn trước” và “Tại quầy” ở các ngày và trạng thái thanh toán khác nhau; có 1 đơn cũ chưa có nguồn.

| Mã TC | Mô tả và dữ liệu | Các bước thực hiện | Kết quả mong đợi | Kết quả thực tế | Ưu tiên | Người kiểm thử | Trạng thái |
|---|---|---|---|---|---|---|---|
| TC05-01 | Hiển thị nguồn trên thẻ đơn | 1. Mở danh sách đơn | Mỗi thẻ hiển thị đúng nguồn của đơn đó | Danh sách hóa đơn là bảng (số bàn, khách, ngày, tổng, đã trả, trạng thái); không có thẻ đơn và không có cột nguồn (xem BUG-02). | C | Tân | Chưa pass |
| TC05-02 | Lọc theo nguồn “QR tại bàn” | 1. Chọn bộ lọc nguồn = QR tại bàn | Chỉ hiển thị đơn có nguồn QR tại bàn | Không có bộ lọc theo nguồn; chỉ lọc theo ngày và trạng thái (xem BUG-02). | C | Tân | Chưa pass |
| TC05-03 | Lọc theo ngày | 1. Chọn ngày D | Chỉ hiển thị đơn của ngày D | Lọc theo ngày trả đúng các hóa đơn lập trong ngày đó. | TB | Tân | Pass |
| TC05-04 | Lọc theo trạng thái thanh toán “Đã thanh toán” | 1. Chọn trạng thái | Chỉ hiển thị đơn đã thanh toán | Lọc theo trạng thái thanh toán hoạt động; chọn “Đã thanh toán” thì chỉ hiển thị các hóa đơn đã thanh toán; mặc định hiện “Chưa thanh toán”. | TB | Tân | Pass |
| TC05-05 | Danh sách rỗng | 1. Lọc theo điều kiện không có đơn nào | Hiện trạng thái rỗng (“Chưa có đơn”), không báo lỗi hệ thống | Hiện “Không có hóa đơn nào phù hợp.”, không báo lỗi. | TB | Tân | Pass |
| TC05-06 | Đơn cũ chưa có nguồn | 1. Mở danh sách có đơn cũ | Đơn cũ vẫn hiển thị với nguồn mặc định (không lỗi, không trống) | Chưa có khái niệm nguồn đơn nên không có giá trị mặc định cho đơn cũ (xem BUG-02). | TB | Tân | Chưa pass |

#### KB06 – Trạng thái chế biến (US05)
**Tiền điều kiện:** có đơn gồm 2 món, cả hai ở trạng thái Mới.

| Mã TC | Mô tả và dữ liệu | Các bước thực hiện | Kết quả mong đợi | Kết quả thực tế | Ưu tiên | Người kiểm thử | Trạng thái |
|---|---|---|---|---|---|---|---|
| TC06-01 | Đổi trạng thái Mới → Đang làm → Đã xong cho 1 món | 1. Đổi món 1 sang Đang làm<br>2. Đổi sang Đã xong | Trạng thái hiển thị đúng sau mỗi bước | Chưa có trạng thái chế biến (Mới/Đang làm/Đã xong) trong mã và giao diện (xem BUG-04). | C | Tài | Chưa pass |
| TC06-02 | Trạng thái giữ nguyên sau khi tải lại | 1. Đổi trạng thái<br>2. Tải lại trang (F5) | Trạng thái vẫn đúng như đã đổi | Chưa có chức năng nên không có gì để giữ lại sau khi tải lại (BUG-04). | C | Tài | Chưa pass |
| TC06-03 | Mọi món xong thì đơn “Đã xong” | 1. Đổi cả 2 món sang Đã xong | Đơn hiển thị Đã xong; trước đó (mới xong 1 món) đơn chưa Đã xong | Chưa có chức năng (BUG-04). | C | Tài | Chưa pass |
| TC06-04 | Lưu thất bại | 1. Ngắt kết nối mạng hoặc dừng cơ sở dữ liệu<br>2. Đổi trạng thái | Hiển thị thông báo lỗi; không hiển thị trạng thái giả | Chưa có chức năng (BUG-04). | TB | Tài | Chưa pass |

#### KB07 – Thống kê đơn và doanh thu theo nguồn (US06)
**Tiền điều kiện:** đăng nhập bằng Quản lý.

| Mã TC | Mô tả và dữ liệu | Các bước thực hiện | Kết quả mong đợi | Kết quả thực tế | Ưu tiên | Người kiểm thử | Trạng thái |
|---|---|---|---|---|---|---|---|
| TC07-01 | Ngày có 10 đơn: 4 QR, 3 đặt bàn, 3 tại quầy | 1. Mở bảng điều khiển, chọn ngày đó | Số đơn theo nguồn hiển thị 4/3/3 | Trang Thống kê có doanh thu theo ngày, món bán chạy, số hóa đơn; không có số đơn và doanh thu theo nguồn (xem BUG-02). | C | Tài | Chưa pass |
| TC07-02 | Tổng doanh thu theo nguồn khớp cả ngày | 1. Cộng doanh thu 3 nguồn<br>2. So với tổng doanh thu cả ngày | Hai số bằng nhau | Không có thống kê theo nguồn nên không đối chiếu được (BUG-02). | C | Tài | Chưa pass |
| TC07-03 | Ngày chưa có đơn | 1. Chọn ngày không có đơn | Hiện thông báo chưa có dữ liệu | Khoảng không có dữ liệu hiện “Chưa có khoản thu nào trong khoảng này.” | TB | Tài | Pass |
| TC07-04 | Hóa đơn đã hủy không vào doanh thu | 1. Hủy 1 hóa đơn chưa thu<br>2. Xem lại thống kê | Doanh thu không tính hóa đơn đã hủy | Doanh thu chỉ tính khoản thanh toán thành công; hóa đơn hủy chưa thu đồng nào nên không vào doanh thu. | C | Tài | Pass |

#### KB08 – Chấm công Check-in/Check-out (US07)
**Tiền điều kiện:** đăng nhập bằng Nhân viên.

| Mã TC | Mô tả và dữ liệu | Các bước thực hiện | Kết quả mong đợi | Kết quả thực tế | Ưu tiên | Người kiểm thử | Trạng thái |
|---|---|---|---|---|---|---|---|
| TC08-01 | Check-in khi đang Offline | 1. Bấm Check-in | Trạng thái chuyển Online; lưu giờ vào | Chưa có Check-in/Check-out hay trạng thái Online/Offline (xem BUG-05). | TB | Tài | Chưa pass |
| TC08-02 | Check-in khi đang Online | 1. Bấm Check-in lần nữa | Báo lỗi; không tạo bản ghi trùng | Chưa có chức năng (BUG-05). | TB | Tài | Chưa pass |
| TC08-03 | Check-out khi đang Online | 1. Bấm Check-out | Trạng thái chuyển Offline; lưu giờ ra | Chưa có chức năng (BUG-05). | TB | Tài | Chưa pass |
| TC08-04 | Quản lý thấy trạng thái nhân viên | 1. Đăng nhập Quản lý, mở danh sách nhân viên | Hiển thị đúng Online/Offline của từng người | Chưa có chức năng (BUG-05). | T | Tài | Chưa pass |

#### KB09 – Khách quét QR gọi món (US08)
**Tiền điều kiện:** có mã QR của bàn số 3 và thực đơn đang có món.

| Mã TC | Mô tả và dữ liệu | Các bước thực hiện | Kết quả mong đợi | Kết quả thực tế | Ưu tiên | Người kiểm thử | Trạng thái |
|---|---|---|---|---|---|---|---|
| TC09-01 | Quét QR, chọn món và gửi | 1. Quét QR bàn 3<br>2. Chọn món A SL 2<br>3. Gửi | Tạo đơn gắn bàn 3, nguồn “QR tại bàn”, tổng 90.000 | Quét QR → mở bàn → gửi món thì món vào hóa đơn của bàn, tổng 90.000 đúng; nhưng đơn không có nguồn “QR tại bàn” (xem BUG-02). | C | Sơn | Chưa pass |
| TC09-02 | Đơn QR hiện trong danh sách thẻ đơn | 1. Đăng nhập Nhân viên, mở danh sách đơn | Thấy thẻ đơn mới với nguồn “QR tại bàn”, trạng thái chế biến Mới | Hóa đơn QR hiện trong danh sách hóa đơn, nhưng không có nguồn và không có trạng thái chế biến (BUG-02, BUG-04). | C | Sơn | Chưa pass |
| TC09-03 | Gửi đơn QR khi chưa chọn món | 1. Quét QR, không chọn món<br>2. Gửi | Báo lỗi; không tạo đơn | Giỏ trống thì không tạo đơn; trang giỏ hiện “Giỏ món đang trống.” | TB | Sơn | Pass |

#### KB10 – Khách đặt bàn trước (US09)
**Tiền điều kiện:** đăng nhập bằng Khách hàng. Quy tắc: nhận đặt 10:00–21:00 mỗi 30 phút; đặt trước ≥ 30 phút và ≤ 30 ngày; tối đa 20 người; tối đa 5 lịch/khách. *Giả sử hiện tại là 09:00 ngày D.*

| Mã TC | Mô tả và dữ liệu | Các bước thực hiện | Kết quả mong đợi | Kết quả thực tế | Ưu tiên | Người kiểm thử | Trạng thái |
|---|---|---|---|---|---|---|---|
| TC10-01 | Đặt hợp lệ: ngày D+1, 18:00, 4 người | 1. Mở Đặt bàn<br>2. Nhập thông tin<br>3. Gửi | Đặt thành công; bàn được giữ 2 giờ | Đặt hợp lệ thì tạo lịch “Đã xác nhận”; bàn bị coi là bận trong cửa sổ 2 giờ quanh giờ đặt. | C | Tài | Pass |
| TC10-02 | Giờ ngoài khung: 09:30 và 21:30 | 1. Chọn giờ 09:30, gửi<br>2. Chọn giờ 21:30, gửi | Cả hai báo lỗi ngoài giờ nhận đặt | Giờ ngoài 10:00–21:00 báo “Giờ đặt không hợp lệ.” | C | Tài | Pass |
| TC10-03 | Giờ không đúng bước 30 phút: 18:15 | 1. Chọn 18:15, gửi | Báo lỗi hoặc không cho chọn giờ lẻ | Giờ lẻ như 18:15 không nằm trong danh sách giờ (bước 30 phút) nên bị từ chối. | TB | Tài | Pass |
| TC10-04 | Đặt sát giờ: sau hiện tại dưới 30 phút | 1. Chọn giờ cách hiện tại 20 phút, gửi | Báo lỗi phải đặt trước ít nhất 30 phút | Báo “Vui lòng đặt trước ít nhất 30 phút.” | C | Tài | Pass |
| TC10-05 | Đặt quá xa: sau 31 ngày | 1. Chọn ngày D+31, gửi | Báo lỗi vượt 30 ngày | Ngày sau 30 ngày báo “Chỉ nhận đặt bàn trong vòng 30 ngày tới.” | TB | Tài | Pass |
| TC10-06 | Số người: 20 và 21 | 1. Đặt 20 người, gửi<br>2. Đặt 21 người, gửi | (1) Thành công. (2) Báo lỗi vượt tối đa 20 người | 21 người báo lỗi (tối đa 20). 20 người hợp lệ về quy tắc, nhưng chỉ đặt được khi có bàn từ 20 chỗ trở lên trong dữ liệu. | C | Tài | Pass |
| TC10-07 | Quá 5 lịch của một khách | 1. Đặt thành công 5 lịch<br>2. Đặt lịch thứ 6 | Lịch thứ 6 bị từ chối kèm thông báo; đơn đặt hợp lệ có nguồn “Đặt bàn trước” trong danh sách thẻ đơn | Lịch thứ 6 bị từ chối đúng (“đang giữ 5 lịch”); nhưng đơn đặt bàn chưa có nguồn “Đặt bàn trước” trong danh sách đơn (BUG-02). | C | Tài | Chưa pass |

### 10.5. Ma trận truy vết và kế hoạch kiểm thử theo Sprint

| Sprint | Kịch bản kiểm thử | User Story | Số TC | Sản phẩm kiểm thử đầu ra |
|---|---|---|---|---|
| Sprint 1 | KB01 | US01 | 7 | Bảng kết quả KB01 |
| Sprint 2 | KB02 | US02 | 6 | Bảng kết quả KB02 |
| Sprint 3 | KB03, KB04, KB09 (TC09-01) | US03, US08 | 22 | Bảng kết quả KB03–KB04 |
| Sprint 4 | KB05, KB06, KB10 | US04, US05, US09 | 17 | Bảng kết quả KB05–KB06, KB10 |
| Sprint 5 | KB07, KB08, KB09; **hồi quy toàn bộ KB01–KB10** | US06, US07, KT-01 | 57 | Biên bản kiểm thử hồi quy (KT-01) |

### 10.6. Danh sách lỗi phát hiện

| Mã lỗi | Test case | Mô tả lỗi | Mức độ | Người phụ trách | Trạng thái |
|---|---|---|---|---|---|
| BUG-01 | TC01-06, TC01-07 | US01 yêu cầu chủ quán đăng ký bằng email và khai báo thông tin quán. Website chỉ có đăng ký khách hàng bằng SĐT; tài khoản nhân viên do Quản lý tạo; email không bị kiểm tra trùng | Trung bình | Nhóm 1 | Mở |
| BUG-02 | TC03-01, TC05-01, TC05-02, TC05-06, TC07-01, TC07-02, TC09-01, TC09-02, TC10-07 | Chưa có “nguồn đơn” (Tại quầy, QR tại bàn, Đặt bàn trước) nên chưa hiển thị, lọc và thống kê theo nguồn được. Đã dự kiến ở Sprint 3–5 | Cao | Nhóm 1 | Mở |
| BUG-03 | TC03-01, TC03-02 | Chưa có màn hình lập đơn một lần nhiều món; chọn bàn là tạo ngay hóa đơn rỗng, chỉ chặn ở bước thanh toán | Trung bình | Nhóm 1 | Mở |
| BUG-04 | TC06-01 đến TC06-04, TC09-02 | Chưa có trạng thái chế biến (Mới, Đang làm, Đã xong). Đã dự kiến ở Sprint 4 | Cao | Nhóm 1 | Mở |
| BUG-05 | TC08-01 đến TC08-04 | Chưa có chấm công Check-in/Check-out và trạng thái Online/Offline. Đã dự kiến ở Sprint 5 | Trung bình | Nhóm 1 | Mở |

### 10.7. Bảng tổng hợp kết quả theo kịch bản

| Kịch bản | Tổng TC | Pass | Chưa pass | Tỷ lệ Pass |
|---|---|---|---|---|
| KB01 | 7 | 5 | 2 | 71,4% |
| KB02 | 6 | 6 | 0 | 100,0% |
| KB03 | 6 | 4 | 2 | 66,7% |
| KB04 | 10 | 10 | 0 | 100,0% |
| KB05 | 6 | 3 | 3 | 50,0% |
| KB06 | 4 | 0 | 4 | 0,0% |
| KB07 | 4 | 2 | 2 | 50,0% |
| KB08 | 4 | 0 | 4 | 0,0% |
| KB09 | 3 | 1 | 2 | 33,3% |
| KB10 | 7 | 6 | 1 | 85,7% |
| **Tổng** | **57** | **37** | **20** | **64,9%** |

### 10.8. Tổng hợp theo người kiểm thử

| Người kiểm thử | Tổng TC | Pass | Chưa pass | Tỷ lệ Pass |
|---|---|---|---|---|
| Phạm Tiến Sơn | 19 | 17 | 2 | 89,5% |
| Nguyễn Nhật Tân | 19 | 12 | 7 | 63,2% |
| Đỗ Anh Tài | 19 | 8 | 11 | 42,1% |
| **Tổng** | **57** | **37** | **20** | **64,9%** |

**Nhận xét kết quả:** 37/57 test case Pass (64,9%). Toàn bộ phần website đã có (đăng nhập, phân quyền, thực đơn, hóa đơn, thanh toán, chuyển khoản, đặt bàn, QR) đạt yêu cầu. 20 test case Chưa pass đều thuộc phần chưa phát triển theo kế hoạch Sprint 3–5 (nguồn đơn, thẻ đơn, trạng thái chế biến, thống kê theo nguồn, chấm công) hoặc lệch tiêu chí US01 (BUG-01). Các kết quả trên là kiểm thử tĩnh trên mã nguồn; cần chạy thực tế để xác nhận lại, đặc biệt các test case về xử lý đồng thời (TC04-10) và dữ liệu bàn (TC10-06).

## KẾT LUẬN

Qua khảo sát 4 quán ăn thuộc bốn loại hình, nhóm xác định nhu cầu cốt lõi của FoodSync: có một danh sách chung để theo dõi order đến từ nhiều kênh (2/4 quán), có nơi quản lý thực đơn và giá món (1/4) và dùng được cho nhiều loại quán, có phân quyền. Cả 4/4 quán đều muốn có công cụ quản lý quán dễ dùng.

Nhu cầu này được chuyển thành 9 User Story có thang ưu tiên MoSCoW, kèm tiêu chí chấp nhận kiểm tra được và các quy tắc nghiệp vụ lấy từ chính website của nhóm. Product Backlog xếp I1 làm trọng tâm và trải qua 5 Sprint, mỗi Sprint cho ra một Increment chạy được: tài khoản, thực đơn, lập đơn có nguồn, danh sách đơn có lọc và trạng thái chế biến, rồi thống kê, kiểm thử và bàn giao.

Báo cáo phân biệt rõ phần website đã có (đăng nhập, thực đơn, hóa đơn, thanh toán, QR gọi món, đặt bàn) với phần cần phát triển (nguồn đơn, trạng thái chế biến, thống kê theo nguồn, chấm công). Hạn chế lớn nhất là cỡ mẫu 4 phản hồi; các giả thuyết về trạng thái chế biến và thống kê theo nguồn cần được xác minh bằng phỏng vấn thực tế trước khi chốt phạm vi.
