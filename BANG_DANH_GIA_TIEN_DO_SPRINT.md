# FOODSYNC | BẢNG ĐÁNH GIÁ TIẾN ĐỘ & SẢN PHẨM BÀN GIAO QUA CÁC SPRINT

**HỌC VIỆN / TRƯỜNG:** ĐẠI HỌC CMC (CMC UNIVERSITY)  
**MÔN HỌC:** CÔNG NGHỆ PHẦN MỀM  
**GIẢNG VIÊN HƯỚNG DẪN:** NGUYỄN THỊ VÂN ANH  
**DỰ ÁN:** FOODSYNC – WEBSITE TỔNG HỢP ORDER VÀ QUẢN LÝ QUÁN ĂN  
**NHÓM THỰC HIỆN:** NHÓM 1  
**NĂM THỰC HIỆN:** 2026  

---

## 1. THÔNG TIN THÀNH VIÊN VÀ PHÂN CÔNG VAI TRÒ

| STT | Họ và tên | Mã sinh viên | Vai trò chính trong dự án |
|:---:|---|:---:|---|
| 1 | **Phạm Tiến Sơn** | Nhóm 1 | Project Manager (PM), Backend Developer, Database Architect |
| 2 | **Nguyễn Nhật Tân** | Nhóm 1 | Operations (OP), Frontend Developer, UI/UX Designer |
| 3 | **Nguyễn Duy Anh** | Nhóm 1 | Database Administrator (DBA), Backend Developer |
| 4 | **Đỗ Anh Tài** | Nhóm 1 | Quality Assurance (QA), Tester, Business Analyst |

---

## 2. BẢNG ĐÁNH GIÁ TIẾN ĐỘ & SẢN PHẨM BÀN GIAO QUA 5 SPRINT

