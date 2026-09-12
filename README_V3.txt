SVA PWA INSTALL-SAFE V3

Mục tiêu: iPhone phải lấy icon từ GitHub Pages, không phải từ Apps Script.

Điểm quan trọng:
- Safari mở GitHub Pages: trang KHÔNG tự redirect.
- Người dùng Add to Home Screen ngay khi vẫn đang ở GitHub Pages.
- Khi mở icon Home Screen (standalone), trang mới tự redirect sang Apps Script.
- Icon dùng filename mới v3 để phá cache icon cũ của iOS.

Upload vào root GitHub:
1 index.html (replace)
2 manifest.webmanifest (replace)
3 sw.js (replace)
4 sva-home-icon-v3.png (new)
5 sva-icon-192-v3.png (new)
6 sva-icon-512-v3.png (new)

Sau deploy:
- Xóa icon Home Screen cũ.
- Safari > mở GitHub Pages URL.
- Không bấm nút Open Portal.
- Share > Add to Home Screen.
- Preview phải thấy logo SVA.
- Add.
