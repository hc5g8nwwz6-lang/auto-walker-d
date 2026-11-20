# Pokémon GO Auto Walker D

專為 **iPhone Safari** 設計的繁體中文漸進式網頁應用程式（PWA），整合 **OpenStreetMap**、**Leaflet** 與免費公開的 **OSRM 步行路線服務**，提供真實戶外 GPS 步行紀錄、路線規劃、孵蛋里程計算與 CSV 匯出功能。

## 主要功能

1. **地圖與步行路線規劃**
   - 整合 OpenStreetMap 圖資與即時 GPS 定位顯示。
   - 點擊地圖任意位置即可透過免費 OSRM 服務規劃步行路線，顯示路線距離與預估步行時間。
2. **真實 GPS 步行紀錄**
   - 支援「開始、暫停、繼續、結束並儲存」完整控制流程。
   - 自動過濾 GPS 靜止飄移與異常跳點，即時計算步行距離（km）、平均速度（km/h）與活動時間。
3. **孵蛋里程計算器**
   - 支援 **2 km、5 km、7 km、10 km、12 km** 五種蛋種目標。
   - 步行紀錄會自動累加至目前孵蛋進度，顯示完成百分比、剩餘距離與孵蛋歷史紀錄。
4. **歷史統計與 CSV 匯出**
   - 透過 `localStorage` 本地保存每日步行明細、累計總公里數與總時數。
   - 支援一鍵匯出 UTF-8 BOM 編碼的 `.csv` 報表，iPhone 內建「檔案」或 Numbers App 開啟不亂碼。
5. **iPhone PWA 體驗**
   - 支援「加入主畫面」全螢幕操作、深色遊戲風格 UI、Safe Area 瀏海適配與 Service Worker 基本離線快取。

## 合規與使用聲明

本工具僅提供**真實戶外 GPS 步行運動紀錄與路線輔助**，不包含任何偽造 GPS、虛擬定位、破解或修改《Pokémon GO》之功能。實際遊戲內孵蛋與夥伴里程計算，仍以官方《Pokémon GO》「時時刻刻冒險」機制判定為準。

## 檔案結構

```text
pokemon-go-auto-walker-d/
├── index.html            # 主程式（HTML5 + CSS3 + 原生 JS + Leaflet）
├── manifest.webmanifest  # PWA 設定檔（繁體中文、Standalone 模式）
├── sw.js                 # Service Worker 離線快取腳本
├── icon-192.png          # 192x192 PWA 應用程式圖示
├── icon-512.png          # 512x512 PWA 高解析度圖示
└── README.md             # 專案說明與部署指南
```

## GitHub Pages 部署與 iPhone 安裝步驟

1. 在 GitHub 建立新的公開儲存庫（Repository），例如 `pokemon-go-auto-walker-d`。
2. 將本專案全部 6 個檔案上傳至儲存庫根目錄（`main` 分支）。
3. 進入儲存庫 **Settings > Pages**，在 **Build and deployment** 選擇 `Deploy from a branch`，Branch 選擇 `main` 與 `/ (root)`，點擊 **Save**。
4. 等待約 1～2 分鐘，開啟產生的 HTTPS 網址：
   `https://<你的GitHub帳號>.github.io/pokemon-go-auto-walker-d/`
5. 使用 iPhone **Safari** 開啟該網址，點擊底部中央「分享」按鈕 → 選擇「**加入主畫面**」，即可作為獨立 App 使用並啟用 HTTPS GPS 定位。