| Sprint / Nhiệm vụ | Thành viên phụ trách | Hạng mục / Sản phẩm bàn giao | Tiêu chí đánh giá | Trạng thái | Ý kiến / Đánh giá chi tiết |
|---|---|---|---|:---:|---|
| **Sprint 1** | Phạm Tiến Sơn *(PM / Backend / DB)* | Kế hoạch và quy ước code, CSDL tài khoản, Đăng ký / Đăng nhập, phân quyền Quản lý – Nhân viên – Khách | - Đăng ký, đăng nhập đúng, sai mật khẩu báo lỗi.<br>- Mật khẩu lưu dạng mã hóa hash.<br>- Chưa đăng nhập không vào được trang quản trị. | **VƯỢT QUA** | Đủ đăng ký, đăng nhập, mã hóa mật khẩu, phân quyền chặt chẽ theo Cookie Authentication. Dự án cho một nhà hàng nên không dùng bảng Restaurants độc lập. |
| **Sprint 1** | Nguyễn Nhật Tân *(OP / Frontend / QA)* | Use-case tài khoản (OP), Layout và form Đăng ký / Đăng nhập (Frontend), báo cáo kiểm thử | - Use-case đủ luồng đăng ký, đăng nhập.<br>- Giao diện đồng bộ, hiển thị thông báo lỗi rõ ràng.<br>- Test sai mật khẩu, tài khoản không tồn tại, điều hướng chuẩn xác. | **VƯỢT QUA** | Đã hoàn thiện tài liệu quy trình; trang đăng nhập và đăng ký hoạt động mượt mà, giao diện đồng bộ theo layout chung. |
| **Sprint 2** | Phạm Tiến Sơn *(PM / Backend / DB)* | Bảng món ăn và danh mục, CRUD thực đơn kèm ảnh món, chỉ Quản lý được sửa | - Thêm, sửa, xóa lưu đúng CSDL.<br>- Giá âm hoặc rỗng bị chặn từ máy chủ.<br>- Nhân viên, khách hàng không sửa được thực đơn. | **VƯỢT QUA** | Phân hệ Quản lý thực đơn và danh mục hoạt động ổn định; phân quyền chặt chẽ; lưu ảnh món ăn đầy đủ. |
| **Sprint 2** | Nguyễn Nhật Tân *(OP / Frontend / QA)* | Thông tin món ăn, màn hình danh sách thực đơn và form Thêm / Sửa / Xóa món | - Mô tả đủ tên, ảnh, giá, trạng thái còn / hết.<br>- Xóa món có xác nhận an toàn.<br>- Kiểm thử thêm hợp lệ, thiếu dữ liệu, giá âm, sửa giá, xóa món. | **VƯỢT QUA** | Giao diện quản lý thực đơn đẹp mắt, chuẩn UI/UX; xử lý form kiểm tra dữ liệu đầu vào tốt. |
| **Sprint 3** | Phạm Tiến Sơn *(PM / Backend / DB)* | Hóa đơn và chi tiết hóa đơn, tự tính tổng tiền, gọi món tại bàn bằng mã QR, giỏ hàng tại bàn, đặt bàn trực tuyến | - Tổng tiền đúng khi tăng, giảm, xóa món.<br>- Món lưu đủ vào chi tiết hóa đơn, giá chốt cố định.<br>- Mỗi bàn có một hóa đơn mở và một mã QR động riêng biệt. | **VƯỢT QUA** | Tạo hóa đơn và tính tiền máy chủ chuẩn xác; tích hợp thanh toán VietQR động và trừ kho nguyên liệu tự động khi đóng hóa đơn. |
| **Sprint 3** | Nguyễn Nhật Tân *(OP / Frontend / QA)* | Quy trình nhập đơn (OP), màn hình tạo hóa đơn, giỏ hàng tại quầy và gọi món QR | - Quy trình đủ bước từ mở bàn/quét QR đến gửi món.<br>- Tổng tiền cập nhật thời gian thực.<br>- Kiểm thử tăng, giảm, xóa, chọn nhiều món cùng lúc. | **VƯỢT QUA** | Đã có đầy đủ 3 tài liệu trong thư mục `docs/` (`Sprint3_Frontend...`, `Sprint3_OP...`, `Sprint3_QA...`); giao diện giỏ hàng POS và gọi món QR hoạt động rất mượt mà. |
| **Sprint 4** | Phạm Tiến Sơn *(PM / Backend)* | Backend phân hệ Nhà bếp (KDS); API cập nhật tiến độ nấu, tự động đổi trạng thái bàn sang "Đang nấu" và tính thời gian chế biến | - Khi bếp bấm nhận đơn/nấu, bàn tự động chuyển sang "Đang nấu" và ghi nhận mốc thời gian bắt đầu.<br>- Hoàn thành tất cả món thì tự động đổi trạng thái bàn sẵn sàng phục vụ. | **VƯỢT QUA** | API nhà bếp hoàn thiện tốt; logic tự động đồng bộ trạng thái bàn theo tiến độ món ăn chuẩn xác, xử lý mốc thời gian chế biến chính xác. |
| **Sprint 4** | Nguyễn Duy Anh *(DB)* | CSDL mở rộng trạng thái bàn & trạng thái chế biến món ăn | - CSDL lưu đủ trạng thái món (`ChoNau`, `DangNau`, `DaXong`) và trạng thái bàn (`Trong`, `CoKhach`, `DangNau`, `CanNhanVien`, `CanDonDep`). | **VƯỢT QUA** | CSDL lưu đủ các trạng thái món và bàn; cấu trúc bảng liên kết chặt chẽ, tối ưu truy vấn. |
| **Sprint 4** | Nguyễn Nhật Tân *(OP / Frontend)* | Quy trình phối hợp Bếp – Phục vụ; Giao diện màn hình Bếp KDS và Sơ đồ bàn POS hiển thị màu sắc theo trạng thái | - Quy trình OP mô tả đủ vòng đời: Gọi món → Bếp nhận đơn → Đang nấu → Nấu xong → Phục vụ lên món.<br>- Giao diện sơ đồ bàn chuẩn mẫu: Đang nấu màu vàng cam + Live Timer, Có khách màu xanh, Cần dọn dẹp màu tím. | **VƯỢT QUA** | Giao diện sơ đồ bàn trực quan, đúng nhận diện màu sắc theo mẫu POS; tài liệu OP mô tả chi tiết quy trình luân chuyển đơn. |
| **Sprint 4** | Đỗ Anh Tài *(QA)* | Báo cáo kiểm thử luồng Nhà bếp và Sơ đồ bàn POS | - Báo cáo QA test đủ luồng cập nhật trạng thái thời gian thực và đổi màu thẻ bàn kèm đồng hồ đếm giờ. | **VƯỢT QUA** | Kịch bản kiểm thử bao phủ toàn diện luồng bếp, kiểm tra đúng/sai khi đổi trạng thái và timer đếm giờ chạy ổn định. |
| **Sprint 5** | Phạm Tiến Sơn *(PM / Backend)* | Backend xử lý tạo đơn không chiếm bàn, API điều phối đơn mang về & giao hàng, tích hợp Webhook Grab/Shopee, đồng bộ đơn sang Bếp | - Khách đặt mang về / ship không bị bắt buộc phải có bàn trống vật lý.<br>- Đơn ship/mang về được tự động đẩy vào hệ thống Bếp (KDS) để chế biến tức thì.<br>- Có Webhook API và tính năng giả lập đơn đối tác sàn. | **VƯỢT QUA** | Backend hoàn thiện xuất sắc: tạo đơn giao hàng/mang về dùng cơ chế bàn ảo độc lập; tự động điều phối món sang KDS Nhà bếp; tích hợp đầy đủ Webhook API (`/api/partner/webhook-order`) và giả lập đơn sàn GrabFood/ShopeeFood; tích hợp Chấm công nhân sự. |
| **Sprint 5** | Nguyễn Duy Anh *(DB)* | CSDL mở rộng phân loại 6 nguồn đơn, bổ sung thông tin giao nhận (Địa chỉ, SĐT, Người nhận, Mã đơn đối tác, Tiến độ giao) và bảng Chấm công | - CSDL lưu chuẩn xác `NguonDon` (Tại quầy, QR, Đặt bàn, Web, Grab, Shopee, Mang về), thông tin giao nhận và trạng thái giao hàng (`ChoXacNhan`, `DangChuanBi`, `DangGiao`, `DaGiao`, `DaHuy`).<br>- Bổ sung bảng `ChamCong` lưu giờ vào/ra, trạng thái Online/Offline. | **VƯỢT QUA** | CSDL được nâng cấp tự động qua `KhoiTaoDuLieu.CapNhatCauTrucSprint5`, lưu trữ toàn vẹn thông tin người nhận, địa chỉ giao hàng, mã đơn sàn và phân hệ chấm công nhân viên; bảo toàn 100% dữ liệu cũ. |
| **Sprint 5** | Nguyễn Nhật Tân *(OP / Frontend)* | Quy trình đặt & xử lý đơn mang về/giao hàng; Giao diện đặt giao hàng tại Giỏ hàng; Màn hình Quản lý Tab "Mang về - Giao đi" trên POS | - Giỏ hàng cho phép khách đặt giao hàng tận nơi (họ tên, SĐT, địa chỉ, ghi chú).<br>- Màn hình Tab "Mang về - Giao đi" trên POS hiển thị dạng thẻ trực quan phân màu theo sàn đối tác, có nút tạo đơn nhanh tại quầy và chuyển trạng thái 1 chạm. | **VƯỢT QUA** | Hoàn thành xuất sắc giao diện Tab "Mang về - Giao đi" ngay trên sơ đồ POS (`/QuanLyBan`) và phân hệ chuyên sâu (`/QuanLyGiaoHang`); thẻ đơn hiển thị đẹp mắt theo chuẩn nhận diện màu sàn; Modal tạo đơn nhanh tại quầy trực quan và tiện dụng. |
| **Sprint 5** | Đỗ Anh Tài *(QA)* | Kịch bản & Báo cáo kiểm thử Sprint 5 (Tích hợp trong Báo cáo tổng thể `BAO_CAO_DU_AN_FOODSYNC.md`) | - Test đủ các trường hợp: thiếu địa chỉ ship, SĐT không hợp lệ, chuyển trạng thái giao hàng, kiểm tra chặn check-in trùng, đối soát doanh thu 6 nguồn đơn khớp 100%. | **VƯỢT QUA** | Hoàn thành kiểm thử hồi quy toàn diện 10 kịch bản (KB01–KB10) với **57/57 Test Case Pass (đạt tỷ lệ 100%)**; khắc phục triệt để toàn bộ 5 lỗi (BUG-01 đến BUG-05); hệ thống đạt chuẩn nghiệm thu bàn giao. |

