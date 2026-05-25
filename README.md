# Auto Build & Release

Dự án này được thiết lập để tự động tạo release trên GitHub mỗi khi bạn push một tag mới.

## Cách sử dụng

1. **Khởi tạo Repo trên GitHub**:
   - Tạo một repository mới trên GitHub.
   - Kết nối thư mục local này với GitHub repo đó.

2. **Cài đặt Git (nếu chưa có)**:
   ```bash
   pkg install git
   ```

3. **Push code lên**:
   ```bash
   git add .
   git commit -m "Initial commit"
   git remote add origin https://github.com/AnNgTv/auto-build.git
   git push -u origin main
   ```

4. **Tạo Release**:
   Để kích hoạt workflow tạo release, hãy tạo và push một tag:
   ```bash
   git tag v1.0.0
   git push origin v1.0.0
   ```

## Workflow hoạt động như thế nào?

Khi bạn push một tag có định dạng `v*` (ví dụ `v1.0.0`), GitHub Actions sẽ:
- Tự động checkout code.
- Cài đặt Node.js.
- Chạy lệnh `npm install` và `npm run build`.
- Nén project lại thành file `release.zip`.
- Tạo một GitHub Release và đính kèm file `release.zip` vào đó.
# auto-build
