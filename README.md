# 互動背單字學習平台（Aero）

單檔 HTML 互動背單字平台，單字卡附 SoR 專利注音積木（P.A.GOes 音節排列與聲調標示）。

## 部署到 GitHub Pages
1. 在 GitHub 建立新的 repository（或打開原本的 repository）。
2. 上傳 `index.html`（取代舊檔）、`README.md`、`.nojekyll`、`manifest.webmanifest`、`sw.js`，以及整個 `icons` 資料夾（內含三張 PNG）。
3. Settings → Pages → Source 選 `Deploy from a branch`，Branch 選 `main`、資料夾 `/ (root)`，按 Save。
4. 約一分鐘後，網址為 `https://<帳號>.github.io/<repository 名稱>/`。

所有積木圖片與程式都已內嵌在 `index.html`。`manifest.webmanifest`、`sw.js` 與 `icons/` 負責「加到主畫面」與離線使用；少了它們網站仍可開，但無法安裝成 App 或離線使用。
