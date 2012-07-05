1、不要使用過小的圖片做背景平鋪。

這就是為何很多人都不用 1px 的原因，這才知曉。寬高 1px 的圖片平鋪出一個寬高 200px 的區域，需要 200*200=40, 000 次，佔用資源。

2、無邊框。

推薦的寫法是 border:none; border:0; 只是定義邊框寬度為零，但邊框樣式、顏色還是會被瀏覽器解析，佔用資源。

3、慎用 * 通配符。

所謂通配符，就是將 CSS 中的所有標籤均初始化，不管用的不用的，過時的先進的，一視同仁，這樣，大大的佔用資源。要有選擇的初始化標籤。

4、CSS 的十六進制顏色代碼縮寫。

習慣了縮寫及小寫，這才知道，原來不是推薦的寫法，為的是減少解析所佔用的資源。但同時會增加文件體積。孰優孰劣，有待仔細考證。

5、樣式放頭上，腳本放腳下。不內嵌，只外鏈。

6、堅決不用 CSS 表達式。

7、使用 引用樣式表，而不是通過 @import 導入。

8、一般來說，PNG 比 GIF 要小，小得多。再者，GIF 中有多少顏色是被浪費的，很值得優化。

9、千萬不要在 HTML 中縮放圖片，一者不好看，二者佔資源。

10、正文字體最好用偶數，12px、14px、16px，效果非常好。特例，15px。

11、block、ul、ol 等上下留出至少一倍行距，左側至少兩倍行距，右側隨意。

12、段落之間，至少要有一倍行距。

13、強行指定某些元素的 line-height，正文 1.6 倍於文字大小，標題 1.3 倍。

14、中文標點用全角。英文夾雜在中文中，左右空格，半角。

1. CSS Reset/重置
你可以copy Eric Meyer Reset, YUI Reset或其它css reset, 但你接下來應該根據你的項目改成你自己的reset.
不要使用* { margin: 0; padding: 0; } 。我個人很愛用，原作者提到使用這句並不適用一些元素比如單選按鈕。不過俺博客裡面也沒有單選按鈕，如果有，又重新給單選按鈕重設就好了嘛。

2. 按字母順序來排列css
3. 更好的組織css結構
即同類歸類，應用註釋

4. 保持一致性
5. 先標記後css
儘量善用子選擇器，而不是一要給哪個元素進行樣式化，就給它添加個選擇器。


一、圖像替換文本
#header h1 a{
display:block;
text-indent:-9999em;
background:(images/logo.png) no-repeat 0 0;
height:87px;
width:250px;
overflow:hidden;
}
　　看得懂這個嗎？我看到很多們都LOGO都只是用圖片代替，而沒有鏈接。其他，只需要更簡單的方法，利用圖像替換文本的方法，顯示LOGO，並擁有鏈接。各個值的功能display:block; a的默認狀態是inline的，需要讓它變成塊狀的，才可能定義高度和寬度，以適應LOGO的寬高。另外的一個功能是，讓鏈接在text-indent後，在原區域可點擊。
　　text-indent:-9999em; - 難道你想刪除logo中的文字?這樣應該是你的最後選擇。因為這不符合語議標記，所以，也對搜索引擎不友好。而這個值就是讓你的字體縮進到看不到的地方。讓你不用刪除文字。
　　其他的不用講了吧…
二、display:inline-block;

　　在寫sofished daily的CSS時，在頂站定日期的空間，就用了display:inline-block;顧名思義，就是在內聯情況也的塊狀，可以設定高度寬度。在GR看到一篇share講了說到了跨瀏覽器顯示這個顯示display:inline-block的方法：
.element-class {
display: -moz-inline-stack; //Firefox only code
display: inline-block; //some standard browsers
zoom: 1; //IE only
*display: inline; //Only IE know this code (CSS Hack)
}
　　好處是什麼？好處就是不用使用float，在一行中顯示設定寬高的元素。不過，上面提到的跨瀏覽器，貌似我在IE下依然可以顯示，難道是IE tester的問題？
三、用line-height文字垂直居中

