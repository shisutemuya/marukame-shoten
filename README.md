# 株式会社丸亀商店 コーポレートサイト

山梨県甲府市の鋼材・土木建築用資材の販売・加工店のコーポレートLP（静的HTML+CSS+JS）。

## 起動方法

ローカルで確認する場合:

```bash
# Python 3
python3 -m http.server 8080

# または npx
npx serve .
```

ブラウザで `http://localhost:8080` を開いてください。

## ディレクトリ構成

```
├── index.html          # メインページ
├── DESIGN.md           # デザイントークン定義
├── css/style.css       # スタイル
├── js/main.js          # インタラクション
├── assets/images/      # Web最適化済み画像
└── docs/               # 原本（PDF・写真・補足資料）
```

## 画像加工手順

原本は `docs/images/` にあります。Web用は `assets/images/` に生成します。

### 前提ツール

- `sips`（macOS標準）
- `cwebp`（`brew install webp`）

### 写真JPG（1024×768）

```bash
mkdir -p assets/images
for f in IMG_0951 IMG_0953 IMG_0954 IMG_0955 IMG_0956 IMG_0967 IMG_0985; do
  cp "docs/images/${f}.jpg" "assets/images/${f}.jpg"
  cwebp -q 82 "docs/images/${f}.jpg" -o "assets/images/${f}.webp"
done
```

### 歴史写真（6048×4272 → 長辺1600px）

```bash
sips -Z 1600 docs/images/Page0001.jpg --out assets/images/history-1600.jpg
cwebp -q 82 assets/images/history-1600.jpg -o assets/images/history.webp
```

### ロゴ・favicon

```bash
cp docs/images/logo_mark.png assets/images/logo-mark.png
sips -z 64 64 docs/images/logo_mark.png --out assets/favicon.png
sips -z 32 32 docs/images/logo_mark.png --out assets/favicon-32.png
```

HTMLでは `<picture>` で webp + jpg フォールバックを使用しています。
