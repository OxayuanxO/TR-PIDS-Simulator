# TR PIDS Simulator｜臺鐵月台列車資訊顯示器模擬器

以 HTML、CSS 與原生 JavaScript 製作的臺鐵月台列車資訊顯示器（Passenger Information Display System，PIDS）網頁模擬器。無須安裝套件或建置，開啟 `index.html` 即可使用，也可部署至 GitHub Pages。

> 本專案為非官方視覺模擬工具，與臺灣鐵路公司、交通部或 TDX 無隸屬關係；顯示內容不應作為實際乘車依據。

## Disclaimer

This project is an independent, unofficial recreation of the Taiwan Railway (TRA) Passenger Information Display System (PIDS).

- This project is not affiliated with, endorsed by, or associated with Taiwan Railway Corporation.
- All source code was independently developed for educational and research purposes.
- Taiwan Railway’s trademarks, logos, and other third-party materials remain the property of their respective owners.
- Any third-party materials used in this project are subject to their respective licenses.

本專案僅供學習、研究及技術展示使用，與國營臺灣鐵路股份有限公司無任何官方合作或隸屬關係。

## Data Source & Attribution

This project uses transportation data provided by the Ministry of Transportation and Communications (MOTC) TDX platform.

資料來源：交通部運輸資料流通服務平臺（TDX）

Official website: [https://tdx.transportdata.tw/](https://tdx.transportdata.tw/)

本專案使用 TDX 提供之交通運輸資料進行個人開發與展示，資料權利及使用條件依 TDX 平臺相關授權規範辦理。

## 功能特色

- **月台顯示器模擬**：呈現月台、發車時間、目的地、車次、車種、狀態、備註、跑馬燈與時鐘。
- **班次編輯**：可新增、刪除及調整班次，設定停靠站、誤點分鐘、取消與即將進站等資訊。
- **車種色彩識別**：區分莒光／自強、自強 3000／普悠瑪／太魯閣、觀光列車與區間車。
- **中英雙語**：到站資訊與跑馬燈可分別使用中文、英文或自動輪替。
- **動態效果**：即將進站指示、跑馬燈、自動縮放與響應式設定介面。
- **TDX 即時同步**：可手動或定時取得指定車站的即時看板、當日班表與列車停靠站資料；沒有 API 金鑰時會嘗試使用免金鑰的舊版 PTX 資料來源。
- **本機保存設定**：一般設定與班次存於瀏覽器 `localStorage`，重新整理後仍可保留。

## 快速開始

### 直接開啟

下載專案後，以現代瀏覽器開啟 `index.html`：

1. 主畫面會顯示預設班次。
2. 點擊右下角齒輪進入設定。
3. 編輯顯示器、班次、跑馬燈或 TDX 同步設定。
4. 點擊「返回主畫面」查看結果。

### 使用本機 HTTP 伺服器

若瀏覽器限制本機檔案的網路請求，可在專案目錄執行：

```bash
python3 -m http.server 8000
```

再前往 `http://localhost:8000`。

## TDX 即時同步

1. 前往 [TDX 運輸資料流通服務平臺](https://tdx.transportdata.tw/) 申請帳號與 API 金鑰。
2. 在設定頁選擇「手動同步」或「自動即時同步」。
3. 選擇車站及同步間隔，輸入 **Client ID** 與 **Client Secret**。
4. 點擊「測試連線」確認憑證，或點擊「立即同步」更新班次。

資料來源包含交通部 TDX／PTX；實際欄位完整度依車站與 API 回應而異，尤其多數車站可能不提供月台編號。瀏覽器必須能連線至相關 API，且請求可能受網路環境或 CORS 政策影響。

### 隱私與安全性

- TDX 憑證只存放於目前分頁的 `sessionStorage`，關閉瀏覽器分頁後清除，不會寫入專案或提交至 GitHub。
- 本專案為純前端應用，瀏覽器會直接向 TDX 請求資料；請勿在公開共用電腦輸入私人憑證。
- 一般顯示設定與班次使用 `localStorage` 保存，可在瀏覽器中清除網站資料以重設。

## 部署至 GitHub Pages

專案包含 `.github/workflows/deploy-pages.yml`，推送至 `main` 或手動執行 **Deploy GitHub Pages** 工作流程時，會將根目錄的靜態檔案發布至 GitHub Pages。

首次使用請在 GitHub 儲存庫中確認：

1. 開啟 **Settings → Pages**。
2. 將 **Build and deployment / Source** 設為 **GitHub Actions**。
3. 等待 Actions 工作流程完成，網址通常為：
   `https://<使用者名稱>.github.io/TR-PIDS-Simulator/`

> GitHub Pages 對私有儲存庫的支援取決於帳號方案；公開儲存庫可直接使用。專案以相對路徑載入，不需要額外設定網站根目錄。

## 專案結構

```text
.
├── index.html                         # 完整單頁應用（樣式、介面與邏輯）
├── .nojekyll                          # 停用 Jekyll 處理
├── .github/workflows/deploy-pages.yml # GitHub Pages 自動部署
└── README.md                          # 專案說明
```

## 技術與相容性

- HTML5、CSS3、原生 JavaScript
- 無第三方前端套件、無建置步驟
- 建議使用最新版 Chrome、Edge、Firefox 或 Safari
- 動畫會尊重系統的「減少動態效果」偏好設定
