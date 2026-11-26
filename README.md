# FoodSync (PrimeViet) — Hệ thống tổng hợp đơn hàng đa kênh và quản lý nhà hàng

> **Học phần:** Công nghệ phần mềm (`INFO2005` – 4 tín chỉ) — Trường Đại học CMC  
> **Giảng viên hướng dẫn:** Nguyễn Thị Vân Anh  
> **Nhóm thực hiện:** Nhóm 1 (Phạm Tiến Sơn – Nhóm trưởng/PM, Nguyễn Nhật Tân, Nguyễn Duy Anh, Đỗ Anh Tài)

---

## 1. Giới thiệu & Tầm nhìn sản phẩm (Product Vision)

**FoodSync (PrimeViet)** là ứng dụng web quản lý nhà hàng đa kênh giúp các quán ăn và nhà hàng quy mô vừa và nhỏ **gom toàn bộ đơn hàng từ 6 nguồn** (*Tại quầy, QR tại bàn, Đặt bàn trước, Giao hàng website, GrabFood, ShopeeFood*) về một luồng tác nghiệp thống nhất giữa **Khách hàng – Sơ đồ bàn POS – Nhà bếp KDS – Thanh toán & Thống kê**.

### Các vấn đề giải quyết từ khảo sát thực tế (`N = 4` quán ăn)
- **I1 (Trọng tâm – 50%):** Order phân tán qua nhiều kênh (gọi trực tiếp, Zalo, app giao đồ ăn) → gom về danh sách thống nhất theo nguồn đơn.
- **I2 (25%):** Quản lý thực đơn và đơn giá tập trung → chốt đơn giá tại thời điểm gọi món (`ChiTietHoaDon.DonGia`), không làm sai lệch hóa đơn cũ khi cập nhật giá.
- **I3 (25%):** Hỗ trợ phân quyền rõ ràng 3 vai trò (`QuanLy`, `NhanVien`, `KhachHang`) và cấu hình thực đơn/bàn ăn linh hoạt.

---

## 2. Công nghệ & Kiến trúc hệ thống

- **Nền tảng:** ASP.NET Core MVC (`.NET 10.0`), C#, Razor Views (`75` tệp `.cshtml`), Bootstrap 5
- **Truy cập dữ liệu:** Microsoft SQL Server & Entity Framework Core `8.0.12` (`18` bảng quan hệ trong `QuanLyNhaHang.sql`)
- **Kiến trúc mã nguồn:** Modular Monolith phân tầng (`Controllers` → `Services` → `Repositories` → `EF Core`) + Dependency Injection (`Extensions/ServiceCollectionExtensions.cs`)
  - `Controllers/` (`28` tệp): kế thừa `BaseController` & `QuanLyBaseController`
  - `Services/` (`21` tệp): nghiệp vụ (`DatBanService`, `GioHangService`, `ThanhToanService`, `XacThucHeThongService`, ...) & `HostedService` chạy nền (`DonDepBanHostedService`, `NoShowCleanupHostedService`)
  - `Repositories/` (`16` tệp): mẫu `IRepository<T>` / `Repository<T>`
  - `Models/` (`24` tệp) & `ViewModels/` (`6` tệp)
  - `Infrastructure/` & `Common/`: `SessionGioHangStore`, `LuuTruAnhMonAn`, `KetQua<T>`, `SoDienThoai`
- **Triển khai thử nghiệm (Cloud PaaS):** Azure App Service (`Properties/PublishProfiles/quanlynhahang - Zip Deploy.pubxml`)

---

## 3. Chức năng chính (MVP – 5 Sprint)

| Vai trò / Kênh | Chức năng & Tuyến đường tiêu biểu |
|---|---|
| **Khách hàng** | Xem/lọc/tìm kiếm thực đơn (`/MonAn`), đặt bàn trước khung `10:00–21:00` (`/DatBan`), đặt giao hàng website (`/GioHang`), đăng nhập/đăng ký (`/TaiKhoan/DangNhap`, `/TaiKhoan/DangKy`, hỗ trợ OAuth demo) |
| **Khách tại bàn (QR)** | Quét mã QR định danh `Ban.MaQR` (`/ban/{token}`), mở menu (`/ban/{token}/menu`), giỏ hàng Session (`/ban/{token}/gio`), gửi món vào bếp, gọi nhân viên (`/ban/goi-nhan-vien`), thanh toán VietQR |
| **Nhân viên (POS / KDS)** | Sơ đồ bàn POS theo tầng + Live Timer UTC + tab Mang về/Giao đi (`/QuanLyBan`), lập/sửa/thanh toán/hủy hóa đơn (`/QuanLyHoaDon`), màn hình Bếp KDS `Chờ nấu → Đang nấu → Đã xong` (`/Bep`), đơn giao hàng (`/QuanLyGiaoHang`), chấm công Online/Offline (`/ChamCong`) |
| **Quản lý** | Dashboard KPI (`/QuanTri`), CRUD Thực đơn & Danh mục (`/QuanLyThucDon`, `/QuanLyDanhMuc`), Kho – Nguyên liệu – Công thức định lượng `CT_NguyenLieu` tự động trừ tồn khi đóng đơn (`/TonKho`, `/NhapKho`, `/QuanLyCongThuc`), Nhân sự (`/QuanLyNhanVien`), Thống kê doanh thu 6 nguồn (`/ThongKe`) |
| **Đối tác ngoài (API)** | Webhook nhận đơn GrabFood/ShopeeFood tự động: `POST /api/partner/webhook-order` |

