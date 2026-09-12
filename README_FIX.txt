SVA Staff Portal PWA — FIXED

Lỗi đã sửa:
1) Icon: repo của bạn đang để icon-180/192/512.png ở ROOT nhưng index/manifest cũ lại trỏ tới icons/... nên logo bị hình dấu hỏi.
2) Splash treo: iframe Apps Script có thể không load ổn định trên iPhone/PWA. Bản này bỏ iframe và chuyển thẳng sang Apps Script Portal sau ~0.65 giây.
3) Service worker cũ cũng cache sai đường dẫn icons/...; đã sửa về file ở root.

Cách cập nhật GitHub:
- Thay 4 file: index.html, manifest.webmanifest, sw.js, config.js
- Giữ 3 icon hiện tại ở root: icon-180.png, icon-192.png, icon-512.png
- Commit changes
- Chờ GitHub Pages deploy lại 1-3 phút
- Trên iPhone: xóa icon Home Screen cũ, mở lại GitHub Pages bằng Safari, Add to Home Screen lại để iOS lấy icon mới.
