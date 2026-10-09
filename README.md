# Nhật Bản – Mùa Lá Đỏ (17–21/11/2026)

Cẩm nang lịch trình 5 ngày 4 đêm: một trang HTML tĩnh duy nhất, tự deploy lên GitHub Pages bằng GitHub Actions.

- Trang web: `site/index.html` (đã nhúng sẵn ảnh và phông chữ; chỉ bản đồ cần mạng để tải Leaflet và nền OpenStreetMap)
- Workflow deploy: `.github/workflows/deploy.yml`
- Ảnh: Wikimedia Commons (giấy phép mở), tác giả và giấy phép ghi ở mục "Nguồn ảnh" cuối trang

## Đưa lên GitHub và bật deploy

1. Tạo repo mới trên GitHub (Public — Pages gói Free chỉ chạy với repo public).
2. Giải nén file zip, đưa **toàn bộ nội dung bên trong** thư mục `japan-travel-book` lên repo, nhớ lấy cả thư mục ẩn `.github`.
   - Dòng lệnh (khuyên dùng — không bỏ sót thư mục ẩn):
     ```bash
     cd japan-travel-book
     git init -b main
     git add .
     git commit -m "Add Japan travel book"
     git remote add origin https://github.com/<tai-khoan>/<ten-repo>.git
     git push -u origin main
     ```
   - Giao diện web: vào repo → **Add file → Upload files**, kéo thả file/thư mục vào (trên macOS bấm `Cmd + Shift + .` trong Finder để thấy thư mục `.github`).
3. Vào **Settings → Pages → Build and deployment → Source = GitHub Actions**.
4. Vào tab **Actions**: nếu lần chạy đầu bị lỗi vì chưa bật Pages, bấm **Re-run all jobs** sau khi đã làm bước 3.
5. Sau ~1 phút trang sẽ có tại `https://<tai-khoan>.github.io/<ten-repo>/`.

## Cập nhật về sau

Thay `site/index.html` bằng bản mới rồi commit và push lên nhánh `main`; Actions tự deploy lại.
