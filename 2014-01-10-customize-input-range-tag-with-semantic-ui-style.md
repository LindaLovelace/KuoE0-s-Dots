<!--
[date]: 2014-01-10
[title]: 打造 Semantic UI 風格的 <input type="range" />
[name]: customize-input-range-tag-with-semantic-ui-style
[tag]: web dev | 網頁開發, Semantic UI, CSS
[photo]: http://i.minus.com/jDiwdCo4axLR8.png
-->

![Semeantic UI range input](http://i.minus.com/jDiwdCo4axLR8.png)

最近在開發訊號繪製的網頁，詳情可參考這篇－[使用網頁作為訊號繪製界面 (with Python)](http://blog.kuoe0.tw/posts/2013/12/30/use-web-page-to-plot-signals-with-python)，其中套用的 [Semantic UI](semantic-ui.com) 來裝飾頁面。最近想加上一個 low-pass filter 的功能，並且希望可以調整 filter 的強度，打算使用 `<intput type="range />` 來實現調整的功能。找遍了 Semantic UI 的文件，完全找不到有定義 range 型別的樣式（還是我眼殘沒找到？！），就只好自己研究一下該怎麼套出類似的樣式了。

可以發現 W3C 並沒有規範 range 型別中控制點的 CSS selector，因此該功能只有在特定的瀏覽器中能夠作用。由於我主要使用的瀏覽器是 [Google Chrome](http://www.google.com/intl/zh-TW/chrome/)，其核心引擎為 [Blink](http://www.chromium.org/blink)，Blink 本身是 [WebKit](http://www.webkit.org/) 的分支，所以本篇的效果都能在任何基於 WebKit 與 Blink 的瀏覽器上。

外框樣式
--------

首先先介紹 CSS selector，要選擇 range 型別的 input 有正規的 selector 是 `input[type="range"]`。但僅能定義整個拉條本身的外觀，並不能定義控制點的樣式。因此在 WebKit 中有規範一些 pseudo element，其中包括一個 `input[type="range"]::-webkit-slider-thumb` 可以用來調整控制點樣式。


由於我們要客制自己的樣式，因此需要先把瀏覽器預設的樣式給去除。只要加上 `-webkit-appearance: none` 的敘述就可以，程式碼如下：

```css
input[type="range"] {
	-webkit-appearance: none;
}
```

效果如下圖：

![step1](http://i.minus.com/j7zj5CJCA0YUW.png)

這樣一來，預設的那條拉條就會消失了，只會剩下一個控制點。為了要搭配 Semantic UI 中 `<input type="checkbox" />` 的[第三種樣式](http://semantic-ui.com/collections/form.html)，下一步就是加上一個左右兩邊都是圓弧的淺灰色外框。程式碼如下：

```css
input[type="range"] {
	-webkit-appearance: none;
	border-width: 1px;
	border-style: solid;
	border-radius: 50rem;
	border-color: rgba(0, 0, 0, 0.1);
}
```

效果如下圖：

![step2](http://i.minus.com/j9R0dZ2l2xaD5.png)


現在看起來很有個樣子了吧！

控制點樣式
----------

最後一步就是調整控制點的樣式了。一樣需要把瀏覽器預設的樣式給去除，所以要加入 `-webkit-appearance: none` 的敘述。

```css
input[type="range"]::-webkit-slider-thumb {
	-webkit-appearance: none;
}
```

效果如下圖：

![step3](http://i.minus.com/jXTkiLnHxuWLN.png)

然後就會發現整個拉條變扁了，這是因為控制點消失了，因此需要給控制點一個大小。利用試誤法大概猜測出控制點的長寬是 0.7 rem，把這個大小的敘述加到 CSS 裡面，程式碼如下：

```css
input[type="range"]::-webkit-slider-thumb {
	-webkit-appearance: none;
	height: 0.7em;
	width: 0.7em;
}
```

效果如下圖：

![step4](http://i.minus.com/jb01WnsKxoLIA9.png)

就可以看到有高度的拉條了，不過控制點還是處於隱形的狀態，所以需要在替控制點加入背景顏色。查了一下 Semantic UI 中 checkbox 的圓點顏色色碼是 <span style="background-color: #58cb73; color: #58cb73">__</span> #58cb73。此外也在樣式中加入圓角的敘述。

```css
input[type="range"]::-webkit-slider-thumb {
	-webkit-appearance: none;
	background-color: #89B84C;
	border-radius: 50rem;
	height: 0.7em;
	width: 0.7em;
```

效果如下圖：

![step5](http://i.minus.com/jCl8grrhSs6Dy.png)

這時候樣子大概就完成了！不過怎麼好像還是有些不一樣的地方，就是控制點與外框的距離。只要在替 `input[type="range"]` 加上個 `padding` 的樣式就大功告成了！程式碼如下：

```
input[type="range"] {
	-webkit-appearance: none;
	border-width: 1px;
	border-style: solid;
	border-radius: 50rem;
	border-color: rgba(0, 0, 0, 0.1);
	padding: 3px 5px;
}
```

效果如下圖：

![step6](http://i.minus.com/jbizg7YfI092ic.png)


Semantic UI 化
--------------

上面的 CSS 雖然可以打造出外觀與 Semantic UI 風格一致的 range input，但為了與 Semantic UI 一起使用，應該將 selector 與 Semantic UI 更一致一些才對。看了一下 checkbox input 的 selector 是 `.ui.slider.checkbox`，所以就直接在原本的 selector 前面加上 `.ui.slider.range` 即可。程式碼如下：

```css
.ui.slider.range input[type="range"] {
	-webkit-appearance: none;
	border-width: 1px;
	border-style: solid;
	border-radius: 50rem;
	border-color: rgba(0, 0, 0, 0.1);
	padding: 3px 5px;
}

.ui.slider.range input[type="range"]::-webkit-slider-thumb {
	-webkit-appearance: none;
	background-color: #89B84C;
	border-radius: 50rem;
	height: 0.7em;
	width: 0.7em;
}
```

Source Code
-----------

<script src="https://gist.github.com/KuoE0/8346849.js"></script>

Source code on [gist](https://gist.github.com/KuoE0/8346849).

Live demo on [codepen](http://codepen.io/KuoE0/pen/pInFu).
