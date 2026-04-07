# jimmy-smile-gallery 網站筆記

## 網址
https://jimmyaitaiwan.github.io/jimmy-smile-gallery

## 概念
個人攝影作品與隨筆的私人空間，不放社群平台。
- 攝影 60% / 隨筆 40%
- 主要給自己看，偶爾分享連結給朋友
- 照片不分類，按發布時間排列
- 隨筆全部同一頁往下捲

## 技術架構
- 純 HTML + CSS + 少量 JS（無框架、無後端）
- 靜態網站，部署在 GitHub Pages
- repo：https://github.com/Jimmyaitaiwan/jimmy-smile-gallery

## 設計規格
- 背景：`#0d0d0d`（近黑）
- 文字：`#d4d4d4`（淺灰）
- 字型：`'Microsoft JhengHei', 'PingFang TC', 'Noto Sans TC', sans-serif`
  - Windows → 微軟正黑體
  - Mac → 蘋方
  - 其他 → Noto Sans TC
- 相簿：3 欄 CSS Grid，gap 3px，1:1 正方形
- Hover：圖片放大 1.04 倍 + 顯示日期地點
- 點擊：Lightbox 放大（純 JS，按 Esc 或點背景關閉）
- 隨筆：最大寬度 680px，每篇底部細線分隔

## 檔案結構
```
site/
├── index.html       # 主檔案，所有內容都在這裡
├── photos/          # 放照片的資料夾
│   └── 1.jpeg       # 範例
└── NOTES.md         # 這份筆記
```

## 新增照片
在 `index.html` 的 `<!-- 攝影 -->` 區塊，照以下格式加：

```html
<div class="photo-item" onclick="openLightbox('photos/檔名.jpg')">
  <img src="photos/檔名.jpg" alt="">
  <div class="meta">2026-04 · 地點</div>
</div>
```

最新的放最上面（時間由新到舊）。

## 新增隨筆
在 `index.html` 的 `<!-- 隨筆 -->` 區塊，照以下格式加：

```html
<div class="journal-item">
  <div class="date">2026-04-07</div>
  <div class="text">內容寫在這裡。</div>
</div>
```

最新的放最上面（時間由新到舊）。

## 更新網站（推上 GitHub）
```bash
cd /Users/YouMACmeHAPPY/Jimmy_Sides/site
git add .
git commit -m "更新內容"
git push
```

或直接叫 Claude：「幫我把網站推上去」

推上去後約 1 分鐘生效。

## 未來可能的改動方向
- 加入分頁（照片太多時）
- 支援手機的更好體驗
- 自訂網域（需另外購買）
- 隨筆支援 Markdown 格式
