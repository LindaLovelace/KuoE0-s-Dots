<!--
[date]: 2012-12-08
[title]: 2012 ACM-ICPC Kaohsiung Site
[name]: 2012-acm-icpc-kaohsiung-site
[tag]: ACM-ICPC, contest | 競賽
-->

![2012 ACM-ICPC Kaohsiung Site][feature photo]

這次比賽的飯店與餐廳都還滿不錯的，相較於前年來說實在好很多XD。除了飯店房間內沒有 wifi，跟早餐只有麥當勞外。但這次比賽結果與前年相較也是退步極多，去年開始就表現的非常差，去年參賽結束後，曾希望可以花一年的時間再來衝一次。但還是沒做到，現在的我好像沒辦法像以前一樣每天都寫 ACM，不眠不休的寫。接觸了許多不同的領域後，好像就很難定下心來純粹鑽研演算法了。

測試賽第二題的決策 DP，從以前就是我的死穴，過了兩年也沒進步。正式比賽的 PB，如此簡單的 BFS 我也想不出來，看來我連基礎的題目都解不出來了。沒練退步真的很快，我覺得我 coding 的能力正在指數級下降，演算法也是。

另外今年清大好強，隊伍數也夠也強，不會像是我們還有勉強湊出來的隊伍。而且清大從 NCPC 就表現不錯，今年派出國的隊伍竟然達五隊之多，與台大相當了呢！反觀成大近兩年，實力大概回到了電子哥開課之前那時候了吧。除了實力大減之外，也面臨了缺乏新生的困境。交大似乎也有相同的問題，這次 ICPC 參賽隊伍竟然只有 3 隊。而台大不用說，依然是台灣最強團隊。

感覺中央也很有機會崛起，除了 Morris 大神外，據說還有一位 inker 大神，一直只聞其名不見其人，希望未來有機會也可以彼此交流。今年還與中央的 Morris 大神同遊瑞豐夜市，真是非常榮幸。

這次比賽的閒暇時間，蠻多都花在討論或詢問其他學校的培訓方式，並請教是否有不錯的培訓方法可以推薦給我們。發現北大的 [POJ][1] 似乎是最多人在練習的 Online Judge，另外東大的選手有推薦會津大學的 [AOJ][2] 給新手，因為可以查看程式碼學習。而台大的朋友則建議可以多練習 [CodeForces][3] div2 的題目，前三題的程度應該較與我們相當。

得到不少的建議真的非常棒，希望未來成大能在重新站起來！不過，我這麼弱，希望不要誤人子弟了。

競賽過程
========

11/23 Day1
----------

早上大家先在火車站集合，再一起出發到往中山大學。前一天太晚睡，在火車上整個睡死，我兩個隊友更扯，趕作業趕到天亮，就直接沒睡了，一樣在火車上睡死。

來到中山大學後，先是簡單的報到手續，拿衣服手冊包包等等。接下來是看看表演的開幕式，金雄大大竟然有來！！！不過，開幕的敲鑼竟然不是金雄大大敲的，真令人意外倒是。接下來終於是機器測試賽，題目有兩題：經典的 3n+1 問題與取石子的決策問題。竟然在 3n+1 就卡死了，這應該要是 5 分鐘就能 AC 的才對阿…。最後發現自己耍蠢，題目上寫運算不會超過 32bit 整數，於是就很自以為的用了 int，死活過不了。最後用 long long int 才 AC，但總覺得這樣表示題目欺騙選手，這時才想到不超過 32bit 整數有可能是指 unsigned 的 32bit 整數，再用 unsigned int 測試一次的確 AC。

再來第二題的決策問題，一開始我們就開始找規律，但一直找到例外。印象中這種決策問題好像都是用 DP 來解，於是開始想遞迴式，最後也有想出來，但測試機器時間過去了還是沒有 AC。看了一下別人的作法，再檢討自己的作法發現我是讓這題無法 AC 的罪魁禍首。原因就只是自己懶惰，想要將很多行的作法，用簡單幾行來完成。但現在 coding 的功力實在大不如前了，不僅邏輯思路常有錯誤，寫出來的程式也是 bug 一堆，導致該決策問題無法解決。

令人難過的測試賽結束了，接下來的行程可以二選一：遊高雄港或是回飯店。其實我滿想去的啦，但好像很多人不想去，不過最後有學弟說要去，我就假裝是去陪他們，就跟著去了XD。兩年前的高雄賽區也是遊高雄港，但我記得我睡死了…。這次就很認真的看看這個我生長二十年的城市，第一次真正把整個高雄港繞一遍！在船上除了看風景外，還是要記得 social 一下，剛開始先跟交大大神聊一下。後來因為看夕陽的關係，旁邊站了個清大的。彼了第三年了，也常常看到他，心裡想著他應該也知道我吧！然後我就跟他裝熟聊了一下，聊聊培訓的方式等等。另外他也告訴我，東京賽區冠軍也在這艘船上，其中有 IOI 第二名跟 Google Code Jam 冠軍，太可怕了…。

