# Markdown 簡易教學
`Markdown` 目前非常普遍用來`撰寫文檔`的`語言`，Markdown的格式語法只涵蓋純文字可以涵蓋的範圍。
+ HTML 是一種 ***`發佈`*** 的格式
+ Markdown是一種 ***`編寫`*** 的格式

---
# Getting Started
+ [Markdown](https://markdown.tw/)
+ 學習目錄
  + [1. Markdown](#1)
    + [1.1 概述](#1-1)
      + [1.1.1 行內 HTML](#1-1-1)
      + [1.1.2 特殊字元自動轉換](#1-1-2)
    + [1.2 區塊元素](#1-2)
      + [1.2.1 段落和換行](#1-2-1)
      + [1.2.2 標題](#1-2-2)
      + [1.2.3 區塊引言](#1-2-3)
      + [1.2.4 清單](#1-2-4)
      + [1.2.5 程式碼區塊](#1-2-5)
      + [1.2.6 分隔線](#1-2-6)
    + [1.3 區段元素](#1-3)
      + [1.3.1 連結](#1-3-1)
      + [1.3.2 強調](#1-3-2)
      + [1.3.3 程式碼](#1-3-3)
      + [1.3.4 圖片](#1-3-4)
    + [1.4 其他](#1-4)
      + [1.4.1 跳脫字元](#1-4-1)
      + [1.4.2 自動連結](#1-4-2)
      + [1.4.3 字體、字號與顏色](#1-4-3)
      + [1.4.4 區塊背景顏色](#1-4-4)
      + [1.4.5 輸入數學公式及符號](#1-4-5)
    + [1.5 資料參考](#1-5)

# <h1 id="1">Markdown</h1>

## <h2 id="1-1">1. 概述</h2>
+ Markdown 可以輸出成 HTML 的格式，顯示的結構上分為兩大類：***`區塊`***、***`行內`***。
![](https://firebasestorage.googleapis.com/v0/b/casper-de5d5.appspot.com/o/images%2Fblog%2F201911%2F%E8%B2%BC%E4%B8%8A%E7%9A%84%E5%BD%B1%E5%83%8F_2019_11_19_%E4%B8%8B%E5%8D%8811_13.png?alt=media&token=893c6e7a-010b-452e-913f-5418e91179e8)
---
### <h2 id="1-1-1">1.1 行內 HTML</h2>
+ Markdown 在段落內加入 html 語法
```html
This is a regular paragraph.

<table>
    <tr>
        <td>Foo</td>
    </tr>
</table>

This is another regular paragraph.
```
+ Demo
<table><tr><td bgcolor=#1D1818><font color="#FFFFFF">This is a regular paragraph.

<table>
    <tr>
        <td>Foo</td>
    </tr>
</table>

This is another regular paragraph.</font><br/></td></tr></table>

---
### <h2 id="1-1-2">1.2 特殊字元自動轉換</h2>
+ 在HTML文件中，有兩個字元需要特殊處理: `<` 和 `&`
  + HTML `<` 要使用並須轉化 `&lt;`
  + HTML `&` 要使用並須轉化 `&amp;`

+ Markdown 會自動化轉化上述 `&lt;`, `&amp;`
```html
4 &lt; 5
http://images.google.com/images?num=30&amp;q=larry+bird
```

+ Demo
<table><tr><td bgcolor=#1D1818><font color="#FFFFFF">4 &lt; 5 <br/>http://images.google.com/images?num=30&amp;q=larry+bird</font><br/></td></tr></table>

---
## <h2 id="1-2">2. 區塊元素</h2>
---
### <h2 id="1-2-1">2.1 段落和換行</h2>
+ Markdown允許段落內的強迫斷行，語法 `<br/>`
+ 連續兩個以上空格+換行Enter
```md
This is an H1<br />
<br />
This is an H2<br />
```
+ 首行縮進兩個字符：(連續使用兩個空即可）
```html
&ensp; 半角的空格
&emsp; 全角的空格
```

---
### <h2 id="1-2-2">2.2 標題</h2>
+ Markdown支援兩種標題的語法，Setext和atx形式。
+ Setext形式是用底線的形式，利用=（最高階標題）和-（第二階標題）
```md
This is an H1
=============

This is an H2
-------------
```
+ Atx形式則是在行首插入1到6個 # ，各對應到標題1到6階
```md
# This is an H1

## This is an H2

###### This is an H6
```
```md
# This is an H1 #

## This is an H2 ##

### This is an H3 ######
```

---
### <h2 id="1-2-3">2.3 區塊引言</h2>
+ Markdown使用email形式的區塊引言
+ Markdown文件中建立一個區塊引言，那會看起來像是你強迫斷行，然後在每行的最前面加上 `>`
```html
> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
> consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
> Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
>
> Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
> id sem consectetuer libero luctus adipiscing.
```

```html
> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.

> Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
id sem consectetuer libero luctus adipiscing.
```

```html
> ## This is a header.
>
> 1.   This is the first list item.
> 2.   This is the second list item.
>
> Here's some example code:
>
>     return shell_exec("echo $input | $markdown_script");
```

---
### <h2 id="1-2-4">2.4 清單</h2>
+ Markdown支援`有序清單`和`無序清單`
+ `有序清單`使用星號 ( `*` )、加號( `+` )或是減號 ( `-` )，以下表達方式皆相同
```html
*   Red
*   Green
*   Blue
```
```html
+   Red
+   Green
+   Blue
```
```html
-   Red
-   Green
-   Blue
```

+ `無序清單`使用數字後加上英文句點
```html
1.  Bird
2.  McHale
3.  Parish
```
+ `無序清單`使用 `html 方式
```html
<ol>
<li>Bird</li>
<li>McHale</li>
<li>Parish</li>
</ol>
```

---
### <h2 id="1-2-5">2.5 程式碼區塊</h2>
+ Markdown中建立程式碼區塊，只要簡單地縮排`4個空白`或是`1個tab
```html
This is a normal paragraph:

    This is a code block.
```
+ Markdown會轉換成：
```html
<p>This is a normal paragraph:</p>

<pre><code>This is a code block.
</code></pre>
```

---
### <h2 id="1-2-6">2.6 分隔線</h2>
+ 一行中用三個或以上的 星號( `*` )、減號( `-` )、底線( `_` ) 來建立一個分隔線
+ 語法

```md
* * *

***

*****

- - -
---------------------------------------
```

---
## <h2 id="1-3">3. 區段元素</h2>
---
### <h2 id="1-3-1">3.1 連結</h2>
+ 語法
```md
[Alt text](link)
[Markdown](https://markdown.tw/)
```
+ Demo
<table><tr><td bgcolor=#1D1818><font color="#FFFFFF"><a href="https://markdown.tw/">Markdown</a></font></td></tr></table>

---
### <h2 id="1-3-2">3.2 強調</h2>
+ Markdown使用星號（*）和底線（_）作為標記強調字詞的符號
  + \*文字\* → \<em\>文字\<\/em\>
  + \*\*文字\*\* → \<strong\>文字\<\/strong\>
+ Example
```md
*single asterisks*

_single underscores_

**double asterisks**

__double underscores__
```
+ Example Markdown 轉化
```md
<em>single asterisks</em>

<em>single underscores</em>

<strong>double asterisks</strong>

<strong>double underscores</strong>
```
+ Demo
<table><tr><td bgcolor=#1D1818><font color="#FFFFFF"><em>single asterisks</em>

<em>single underscores</em>

<strong>double asterisks</strong>

<strong>double underscores</strong></font></td></tr></table>


---
### <h2 id="1-3-3">3.3 程式碼</h2>
+ 標記一小段行內程式碼，你可以用反引號把它包起來（\`）
+ Example
```md
Use the `printf()` function.
```
+ Example Markdown 轉化
```md
<p>Use the <code>printf()</code> function.</p>
```
+ Demo
<table><tr><td bgcolor=#1D1818><font color="#FFFFFF"><p>Use the <code>printf()</code> function.</p></font></td></tr></table>

---
### <h2 id="1-3-4">3.4 圖片</h2>
+ 語法
```md
![Alt text](link)
![markdown](https://markdown.tw/images/208x128.png)
```
+ Demo
<table><tr><td bgcolor=#FFFFFF> <img src="https://markdown.tw/images/208x128.png"></td></tr></table>

---
## <h2 id="1-4">4. 其他</h2>
---
### <h2 id="1-4-1">4.1 跳脫字元</h2>
+ Markdown支援在下面這些符號前面加上反斜線(`\`)來幫助插入普通的符號：
```md
\   反斜線
`   反引號
*   星號
_   底線
{}  大括號
[]  方括號
()  括號
#   井字號
+   加號
-   減號
.   英文句點
!   驚嘆號
```

---
### <h2 id="1-4-2">4.2 自動連結</h2>
+ Markdown支援比較簡短的自動連結形式來處理`網址`和`電子郵件信箱`，使用 "\<" 和 "\>"。
+ `網址`
```md
<http://example.com/>
```
+ `網址` Markdown 轉換
```md
<a href="http://example.com/">http://example.com/</a>
```

+ `電子郵件信箱`
```md
<address@example.com>
```
+ `電子郵件信箱` Markdown 轉換
```md
<a href="&#x6D;&#x61;i&#x6C;&#x74;&#x6F;:&#x61;&#x64;&#x64;&#x72;&#x65;
&#115;&#115;&#64;&#101;&#120;&#x61;&#109;&#x70;&#x6C;e&#x2E;&#99;&#111;
&#109;">&#x61;&#x64;&#x64;&#x72;&#x65;&#115;&#115;&#64;&#101;&#120;&#x61;
&#109;&#x70;&#x6C;e&#x2E;&#99;&#111;&#109;</a>
```

---
### <h2 id="1-4-3">4.3 字體、字號與顏色</h2>
+ Markdown 本身是不支持修改字體、字號與顏色
+ CSDN-markdown 擴展了Markdown的功能（如表格、腳註、內嵌HTML等等）
+ 內嵌HTML的方法來實現
```html
<font face="黑體">我是黑體字</font>
<font face="微軟雅黑">我是微軟雅黑</font>
<font face="STCAIYUN">我是華文彩雲</font>
<font color=#0099ff size=7 face="黑體">color=#0099ff size=72 face="黑體"</font>
<font color=#00ffff size=72>color=#00ffff</font>
<font color=gray size=72>color=gray</font>
```

---
### <h2 id="1-4-4">4.4 區塊背景顏色</h2>
+ Markdown本身不支持背景色設置
+ 內嵌HTML的方法來實現，藉助 table, tr, td 等表格標籤的 bgcolor 屬性來實現背景色的功能
```html
<table><tr><td bgcolor=orange>背景色是：orange</td></tr></table>
```

---
### <h2 id="1-4-5">4.5 輸入數學公式及符號</h2>
+ LaTex數學公式，分`行內公式`與`獨立公式`兩種
```html
$ 行內公式 $

$$ 獨立公式 $$
```

+ Example
```md
$$\sum_{i=1}^n \frac{1}{i^2} \quad and \quad \prod_{i=1}^n \frac{1}{i^2} \quad and \quad \bigcup_{i=1}^{2} R$$
```
+ Demo
$$\sum_{i=1}^n \frac{1}{i^2} \quad and \quad \prod_{i=1}^n \frac{1}{i^2} \quad and \quad \bigcup_{i=1}^{2} R$$

---
## <h2 id="1-5">5. 資料參考</h2>
+ [Markdown文件](https://markdown.tw/)
+ [為什麼我的 Markdown 會跑版](https://dwy6626.github.io/post/markdown-intro-history/)
+ [十分鐘快速掌握 Markdown](https://wcc723.github.io/development/2019/11/23/ten-mins-learn-markdown/)
+ [如何在 Markdown 輸入數學公式及符號](https://blog.maxkit.com.tw/2020/02/markdown.html)
+ [LaTeX/數學公式](https://zh.m.wikibooks.org/zh-tw/LaTeX/%E6%95%B0%E5%AD%A6%E5%85%AC%E5%BC%8F)
+ [Color Picker - 查詢顏色代碼](https://htmlcolorcodes.com/)
