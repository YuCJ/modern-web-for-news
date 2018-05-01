## 互動式新聞技術基礎

<span style="opacity:0.5;font-size:0.7em">講者：《報導者》前端工程師 余崇任</span>

[<span style="opacity:0.5;font-size:0.4em">source code</span>](https://github.com/YuCJ/modern-web-for-news)

---

## 三週應用課程

- 第一週：互動式網頁的技術原理
- 第二週：開源平台 Github 和開發軟體 Visual Studio Code 使用
- 第三週：如何改別人的 code 做出一個多媒體成果

Note:

第一個禮拜會跟大家介紹互動式網頁的技術原理，我們會簡單介紹會用到的程式技術，還有給大家未來繼續學習的工具。第二個禮拜則會介紹現在程式圈普遍流行的開源平台 Github。這個平台主要的功用，是輔助工程師合作寫程式的工具。開源程式的本質是開放給所有的工程師都可以加入開發。人多手雜，勢必要有一個工具，讓主持的團隊不只自己內部可以合作，還可以跟不特定的多數人合作。第三週會教導大家怎麼用我發佈在 Github 上面的程式碼，改寫成你自己版本的網站。

---

## 預期成果

[廢墟裡的少年](https://www.twreporter.org/i/high-risk-youth-life-is-a-struggle)

https://yucj.github.io/fullpage/

---

## 網頁運作的背後原理

![Web Fundation](assets/01-web-fundation.png)

Note:

(1) 使用者進瀏覽器打 url  (2) 瀏覽器送出訊息到 server 說我要拜訪這個位置 (3) Server 在分析你的要求後 吐一包東西回來 （4) 瀏覽器接收到這包東西後處理

Server 的部分 接收到瀏覽器的要求以後，他可能會做一些處理。例如去 database 裡面找資料，檢查這個使用者是否有權限拿這些資料，做一些複雜的計算等等。在現在網頁工程的分工裡面，這邊通常被叫做後端。這個部分我們不會講到。

---

## 課程的主角

![HTML](assets/01-web-fundation-html.png)

HTML (with CSS & Javascript)

Note: 

我們課程的主角會放在前端

這個部分，在大多數的情況，伺服器吐回來給瀏覽器的這包東西，會是一個 HTML 程式，這個 HTML 程式就會帶著很多。

前端的好處：成本低，效果快，開發時程短

---

## 前端語言三本柱

- **HTML**：網頁的<span style="color: yellow;">基礎</span>語言，打造出骨架和血肉
- **CSS**：網頁的<span style="color: yellow;">裝飾</span>語言，幫網頁塑型、置裝
- **Javascript**：網頁的<span style="color: yellow;">巫術</span>語言！用這個要做什麼都可以！（誤

---

## HTML：網頁的基礎

```html
<p>春眠不覺曉</p>
<a href="https://www.twreporter.org">報導者網站</a>
<input type="checkbox" />
<div>I'm a block</div>
<div>
    <div>
        <div>
            <p>春眠不覺曉</p>
        </div>
    </div>
</div>
```

@[1](這是一個段落)

@[2](這是一個連到報導者網站的超連結)

@[3](這是一個使用者可以輸入資料的元素)

@[4](這是一個區塊)

@[5-11](元素和元素可以 nesting)

Playground: [CodePen](https://codepen.io/yucj0123/pen/QrvMgB)

+++

### 拆解 Html Tag (Element) 的文法

```html
<a href="https://www.twreporter.org" target="_blank">報導者網站</a>
```

See Also: http://alolsen.net/blogs/webdesign/html/html-attributes/

+++

### 各種 HTML Tags (Elements)

- [常用 HTML tags](https://github.com/nickhsine/teach-at-nccu/blob/master/2018-03-22.md)
- [HTML Cheat Sheet](https://www.hostinger.com/tutorials/html-cheat-sheet#HTML-Cheat-Sheet-in-pdf) （好用）
- [Html Reference](https://htmlreference.io/)

+++

### 重要的特別屬性（attribute）

- id="xxx"
- class="xxx ooo"
- 為什麼有的屬性沒有 `="xxxx"` （[ex](https://github.com/YuCJ/fullpage/blob/9c6dbbd64ce9d82243853c186c19192af2278e9d/index.html#L75)）

Note:

true false

---

## CSS：網頁的裝飾

```css
div {
    background-color: black;
}

.large-picture {
    width: 100%;
}
.small-picture {
    width: 50%;
}
```

+++

### CSS－選擇器

- [W3School](https://www.w3schools.com/cssref/css_selectors.asp)


- [CSS Diner（練習 CSS Selector 的遊戲）](https://flukeout.github.io/)

+++

### CSS－Properties

- [常用CSS語法](https://github.com/nickhsine/teach-at-nccu/blob/master/2018-03-29.md)
- [圖解 CSS 語法（英文網站）](https://cssreference.io/)

+++

### CSS－Animation

+++

### CSS－怎麼放進 HTML？

```html
<!DOCTYPE html>
<html>
    <head>
        <link rel="stylesheet" href="/css/main.css" />
        <style>
            body {
                background-color: black;
            }
        </style>
    </head>
    <body>
        <div style="width:50px; height: 50px; background-color: white;"></div>
    </body>
</html>
```



@[4](打包成`xxxx.css` 檔，把連結放在 `<link>`裡面)

@[5-9](寫在 `<style></style>` 裡面)

@[12](把 property 直接寫在 html element 裡面！（俗稱 inline style）)

+++

### CSS 進階：CSS 語法限制好多，好難寫好難管理…

```scss
article .publish-date .year {/* ... */}
article .publish-date .month {/* ... */}
article .publish-date .date {/* ... */}

article {
    .publish-date {
        .year {/* ... */}
        .month {/* ... */}
        .date {/* ... */}
    }
}
```

@[1-3](我如果有一個發佈時間要把年月日分開上色，要寫成這樣....)

@[5-11](如果可以寫成 nesting 有多好！跟 html 更接近更好懂)

+++

#### CSS Pre-Processing

[某種更好寫的語法] -- *(用程式幫我轉成)* ---> [舊瀏覽器也看得懂的`CSS`]

+++

### CSS進階：寫 style 好累，如果有人幫我先把 CSS 寫好…

#### CSS Framework

根據別人定義好的 `class` 和 `id` 來寫我的 HTML，再掛上他的 CSS file！

- [Bootstraps](https://getbootstrap.com/docs/4.1/components/buttons/)
- [Semantic UI](https://semantic-ui.com/elements/button.html)
- [Bulma](https://bulma.io/documentation/elements/button/)

---

## Javscript：網頁的巫術

![HTML, Javascript, and DOM](assets/01-html-dom.gif)

+++

### DOM操作的霸主：jQuery

[Example](https://codepen.io/yucj0123/pen/zjwrdO)

+++

### 最新的流派：HTML空空的，全部都用 Javascript 來寫

```html
<html>
    <head></head>
    <body>
        <div id="root">
            This is the root element for React.
        </div>
    </body>
</html>
```

為什麼要這樣？因為方便分工和管理

+++

### Javascript 怎麼放進 HTML？

```html
<!DOCTYPE html>
<html>
    <head>
        <script type="text/javascript" src="/js/jquery.min.js"></script>
        <script type="text/javascript">
            function customTask() {
                /* 一些程式動作 */
            }
        </script>
    </head>
    <body>
        <button onclick="function handleClick() { /* 一些程式動作 */ }" />
        <script type="text/javascript" src="/js/jquery.min.js"></script>
        <script type="text/javascript">
            function customTask() {
                /* 一些程式動作 */
            }
        </script>
    </body>
</html>
```

@[4](打包成`xxxx.js` 檔，把連結放在 `<script></script>` 裡面)

@[5-9](寫在 `<script></script>` 裡面)

@[12](寫在 html element 的事件監聽器裡面！)

@[13-18](`<script>`也可以放在 `<body>`裡面，差別是被載入的時機)

---

## 關於互動網頁開發

+++

## 互動網頁製作的兩種工具

|                         | 前端基礎 | 作品彈性 | 費用     | 例子                                                         |
| ----------------------- | -------- | -------- | -------- | ------------------------------------------------------------ |
| 程式 library, framework | 需要     | 高       | 通常不用 | [fullpage.js](https://github.com/alvarotrigo/fullPage.js/) [chart.js](https://www.chartjs.org/) [animate.css](https://daneden.github.io/animate.css/) |
| 所見即所得工具          | 低       | 低       | 要       | [Adobe Muse](https://www.adobe.com/tw/products/muse.html)  [makeweb.io(beta)](https://makeweb.io/) [Wix](https://www.wix.com/) [Venngage](https://venngage.com/) |

+++

## 互動網頁/前端工程技術地圖

- http://www.hexschool.com/2018/04/16/2018-04-16-skill_tree/
- [自學資源](https://github.com/YuCJ/modern-web-for-news/blob/master/resources.md)
- 如果我未來是想作 PM / 記者 / 研究員，要學到什麼程度？

+++

## 互動網頁開發的兩種樣態

| 版面功能     | 獨特性高                 | 重用性、模組化高                     |
| ------------ | ------------------------ | ------------------------------------ |
| 首次開發時程 | 開發時間較低             | 開發時間較高                         |
| 衍生開發時程 | 時間較長，或難以衍生開發 | 時間較短                             |
| 適合專案類型 | 一次性，強調視覺特效     | 資料結構、版面或功能類似，需長期更新 |

---

## 本週作業

1. 安裝下週要用到的 [Visual Studio Code](https://code.visualstudio.com/) 免費軟體
2. 安裝下週要用到的 [Source Tree](https://www.sourcetreeapp.com/) 免費軟體
3. 申請 [Adobe Typekit](https://typekit.com/) 免費版帳號
4. 開始規劃自己的作品腳本，如果有版型或功能上的需求，可以 email 或下週跟我討論