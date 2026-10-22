# 讀數獨數

香港中學數學教學網站，由蔡樹堅老師使用。靜態網頁，由 GitHub Pages 從 **main 分支根目錄** 提供，無需 build。

- 顯示名稱：讀數獨數
- 語文：繁體中文（香港）
- 公式：課題頁以 [KaTeX](https://katex.org/) 顯示。首頁及課題頁經 jsDelivr 載入 KaTeX；`demo.html`／`problems.html` 已內嵌 KaTeX，離線亦可開啟。

## 資料夾約定

```
teaching/fN/<topic-slug>/<subtopic-slug>/index.html
exam/<compulsory|m1|m2>/<topic-slug>/index.html
```

- `fN`：`f1` 至 `f6`，對應中一至中六。
- `topic-slug`：章或課題組（例：`angles`、`functions`、`circles-basic`）。
- `subtopic-slug`：個別課題。課題頁就是這一層的 `index.html`，固定有三節：**筆記**、**互動 HTML**、**教學影片**。未有檔案的一節寫「陸續上架」，不要刪走該節。
- 公開試按課題分頁：`compulsory` 必修部分、`m1` 延伸部分單元一、`m2` 延伸部分單元二。每頁固定有兩節：**題目**、**答案**。未有內容就保留「陸續上架」。
- 課題名稱依教育局《數學教育學習領域課程指引》（2017）的學習單位。

同層可放 `notes.pdf`、`學生筆記.pdf`、`demo.html`、`problems.html`、`video.mp4`，在課題頁用相對路徑連結。

級別目錄在 `teaching/fN/index.html`。該級尚未有任何課題檔時，目錄頁顯示「陸續上架」。

## 新增一個教學課題

1. 建立 `teaching/fN/<topic-slug>/<subtopic-slug>/`。
2. 新增 `index.html`（可複製現有課題頁），保留筆記、互動 HTML、教學影片三節，並更新麵包屑與標題。
3. 把 PDF、互動 HTML、影片放在同一資料夾，用相對路徑連上。沒有的項目維持「陸續上架」。
4. 在 `teaching/fN/<topic-slug>/index.html`（課題組）及 `teaching/fN/index.html`（級別目錄）加上連結，徽章寫「已上架」。若該級原本只有「陸續上架」空狀態，保留下方課題目錄即可，不必再顯示整級空白提示。
5. 更新首頁「最新上架」（見下）。

## 新增一題公開試課題內容

1. 打開已有的 `exam/compulsory/<topic-slug>/index.html`，或 `exam/m1/...`、`exam/m2/...`。新課題才要新建資料夾；課程清單上的課題頁已建好。
2. 在 **題目**、**答案** 兩節放入內容，取代「陸續上架」。
3. 把該課題在 `exam/compulsory/index.html`（或 `m1`、`m2`）及 `exam/index.html` 的徽章由「陸續上架」改為「已上架」。

甲部(1) 已上架的坐標變換在 `exam/compulsory/coord-transform/`。三角形外角示例在 `exam/compulsory/angles/`，介面示例仍在 `exam/sample/exterior-angle.html`。

## 更新首頁「最新上架」

編輯根目錄 `index.html` 裏 `id="latest"` 的清單。新項目放在 `<ul class="topic-list">` 最上方。每一項包含：

- 連結：課題頁的相對路徑（教學課題用 `teaching/fN/<topic-slug>/<subtopic-slug>/index.html`）
- 標題
- `<small>`：級別 · 課題組 · 已有資源（筆記／互動 HTML／教學影片）
- 徽章：已上架

首頁只保留最近數項，舊項目可刪去清單，但不要刪課題頁本身。

## 本機預覽

```bash
python3 -m http.server 8080
```

瀏覽器開啟 `http://localhost:8080/`。請用本機伺服器，不要直接以 `file://` 開啟，否則部分相對路徑與 PDF 會失效。

## GitHub Pages

倉庫根目錄有 `.nojekyll`，避免 Jekyll 忽略底線開頭的檔案。Pages 來源為 **main** 分支、資料夾 **`/`（root）**。網站位址約為 `https://<user>.github.io/dukdoksu/`。