遊港後回到飯店吃大餐，今年飯店是－**蓮潭會館**，好棒啊。有一隊日本選手與我們同桌，但教練是個巴西人！同桌不聊天是一件很尷尬的事情，於是我又只能用單字溝通法來跟他們聊天，第一個就是要先問他們來自哪間大學。一問之下發現是 University of Tsukuba 筑波大学，嗯沒聽過…。多虧餐廳有 wifi 讓我可以在用 Google Maps 延續這個話題，也多虧這暑假有去一下日本，所以又可以跟他們多一個話題，例如：京都怎麼都是廟！然後每上一道菜，我就會跟他們說這是什麼肉，像是 beef、pork、duck。最後上水果了，是西瓜，watermellon！無聊又問了他們西瓜的日文，すいか（suika）。我們好像一直念錯，他就拿出了一張卡－西瓜卡 suica card，讓我們照著唸！

晚飯後，我們各自回房間休息了。回到房間打開電視這是我的習慣，此時剛好九點，這時候的電影台幾乎都是剛開演。不小心轉到了「[讓子彈飛][4]」，想說九點開演應該十一點就演完了…，結果演到十二點！！！不過真的很好看就是了，蠻有趣有點像相聲，好期待第二集。不過演到十二點，害我十二點才能洗澡，網路成癮的我又一定要上個網才肯睡覺，最後十二點半睡覺，跟平常比起來是很早就是了。

11/24 Day2
----------

