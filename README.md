# 愛兒家預班表

員工打開網址 → 選名字 → 點下個月想休的日期 → 送出；「日期總表」即時彙整。

## 架設步驟（約 10 分鐘）

1. **建立 Firebase 專案**：到 https://console.firebase.google.com 新增專案。
2. **開啟 Firestore**：左側「Firestore Database」→ 建立資料庫 → 選 `asia-east1`（台灣）→ 正式版模式。
3. **貼上安全規則**：Firestore →「規則」分頁，把 `firestore.rules` 全文貼上並發布。
4. **取得設定**：專案設定 → 一般 → 你的應用程式 → 新增「網頁」應用程式，把 `firebaseConfig` 的值填進 `config.js`。
5. **改管理密碼**：`config.js` 裡的 `ADMIN_PIN`。
6. **部署到 Vercel**：把整個資料夾上傳到 GitHub 後在 Vercel 匯入，或直接 `npx vercel` 部署（純靜態網站，不需建置設定）。
7. 打開網址 →「設定」→ 輸入管理密碼 → 貼上員工名單、設定每日上限 → 儲存。之後把網址傳給員工即可。

## 注意
- 管理密碼只擋在頁面上，懂技術的人仍可能直接改資料庫；適合內部使用。若需要更嚴格的權限，可再加上 Firebase 登入。
- 月份設為「已截止」後，資料庫規則會拒絕該月的修改。
- 總表可「複製到 Excel」或「下載 CSV」（Excel 直接開啟不會亂碼）。
