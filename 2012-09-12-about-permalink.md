<!--
[date]: 2012-09-12
[titel]: 關於 PermaLink
[title]: about-permalink
[tag]: permalink | 永久鏈結, web dev | 網頁開發
[photo]: http://i.minus.com/jf08FqLl8RSZ9.png
-->

PermaLink 其實是 permanent link 的意思，也就是「永久鏈結」，也有人翻作「靜態鏈結」。用來使網站中的每一頁面都有屬於自己的網址！

# 為什麼要用 PermaLink

以 wordpress 為例，在 wordpress 上每篇文章預設的鏈結是 **yourdomainname/?p=post_id** ，這是採用 http 中的 get 請求從首頁請求文章內容的作法。如此該 blog 中，唯一存在的網址可能只有**首頁**。其餘頁面都沒有自己的網址，若要說採用 get  request 的方式算是網址的話也是可行。但若是在不支援 get request 的方式擷取，那麼網頁的訪客若想找尋某特定文章的話，僅能自首頁使用滾輪向下拉呀拉，或是一直點選下一頁。

而不使用 permalink 最大的缺點我認為是在 [SEO][wiki-seo] 上。一般在使用 permalink 時，需要決定 permalink 的結構，真正影響  SEO 的就是 permalink 的結構。通常我們在設計 permalink 時，會賦予該網址關於該文章的相關資訊，例如：日期、文章標題、分類等等。在 permalink 上賦予相關資訊，對搜尋引擎來說也可以從網址中得到相關資訊，或許該網頁也因此得到較高的權重（當然決定權在搜尋引擎的演算法上）。而且使用具有意義的 permalink 不僅可以讓搜尋引擎從網址中得知資訊，人類也能直接從網址中獲得相關資訊！

# permalink 結構設計

permalink 的結構究竟怎麼設計比較好，網路上也有許多討論，目前似乎也沒有絕對好的結構。我覺得還是要針對文章與部落格的特性去做調整！

若是時效性較強的資訊，建議可以將日期放置於 permalink 的結構中！若是有分類導向的，即可將類別放置於 permalink 中！我個人也很推薦將標題也放入 permalink 中，如此一來，當他人看到網址也可以簡單知道該網頁的標題！

另外，雖然現在許多瀏覽器都支援中文的網址了，但在複製網址時，中文仍然會被轉換為 unicode，此時的網址就像是串亂碼，如此一來，本來用意是讓人類可讀的 permalink 也失去了該功能了！

### 以 yahoo 的一篇新聞為例：

我在瀏覽器網址列上看到的是 ↓

> http://tw.news.yahoo.com/嘉市城隍廟-將申請國定古蹟-105609981.html

而我複製下網址後，貼上於記事本上則看到↓

> http://tw.news.yahoo.com/%E9%99%B8%E8%BB%8D%E6%96%B9%E6%94%BE%E8%A9%B1-%E8%AD%A6%E5%91%8A%E6%97%A5%E6%9C%AC%E5%8B%BF%E7%8E%A9%E7%81%AB-051606525.html

當然搜尋引擎在檢索時，我想應該還是看到中文的部份，所以在 SEO 上應該影響不大！

另外關於使用中文於 permalink 中時，其順序也很重要，因為每個瀏覽器處理 url 編碼的方法不一，小心因此而使得訪客無法瀏覽文章只獲得 404 Error！關於該問題可以參考 xdite 前輩的「[Yahoo News 的 SEO 網址所帶來的問題][1]」，裡頭有更詳盡的解說。

我也因為 xdite 前輩的文章而決定將 permalink 的結構設定為 **domainname/post_id/post_title**，以避免我有需要使用中文作為網址時，我的文章還可以使用 **domainname/post_id** 連結！


[1]:http://blog.xdite.net/posts/2011/10/25/yahoo-seo-url/?utm_source=feedburner&utm_medium=feed&utm_campaign=Feed%3A+xxddite+%28Blog.XDite.net%29

[wiki-seo]: http://en.wikipedia.org/wiki/Search_engine_optimization



