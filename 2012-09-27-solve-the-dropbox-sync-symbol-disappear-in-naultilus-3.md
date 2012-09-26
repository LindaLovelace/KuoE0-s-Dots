<!--
[date]: 2012-09-27
[titel]: 解決 nautilus 3 資料夾上 dropbox 同步符號消失
[title]: solve-the-dropbox-sync-symbol-disappear-in-naultilus-3
[tag]: Ubuntu, Linux, Dropbox
[photo]: http://i.minus.com/jbuADYTU24BwXF.png
-->

我目前的桌面管理套件為 [Cinnamon][1]，是一套非常優雅漂亮的桌面系統。實在用不習慣 [unity][2] 與 [GNOME-Shell][3]，unity 實在難用到爆，而 GNOME-Shell 在平鋪預覽視窗時較不規則，比較喜歡 Cinnamon 對齊的平鋪風格。而 Cinnamon 本身也是衍生自 [GNOME 3][3]，因此會遇到安裝 Dropbox 後，Dropbox 資料夾上不會顯示同步狀態。

該問題主要為從 Dropbox 官網下載的版本或是利用 `apt-get install nautilus-dropbox` 安裝的，都是以 nautilus 2 (檔案管理系統) 為對象，在 GNOME 3 後，預設所安裝的都已經是 nautilus 3 了！因此我們需要特別重新編譯 Dropbox 並安裝，才能令 Dropbox 同步狀態顯示於 nautilus 3 的資料夾上。

安裝步驟
--------

### 加入 dropbox source

	$ sudo apt-key adv --keyserver pgp.mit.edu --recv-keys 5044912E # add dropbox source key
	$ sudo sh -c 'echo "deb http://linux.dropbox.com/ubuntu/ precise main" >> /etc/apt/sources.list.d/dropbox.list'  # add dropbox package URI
	$ sudo sh -c 'echo "deb-src http://linux.dropbox.com/ubuntu/ precise main" >> /etc/apt/sources.list.d/dropbox.list' # add dropbox source file URI
	$ sudo apt-get update # update package database



### 下載原始碼並編譯安裝

	$ sudo apt-get source nautilus-dropbox
	$ sudo apt-get build-dep nautilus-dropbox
	$ sudo apt-get install build-essential dpkg-dev
	$ cd dropbox-1.4.0/
	$ sudo dpkg-buildpackage
	$ sudo dpkg -i ../dropbox_1.4.0_amd64.deb

### 重新啟動 dropbox

	$ killall nautilus
	$ nautilus&


[1]: http://cinnamon.linuxmint.com/
[2]: http://unity.ubuntu.com/
[3]: http://www.gnome.org/gnome-3/