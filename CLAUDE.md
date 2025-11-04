# HTML簡報製作指南

## 專案概述
本專案使用HTML5 UP的Editorial模板來創建專業的HTML簡報，取代傳統的PowerPoint格式。這種方法提供更好的響應式設計、互動性和網頁分享能力。

## 工作流程

### Markdown到HTML簡報轉換流程
本專案支援從Markdown報告檔案自動生成HTML簡報的工作流程：

1. **準備Markdown報告檔案** - 包含完整的報告內容和結構
2. **內容解析與對應** - 將Markdown元素對應到HTML模板組件
3. **元素選擇與配置** - 從editor-temp資源中選擇合適的UI組件
4. **HTML生成與客製化** - 生成最終的HTML簡報檔案
5. **預覽與調整** - 檢視效果並進行細節調整

### 協作方式
- 您提供結構化的Markdown報告檔案
- Claude分析內容並建議最適合的HTML組件
- 自動生成對應的HTML簡報代碼
- 支援迭代調整和優化

## 可用資源

### 模板檔案
- `editor-temp/index.html` - 主要模板檔案
- `editor-temp/elements.html` - UI元素展示頁面
- `editor-temp/generic.html` - 通用內容頁面

### 樣式資源
- `editor-temp/assets/css/main.css` - 編譯後的主要樣式
- `editor-temp/assets/sass/` - SASS源碼檔案
  - `main.scss` - 主樣式檔案
  - `base/` - 基礎樣式（重置、字體、頁面）
  - `components/` - 元件樣式（按鈕、表單、圖片等）
  - `layout/` - 佈局樣式（標題、導航、側邊欄等）

### JavaScript功能
- `editor-temp/assets/js/main.js` - 主要互動功能
- `editor-temp/assets/js/jquery.min.js` - jQuery庫
- `editor-temp/assets/js/breakpoints.min.js` - 響應式斷點
- `editor-temp/assets/js/util.js` - 工具函數

### 圖片資源
- `editor-temp/images/` - 11張示例圖片（pic01.jpg ~ pic11.jpg）

## 簡報架構建議

### 1. 簡報首頁結構
```html
<!-- Banner區域 - 作為簡報封面 -->
<section id="banner">
    <div class="content">
        <header>
            <h1>簡報標題</h1>
            <p>副標題或簡要描述</p>
        </header>
        <p>簡報摘要內容...</p>
    </div>
    <span class="image object">
        <img src="images/cover-image.jpg" alt="封面圖片" />
    </span>
</section>
```

### 2. 內容章節劃分
```html
<!-- 主要內容章節 -->
<section>
    <header class="major">
        <h2>章節標題</h2>
    </header>
    <!-- 章節內容 -->
</section>
```

### 3. 重點內容展示
使用features區塊展示重點：
```html
<div class="features">
    <article>
        <span class="icon fa-chart-bar"></span>
        <div class="content">
            <h3>數據分析</h3>
            <p>重點說明...</p>
        </div>
    </article>
</div>
```

## 簡報專用樣式自定義

### 1. 創建簡報導航
在側邊欄menu區域添加簡報章節導航：
```html
<nav id="menu">
    <header class="major">
        <h2>簡報大綱</h2>
    </header>
    <ul>
        <li><a href="#intro">介紹</a></li>
        <li><a href="#analysis">分析</a></li>
        <li><a href="#conclusion">結論</a></li>
    </ul>
</nav>
```

### 2. 章節分頁效果
添加CSS實現分頁效果：
```css
.slide-section {
    min-height: 100vh;
    padding: 2rem 0;
    border-bottom: 2px solid #f4f4f4;
}

.slide-section:last-child {
    border-bottom: none;
}
```

### 3. 圖表和數據視覺化
```html
<!-- 數據展示區域 -->
<div class="row">
    <div class="col-6 col-12-medium">
        <div class="box">
            <h3>關鍵數據</h3>
            <p class="stat-number">85%</p>
            <p>成長率</p>
        </div>
    </div>
</div>
```

## 文字排版最佳實踐

本節整理了參考 `inquiry-rule-presentation.html` 的優秀文字排版設計，確保每次製作簡報都能保持一致且專業的視覺效果。

### 完整樣式模板

