# SVA Staff Portal — PWA Frontend

Đây là lớp PWA độc lập để **icon SVA chắc chắn nằm trên Home Screen** và app mở ở chế độ standalone.
Hệ thống báo cáo/HR vẫn chạy bằng Apps Script hiện tại:

https://script.google.com/macros/s/AKfycbwAgIKID3jpCChbsG4AlGdZjKeqcaJWGhq8O11QYIjioCSOkWS9hu4tl2PyCTVVXTbnnA/exec

## Cách hoạt động
PWA này là một "app shell" cùng icon/manifest/service worker của SVA.
Bên trong, nó hiển thị Apps Script portal bằng iframe full-screen.
Vì Apps Script hiện đã dùng XFrameOptionsMode.ALLOWALL, backend hiện tại không cần đổi.

## Cách deploy dễ nhất — GitHub Pages
1. Tạo repository mới, ví dụ `sva-staff-portal`.
2. Upload TOÀN BỘ nội dung thư mục này vào root repository.
3. GitHub > Settings > Pages.
4. Source: `Deploy from a branch`.
5. Branch: `main`, Folder: `/ (root)` > Save.
6. GitHub sẽ cấp URL dạng:
   `https://TEN-TAI-KHOAN.github.io/sva-staff-portal/`
7. Mở URL đó trên điện thoại:
   - iPhone Safari > Share > Add to Home Screen.
   - Android Chrome > Install app / Add to Home screen.
8. Icon ngoài Home Screen sẽ là logo SVA và tên **SVA Staff Portal**.

## Netlify / Cloudflare Pages
Có thể deploy cùng bộ file này như một static site. Không cần build command.

## Khi Apps Script URL thay đổi
Chỉ sửa `config.js`:
`PORTAL_URL: "URL_/exec_MOI"`

## Quan trọng
- Không dùng URL Apps Script `/exec` để Add to Home Screen nữa.
- Dùng URL PWA (GitHub Pages/Netlify/Cloudflare Pages).
- PWA chỉ cache giao diện shell; dữ liệu nhân sự/report không được cache offline.
- Nếu iframe không hiển thị, kiểm tra Apps Script `doGet()` vẫn có:
  `.setXFrameOptionsMode(HtmlService.XFrameOptionsMode.ALLOWALL)`.
