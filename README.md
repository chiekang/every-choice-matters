# 每一個選擇都很重要 · Every Choice Matters

**這個月，市場有什麼食材？ / What's in the market this month?**

一個給課堂與工作坊使用的雙語（繁體中文／English）互動網頁。老師投影在螢幕上，學生用手機開啟，一起認識當季與在地食材，並看見運輸方式與距離如何影響一道菜的碳排。

🔗 **線上版本 / Live:** https://chiekang.github.io/every-choice-matters/

---

## 設計理念

挑選食材時，建議依這個順序思考：

1. **先看當季**：當季食材不需要溫室加溫或長期冷藏。
2. **再看運輸方式**：海運很低、公路中等、空運最高。
3. **最後看距離**：同樣是運輸，越遠累積越多。

「本地」不一定等於「低碳」，但「當季 + 少空運 + 少冷鏈」通常是更好的選擇。此外，肉類（特別是牛肉與羊肉）的碳排遠高於蔬果，這一點往往比產地更重要。

## 功能

- **每月食材**：選擇月份，查看蔬菜、水果、海鮮的當季本地食材，以及超市與量販店常見的進口食材（標示「距離遠／冷鏈／進口」）。
- **台灣縣市產地**：本地蔬果標示主要產地縣市。
- **我想吃**：點選想吃的食材，自動產生 3 到 5 道簡單食譜。
- **每道菜的預估碳排**：進口食材會讓整道菜的碳排變高，並提供同類當季食材的替換建議。
- **碳排小測驗**：隨機抽 9 題二選一，點選後立即揭曉答案與出處。
- **我的承諾**：至少 9 項可選的減碳行動，儲存在自己手機的瀏覽器中（localStorage）。
- **雙語切換**：繁體中文與 English。
- **多地區版本**：目前完成台灣、印尼、德國，其他地區陸續加入。

## 地區進度

| 地區 | 狀態 |
|---|---|
| 台灣 Taiwan | ✅ 已完成 |
| 印尼 Indonesia | ✅ 已完成 |
| 德國 Germany | ✅ 已完成 |
| 日本等其他 10 個地區 | 🚧 規劃中 |

## 碳排估算方法

每道菜的估算由三部分相加：

- **種植／養殖**：份量 × 排放係數。份量預設為蔬果 150 g、海鮮與肉類 100 g，部分食材（如香辛料）另訂。排放係數來自 Poore & Nemecek (2018)，透過 Our World in Data 取得。
- **運輸**（僅進口食材）：距離 × 運輸係數。海運 0.01（常溫）或 0.02（冷藏）、空運 1.13、公路 0.2（常溫）或 0.43（冷藏），單位為 kg CO₂e／公斤·公里。
- **雞蛋**：食譜用到蛋時，每顆以 60 g 計入。

等級：低於 0.3 為低、低於 1.5 為中、其餘為高（單位 kg CO₂e／份）。

**已知限制**
- 野生捕撈海鮮沒有可靠係數，不計入並加註提醒。
- 冷凍食材只計作物係數與運輸，未計冷凍耗能。
- 進口食材的產地、運輸方式與距離是代表性假設，不代表個別商品。
- 所有食材資料為手動整理，**每一筆都標示「待校對」**。使用前請先自行核對。

## 技術

單一 `index.html`，不需要建置、伺服器或外部套件。

- 純 HTML／CSS／JavaScript，資料寫在檔案內。
- 字型：Open Sans 與 Noto Sans TC（Google Fonts）。
- 配色參考 Climate Fresk 社群的視覺規範，支援淺色與深色主題。
- 為手機與投影螢幕設計，不含列印版面。

### 本機預覽

直接用瀏覽器開啟 `index.html` 即可，或：

```bash
python3 -m http.server 8000
# 開啟 http://localhost:8000
```

### 發布

本專案使用 GitHub Pages 從 `main` 分支根目錄發布。推送新版 `index.html` 後，約 1 到 2 分鐘內生效，網址與 QR code 不變。

## 主要資料來源

- Poore, J. & Nemecek, T. (2018). *Reducing food's environmental impacts through producers and consumers.* Science.
- Our World in Data：食物碳排與運輸排放。
- 各地區的產季、產地統計與官方資料，完整清單與連結見網頁內「資料來源」區塊。

## 作者

**李紀綱 (Francis Lee)** — 輔仁大學助理教授、Climate Fresk（氣候拼圖）台灣國家代表。

本頁為教學用途，與 Climate Fresk 國際組織的官方立場無關。

---

# Every Choice Matters (English)

A bilingual (Traditional Chinese / English) interactive page for classrooms and workshops. The teacher projects it, and students open it on their phones to learn which foods are in season and local, and how transport mode and distance change the carbon footprint of a dish.

**Selection order:** in season first, then how it travelled (sea is low, road is medium, air is highest), then distance. Local is not automatically low-carbon, and meat, especially beef and lamb, often matters more than origin.

**Features:** monthly seasonal items (vegetables, fruit, seafood, meat) with imported items flagged as far, cold-chain or imported; main producing counties for Taiwan; "I want to eat" recipe picks with per-dish CO₂e estimates and in-season swap suggestions; a 9-question random quiz; 9+ personal pledges saved in localStorage; Taiwan, Indonesia and Germany editions.

**Method and caveats:** farm-stage factors from Poore & Nemecek (2018) via Our World in Data, plus distance × transport factors for imports. Wild-caught seafood is excluded, freezing energy is not counted, and origins, modes and distances are representative assumptions. All data is hand-curated and marked "待校對" (needs review).

**Run locally:** open `index.html` in a browser. No build step.

**Author:** Francis Lee (李紀綱), Assistant Professor at Fu Jen Catholic University and Climate Fresk Taiwan national representative. This is an educational project and is not an official Climate Fresk publication.