在HTML檔案的 `<head>` 區塊中加入以下自訂樣式：

```html
<style>
    /* 章節分頁效果 */
    .slide-section {
        min-height: 100vh;
        padding: 2rem 0;
        border-bottom: 2px solid #f4f4f4;
    }

    .slide-section:last-child {
        border-bottom: none;
    }

    /* 數據數字樣式 - 用於重要統計數據 */
    .stat-number {
        font-size: 2em;
        font-weight: bold;
        color: #f56a6a;
        margin: 0;
    }

    /* 強調框樣式 - 用於重要提醒和註記 */
    .highlight-box {
        background: #f7f7f7;
        border-left: 4px solid #f56a6a;
        padding: 1rem;
        margin: 1rem 0;
    }
</style>
```

### 樣式使用說明

#### 1. 數據數字樣式 (`.stat-number`)

**設計規格：**
- 字體大小：`2em`（是正常文字的2倍）
- 字體粗細：`bold`（粗體）
- 顏色：`#f56a6a`（紅色系）
- 外距：`0`（無外距）

**適用場景：**
- 百分比數據（如：30%、40%）
- 關鍵指標數字
- 統計結果展示
- 表格中的重要數據

**使用範例：**
```html
<!-- 在表格中使用 -->
<table>
    <tbody>
        <tr>
            <td><strong>課堂表現</strong></td>
            <td><span class="stat-number">30%</span></td>
            <td>參與討論、提問、實驗操作等</td>
        </tr>
    </tbody>
</table>

<!-- 在Box元件中使用 -->
<div class="box">
    <h3>關鍵數據</h3>
    <p class="stat-number">85%</p>
    <p>成長率</p>
</div>
```

#### 2. 強調框樣式 (`.highlight-box`)

**設計規格：**
- 背景色：`#f7f7f7`（淺灰色）
- 左邊框：`4px solid #f56a6a`（紅色粗邊框）
- 內距：`1rem`
- 外距：`1rem 0`（上下各1rem）

**適用場景：**
- 重要註記事項
- 課程規則說明
- 小提醒、警告訊息
- 需要特別注意的內容

**使用範例：**
```html
<!-- 重要註記 -->
<div class="highlight-box">
    <h3>重要註記事項</h3>
    <ul>
        <li><strong>註一：</strong>各項計分方式，將於每次實作主題中再次提醒。</li>
        <li><strong>註二：</strong>各項表單、紀錄，原則上當次課程結束前完成。</li>
        <li><strong>註三：</strong>課程期間，請勿處理非本課程事務!!</li>
    </ul>
</div>

<!-- 小提醒 -->
<div class="highlight-box">
    <h3><span class="icon solid fa-lightbulb"></span> 小提醒</h3>
    <p>遵守以上規則，不僅能避免扣分，更能創造良好的學習環境。</p>
</div>
```

#### 3. 章節分頁樣式 (`.slide-section`)

**設計規格：**
- 最小高度：`100vh`（占滿整個螢幕高度）
- 內距：`2rem 0`（上下各2rem）
- 下邊框：`2px solid #f4f4f4`（淡灰色分隔線）
- 最後一個章節無下邊框

**適用場景：**
- 每個主要章節
- 需要分頁效果的內容區塊
- 簡報各大主題分隔

**使用範例：**
```html
<!-- 計分方式章節 -->
<section id="scoring" class="slide-section">
    <header class="major">
        <h2><span class="icon solid fa-chart-bar"></span> 計分方式</h2>
    </header>
    <!-- 章節內容 -->
</section>

<!-- 請假問題章節 -->
<section id="absence" class="slide-section">
    <header class="major">
        <h2><span class="icon solid fa-calendar-times"></span> 請假問題</h2>
    </header>
    <!-- 章節內容 -->
</section>
```

### HTML標籤使用規範

#### 1. 標題層級標準

**h1 標題（主標題）**
- 用途：簡報封面的主標題
- 出現位置：Banner區域
- 每個簡報僅使用一次
- 範例：`<h1>自然探究與實作探究入門</h1>`

**h2 標題（章節標題）**
- 用途：各大章節的標題
- 搭配：`class="major"` 增強視覺效果
- 可加入圖示增加辨識度
- 範例：`<h2><span class="icon solid fa-chart-bar"></span> 計分方式</h2>`

