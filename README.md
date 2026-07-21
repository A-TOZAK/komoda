# 菰田小学校 校内研修（ICT活用）

令和8年7月22日（水）・30分。校内研修の資料ページと配布資料。

- 公開URL: https://a-tozak.github.io/komoda/
- 本文・図版（SVG）・配布資料はすべて自作。
- 児童の個人情報・校内資料・教科書紙面は含まない。

## 本日の流れ

| 時間 | 内容 |
|---|---|
| 0–3 | 趣旨の確認 |
| 3–11 | 活用事例の共有（近くの席の方と3分 → 全体で交流） |
| 11–20 | 実践報告（授業・支援・校務） |
| 20–25 | 教材資料の紹介 |
| 25–30 | ツールの紹介（先生のPDF道具箱） |

## 構成

```
index.html          資料ページ（1 流れ／2 活用事例／3 実践報告／4 教材資料／5 ツール／6 配布資料／7 想定される質問／8 参考リンク）
styles.css          見た目
handout/            配布資料（A4両面1枚・白黒印刷前提）
  komoda_handout.html   組版元。ここを直して再生成する
  komoda_handout.pdf    配る現物
qr/                 QR一式と投影用スライド
  komoda_qr.png/.svg          本ページのQR
  qr_schoolstock.png          教材資料サイトのQR
  qr_pdftoolbox.png           先生のPDF道具箱のQR
  projection_slide.html/.png  開始時に映すQRスライド（1920×1080）
```

## 更新のしかた

配布資料を直したら、`handout/komoda_handout.html` を編集してPDFを焼き直す。

```bash
cd handout
"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" --headless --disable-gpu \
  --no-pdf-header-footer --run-all-compositor-stages-before-draw --virtual-time-budget=6000 \
  --print-to-pdf="komoda_handout.pdf" "file://$PWD/komoda_handout.html"
```

印刷は A4・両面（長辺とじ）・実際のサイズ（100%）。白黒でそのまま刷れる。
反映は commit → push（GitHub Pages に数分で反映）。

© 2026 外﨑顯博
