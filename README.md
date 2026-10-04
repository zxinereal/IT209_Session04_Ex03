# Bài 3 – Cấu hình xác thực SSH và đẩy dự án lên GitHub

## Báo cáo thực hiện

1. Sinh khóa Ed25519 (chỉ thực hiện một lần trên máy cá nhân):
   ```powershell
   ssh-keygen -t ed25519 -C "your-email@example.com"
   ```
2. Sao chép **nội dung file public** `~/.ssh/id_ed25519.pub` và thêm vào GitHub: **Settings → SSH and GPG keys → New SSH key**. Không chia sẻ file private `id_ed25519`.
3. Liên kết remote bằng giao thức SSH:
   ```powershell
   git remote add origin git@github.com:zxinereal/IT209_Session04_Ex03.git
   ```
4. Kiểm tra xác thực và remote:
   ```powershell
   ssh -T git@github.com
   git remote -v
   ```
5. Sau khi tạo repository `IT209_Session04_Ex03` trên tài khoản GitHub, đẩy nhánh chính:
   ```powershell
   git push -u origin main
   ```

## Remote đã cấu hình

`git@github.com:zxinereal/IT209_Session04_Ex03.git`

> Không có private key nào được đưa vào bài nộp. Lệnh `ssh -T` chỉ xác thực thành công sau khi public key đã được thêm vào đúng tài khoản GitHub và repository ở trên đã tồn tại.
