# DESIGN.md — 株式会社丸亀商店

## 1. Overview

山梨県甲府市の老舗B2B鋼材・建材販売店のコーポレートLP。老舗 × 重厚インダストリアルの方向性。スチールグレー基調 + 鉛丹レッドアクセント。見出しは明朝、本文はゴシック。

## 2. Color Palette

| Token | Value | Usage |
|-------|-------|-------|
| `--color-bg` | `#ffffff` | Page background |
| `--color-surface` | `#f4f5f6` | Section alt background |
| `--color-ink` | `#1a1d21` | Body text |
| `--color-muted` | `#5b626b` | Secondary text |
| `--color-steel-900` | `#1d2024` | Dark sections, footer |
| `--color-steel-700` | `#363b41` | Header scrolled |
| `--color-steel-500` | `#6b7280` | Borders, icons |
| `--color-accent` | `#b3402a` | CTA, emphasis |
| `--color-accent-deep` | `#8c2f20` | CTA hover |
| `--color-brass` | `#a8842c` | Heritage badge |
| `--color-line` | `#e0e2e5` | Dividers |

## 3. Typography

### 3.1 Font Families

**見出し（明朝 / 老舗感）**
```css
font-family: "Noto Serif JP", "Hiragino Mincho ProN", "Yu Mincho", serif;
```

**本文・UI（ゴシック）**
```css
font-family: "Noto Sans JP", "Hiragino Kaku Gothic ProN", "Hiragino Sans", "Meiryo", "Yu Gothic", sans-serif;
```

**欧文・数字**
```css
font-family: "Inter", -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
```

### 3.2 Type Scale

| Role | Size | Weight | Line-height | Letter-spacing |
|------|------|--------|-------------|----------------|
| Display | 2.5rem | 700 | 1.4 | -0.01em |
| Heading 1 | 2rem | 700 | 1.4 | -0.01em |
| Heading 2 | 1.5rem | 600 | 1.4 | 0 |
| Body | 1rem | 400 | 1.8 | 0.04em |
| Small | 0.875rem | 400 | 1.7 | 0.04em |
| Caption | 0.75rem | 400 | 1.6 | 0.06em |

### 3.3 Japanese Typography Rules

```css
font-feature-settings: "palt" 1, "kern" 1;
-webkit-font-smoothing: antialiased;
-moz-osx-font-smoothing: grayscale;
text-rendering: optimizeLegibility;
```

**Kinsoku shori (禁則処理):**
```css
p, li, td, th {
  line-break: strict;
  word-break: normal;
  overflow-wrap: break-word;
}
```

## 4. Spacing & Layout

Base unit: 8px

| Token | Value |
|-------|-------|
| `--space-xs` | 4px |
| `--space-sm` | 8px |
| `--space-md` | 16px |
| `--space-lg` | 32px |
| `--space-xl` | 64px |

Max content width: 1120px. Horizontal padding: 20px (mobile), 24px (desktop).

## 5. Components

- **Buttons**: Primary (accent red), Secondary (outline), min-height 44px
- **Cards**: White bg, 1px border `--color-line`, 8px radius, subtle shadow on hover
- **Tags/Chips**: Surface bg, small text, rounded pill for product items
- **Heritage badge**: Brass border + brass text on dark bg
- **Logo on dark bg**: `filter: brightness(0) invert(1);`

## 6. Icons & Imagery

- Hero: warehouse photo with dark gradient overlay
- Gallery: hover scale 1.04, grayscale(0.15) contrast(1.05) optional
- History photo: sepia, framed style
- All images: meaningful alt, lazy loading, width/height set

## 7. Motion & Animation

- Transition: 0.25s ease
- Section fade-in via IntersectionObserver
- Respect `prefers-reduced-motion: reduce`

## 8. Responsive Breakpoints

| Name | Width |
|------|-------|
| Mobile | < 768px |
| Tablet | 768–1024px |
| Desktop | > 1024px |

## 9. Accessibility

- Contrast ratio: minimum 4.5:1 for body text
- Focus indicators: visible 2px outline
- Tap targets: minimum 44×44px
