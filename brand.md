# Gaian Design Guideline

Nguồn tham chiếu: [gaian.network](https://gaian.network/) tại ngày 13/05/2026, CSS public của site, và OG thumbnail của thương hiệu. Các phần về "nguyên tắc" và "do / don't" là suy luận hệ thống hóa từ các nguồn này để dùng làm source of truth khi thiết kế tiếp.

## 1. Brand DNA

Gaian nên được cảm nhận như một hạ tầng thanh toán stablecoin:

- đáng tin, gọn, có tính vận hành
- hiện đại nhưng không khoa trương kiểu "crypto neon"
- mang chất editorial nhẹ để tạo sự khác biệt với các landing page fintech mặc định
- đủ ấm và dễ tiếp cận cho APAC, nhưng vẫn giữ cảm giác infrastructure-first

Từ khóa: `trustworthy`, `operational`, `editorial`, `calm`, `fast`, `borderless`.

## 2. Visual Direction

### Tổng thể

- Nền sáng, sạch, thở nhiều.
- Trục màu chính là xanh đậm + lime green rất sáng.
- Bề mặt dùng kính mờ nhẹ, border mảnh, shadow mềm.
- Các section quan trọng có grid/radial glow để tạo cảm giác "network rail" thay vì chỉ là block marketing tĩnh.
- Typography trộn giữa sans nghiêm túc và serif editorial cho headline.

### Cảm giác cần giữ

- "Infrastructure with polish", không phải "consumer app đầy hiệu ứng".
- "Global payment rail", không phải "web3 meme brand".
- "Production-ready", không phải "experimental lab".

## 3. Color System

### Core palette

Các màu dưới đây được suy ra trực tiếp từ CSS của site:

```css
:root {
  --gaian-ink: #163300;
  --gaian-ink-deep: #0A1F00;
  --gaian-ink-darker: #051200;
  --gaian-accent: #9FE870;
  --gaian-accent-soft: #D8F2C4;
  --gaian-surface-tint: #F6FDF1;
  --gaian-white: #FFFFFF;

  --gaian-border-soft: rgba(22, 51, 0, 0.10);
  --gaian-border-mid: rgba(22, 51, 0, 0.15);
  --gaian-border-strong: rgba(22, 51, 0, 0.20);
  --gaian-grid-line: rgba(22, 51, 0, 0.06);

  --gaian-glass-white: rgba(255, 255, 255, 0.70);
  --gaian-glass-white-strong: rgba(255, 255, 255, 0.80);
  --gaian-dark-overlay: rgba(22, 51, 0, 0.60);

  --gaian-reward-gold: #B78A3C;
}
```

### Cách dùng màu

- `--gaian-ink` là màu text/chrome chính. Dùng thay cho đen thuần.
- `--gaian-accent` chỉ nên là màu kích hoạt: CTA, trạng thái live, bullet, điểm nhấn trong headline, badge, active chip.
- `--gaian-surface-tint` dùng cho section mở đầu, card sáng, input nền sáng và vùng wash.
- `--gaian-reward-gold` chỉ dùng cho award, recognition, distinction. Không dùng làm CTA chính.

### Tỷ lệ khuyến nghị

- 70% nền trắng hoặc very-light green
- 20% xanh đậm cho text, footer, control states
- 10% lime accent cho emphasis

### Không nên

- Không chuyển brand sang xanh dương fintech mặc định.
- Không dùng lime trên diện rộng thành nền chính của cả page.
- Không dùng gradient tím/xanh như visual language chủ đạo.

## 4. Typography

### Font families

Các family đang xuất hiện trực tiếp trong CSS:

- UI sans: `Aeonik, sans-serif`
- Display/editorial: `Georgia, Cambria, "Times New Roman", serif`
- Mono accent: `"Geist Mono", ui-monospace, monospace`

### Vai trò

- `Aeonik` cho body copy, nav, button, form, labels, cards.
- `Serif` cho hero headline, section titles, stats lớn, pull quote, emphasis italic.
- `Geist Mono` cho dữ liệu ngắn, chain/status, ticker, system badges, numeric meta.

### Type behavior

- Headline serif rất lớn, line-height chặt, tracking hơi âm.
- Serif italic chỉ dùng như một nhịp nhấn, không dùng cho cả đoạn dài.
- Eyebrow/section label luôn uppercase nhỏ, tracking rộng.
- Body copy nên giữ nhịp 16-18px, line-height thoáng, không vượt quá 42ch-48ch nếu là đoạn giới thiệu.

### Scale khuyến nghị

```text
Eyebrow: 10-11px / uppercase / tracking 0.12em-0.18em
Body: 16px mobile, 18px desktop
Card title: 22-28px
Section title: clamp(40px, 5vw, 72px)
Hero title: 48px -> 88px
Metric number: 40px -> 60px
Mono/system label: 10px -> 12px
```

## 5. Layout Principles

### Container

- Max content width chính: `1600px` (`max-w-screen-xl`).
- Wide wrapper/background canvas: `2240px` (`max-w-screen-4xl`).
- Hero nên dùng gần full viewport height.

### Spacing rhythm

- Mobile horizontal padding: `16px`
- Desktop horizontal padding thường: `40px`
- Section padding desktop: `96px - 112px`
- Card padding: `24px - 32px`

### Composition

- Hero: split editorial copy bên trái, product/system visual bên phải.
- Mỗi section nên có 1 eye-catching anchor: stat row, testimonial rail, award ledger, FAQ list, visual demo.
- Dùng nhiều khoảng trắng; đừng cố lấp kín layout.

## 6. Shape, Border, Surface

### Radius

Các radius cốt lõi trên site:

- `rounded-full`
- `rounded-2xl` = `16px`
- `rounded-3xl` = `24px`

### Border

- Border mảnh `1px - 1.5px`
- Ưu tiên xanh đậm ở opacity thấp hoặc trắng ở opacity thấp
- Border là một phần quan trọng của brand; đừng bỏ hết border để dùng shadow-only

### Surface styles

- Header/nav: glass trắng với blur vừa (`12px`)
- Premium card/dark section: blur mạnh hơn (`24px`), border trắng mờ, gradient trong suốt
- CTA sáng: lime fill + inset highlight

### Shadow

Các shadow nên bám chất liệu hiện tại:

```css
--gaian-shadow-soft: 0 20px 60px -20px rgba(15, 64, 12, 0.35);
--gaian-shadow-hover: 0 4px 20px 0 rgba(15, 64, 12, 0.30);
--gaian-shadow-inset-lime: inset 0 4px 6px rgb(216, 242, 196);
--gaian-shadow-inset-cta: inset 0 4px 6px rgba(0, 0, 0, 0.05),
  inset 0 -4px 6px rgb(216, 242, 196);
```

## 7. Background Language

Background của Gaian không phẳng hoàn toàn. Nên giữ các lớp sau:

- wash trắng sang green tint rất nhẹ
- grid line mờ `rgba(22, 51, 0, 0.06)`
- radial lime glow blur lớn
- hình nền network/rail rất nhẹ hoặc ảnh texture mờ

### Công thức nền khuyến nghị

```css
background:
  linear-gradient(to bottom, #f6fdf1 0%, #ffffff 100%);
```

Khi cần thêm chiều sâu:

```css
background-image:
  linear-gradient(to right, rgba(22, 51, 0, 0.06) 1px, transparent 1px),
  linear-gradient(to bottom, rgba(22, 51, 0, 0.06) 1px, transparent 1px);
background-size: 48px 48px;
```

## 8. Component Language

### Header

- Floating top bar, full-width nhưng có breathing room.
- Hình capsule lớn, border sáng, nền trắng mờ, blur.
- Nav text nhỏ, semi-bold, đổi màu tinh tế khi hover.

### Buttons

- Primary CTA: lime fill, text xanh đậm, border xanh olive, shadow inset.
- Secondary CTA: sáng hơn, vẫn giữ border và tactile feel.
- Label button nên uppercase hoặc semi-uppercase, tracking vừa phải.
- Hover nên là tăng chiều sâu nhẹ, không nên dùng glow mạnh kiểu gaming.

### Cards

- Card sáng: nền trắng/green tint, border soft, shadow nhẹ.
- Card tối: border trắng 10%, glass gradient, nội dung trắng và accent lime.
- Card không nên quá vuông hoặc flat.

### Stats

- Số lớn bằng serif.
- Meta label bằng Aeonik hoặc mono uppercase nhỏ.
- Có thể thêm bullet lime hoặc chip mô tả ngắn để tránh cảm giác dashboard khô.

### FAQ / list rows

- Row dạng ledger/editorial list.
- Serif cho câu hỏi, meta nhỏ ở hai đầu.
- Hover chỉ cần đổi màu text và border; không cần animation lớn.

### Forms

- Input full-pill hoặc rounded lớn.
- Nền translucent nếu nằm trên dark section.
- Focus state dùng accent green ở border, không dùng xanh browser mặc định.

## 9. Motion

Motion trên site hiện tại thiên về subtle entrance và tactile hover.

### Nên dùng

- fade + translateY ngắn khi vào viewport
- letter reveal cho hero hoặc headline chính
- hover arrow reveal trong CTA
- ping/pulse rất nhỏ cho "live" state
- marquee chậm cho social proof nếu cần

### Không nên

- parallax mạnh
- spring quá nảy
- loop animation dày đặc
- motion làm giảm cảm giác tin cậy

### Timing gợi ý

- entrance: `300ms - 600ms`
- hover: `200ms - 300ms`
- special hero reveal: `500ms - 900ms`

## 10. Imagery & Illustration

Từ OG image và visual trên site, ngôn ngữ minh họa phù hợp là:

- object 3D đơn giản hoặc isometric nhẹ
- viền đen rõ, sạch, hơi giống technical illustration
- lime accent đặt có chủ đích trên vật thể
- gold/yellow chỉ là màu phụ cho reward/coin moments
- nền ảnh luôn thoáng, có glow xanh nhẹ hoặc wireframe/network motif

### Không nên

- stock photo doanh nghiệp bắt tay
- 3D bóng loáng quá "startup template"
- icon set quá bo tròn hoặc cartoon
- visual đầy màu không liên quan tới core palette

## 11. Voice & Copy

Copy của Gaian nên ngắn, tự tin, operational.

### Giọng điệu

- nói như một team đã ship
- claim đi cùng proof
- tránh hype jargon
- tránh "revolutionize finance" hoặc slogan sáo rỗng

### Công thức câu phù hợp

- capability + speed
- infrastructure + geography
- product + proof

Ví dụ pattern:

- "Move stablecoins across X and settle in local currency in seconds."
- "Built for businesses, accessible to everyone."
- "Validated in production."

## 12. Do / Don't

### Do

- dùng nền sáng với độ tương phản cao
- dùng serif để tạo sự khác biệt ở headline
- giữ CTA tactile, có border và shadow inset
- dùng lime như tín hiệu định hướng, không phải flood fill
- giữ nhiều khoảng trắng
- thêm proof layer: metrics, logos, testimonials, award ledger

### Don't

- không dùng black tuyệt đối cho toàn bộ UI
- không chuyển sang dashboard crypto neon
- không dùng card vuông, border nặng, shadow đen dày
- không dùng quá nhiều accent color ngoài green + gold phụ
- không viết copy dài, chung chung hoặc self-congratulatory

## 13. Implementation Notes

Nếu cần dựng lại style trong web app mới, có thể bắt đầu với token sau:

```css
:root {
  --background: #ffffff;
  --surface: #f6fdf1;
  --foreground: #163300;
  --foreground-soft: rgba(22, 51, 0, 0.7);
  --primary: #9fe870;
  --primary-foreground: #163300;
  --border: rgba(22, 51, 0, 0.1);
  --ring: rgba(159, 232, 112, 0.6);
  --card: rgba(255, 255, 255, 0.7);
  --card-strong: rgba(255, 255, 255, 0.8);
}
```

Tailwind direction:

- body font: `Aeonik`
- display font: `serif`
- mono/meta: `Geist Mono`
- radii: `rounded-full`, `rounded-2xl`, `rounded-3xl`
- shell background: `from-green-50 to-white`
- accent surface: `bg-textGreen`, `bg-textGreen/20`, `border-textGreen/40`
- text: `text-darkGreen`, `text-darkGreen/70`, `text-darkGreen/45`

## 14. Default Checklist For New Screens

Mỗi màn mới nên tự check:

1. Có còn đúng green + editorial serif + glass-border language không?
2. Có quá giống template fintech generic không?
3. CTA đã đủ tactile chưa?
4. Có proof layer hoặc system signal nào giúp tăng trust chưa?
5. Accent green có đang bị lạm dụng thành màu nền chính không?
6. Typography đã có nhịp giữa sans operational và serif editorial chưa?
