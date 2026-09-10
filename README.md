# RideLife 商品註冊流程 — 互動提案原型

Giant RideLife App「商品註冊」流程的 HTML 互動 prototype。每個版本都是**單一 HTML 檔**，字型、圖片全部內嵌，離線可開、可直接寄給客戶，用瀏覽器打開即可操作。

## 線上預覽

| 版本 | 預覽 | 說明 |
|---|---|---|
| **0910 序號問題回報**（最新） | [serial-issue-report.html](https://bct-tpe.github.io/ridelife-product-registration/serial-issue-report.html) | 本版提案，見下方說明 |
| 0825 商品註冊 | [add-product-final-0825.html](https://bct-tpe.github.io/ridelife-product-registration/add-product-final-0825.html) | 前版：Add Product → Product Found → 保固流程（Verify Warranty / Policy / Checklist / Signature / Warranty Card）、Giant Certified、非 Giant 車表單 |

畫面右側的 **Demo Tips / Switch Case** 面板是簡報用的操作提示（在手機畫面外），非 App 介面的一部分。

## 0910 版提案理念

商品註冊是 RideLife 的第一步，但序號環節有三種常見的卡關情境：**刷不到條碼**、**序號查得到但商品資訊錯誤**、**序號輸入正確 App 卻查無資料**。目前 user 遇到這些狀況只能中斷註冊、自行聯絡客服，流程就斷在門口。

這版提案把「序號有問題」變成一條**可回報、可追蹤的閉環**：

> 查無序號 → 建議重試 → 一鍵回報（自動帶入情境與序號）→ 表單送出取得 Issue 編號 → 客服回覆推播通知 → App 內查看處理進度

讓卡關的 user 留在 App 裡完成回報，也讓門市／客服拿到結構化的問題資訊（問題類型、序號、購買證明照片、取車門市）。

## 本版新增功能

1. **序號輸入與查無序號對話框** — Start with Serial Number 可實際輸入（含手機鍵盤模擬）；輸入 `111` 或錯誤 12 碼序號按 LOOK UP 會跳「Serial Number Not Found」：主按鈕 TRY AGAIN 建議重試，下方「Still can't find it? Report an issue」進入回報。
2. **QR 掃描 demo** — 真實相機畫面、半透明遮罩＋掃描框、「Align the QR code within the frame」提示；「Where to find your Serial Number」bottom sheet 教學（依部位切換）；掃到但查無資料時跳「Product Not Found」對話框，同樣可直接回報。
3. **Report Issue 整頁表單** — 問題類型 radio（Barcode won't scan / Incorrect product info / Serial number not found / Other，依入口自動預選並帶入序號）、Issue Description、Pickup Store、Submitted By（唯讀顯示使用者與 Giant ID）、照片上傳（預設帶購買證明＋序號標籤 2 張、可刪除補傳、上限 3 張）、必填欄位驗證。
4. **Find a Store 門市選擇頁** — 參考 App 的 Find a Dealer 設計：搜尋欄、品牌 filter chips、台北門市地圖與定位 pin、4 家門市卡片（地址／電話／距離／服務 tag）；SELECT 選取後帶回表單（店名＋地址），已選取門市顯示灰階 SELECTED 與藍色外框。
5. **送出與 Issue 編號** — Submit 通過驗證後回到 Add Product，toast 顯示「Issue #GS-10281 submitted successfully」，序號欄位清空。
6. **通知閉環** — 客服回覆時右上角鈴鐺出現通知圓點；My Notification 列表置頂顯示「We've Received Your Report」（含未讀圓點）；點入 Issue 詳細頁查看客服回覆與處理狀態（Now being processed）。

## 檔案結構

```
├── serial-issue-report.html      # 0910 序號問題回報（最新）
├── add-product-final-0825.html   # 0825 商品註冊提案
└── assets/                       # 原始素材（掃描底圖、購買證明照片；已內嵌於 HTML）
```