**h3 標題（小節標題）**
- 用途：章節內的子主題
- 位置：列表項目、Box內容、Features網格等
- 範例：`<h3>通知義務</h3>`、`<h3>重要註記事項</h3>`

#### 2. 文字強調方式

**粗體強調 (`<strong>`)**
- 用於重要欄位名稱
- 用於關鍵規則說明
- 用於需要特別注意的內容
- 範例：`<strong>課堂表現</strong>`、`<strong>若課程有請假，請寫信通知老師</strong>`

**斜體說明 (`<em>`)**
- 用於次要說明文字
- 用於補充資訊
- 範例：`<em>(若有疑問，先問同組同學、再問任課老師)</em>`

**組合使用**
```html
<p><strong>若是當週作業，請於下次上課前補完作業</strong></p>
<p><strong>請自行補作課程規定作業 (加註當日請○○假)。</strong><br />
<em>(若有疑問，先問同組同學、再問任課老師)</em></p>
```

#### 3. 表格內的文字處理

**標準表格結構**
```html
<div class="table-wrapper">
    <table>
        <thead>
            <tr>
                <th>計分項目</th>
                <th>佔比</th>
                <th>細節</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td><strong>課堂表現</strong></td>
                <td><span class="stat-number">30%</span></td>
                <td>參與討論、提問、實驗操作/考試、課程出缺席等</td>
            </tr>
        </tbody>
    </table>
</div>
```

**表格文字規範：**
- 表頭 (`<th>`)：使用模板預設樣式，無需額外設定
- 重要欄位：使用 `<strong>` 標籤
- 數據欄位：使用 `.stat-number` 類別
- 說明欄位：使用正常段落文字

### 完整範例：綜合應用

以下是一個完整的章節範例，展示如何綜合運用以上所有排版技巧：

```html
<section id="scoring" class="slide-section">
    <header class="major">
        <h2><span class="icon solid fa-chart-bar"></span> 計分方式</h2>
    </header>

    <!-- 數據表格 -->
    <div class="table-wrapper">
        <table>
            <thead>
                <tr>
                    <th>計分項目</th>
                    <th>佔比</th>
                    <th>細節</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td><strong>課堂表現</strong></td>
                    <td><span class="stat-number">30%</span></td>
                    <td>參與討論、提問、實驗操作/考試、課程出缺席等</td>
                </tr>
                <tr>
                    <td><strong>實驗相關紀錄</strong></td>
                    <td><span class="stat-number">40%</span></td>
                    <td>科學筆記、實驗學習單、實驗書面報告等</td>
                </tr>
                <tr>
                    <td><strong>簡報與分享能力</strong></td>
                    <td><span class="stat-number">30%</span></td>
                    <td>簡報製作、上臺發表、同儕評鑑等</td>
                </tr>
            </tbody>
        </table>
    </div>

    <!-- 重要註記框 -->
    <div class="highlight-box">
        <h3>重要註記事項</h3>
        <ul>
            <li><strong>註一：</strong>各項計分方式，將於每次實作主題中再次提醒。</li>
            <li><strong>註二：</strong>各項表單、紀錄，原則上當次課程結束前完成；或於下次上課前交回、不補交。</li>
            <li><strong>註三：</strong>課程期間，請勿處理非本課程事務!! (無論做完與否!!)</li>
        </ul>
    </div>
</section>
```

### 排版檢查清單

製作簡報時，請確認以下事項：

**CSS樣式檢查**
- [ ] 已在 `<head>` 中加入完整的自訂樣式
- [ ] `.stat-number` 樣式設定正確（2em、粗體、紅色）
- [ ] `.highlight-box` 樣式設定正確（灰底、紅色左邊框）
- [ ] `.slide-section` 樣式設定正確（100vh、分隔線）

**HTML結構檢查**
- [ ] 每個主要章節使用 `.slide-section` 類別
- [ ] 章節標題使用 `<h2 class="major">`
- [ ] 重要數據使用 `.stat-number` 類別
- [ ] 註記事項使用 `.highlight-box` 包裹

**文字標記檢查**
- [ ] 重要欄位使用 `<strong>` 標籤
- [ ] 次要說明使用 `<em>` 標籤
- [ ] 表格結構使用 `<div class="table-wrapper">` 包裹
- [ ] 圖示搭配標題適當使用

