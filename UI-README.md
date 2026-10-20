# Mark4 UI 設計分拆說明

介面樣式已從單檔拆出，方便單獨修改外觀而不動到業務邏輯。

## 檔案

| 檔案 | 用途 |
|------|------|
| `mark4.html` | 結構（頁面、表單、彈窗）+ 邏輯腳本 |
| `mark4-ui.css` | **全部 UI 設計**（色彩、排版、元件、深色模式、RWD） |

兩個檔需放在**同一目錄**，用瀏覽器開啟 `mark4.html` 即可。

## 改外觀從哪改

編輯 **`mark4-ui.css`** 頂部的 Design tokens：

```css
:root {
  --primary: #4F46E5;      /* 主色 */
  --income: #10B981;       /* 收入綠 */
  --expense: #F43F5E;      /* 支出紅 */
  --bg: #EEF2F6;           /* 背景 */
  --card: #FFFFFF;         /* 卡片 */
  --radius-lg: 20px;       /* 大圓角 */
  --nav-h: 68px;           /* 底欄高度 */
  /* … */
}
```

深色模式在檔案後半的 `[data-theme="dark"] { … }`。

## 區塊索引（css 內已標註）

1. Design tokens  
2. Base / Layout  
3. Buttons  
4. Cards / Surfaces  
5. Month nav / Sections  
6. Bars / Charts  
7. Filters  
8. Records / Day groups  
9. Forms / Modal  
10. Bottom nav  
11. Accounts / Assets  
12. Analysis / Year  
13. Category / chips  
14. Budget / Savings  
15. Responsive  
16. Dark mode  
17. UI polish  

## 若要再合併成單檔部署

把 `mark4-ui.css` 內容貼回 `mark4.html` 的 `<head>`：

```html
<style>
  /* 貼上 mark4-ui.css 全文 */
</style>
```

並移除 `<link rel="stylesheet" href="mark4-ui.css">`。
