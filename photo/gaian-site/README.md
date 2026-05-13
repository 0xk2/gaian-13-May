# Gaian Site Assets

Asset trong thư mục này được tải từ `https://gaian.network/` để dùng làm reference.

## Preferred References

Ưu tiên dùng các file sau:

- `root/logo.svg`
  Logo chính của site.
- `_next/static/media/logo-without-text.928ee2d5.svg`
  Biểu tượng logo không kèm wordmark.
- `meta/thumbnail.png`
  OG / social thumbnail.
- `bg-section-1/L2.webp`
  Background image của hero/section.
- `feedback/*.jpg`
  Ảnh testimonial/avatar gốc lấy từ site.
- `_next/static/media/*.svg`
  Logo ecosystem, partner, award, social icon.
- `external/pbs.twimg.com/5hgApmLp_400x400.png`
  Avatar ngoài site được homepage nhúng qua `next/image`.

## About Duplicates

Một số file xuất hiện nhiều hơn một lần vì homepage dùng đồng thời:

- file gốc như `feedback_image/...`, `images/...`, `logo.svg`
- file tối ưu hóa hoặc bundle path của Next.js như `_next/...`

Các bản duplicate được giữ nguyên để bạn đối chiếu source path khi cần.