**視覺效果檢查**
- [ ] 數據數字醒目易讀
- [ ] 強調框視覺層次分明
- [ ] 章節分隔清晰
- [ ] 整體排版一致協調

### 色彩使用建議

基於 inquiry-rule-presentation.html 的配色方案：

**主要色彩：**
- 強調色：`#f56a6a`（紅色系）- 用於數據、邊框、圖示
- 背景色：`#f7f7f7`（淺灰色）- 用於強調框背景
- 分隔線：`#f4f4f4`（更淡的灰色）- 用於章節分隔

**使用原則：**
- 重要數據使用紅色強調
- 背景使用淡色系不搶眼
- 保持色彩一致性
- 避免過多色彩造成視覺混亂

這些排版最佳實踐確保了簡報的專業性、可讀性和視覺一致性，是製作高品質HTML簡報的關鍵要素。

## 互動功能增強

### 1. 平滑滾動導航
添加平滑滾動到章節：
```javascript
// 在main.js中添加
$('a[href^="#"]').on('click', function(e) {
    e.preventDefault();
    var target = $(this.getAttribute('href'));
    if(target.length) {
        $('html, body').animate({
            scrollTop: target.offset().top - 100
        }, 1000);
    }
});
```

### 2. 進度指示器
```html
<!-- 添加到header中 -->
<div class="progress-bar">
    <div class="progress"></div>
</div>
```

### 3. 簡報控制按鈕
```html
<!-- 添加簡報控制 -->
<div class="slide-controls">
    <button onclick="previousSlide()">上一頁</button>
    <button onclick="nextSlide()">下一頁</button>
    <button onclick="toggleFullscreen()">全螢幕</button>
</div>
```

## 內容組織建議

### 1. 簡報結構模板
```
1. 封面 (Banner)
2. 議程/大綱 (Features區塊)
3. 主要內容章節 (多個Section)
4. 數據展示 (Posts格式轉換為圖表)
5. 結論與行動方案
6. Q&A或聯絡資訊
```

### 2. 視覺層次
- 使用`<h1>`作為簡報標題
- 使用`<h2 class="major">`作為章節標題
- 使用`<h3>`作為小節標題
- 重要數據使用大字體和對比色

### 3. 圖片使用建議
- 替換現有pic01-pic11.jpg為您的簡報圖片
- 保持1200x800像素左右的解析度
- 使用高品質、相關性強的圖片

## 部署和分享

### 1. 本地預覽
直接開啟`index.html`或設置本地伺服器：
```bash
# 使用Python簡單伺服器
python -m http.server 8000
# 或使用Node.js
npx serve .
```

### 2. 網頁部署選項
- GitHub Pages
- Netlify
- Vercel
- 任何靜態網站託管服務

### 3. 離線簡報
- 所有資源已本地化，可離線使用
- 建議打包為zip檔案分享

## 客製化提示

### 1. 品牌色彩
修改`assets/sass/libs/_vars.scss`中的顏色變數

### 2. 字體調整
在`assets/sass/base/_typography.scss`中調整字體樣式

### 3. 響應式調整
模板已支援響應式設計，適合各種螢幕尺寸展示

## 常用簡報元素

### 1. 重點框
```html
<div class="box">
    <h3>重點標題</h3>
    <p>重點內容...</p>
</div>
```

### 2. 按鈕行動呼籲
```html
<ul class="actions">
    <li><a href="#next-section" class="button big">繼續閱讀</a></li>
</ul>
```

### 3. 圖片說明
```html
<span class="image fit">
    <img src="images/chart.jpg" alt="數據圖表" />
</span>
```

## Markdown轉換指南

### Markdown檔案結構規範

#### 1. 基本結構
```markdown
# 簡報標題
> 簡報副標題或摘要

## 章節一：介紹
<!-- slide-type: banner -->
### 重點一
- 列點內容
- 重要資訊

![封面圖片](images/pic01.jpg)

## 章節二：分析
<!-- slide-type: features -->
### 數據重點
<!-- icon: fa-chart-bar -->
重要的分析內容...

### 市場趨勢  
<!-- icon: fa-trending-up -->
趨勢分析內容...

## 章節三：結論
<!-- slide-type: section -->
> 重要結論引用

**行動方案：**
1. 第一步行動
2. 第二步行動
3. 第三步行動
```