　　你可能知道用text-align來讓文字水平劇中，不過，卻找不到更直接的方法來讓元素垂直居。這裡，或許你可以利用一下line- height。比如你要在導航中讓文字簡直居中於導航，可能會想到用padding和margin，不過，這時，煩人的IE可能會給你製造出麻煩，所以，用line-height吧，這是一個更簡單的方法：
　　上面這張圖片的導航高度是28px，你可以給a設定這樣的值：#navigation a{font-size:14px;line-height:28px;}，這樣，就少去了用padding和margin的麻煩了。
四、佈局居中

　　你會發現，很多網站的佈局都是劇中的。原因是方便瀏覽，對用戶比較好？對於初學CSS的人來說，可能並不知道怎麼做吧。很簡單，就一句，假設你的佈局的那個div殼是#wrapper：
　　div#wrapper{margin:0 auto;}
　　這就是說，讓上面沒有margin，而左右自動適應，選擇相等的寬度。這樣就可以更好地在各個瀏覽器中表現了。
五、CSS縮寫
　　CSS縮寫，為什麼？簡單來說有兩個好處。一，讓你寫代碼更有效率，因為短；二方便修改，誰也不想對著一堆雜亂的代碼發呆。貌似有很多人寫過這個，不過，這裡，就重複一下吧。我並不想直接寫出所有，這樣文章看起來似乎特別長，就給一些鏈接看看，你就明白了。


www.cncfan.com提示：本文作者：Trenton Moss，本文首發於http://www.webcredible.co.uk/。
本翻譯並未得到作者或網站授權。一切權利都歸原作者及原網站所有。
如果你得到原作者或原發表網站的授權，可以自由使用本翻譯。
1.CSS字體屬性簡寫規則

一般用CSS設定字體屬性是這樣做的：

font-weight:bold;
font-style:italic;
font-varient:small-caps;
font-size:1em;
line-height:1.5em;
font-family:verdana,sans-serif;

但也可以把它們全部寫到一行上去：

font: bold italic small-caps 1em/1.5em verdana,sans-serif;

真不錯！只有一點要提醒的：這種簡寫方法只有在同時指定font-size和font-family屬性時才起作用。而且，如果你沒有設定font-weight, font-style, 以及 font-varient ，他們會使用缺省值，這點要記上。

2. 同時使用兩個類

一般只能給一個元素設定一個類（Class），但這並不意味著不能用兩個。事實上，你可以這樣：

同時給P元素兩個類，中間用空格格開，這樣所有text和side兩個類的屬性都會加到P元素上來。如果它們兩個類中的屬性有衝突的話，後設置的起作用，即在CSS文件中放在後面的類的屬性起作用。

補充：對於一個ID，不能這樣寫<p side">...</p>也不能這樣寫

3. CSS border的缺省值

通常可以設定邊界的顏色，寬度和風格，如：
border: 3px solid #000
這位把邊界顯示成3像素寬，黑色，實線。但實際上這裡只需要指定風格即可。

如果只指定了風格，其他屬性就會使用缺省值。一般地，Border的寬度缺省是medium，一般等於3到4個像素；缺省的顏色是其中文字的顏色。如果這個值正好合適的話，就不用設那麼多了。

4. CSS用於文檔打印

許多網站上都有一個針對打印的版本，但實際上這並不需要，因為可以用CSS來設定打印風格。

也就是說，可以為頁面指定兩個CSS文件，一個用於屏幕顯示，一個用於打印：

第1行就是顯示，第2行是打印，注意其中的media屬性。

但應該在打印CSS中寫什麼東西呢？你可以按設計普通CSS的方法來設定它。設計的同時就可以把這個CSS設成顯示CSS來檢查它的效果。也許你會使用 display: none 這個命令來關掉一些裝飾圖片，再關掉一些導航按鈕。要想瞭解更多，可以看「打印差異」這一篇。

5. 圖片替換技巧

一般都建議用標準的HTML來顯示文字，而不要使用圖片，這樣不但快，也更具可讀性。但如果你想用一些特殊字體時，就只能用圖片了。

