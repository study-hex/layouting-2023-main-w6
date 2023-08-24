# layouting-2023-main-w6

- W6

> <https://rpg.hexschool.com/task/351/show>

- 設計稿：

> <https://www.figma.com/file/1qhYNCLtQHg6qmBnzV5A6y>

- 圖片倉庫：

> <https://github.com/hexschool/2022-web-layout-training/tree/main/2023week6>

---

## TA-REVIEW

```markdown
### 首頁整體建議：

- [ ] 部分文字大小要再留意一下，例如：在手機版「探索更多」裡面 li 標題大小為 16px、「近期活動」的日期為 32px 等。
  - 「近期活動」已經調整 
  - Q：「探索更多」在程式碼沒有設定，應該還是 `16px`，但為何呈現出來不同QQ

---

- [ ] 「探索活動」input 的寬高可以再調整一下，設計稿為 284 x 55。
  - Q：寬高不知道能否寫死？

- [ ] 「隔牆有耳-沒有草東的派對」的 banner 建議可以使用 background 的方式來完成 ~
  - Q：何時適合使用 `background` 呢？

---

#### [commit](https://github.com/study-hex/layouting-2023-main-w6/commit/e567ea909b84fbb7d4fee488d357697af5d8e0e0)

- [x] 建議在 992px 可以變換為平板的版型，像是在「探索更多」或是「近期活動」等區塊都可以採用雙欄式的排版，避免空間不夠導致跑版。
  - 「探索更多」、「近期活動」改在 `row` 設定；「活動集錦」各自調整，因為手機版 `col-11`

- [x] _mixins.scss 的第五行要補上分號。

---

#### [commit](https://github.com/study-hex/layouting-2023-main-w6/commit/88a11ba5d0466bb87fb343a6612fd0659bb5f48d)

- [x] 日期比較不屬於標題，所以像是「隔牆有耳-沒有草東的派對」就可以更換為 h2 標籤，而底下「近期活動」的日期標籤也需要做調整。
  - 調整為 `<time>` 標籤，後續的標題也提高順序

#### [commit](https://github.com/study-hex/layouting-2023-main-w6/commit/d79bea19538bae86090851bbb2731bc4cddd388f)

- [x] 圖片本身若沒有連結，可以不用加上 :hover 的效果，避免使用者誤以為可以點擊。

---

#### [commit](https://github.com/study-hex/layouting-2023-main-w6/commit/cb9e20533bb3c8531b971fa49a615d37480c2f69)

- [x] 切特居批踢底下 tag 在 hover 的時候與設計稿不符

- [x] 「確認訂閱」的按鈕在 hover 到時，文字顏色可以改變為黃色。

---

### Login 頁面：

#### [commit](https://github.com/study-hex/layouting-2023-main-w6/commit/a136e0fd61f409dcb7108bc74b830432861efe09)

- [x] 漢堡選單為滿版，另外最下方會有 border 線條，可以再嘗試調整看看

---

#### [commit](https://github.com/study-hex/layouting-2023-main-w6/commit/d673a787b3a23a80ac70448aa23b8ba8df64f828)

- [x] 可以在 .main 加上 `height: calc(100vh - 170px);`
  - （170px 為 header 跟 footer 的高度） 
  - 這樣的話就不會出現垂直軸了。

---

- [ ] 同學除了自己撰寫驗證之外，也可以使用 [Validation](https://getbootstrap.com/docs/5.0/forms/validation/) 的方式來加上驗證的功能。

---

```

---

## LV.2

```markdown
LV2（80、100% 獎品門檻）：至少做 2 頁含 RWD，其中 1 頁必須為首頁
```

- [x] p1-首頁
- [x] p2-登入頁面

---

### 已知問題

1. ~~`hover` 效果失效：`button`、`nav-link`~~（客製化樣式不能把顏色拆分到 `HTML`，這樣 `hover` 時會蓋不掉）

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

## NOTES

- 在 `row` 直接設定滿方便的；多張卡片區域要有 `md`、`lg` 的斷點才不會太擠

```HTML
row row-cols-1 row-cols-md-2 row-cols-lg-3 g-6
```

> - BEFORE
> ![BEFORE](./assets/images/cardlist-before_2023-08-24.png)
> - AFTER
> ![AFTER](./assets/images/cardlist-after_1692851762_2023-08-24.png)

- 登入頁面的主要區塊可以利用 `(100vh - navbar - footer)` 來呈現滿版

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
