<!--
[date]: 2011-08-09
[title]: 遷移至 AWS 以及新域名
[name]: migration-to-the-aws-and-the-new-domain-name
[tag]:  AWS, WordPress, domain name | 域名
-->

![遷移至 AWS 以及新網域][feature photo]

上禮拜歷經千辛萬苦，總算成功申請到 AWS 的帳號，也曾經先自己在 localhost 嘗試搬家的工程，歷經一整晚才成功。

由於 [AWS][1] 現在有新用戶可以免費用一年的 micro instance 的優惠。其實剛開始完全不知道 AWS 是什麼，但 Gulu 就是架在 AWS 上面，所以在公司常聽到這個詞。去查了一下才發現於原來是 [Amazon Web Service][1]。之前部落格都架在家裡，我家網路又超級無敵慢，用的是種花電信的 ADSL，頻寬只有 3M/384K，相信之前來過我部落格的讀者都可以體會有多慢:(。

因為只有一年，實在不希望浪費到任何的時間，所以決定一定要先搞定整個遷移的工作。所以花了一兩天，在自己的電腦上重新安裝 wordpress，然後下載資料庫並匯入新的資料庫裡。但被檔案權限搞死，一直有地方失敗。而且之前的主機是 mac osx server，跟 ubuntu 的設定方式感覺滿多不一樣的。畢竟 mac 的 server 其實真的是滿人性化的，很多設定只要打開 server admin 打個勾就完成了。另外搞最久的大概是 permalink，上網查資料發現好像 Ubuntu + Apache2 的設定方式有比較特殊？！至少我按照很多方法都失敗，最後是加上 ubuntu 關鍵字去搜尋，好像是在 `/etc/apache2/apache2.conf` 加了點東西才成功的，不像很多都只是打開 rewrite_mod 就好。

在有把握移植的程序後，就申請了 AWS，然後開始等待驗證電話。結果我驗證電話等了好幾天都沒來，在禮拜一去上班時，跟小Q借他的號碼重試，但還是沒有任何電話打來:(。後來跟阿呈借，沒想到按了確定沒多久後，就又電話打來了＝ ＝。**我強烈懷疑 Amazon 對 android 有偏見！！！**（我跟小Q都用 android，阿呈用 iPhone！！）

AWS 申請好後，就是要建立一個 instance，試了將近十種 AIM 才找到個滿意的。本來找了 bitnami 的 LAMP，後來又找了 for wordpress 的版本，還是了一大堆都不滿意。找了好久才找到一個乾淨的 ubuntu 11.04，還是乾淨的 ubuntu 用起來比較順手，畢竟自己不熟，別人裝好感覺設定更麻煩還要遷就他，自己重頭還是比較放心。

在嘗試各種 AIM 的過程中，也去 [only domains][2] 買了 [kuoe0.ch][3] 這個網域，有個自己的網域真爽 XD。接著總算可以正式得來搬家了！但這是搬家超級不順利，但不外乎都是權限問題，這次很用心地去瞭解了 owner 跟 group 等等的關係了，還好上禮拜在鳥哥有看到這個章節。加上之前有紀錄權限設定的文章，但其實那篇好像有點問題。最後還是去看原來主機的設定，依樣畫葫蘆的方式照著設定。

接著又遇到一個非常棘手的問題，**所有的圖片都連到舊的主機**…這太慘了。但我不會 SQL 語法，所以我就用記事本打開備份出來的 SQL 檔案，直接全部取代= =。*方法有點愚蠢，但竟然真的有效！*最後再解決 permalink 就總算大功告成了！！話說今天早上 AWS 還掛掉，該不會是我害的吧．．．。我還以為是我的 instance 又掛掉了．．．（他被我弄掛滿多次，常常莫名就不動了，還登入不了，只好砍掉重練）。

至於為什麼要買 [kuoe0.ch][3] 這個網址呢？KuoE0 應該不用解釋，但我為了 domain name 想了好久。首先是想要 `.ac`（ACMer 都懂 XD），但他實在太貴我負擔不起 :(。後來又考慮 `.py`，最近開始寫 Python，想說 `.py` 滿酷的！！但其實比較適合小Q，我對 Python 其實還不熟。然後 `.com` 跟 `.org` 價格好像還好而已。可是我只是個人，覺得 `.com` 太怪了，`.org` 又太普遍了，就是不想要太普通的 domain name。就在 wiki 的 [domain name][4] 這頁研究好久，看到 `.ch` 就覺得還不錯。就順便查了價格，價格是 **$15/Year**，換成台幣大概四百多，一年四百多滿便宜的！！就決定用 `.ch` 了，因為 CH 是我名字 Chih-Hsuan 的縮寫 XD。

[1]: http://aws.amazon.com/
[2]: http://www.onlydomains.com/
[3]: http://kuoe0.ch/
[4]: http://zh.wikipedia.org/wiki/%E5%9F%9F%E5%90%8D
[feature photo]: http://i.minus.com/jbhjObcQQQ58WC.png