隔天七點起床，開始盥洗整理比賽物品，早早下樓準備吃早餐！結果 WTF，竟然只有教練可以吃飯店早餐，選手都沒有早餐券。研究了手冊才發現早餐會送到房間，還好沒有怒衝 7-11 買早餐，只好回房間等早餐了…。不過跟教練的差好多，我們的只有麥當勞，太傷心了 :(。

吃完早餐就出發往中山大學，比賽也正式開始了。首先看到 PA，與二進位轉換相關的題目。蠻早寫完的，但 submit 拿到 WA 就整個很驚嚇。題目說會有 120 位的十進位整數，才發現我陣列開太小。120 位的十進位整數轉換為二進位，我竟然算成會有 2<sup>120</sup> 位，陣列再大也不能開這麼大，於是我開始是純數學公式的解法，就暫時擱置他了，並丟給聖棨請他想數學解法。電腦就讓給白狗寫 PG 了，貌似是背包問題，他還問我 DP 怎麼將數字分兩堆且數字最小，我竟然想不到怎麼做，他就自己開始研究了。

我就在去看別題，看到 PE 好像是 matching 的題目，不過點的數量有 1000 個，感覺應該不是普通的 matching 了。於是決定去做 PB，8-puzzle 的變形，而且超多人 AC…，看到大家都有藍色氣球，自己卻沒有的壓力實在很大阿。想說既然大家都寫的出來，那應該不難，決定暴搜好了。白狗在 debug 的時間，我就拿來寫 PB，但我連暴搜的作法都寫不出來，很多條件沒設定好，導致遞迴時堆疊爆炸了…。

突然聖棨發現我算錯了，120 位的十進位整數轉換為二進位的長度應該是 log<sub>2</sub> 10<sup>120</sup>，大約 400 左右，根本不需要大數運算，改完陣列長度後就 AC 了… 199 分鐘過去了 :(。

接著繼續給白狗寫 PG，還好他後來很給力的把它 AC 了。這時候時間已經剩下大約一小時了，白狗告訴我他對於 PC 的想法，這題就多了些限制的 shortest path。平常只記錄距離的算法改成多記錄路徑就可以了，不過也是寫的很不順阿，還好最後有 AC 就是了。時間還有二十分鐘，聖棨好像想出了 PG 的作法，於是電腦就交給他去做 PG，我則繼續想 PB，那麼多人有藍色氣球應該不難阿！！！可惜最後，就只解出這三題了。

比賽結束馬上去問大家的 PB 怎麼做，一問就問到兩個暴搜＋剪支的作法。如果是這樣，也太多人解出來了吧！！另一隊大三的學弟也有解出 PB，於是請教了他們的作法，才知道竟然只是 BFS 就可以解決了。

最後僅拿到三顆氣球，很沮喪的離開賽場去拿托管的包包，在拿包包的過程中，白狗跟聖棨在交接氣球，但一不注意沒接好，**氣球飛走了**！！！好吧，就當我們零題吧，根本是來丟臉的 :(。成大最好的成績是四題，有兩隊，一隊是大三的學弟，另一隊是碩一的老人隊。接下來就是等官方決議比賽結果，大概要等個兩三小時吧。這段時間官方安排了爬柴山的活動，但實在沒有很想參加，我們成大的就只好一起走到西子灣的堤防上，然後爬上去，再坐下…大家圍起來取暖，唉 :(。

漫長的等待時間過去了，可以回到會場等頒獎了。按照慣例先頒 NCPC 的獎，所以我還是有上台丟臉的機會。外國隊伍說不定都心想：這傢伙這麼弱竟然是台灣國內賽第三名，台灣好弱喔，之類的。NCPC 頒獎過程超久，除了甲組外還有乙組丙組，我覺得國外隊伍大概要等的不耐煩了。最後終於要頒 ICPC 的獎項了，台大的 **+1 ironwood branch** 真的好強，讓台灣賽區的冠軍可以留在台灣！第二名則是上海交大，就去年跟上海交大教練聊過，他們派來台灣的都是來練經驗的不是最強的。第三名則是東京賽區冠軍隊伍－東京大學。另外，與我們同桌的筑波大學也拿到第六名，非常威猛啊！台灣隊伍除了台大之外，就剩清大有上頒獎台了，交大實力感覺真的變差了，而我們更慘就是。

頒獎後是令人期待的晚宴時間－**西子灣海景餐廳**！一進餐廳就看到大量的食物與水果，但卻不能吃，好像要長官們都到場了才能開動。大概過了十分鐘左右，大官們都到場了，晚宴也正是開動啦！就看到會場像暴動一樣，每樣食物都排滿了人，沒過多久食物就空了＝ ＝。整個沒吃到多少，不過晚宴時間對我來說食物沒很重要就是了，比較重要的是去找些其他學校的朋友聊天，以及認識些新朋友，這些可是每年比賽才見的到面的阿！聊天內容不外乎是比賽，討論各自學校狀況，討論培訓的方式，討論學弟妹等等。另外清大的也向東大請教培訓方式，也聽取了不少建議，對未來學弟妹的培訓我相信都非常有幫助。另外，這次晚宴超酷的竟然有抽獎！！獎品有 SONY 耳機，還有其他的忘了是啥，最大獎是－ SSD！抽到的也太爽，不過也是推坑，SSD 可是用了就回不去了。

晚宴後就搭車回飯店休息，白狗跟聖棨說想跟中央的 Morris 大神拍照，於是我就跟著去參觀神社了。最後竟然在 Morris 房間聊了超久，他們講到說想去夜市，最後就莫名成行了 XD。就跟學弟妹們還有 Morris 及他隊友一起去逛「**瑞豐夜市**」，不知道多久沒來瑞豐了，跟我以前來的印象真的差很多，自從捷運蓋好，人潮變多後就不太來了。還好有住這附近的學弟推薦美食跟飲料，不然我還真不知道該推薦他們吃啥。我們就隨便逛，看到想買的就買，我買了很酷的炸香蕉皮！之前在那些偽裝成新聞的綜藝節目裡面看過，一直很想試試看，不過一片香蕉皮要新台幣 30 元也頗貴的就是。

在買足了食物後，我們開始往其他地方繞，不小心就繞道了投籃跟丟球的地方。本來沒人要玩，結果身為系籃隊長的學弟被捧去投籃，最後竟然大家都想玩一局，不過大家都跑去玩丟憤怒鳥的遊戲，一切可能是白狗跟聖棨兩個人無聊想 PK 的緣故。遊戲結束後，我就莫名其妙的獲得愛心小手一支，看來下學期的培訓課程需要拿愛心小手好好教訓學生了！

逛完夜市後回到飯店，與 Morris 道別後，我們前往正在打牌的房間。然後就繼續打牌了，人數眾多還得分兩攤，一攤打撲克牌，一攤玩矮人礦坑。還因為太吵導致隔壁房客抗議，於是大廳就打電話來請我們放低音量了。為了不丟成大的臉，我們也非常自制的安靜打牌，寧可笑到內傷也不可打擾其他房客！時間不知不覺的過去，來到了三點多。整個想睡了才解散各自回房，此時還沒洗澡整個很崩潰，疲累的身心都快睡著了。我們用擲骰子來決定洗澡順序，擲三次，按照和的大小決定，最大的先洗，第一次就擲出 1 點！！！幾乎註定我輸了…，最後果然我最後洗了，現在的學弟，唉。洗完4洗完澡後，還因為學弟一些突發狀況心情不好，身為一個好學長一定要幫助學弟，只好陪他們聊聊天談談心，然後就五點多了，不知不覺的也睡著了。

起床也近十點了，早餐也都送來了，不過都冷掉了就是。最後大家都起床了，並在大廳集合一起拍張照留念，就各自解散了。

![][p1]

**update**

2013/08/04: 更正 AOJ 為會津大學的 OJ，並非愛知大學。

[1]: http://poj.org/
[2]: http://judge.u-aizu.ac.jp/onlinejudge/index.jsp
[3]: http://codeforces.com/
[4]: http://app.atmovies.com.tw/movie/movie.cfm?action=filmdata&film_id=flch41533117

[p1]: http://i.minus.com/jEG5qihqcXIMM.jpg
[feature photo]: http://i.minus.com/jK5OPFRa5PobJ.jpg