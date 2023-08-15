# layouting-2023-main-w6

- W6

> <https://rpg.hexschool.com/task/351/show>

- 設計稿：

> <https://www.figma.com/file/1qhYNCLtQHg6qmBnzV5A6y>

---

## LV.2

```markdown
LV2（80、100% 獎品門檻）：至少做 2 頁含 RWD，其中 1 頁必須為首頁
```

- [x] p1-首頁
- [x] p2-登入頁面

---

### 已知問題

1. `hover` 效果失效：`button`、`nav-link`

2. `navbar-collapse` 在手機版加上 `border` 之後，到桌機版拿不掉

3. 導覽列加上 `fixed-top` 會出現鏤空

---

### 自訂變數

#### 更改基礎項目

1. 複製 `variables` 設定到自己的 `variables`

2. `all.scss` 順序

```SCSS
@import "../../node_modules/bootstrap/scss/functions";
@import './utils/variables';

...

@import "../../node_modules/bootstrap";
```

- 講義架構：

> <https://hackmd.io/@hexschool/rJahqpg2h#BS5-SCSS-載入-架構圖講解>

- 文件：

> <https://getbootstrap.com/docs/5.3/customize/sass/#importing>

---

### 開啟文字的響應式變數設定

1. 新增自訂 `utilities`

2. 匯入需要的設定，只修改 `font-size` 加入 `responsive: true`

- 參考來源：

> <https://stackoverflow.com/a/75715691>

---

### 首頁

#### 元件

> <https://bootstrap5.hexschool.com/docs/5.1/components/navbar/#scrolling>
>
> <https://bootstrap5.hexschool.com/docs/5.1/components/card/#image-overlays>
>
> <https://bootstrap5.hexschool.com/docs/5.1/layout/grid/#variable-width-content>
>
> <https://bootstrap5.hexschool.com/docs/5.1/utilities/borders/>

---

#### 跑馬燈

- 參考來源：

> <https://codepen.io/NoNameNote/pen/KKrEgZp>

---

## Screenshot

![Screenshot-Home](./assets/images/Screenshot-Home.png)

---

## 原版指令說明

### Bootstrap 版本

1. 多加入了 Bootstrap 模組
2. 多加入了 Bootstrap JS，讓 dist 編譯出來的 js 可以載入 BS5 JS 套件
3. index.html 加入了些 BS5 範例元件
4. SCSS 範例有變更

### Node.js 版本

- 專案的 Node.js 版本需為 v16 以上
- 查看自己版本指令：`node -v`

---

### 指令列表

- `npm install` - 初次下載該範例專案後，需要使用 npm install 來安裝套件
- `npm run dev` - 執行開發模式
  - 若沒有自動開啟瀏覽器，可嘗試手動在瀏覽器上輸入
    `http://localhost:5173/<專案名稱>/pages/index.html`
- `npm run build` - 執行編譯模式（不會開啟瀏覽器）
- `npm run deploy` - 自動化部署

---

### 資料夾結構

- assets # 靜態資源放置處
  - images # 圖片放置處
  - scss # SCSS 的樣式放置處
    - layout # ejs 模板放置處
    - pages # 頁面放置處

- JavaScript 程式碼可寫在 main.js 檔案

#### 注意事項

- 已將 pages 資料夾內的 index.html 預設為首頁，建議不要任意修改 index.html 的檔案名稱

- .gitignore 檔案是用來忽略掉不該上傳到 GitHub 的檔案（例如 node_modules），請不要移除 .gitignore

### 開發模式的監聽

vite 專案執行開發模式 `npm run dev` 後即會自動監聽，不需要使用 `Live Sass Compiler` 的 `Watch SCSS` 功能

---

### 部署 gh-pages 流程說明

#### Windows 版本

1. 在 GitHub 建立一個新的 Repository

2. 部署前請務必先將原始碼上傳到 GitHub Repository 也就是初始化 GitHub，因此通常第一步驟會在專案終端機輸入以下指令

```cmd
git init # 若已經初始化過就可以不用輸入
git add .
git commit -m 'first commit'
git branch -M main
git remote add origin [GitHub Repositories Url]
git push -u origin main // 僅限第一次輸入，往後只需要輸入 git push
```

```markdown
3. 初始化完畢後，執行 `npm run deploy` 指令進行自動化部署
```