#### 2. 特殊標記說明
- `<!-- slide-type: banner -->` - 指定使用banner區塊
- `<!-- slide-type: features -->` - 指定使用features網格
- `<!-- slide-type: section -->` - 指定使用一般section
- `<!-- icon: fa-icon-name -->` - 指定FontAwesome圖示
- `<!-- image-style: fit/object -->` - 指定圖片顯示樣式

### Markdown元素對應表

| Markdown元素 | HTML組件 | 使用場景 |
|-------------|--------|---------|
| `# 標題` | Banner區塊 | 簡報封面、主標題 |
| `## 章節標題` | Section with major header | 主要章節分割 |
| `### 小節標題` | H3標題 | 章節內子主題 |
| `- 列表項目` | Features網格 | 重點條列、特色展示 |
| `> 引用` | Box組件 | 重要說明、強調內容 |
| `![圖片](path)` | Image組件 | 圖片展示、圖表 |
| `**粗體**` | Strong標籤 | 重點文字 |
| `數字統計` | 大字體數據展示 | 關鍵數據、指標 |
| `連結` | Button組件 | 行動呼籲、導航 |
| `表格` | HTML Table | 數據比較、清單 |
| `代碼區塊` | Code區塊 | 技術內容、範例 |

### 自動轉換流程

#### 1. 內容解析階段
```
Markdown解析 → 結構分析 → 元素識別 → 組件選擇
```

#### 2. 組件對應邏輯
- **標題層級** → HTML標題標籤 + 對應樣式
- **內容類型** → 選擇最適合的展示組件
- **圖片資源** → 自動配置圖片展示方式
- **數據內容** → 轉換為視覺化元素

#### 3. Claude輔助轉換
當您提供Markdown檔案時，Claude會：
1. 分析內容結構和類型
2. 建議最適合的HTML組件
3. 生成對應的HTML代碼
4. 提供樣式和佈局建議
5. 協助進行細節調整

### 元素庫參考

#### 可用HTML組件清單

**佈局組件：**
- `Banner` - 主要標題區塊（適合封面）
- `Section` - 一般內容區塊（適合章節）
- `Features` - 網格展示區塊（適合重點列表）
- `Posts` - 卡片展示區塊（適合案例展示）

**內容組件：**
- `Box` - 強調框（適合重要資訊）
- `Button` - 按鈕（適合行動呼籲）
- `Image` - 圖片展示（多種樣式）
- `Table` - 表格（適合數據比較）
- `List` - 清單（有序/無序）

**特殊組件：**
- `Icons` - FontAwesome圖示
- `Contact` - 聯絡資訊區塊
- `Mini-posts` - 小型內容卡片
- `Actions` - 行動按鈕組

### 最佳實踐建議

#### 1. Markdown撰寫建議
- 使用清晰的標題層級
- 善用特殊標記指定組件類型
- 保持內容結構的邏輯性
- 預先準備好所需的圖片資源

#### 2. 轉換效率提升
- 遵循標準的Markdown格式
- 使用語義化的標題和內容
- 適當使用引用和強調
- 合理規劃圖片和媒體資源

#### 3. 品質控制
- 轉換後檢查響應式效果
- 確認圖片和連結的正確性
- 測試導航和互動功能
- 進行跨瀏覽器相容性測試

### 範例：完整轉換流程

#### 輸入：Markdown報告
```markdown
# 2024年度業績報告
> 超越目標，創造佳績

## 執行摘要
<!-- slide-type: features -->
### 營收成長
<!-- icon: fa-chart-line -->
年度營收成長25%，超越原定目標

### 市場擴張
<!-- icon: fa-globe -->
成功進入3個新市場區域

## 詳細分析
<!-- slide-type: section -->
![營收圖表](images/revenue-chart.jpg)

> "今年是公司歷史上最成功的一年" - CEO

**關鍵成功因素：**
1. 產品創新
2. 團隊合作
3. 市場策略
```

#### 輸出：HTML簡報代碼
Claude會自動生成對應的HTML結構，包括適當的CSS類別和JavaScript功能。