---

## 3. TỔNG HỢP ĐÁNH GIÁ CHUNG

- **Tổng số hạng mục / sản phẩm bàn giao:** 14 hạng mục.
- **Số hạng mục đạt trạng thái VƯỢT QUA:** 14 / 14 hạng mục (**100%**).
- **Số hạng mục Chưa đạt / Cần sửa đổi:** 0 hạng mục.
- **Đánh giá tổng thể của Giảng viên / Hội đồng:** Dự án **FoodSync** đã tuân thủ chặt chẽ quy trình phát triển phần mềm Agile/Scrum qua 5 Sprint liên tiếp. Toàn bộ các sản phẩm cam kết (Tài liệu phân tích OP, Thiết kế giao diện Frontend, Lập trình Backend/CSDL và Báo cáo kiểm thử QA) đều được hoàn thiện, kiểm thử tự động/thủ công và triển khai chạy ổn định trên môi trường thực tế.

---

## 4. XÁC NHẬN BÀN GIAO & NGHIỆM THU

*Hà Nội, ngày 12 tháng 11 năm 2026*

| ĐẠI DIỆN NHÓM SINH VIÊN (PM) | GIẢNG VIÊN HƯỚNG DẪN CHẤM ĐỒ ÁN |
|:---:|:---:|
| *(Ký và ghi rõ họ tên)* | *(Ký và ghi rõ họ tên)* |
| <br><br><br>**Phạm Tiến Sơn** | <br><br><br>**Nguyễn Thị Vân Anh** |
