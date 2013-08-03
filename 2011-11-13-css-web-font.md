<!--
[date]: 2011-11-13
[title]: [CSS] 網頁字體
[name]: css-web-font
[tag]: CSS, font | 字體, web dev | 網頁開發
-->

![\[CSS\] 網頁字體][feature photo]

一般字體
-------

CSS 中 `font-family` 用來指定網頁上所要呈現的字體，但若此裝置並無安裝該字體時，則會使用瀏覽器預設之字體。我們可以在 `font-family` 中定義多套字體（以逗號分隔），瀏覽器會依照開發者所排的順序來搜尋此裝置中是否有該字體。


通用字集 (generic-family)
---------------------

`font-family` 可以接收*一般字體名稱 (family-name)* 與*通用字集名稱 (generic-family)* 作為其屬性。在設定 `font-family` 時，***切記在最後面加上一個通用字集名稱***。可以使瀏覽器在找不到字體時，使用一個最接近設計者原意的字體來取代。

**通用字集一般有五種，分別為：**

| 字體集名稱 | 中文 | 圖片範例 |
| ----- | ------ | ------- | ------- |
| `serif` | 襯線字 | ![serif][serif] |
| `sans-serif` | 無襯線字 | ![sans-serif][sans-serif] |
| `cursive` | 草書 | ![cursive][cursive] |
| `fantasy` | 潮字體 | ![fantasy][fantasy] |
| `monospace` | 等寬字體 | ![monospace][monospace] |

有興趣可以去了解這些通用字集各適合用於什麼時候，以及其差異。另外，每個通用字集所會使用的字體也不盡相同，依照瀏覽器或使用者設定的不同，而會使用不同的字體。

中文字體
-------

中文字體需要將其英文名稱與中文名稱皆寫入，因為在不同語系的裝置中，他會依照該裝置的預設語言去搜尋。因此將中英文名稱都放入 font-family 是最安全的作法。

**以下為常用中文字體之中英文名稱：**

**Windows**

- 微軟正黑體：`Microsoft JhengHei`
- 新細明體：`PMingLiU`
- 細明體：`MingLiU`
- 標楷體：`DFKai-sb`

**OS X**

- 標楷體：`BiauKai`
- 儷黑 Pro：`LiHei Pro`
- 儷宋 Pro：`LiSong Pro`
- 蘋果儷中黑：`Apple LiGothic`
- 蘋果儷細宋：`Apple LiSung`
- 黑體-繁：`Heiti TC`

另外，推薦一個漂亮的 OS X 上字體－**ヒラギノ角ゴ Pro (`Hiragino Kaku Gothic Pro`)**。雖然為日本字體，但同樣適用於繁體字，個人覺得這個字體看起來很舒服！基本上現在 OS X都有預設安裝這個字體，儷黑有點太粗了。

**Ubuntu**

- 文泉驛正黑：`WenQuanYi Zen Hei` (`Wen Quan Yi Zen Hei`)
- 文泉驛微米黑：`WenQuanYi Micro Hei` (`Wen Quan Yi Micro Hei`)

**注意**

若**一般字體名稱**含空白，請用**引號**括住。但**通用字集不需要加上引號**！！

相關資料
-----

- Wiki: [serif][1]
- Wiki: [sans-serif][2]

(photo via [arnoKath][3]，CC License)

[1]: http://en.wikipedia.org/wiki/Serif
[2]: http://en.wikipedia.org/wiki/Serif
[3]: http://www.flickr.com/photos/typoatelier/4574136682/

[serif]: http://i.minus.com/jbsmm6YI3cPwzV.png
[sans-serif]: http://i.minus.com/juloolH1tqeNq.png
[cursive]: http://i.minus.com/jb2hxYWm0yI2jV.png
[fantasy]: http://i.minus.com/jy00pl9GnrlNV.png
[monospace]: http://i.minus.com/jp9n6LFRAyLGN.png

[feature photo]: http://i.minus.com/j84slZAkDRHVc.jpg