---

## 4. Hướng dẫn cài đặt & chạy cục bộ

### Yêu cầu môi trường
- [.NET 10 SDK](https://dotnet.microsoft.com/)
- Microsoft SQL Server (Express hoặc Developer Edition)
- Python 3 (tùy chọn, dùng để chạy bộ kịch bản kiểm thử HTTP trong `scratch/`)

### Các bước thiết lập
1. **Khởi tạo cơ sở dữ liệu:**
   Mở Azure Portal Query Editor, Azure Data Studio hoặc SSMS, kết nối vào database đích (`QuanLyNhaHang` ở local hoặc Azure SQL Database của website) và chạy toàn bộ kịch bản [`QuanLyNhaHang.sql`](QuanLyNhaHang.sql) để tạo/đồng bộ 18 bảng, ràng buộc và dữ liệu mẫu (46 món ăn mẫu, 17 bàn + 1 bàn ảo `Giao hàng`, đơn đa kênh Sprint 5). Nếu chạy lần đầu từ `[master]` ở SQL Server local, bỏ comment 5 dòng `CREATE DATABASE / USE` ở đầu tệp.
2. **Cấu hình chuỗi kết nối:**
   Kiểm tra tệp `appsettings.json` (mặc định trỏ tới `Server=localhost\SQLEXPRESS;Database=QuanLyNhaHang;Trusted_Connection=True;TrustServerCertificate=True;`).
3. **Biên dịch và chạy ứng dụng:**
   ```bash
   dotnet restore
   dotnet build --no-restore
   dotnet run
   ```
   Mặc định chạy tại `http://localhost:5011` (hoặc `https://localhost:7110;http://localhost:5011` theo `Properties/launchSettings.json`). Khi khởi động, `Program.cs` tự chạy `KhoiTaoDuLieu.CapNhatCauTrucSprint5(db)` và `KhoiTaoDuLieu.MaHoaMatKhauCu(db)` để đồng bộ cấu trúc và băm mật khẩu PBKDF2.
4. **Tài khoản mẫu trong `QuanLyNhaHang.sql` (mật khẩu mặc định `123456`):**
   - Quản lý: `admin` (Lê Minh Quân), `sonpt` (Phạm Tiến Sơn)
   - Nhân viên: `nhattan` (Đầu bếp), `thuha` (Thu ngân), `nhanvien` (Phục vụ)
   - Khách hàng: đăng ký mới tại `/TaiKhoan/DangKy` hoặc dùng SĐT mẫu `0901234567`

---

## 5. Kiểm thử & Tài liệu dự án

- **Kiểm tra biên dịch:** `dotnet build --no-restore` → `0 Warning(s), 0 Error(s)`.
- **Kế hoạch & kết quả kiểm thử tổng thể:** Xem [`BAO_CAO_DU_AN_FOODSYNC.md`](BAO_CAO_DU_AN_FOODSYNC.md) (10 kịch bản `KB01–KB10`, **57/57 Test Case Pass**, khắc phục `BUG-01..05`).
- **Đánh giá tiến độ 5 Sprint:** Xem [`BANG_DANH_GIA_TIEN_DO_SPRINT.md`](BANG_DANH_GIA_TIEN_DO_SPRINT.md) (`14/14` hạng mục vượt qua).
- **Tài liệu Sprint 3 & Script kiểm thử:** Thư mục [`docs/`](docs/) và [`scratch/`](scratch/) (`test_suite.py`, `test_admin_deep.py`, `test_order_and_payment.py`, `test_qr.py`).

---

## 6. Phân công & Đóng góp thành viên (Nhóm 1)

| Thành viên | Vai trò chính | Phạm vi phụ trách chính | Tỷ lệ đóng góp |
|---|---|---|---:|
| **Phạm Tiến Sơn** (`BIT250302`) | PM, Backend & DB Architect | Kiến trúc MVC + DI, Bảo mật/Concurrency, Backend Sprint 1–5 (POS, Hóa đơn, KDS, QR, Giao hàng/Webhook API), tích hợp & Azure | **40%** |
| **Nguyễn Nhật Tân** (`BIT250314`) | OP, Frontend & UI/UX | 3 Layout Bootstrap 5 Responsive, `site.css`/`site.js`, giao diện QR/POS/KDS/Delivery, tài liệu Sprint 3, kiểm thử 15 TC | **25%** |
| **Nguyễn Duy Anh** (`BIT250008`) | DBA & Backend CSDL | Thiết kế & mở rộng CSDL SQL Server 18 bảng (`QuanLyNhaHang.sql`), nâng cấp Sprint 4–5 (`ChamCong`, 6 nguồn đơn), kiểm thử 14 TC | **18%** |
| **Đỗ Anh Tài** (`BIT250312`) | BA & QA/Tester | Khảo sát `N = 4`, Persona/Scenario/User Story/Backlog, ma trận 57 TC, kiểm thử 14 TC & báo cáo kiểm thử hồi quy | **17%** |
