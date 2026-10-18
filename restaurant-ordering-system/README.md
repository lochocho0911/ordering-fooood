# 美味食堂｜HTML 購物車式點餐系統

純前端（HTML5 + CSS3 + JavaScript）的餐廳點餐展示網站，單一 `index.html`，不需後端、不需建置，可直接部署至 GitHub Pages。

## 系統功能
- 瀏覽 12 道餐點，依「全部／主餐／小菜／飲料／甜點」分類切換
- 加入購物車、增減數量、刪除餐點、清空購物車（含確認提示）
- 即時計算小計、總數量與總金額（新台幣整數）
- 訂單確認視窗（返回修改／確認完成）、訂單完成畫面、重新點餐
- 響應式設計：桌面雙欄、手機單欄並提供底部購物車列
- 圖片載入失敗時自動改用 `images/placeholder.svg`（僅替換一次，不會無限重試）

## 使用技術
原生 HTML5、CSS3、JavaScript，無外部函式庫、無 API Key、無 Node.js。

## 資料夾結構
```text
restaurant-ordering-system/
├── index.html
├── README.md
├── .gitignore
└── images/
    ├── placeholder.svg
    └── （放入 12 張餐點照片，檔名見下表）
```

## 如何在本機執行
下載專案後，直接雙擊 `index.html` 以瀏覽器開啟即可。

## 如何更換餐點圖片
把照片（建議 800 × 600、4:3）放進 `images/`，檔名須與下列完全一致（**大小寫也要相同**）：

| 餐點 | 檔名 |
|---|---|
| 香酥雞排飯 | chicken-rice.jpg |
| 滷肉飯 | braised-pork-rice.jpg |
| 排骨飯 | pork-chop-rice.jpg |
| 紅燒牛肉麵 | beef-noodles.jpg |
| 燙青菜 | vegetables.jpg |
| 滷蛋 | braised-egg.jpg |
| 黃金泡菜 | kimchi.jpg |
| 紅茶 | black-tea.jpg |
| 奶茶 | milk-tea.jpg |
| 冬瓜茶 | winter-melon-tea.jpg |
| 焦糖布丁 | pudding.jpg |
| 巧克力蛋糕 | chocolate-cake.jpg |

放入後不需修改程式。尚未放入的圖片會顯示預設圖。

## 如何修改菜單與價格
用文字編輯器開啟 `index.html`，找到 `MenuData.items`，修改各餐點的 `name`、`price`、`image`、`description` 即可。價格只存在這一處，其他計算都會自動沿用。

## GitHub Pages 部署步驟
1. 在 GitHub 建立新的 Repository。
2. 上傳完整專案（`index.html` 必須在根目錄，並包含 `images/` 資料夾）。
3. 開啟 Repository 的 **Settings**。
4. 進入 **Pages**。
5. Source 選擇 **Deploy from a branch**。
6. Branch 選擇 **main**，資料夾選 **/(root)**。
7. 按 **Save**，等待約 1–3 分鐘。
8. 開啟 `https://<帳號>.github.io/<儲存庫名稱>/` 進行測試。

> 注意：GitHub Pages 的檔名區分大小寫，`Chicken-Rice.jpg` 與 `chicken-rice.jpg` 會被視為不同檔案，請務必與上表一致。

## 系統限制
- 純展示用途，無登入、會員、後端、付款、訂單歷史、折扣、庫存功能
- 不使用 localStorage／sessionStorage，重新整理網頁後購物車會清空