這個指南提供了將Editorial模板轉換為專業HTML簡報的完整方法，特別強化了Markdown到HTML的自動轉換流程。您可以根據具體需求調整和擴展這些建議。

## 子目錄專案工作流程

### 專案組織架構

本工作流程採用子目錄模式，每個簡報專案都有獨立的子目錄，以確保專案間的獨立性和檔案組織的清晰度。

#### 標準目錄結構
```
claude-slides/
├── editor-temp/              # 共用的模板資源
│   ├── assets/
│   │   ├── css/main.css     # 共用樣式檔案
│   │   └── js/              # 共用JavaScript檔案
│   ├── index.html           # 主要模板檔案
│   └── elements.html        # UI元素展示頁面
├── project-name-1/          # 專案一子目錄
│   ├── project-name-1.md    # Markdown報告檔案
│   ├── project-name-1-presentation.html  # HTML簡報檔案
│   ├── cover-image.jpg      # 專案專用圖片
│   ├── chart-1.png          # 專案專用圖片
│   └── diagram.png          # 專案專用圖片
├── project-name-2/          # 專案二子目錄
│   ├── project-name-2.md
│   ├── project-name-2-presentation.html
│   └── images...
└── CLAUDE.md               # 本指南檔案
```

### 路徑處理標準化

#### 1. CSS和JavaScript資源路徑
子目錄中的HTML檔案應使用相對路徑指向共用的editor-temp資源：

```html
<!-- CSS資源 -->
<link rel="stylesheet" href="../editor-temp/assets/css/main.css" />

<!-- JavaScript資源 -->
<script src="../editor-temp/assets/js/jquery.min.js"></script>
<script src="../editor-temp/assets/js/browser.min.js"></script>
<script src="../editor-temp/assets/js/breakpoints.min.js"></script>
<script src="../editor-temp/assets/js/util.js"></script>
<script src="../editor-temp/assets/js/main.js"></script>
```

#### 2. 圖片資源路徑
子目錄中的圖片檔案應使用直接檔名（同目錄相對路徑）：

```html
<!-- 專案專用圖片 -->
<img src="cover-image.jpg" alt="封面圖片" />
<img src="chart-1.png" alt="數據圖表" />
<img src="diagram.png" alt="流程圖" />
```

#### 3. 路徑模板
創建新專案時，HTML檔案的路徑配置模板：

```html
<!DOCTYPE HTML>
<html>
<head>
    <title>專案標題 - 簡報</title>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1, user-scalable=no" />
    <!-- 共用CSS資源 - 使用 ../ 指向上層目錄 -->
    <link rel="stylesheet" href="../editor-temp/assets/css/main.css" />
</head>
<body>
    <!-- 簡報內容 -->
    <div id="wrapper">
        <div id="main">
            <div class="inner">
                <!-- 使用專案內圖片 - 直接檔名 -->
                <img src="project-cover.jpg" alt="專案封面" />
            </div>
        </div>
    </div>
    
    <!-- 共用JavaScript資源 - 使用 ../ 指向上層目錄 -->
    <script src="../editor-temp/assets/js/jquery.min.js"></script>
    <script src="../editor-temp/assets/js/browser.min.js"></script>
    <script src="../editor-temp/assets/js/breakpoints.min.js"></script>
    <script src="../editor-temp/assets/js/util.js"></script>
    <script src="../editor-temp/assets/js/main.js"></script>
</body>
</html>
```

### 專案建立標準作業程序 (SOP)

#### 步驟一：建立專案子目錄
1. 在 `claude-slides/` 下創建新的子目錄
2. 目錄命名慣例：使用描述性名稱，避免空格和特殊字元
   - ✅ 好的命名：`inquiry-rule`, `annual-report-2024`, `product-launch`
   - ❌ 避免命名：`新專案`, `project 1`, `my-presentation!`

#### 步驟二：準備專案檔案
**必要檔案清單：**
- [ ] `{project-name}.md` - Markdown報告檔案
- [ ] `{project-name}-presentation.html` - HTML簡報檔案
- [ ] 專案相關圖片檔案（.jpg, .png等）

#### 步驟三：設置正確的路徑
**路徑檢查清單：**
- [ ] CSS路徑：確認使用 `../editor-temp/assets/css/main.css`
- [ ] JavaScript路徑：確認所有JS檔案使用 `../editor-temp/assets/js/`
- [ ] 圖片路徑：確認使用直接檔名（無 `../` 前綴）