比如你想整個賣東西的圖標，你就用了這個圖片：
<h1><img src="widget-image.gif" alt="Buy widgets" /></h1>
這當然可以，但對搜索引擎來說，和正常文字相比，它們對alt裡面的替換文字幾乎沒有興趣這是因為許多設計者在這裡放許多關鍵詞來騙搜索引擎。所以方法應該是這樣的：
<h1>Buy widgets</h1>
但這樣就沒有特殊字體了。要想達到同樣效果，可以這樣設計CSS：
h1 { background: url(widget-image.gif) no-repeat; height: image height text-indent: -2000px }

注意把image height換成真的圖片的高度。這裡，圖片會當作背景顯示出來，而真正的文字由於設定了-2000像素這個縮進，它們會出現在屏幕左邊2000點的地方，就看不見了。但這對於關閉圖片的人來說，可能全部看不到了，這點要注意。

6. CSS box模型的另一種調整技巧

這個Box模型的調整主要是針對IE6之前的IE瀏覽器的，它們把邊界寬度和空白都算在元素寬度上。比如：

#box { width: 100px; border: 5px; padding: 20px }

這樣調用它：
<div >...</div>
這時盒子的全寬應該是150點，這在除IE6之前的IE瀏覽器之外的所有瀏覽器上都是正確的。但在IE5這樣的瀏覽器上，它的全寬仍是100點。可以用以前人發明的Box調整方法來處理這種差異。

但用CSS也可以達到同樣的目的，讓它們顯示效果一致。

#box { width: 150px } #box div { border: 5px; padding: 20px }

這樣調用：
<div ><div>...</div></div>
這樣，不管什麼瀏覽器，寬度都是150點了。

7. 塊元素居中對齊

如果想做個固定寬度的網頁並且想讓網頁水平居中的話，通常是這樣：

#content { width: 700px; margin: 0 auto }

你會使用 <div > 來圍上所有元素。這很簡單，但不夠好，IE6之前版本會顯示不出這種效果。改CSS如下：

body { text-align: center } #content { text-align: left; width: 700px; margin: 0 auto }

這會把網頁內容都居中，所以在Content中又加入了
text-align: left 。

8. 用CSS來處理垂直對齊

垂直對齊用表格可以很方便地實現，設定表格單元 vertical-align: middle 就可以了。但對CSS來說這沒用。如果你想設定一個導航條是2em高，而想讓導航文字垂直居中的話，設定這個屬性是沒用的。

CSS方法是什麼呢？對了，把這些文字的行高設為 2em：line-height: 2em ，這就可以了。

9. CSS在容器內定位

CSS的一個好處是可以把一個元素任意定位，在一個容器內也可以。比如對這個容器：

#container { }

這樣容器內所有的元素都會相對定位，可以這樣用：
<div ><div >...</div></div>
如果想定位到距左30點，距上5點，可以這樣：

#navigation { ; left: 30px; top: 5px }

當然，你還可以這樣：
margin: 5px 0 0 30px
注意4個數字的順序是：上、右、下、左。當然，有時候定位的方法而不是邊距的方法更好些。

10. 直通到屏幕底部的背景色

在垂直方向是進行控制是CSS所不能的。如果你想讓導航欄和內容欄一樣直通到頁面底部，用表格是很方便的，但如果只用這樣的CSS：

#navigation { background: blue; width: 150px }

較短的導航條是不會直通到底部的，半路內容結束時它就結束了。該怎麼辦呢？

不幸的是，只能採用欺騙的手段了，給這較短的一欄加上個背景圖，寬度和欄寬一樣，並讓它的顏色和設定的背景色一樣。

body { background: url(blue-image.gif) 0 0 repeat-y }

此時不能用em做單位，因為那樣的話，一旦讀者改變了字體大小，這個花招就會露餡，只能使用px。



http://www.csswang.com/html/1482.html
http://www.panjunyu.com/front/111.html
http://www.cncfan.com/html/?96_6679.html
http://www.phpstudy.net/a.php/115.html