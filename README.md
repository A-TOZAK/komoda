# 菰田小学校 校内研修「『使える』の次は、分け合う。」

校内研修（30分・2026年7月22日）の当日ページと、あとから読む資料置き場。

- 公開URL: https://a-tozak.github.io/komoda/
- 本文・図版（SVG）・配布資料はすべて外﨑顯博の自作。
- 児童の個人情報・校内の資料・教科書の紙面は含まない。

## 30分の流れ

| 時間 | 内容 |
|---|---|
| 0–3 | 今日やること（見取り図） |
| 3–11 | 今、どう使ってる？（ペア3分 → 全体で拾う） |
| 11–20 | 私の実践から3つ（授業で・気になる子に・校務で） |
| 20–25 | 教材の棚（School Stock） |
| 25–30 | 先生のPDF道具箱 |

## 構成

```
index.html          当日ページ（見取り図・4つの型・実践3つ・School Stock・PDF道具箱・Q&A）
styles.css          見た目（LiFE with 編集ブランド。高田小・立岩小と同じトークン）
handout/            配布資料（A4両面1枚）
  komoda_handout.html   組版元。ここを直して再生成する
  komoda_handout.pdf    配る現物
qr/                 QR一式と投影用スライド
  komoda_qr.png/.svg      このサイトのQR
  qr_schoolstock.png      School Stock のQR
  qr_pdftoolbox.png       先生のPDF道具箱 のQR
  projection_slide.html/.png  開始時に映すQRスライド（1920×1080）
author.jpg          プロフィール写真
```

## 更新のしかた（自分用メモ）

- **配布資料を直したら**: `handout/komoda_handout.html` を編集 → 下のコマンドでPDFを焼き直す

```bash
cd handout
"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" --headless --disable-gpu \
  --no-pdf-header-footer --run-all-compositor-stages-before-draw --virtual-time-budget=6000 \
  --print-to-pdf="komoda_handout.pdf" "file://$PWD/komoda_handout.html"
```

- **印刷**: A4・両面（長辺とじ）・実際のサイズ（100%）。白黒でそのまま刷れる
- **反映**: commit → push（GitHub Pagesに数分で反映）

© 2026 外﨑顯博 / LiFE with
