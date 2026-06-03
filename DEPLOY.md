# Hướng dẫn deploy & setup (nội bộ)

Landing page tĩnh trên GitHub Pages, 100% free. (File này là tài liệu kỹ thuật — phần giới thiệu công khai nằm ở `README.md`.)

---

## A. Deploy lên GitHub Pages

> Repo: `barobaonguyen/barobao` → live tại https://barobaonguyen.github.io/barobao/
> ✅ Đã deploy 2026-06-03. Các lần cập nhật sau:

```bash
git add . && git commit -m "update landing" && git push
```
(Thư mục đã pin sẵn identity **barobaonguyen** qua local config + SSH alias `git@barobaonguyen:` — không cần switch account thủ công.)

### Gắn domain riêng `barobao.com` (sau khi validate, ~$10/năm)
- Mua domain → repo Settings → Pages → Custom domain → nhập `barobao.com` → thêm DNS theo hướng dẫn GitHub. Không phải build lại.

---

## B. Bắt email + tự gửi lead magnet (free) — MailerLite

> GitHub Pages không tự lưu email → cần form của công cụ email. **MailerLite free**: tới 1.000 subscriber + automation.

1. Đăng ký mailerlite.com (free).
2. **Forms → Embedded form** → tạo form "Nhận bộ prompt" → **Embed** → copy mã HTML.
3. Trong `index.html`, tìm khối `<!-- CHÈN FORM EMAIL Ở ĐÂY -->` → xóa cả khối `<form>` demo → dán mã MailerLite vào.
4. **Automation**: trigger "khi đăng ký form này" → gửi email kèm link PDF lead magnet (nội dung lấy từ `PHASE0/04_tech_studio.md`).
5. Commit + push.

> Có thể thay bằng **Kit (ConvertKit) free** — bước tương tự.

---

## C. Host PDF lead magnet (free)
- Bỏ `leadmagnet.pdf` vào repo → link `https://barobaonguyen.github.io/barobao/leadmagnet.pdf`, hoặc Google Drive (share "ai có link").
- Nội dung PDF: `PHASE0/07_lead_magnet_AI.md`, format bằng Canva free.

---

## D. Cần thay trong `index.html`
- [ ] `avatar.jpg`: bỏ ảnh chân dung vào thư mục (hoặc xóa dòng `<img>`).
- [ ] 3 link social `href="#"` → link thật.
- [ ] Khối `<form>` demo → mã nhúng MailerLite/Kit.

## E. Analytics free (tùy chọn)
- Cloudflare Web Analytics (free, không cookie banner) hoặc GA4.

---

## Git identity (quan trọng)
- Thư mục này MUST dùng **barobaonguyen**, KHÔNG dùng bao-mk1.
- Đã set: local `user.name=barobaonguyen`, `user.email=265752715+barobaonguyen@users.noreply.github.com`, remote `git@barobaonguyen:barobaonguyen/barobao.git`.