#### 步驟四：本地測試
1. 在瀏覽器中開啟HTML檔案
2. 檢查樣式是否正確載入
3. 檢查圖片是否正常顯示
4. 測試JavaScript功能（如導航、搜尋等）

#### 步驟五：部署準備
**GitHub部署檢查：**
- [ ] 確認所有圖片檔案已加入專案目錄
- [ ] 確認HTML檔案中的圖片路徑為直接檔名
- [ ] 確認CSS/JS路徑指向 `../editor-temp/`
- [ ] 測試線上版本的功能完整性

### 常見問題與解決方案

#### 問題一：本地能顯示，上傳GitHub後圖片無法顯示
**原因：** 圖片路徑設置錯誤
**解決方案：**
1. 檢查圖片是否已上傳到正確的子目錄
2. 確認HTML中的圖片路徑為直接檔名（不含 `../`）
3. 檢查檔案名稱大小寫是否一致

#### 問題二：樣式無法載入，排版混亂
**原因：** CSS/JS路徑設置錯誤
**解決方案：**
1. 確認使用 `../editor-temp/assets/css/main.css`
2. 檢查 `editor-temp` 目錄是否存在於上層目錄
3. 確認所有JavaScript檔案路徑都有 `../` 前綴

#### 問題三：圖片檔案過大導致載入緩慢
**解決方案：**
1. 壓縮圖片檔案（建議1200x800像素以下）
2. 使用適當的圖片格式（JPG用於照片，PNG用於圖表）
3. 考慮使用WebP格式提升載入效率

#### 問題四：專案間檔案衝突
**預防措施：**
1. 每個專案使用獨立的子目錄
2. 圖片檔案使用描述性命名
3. 避免使用通用檔案名（如 `image1.jpg`）

### 路徑診斷工具

#### 快速檢查命令
```bash
# 檢查目錄結構
ls -la claude-slides/
ls -la claude-slides/project-name/

# 檢查檔案存在性
find claude-slides/project-name -name "*.jpg" -o -name "*.png"

# 檢查HTML中的路徑
grep -n "src=" claude-slides/project-name/*.html
```

#### 路徑驗證清單
建立新專案時，可使用此清單快速驗證：

```markdown
## 路徑驗證清單

### CSS/JS 資源路徑
- [ ] `<link rel="stylesheet" href="../editor-temp/assets/css/main.css" />`
- [ ] `<script src="../editor-temp/assets/js/jquery.min.js"></script>`
- [ ] `<script src="../editor-temp/assets/js/browser.min.js"></script>`
- [ ] `<script src="../editor-temp/assets/js/breakpoints.min.js"></script>`
- [ ] `<script src="../editor-temp/assets/js/util.js"></script>`
- [ ] `<script src="../editor-temp/assets/js/main.js"></script>`

### 圖片資源路徑
- [ ] 封面圖片：`<img src="filename.jpg">` (無 ../ 前綴)
- [ ] 內容圖片：`<img src="filename.png">` (無 ../ 前綴)
- [ ] 側邊欄圖片：`<img src="filename.png">` (無 ../ 前綴)

### 檔案存在性
- [ ] 所有引用的圖片檔案都存在於專案子目錄中
- [ ] 檔案名稱大小寫一致
- [ ] 檔案格式正確（.jpg, .png等）
```

### 最佳實踐建議

#### 1. 檔案命名規範
- 使用英文和數字，避免中文檔名
- 使用連字符分隔單詞：`cover-image.jpg`
- 保持檔名簡潔且具描述性

#### 2. 圖片優化建議
- 封面圖片：1200x800像素，JPG格式
- 圖表截圖：PNG格式，保持清晰度
- 檔案大小控制在500KB以下

#### 3. 版本控制
- 定期備份專案檔案
- 使用Git進行版本控制
- 建立README.md說明專案內容

#### 4. 協作開發
- 建立專案模板檔案
- 制定統一的命名規範
- 使用Issue追蹤待修復問題

這個子目錄工作流程確保了專案的獨立性、路徑的一致性，以及部署的穩定性。遵循這些標準將大幅提升開發效率和降低錯誤發生率。