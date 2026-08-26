# Aero 背單字 App（PWA）— 安裝與部署說明

這是一個**漸進式網頁應用程式（PWA）**：上傳到任何 HTTPS 網址後，手機開啟即可「加入主畫面」，
之後從桌面圖示啟動，**全螢幕、無網址列、可離線使用**。

## 檔案清單
```
index.html              主程式（單檔，含全部 50 單元 1,973 張卡與 50 篇短文）
manifest.webmanifest    App 名稱、圖示、啟動方式
sw.js                   Service Worker：離線快取
icons/                  App 圖示（192 / 512 / maskable / iOS 180）
```

## 部署方式（擇一）

### A. Netlify 拖曳（最快）
1. 打開 https://app.netlify.com/drop
2. 把**整個資料夾**（不是單一檔案）拖進去
3. 得到 `https://xxx.netlify.app` 網址即可

### B. GitHub Pages
1. 新建 repo，把四項（index.html、manifest.webmanifest、sw.js、icons/）上傳到根目錄
2. Settings → Pages → Source 選 `main` / `root`
3. 等待部署完成後開啟網址

> ⚠️ 一定要用 **https://** 開啟，Service Worker 才會生效（本機 `file://` 直接點開只能當一般網頁用，無法離線）。

## 學生安裝方式

**Android / Chrome**：開啟網址 → 底部會出現「📲 把 Aero 裝進主畫面」→ 點一下 → 安裝

**iPhone / Safari**：開啟網址 → 點下方「分享 ⬆️」→ 往下選「加入主畫面」→ 新增

## 改版更新流程
1. 修改 `index.html`
2. **把 `sw.js` 第一行的 `CACHE = "aero-vocab-v18"` 版本號改掉**（例如 v18）
3. 重新上傳整個資料夾

沒有改版本號的話，學生手機會繼續讀舊的快取版本。

## 已內建的 App 功能
- 啟動畫面（Aero 動畫）
- 離線提示列：斷線時顯示，內容照常可用
- App 捷徑：長按圖示可直接跳「單字卡 / 測驗 / 閱讀」
- 瀏海與底部安全區自動避讓（iPhone 全螢幕不遮擋）
- 學習進度、星星、獎卡都存在裝置本機，離線也會累積
