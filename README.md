# NVC 即時改寫

把你想講、但語氣不好的話，即時改寫成「非暴力溝通（NVC）」版本。
純前端網頁、可加到手機主畫面像 App 用。輸出 🌱 溫和版 / 🎯 直接版 / 💡 一行點評，並自動存歷史。

---

## 一、先拿一把免費金鑰（Google Gemini）

1. 開 https://aistudio.google.com/app/apikey （用 Google 帳號登入）。
2. 點 **Create API key** → 建立 → **複製金鑰**。
3. 免費、不用綁信用卡；你這種個人用量遠用不完每日額度。

> 之後在工具裡點右上 **⚙️** 貼上金鑰即可。金鑰只存在你手機本機（localStorage），**不會上傳、不在程式碼裡**。

---

## 二、部署到 GitHub Pages（跟封面產生器一樣）

1. 把這個 `nvc-rewriter/` 資料夾的檔案推到一個 GitHub repo（可沿用既有 repo 放子資料夾，或開新 repo）。
2. repo → **Settings → Pages** → Source 選 `main` 分支（資料夾選 `/root` 或對應路徑）。
3. 等一兩分鐘，拿到網址（例：`https://你的帳號.github.io/nvc-rewriter/`）。
4. 手機用 Safari / Chrome 開那個網址 → 分享選單 → **加入主畫面**。之後點圖示就全螢幕開啟。

> 程式碼公開沒關係——裡面沒有任何金鑰。

---

## 三、怎麼用

1. 第一次開會直接進設定，貼上金鑰、儲存。
2. 主畫面把想講的話貼進框（或用手機鍵盤的**麥克風鈕**直接口述）。
3. 按「改寫」→ 得到溫和版、直接版、點評，各有複製鈕。
4. 語氣很重時，上面會多一條「先深呼吸」提醒。
5. 右上 🕘 看歷史，回顧自己常踩的語氣地雷；可單筆刪除或清空。

---

## 四、想換模型 / 換回 Claude？

打開 `index.html`，最上面 `<script>` 裡有設定區：

```js
const MODEL = "gemini-2.5-flash"; // 換 Gemini 其他型號改這行即可
```

- 換成別的 Gemini 型號（如 `gemini-2.0-flash`）：只改 `MODEL` 這行。
- 想換成 Claude 或其他家：改 `ENDPOINT`、`headers`、`body` 三處（集中在同一段），UI 不用動。

---

## 檔案

| 檔案 | 用途 |
|---|---|
| `index.html` | 全部：UI＋設定＋改寫邏輯＋歷史（單檔） |
| `manifest.json` | PWA 設定，讓它能加到主畫面 |
| `icon.svg` | App 圖示 |
| `README.md` | 本說明 |

設計文件：`../docs/superpowers/specs/2026-06-12-nvc-rewriter-design.md`
