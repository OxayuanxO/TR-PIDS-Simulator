# TR PIDS Simulator｜臺鐵月台列車資訊顯示器模擬器

一個以網頁呈現的臺鐵月台列車資訊顯示器（PIDS）模擬器，可自由編輯班次、車種、狀態與跑馬燈，也能透過 TDX 取得即時列車資料。

**[開啟線上模擬器](https://oxayuanxo.github.io/TR-PIDS-Simulator/)**

## 主要功能

- 模擬月台顯示器的班次、車次、車種、狀態、備註與時鐘。
- 自訂列車停靠站、誤點、停駛及即將進站狀態。
- 支援中英文到站資訊與跑馬燈。
- 可選擇車站，手動或自動同步 TDX 列車資料。

## 如何使用

### 線上使用

開啟[線上模擬器](https://oxayuanxo.github.io/TR-PIDS-Simulator/)，不需要安裝或註冊。

1. 點擊右下角的齒輪進入設定。
2. 編輯班次、顯示器或跑馬燈內容。
3. 點擊「返回主畫面」查看結果。

設定會保存在目前使用的瀏覽器中。

### 在本機開啟

下載這個專案後，直接用瀏覽器開啟 `index.html` 即可，不需要安裝套件。

## 使用 TDX 即時資料

這是可選功能；不設定也能使用手動編輯模式。

1. 在 [TDX 平臺](https://tdx.transportdata.tw/)申請 API 金鑰。
2. 進入模擬器設定的「TDX 即時同步」。
3. 選擇車站與同步模式，輸入 Client ID 和 Client Secret。
4. 點擊「測試連線」或「立即同步」。

TDX 金鑰只保存在目前分頁的暫存空間，關閉分頁後就會清除。實際顯示內容取決於 TDX 回傳的資料，部分車站可能沒有月台資訊。

## 資料來源｜Data Source & Attribution

This project uses transportation data provided by the Ministry of Transportation and Communications (MOTC) TDX platform.

資料來源：[交通部運輸資料流通服務平臺（TDX）](https://tdx.transportdata.tw/)

本專案使用 TDX 提供之交通運輸資料進行個人開發與展示，資料權利及使用條件依 TDX 平臺相關授權規範辦理。

## 免責聲明｜Disclaimer

This project is an independent, unofficial recreation of the Taiwan Railway (TRA) Passenger Information Display System (PIDS).

- This project is not affiliated with, endorsed by, or associated with Taiwan Railway Corporation.
- All source code was independently developed for educational and research purposes.
- Taiwan Railway’s trademarks, logos, and other third-party materials remain the property of their respective owners.
- Any third-party materials used in this project are subject to their respective licenses.

本專案僅供學習、研究及技術展示使用，與國營臺灣鐵路股份有限公司無任何官方合作或隸屬關係。顯示內容不應作為實際乘車依據。
