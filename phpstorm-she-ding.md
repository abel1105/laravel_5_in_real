# PHPStorm 調教

## 一、資料夾設定

進入 Preference -&gt; Directories

![](/assets/螢幕快照 2017-04-24 上午8.44.03.png)

選到 app 的資料夾後，點一下上面的 mark as 「Sources」，完成後右邊就會如下圖一樣多出 Source Folder

![](/assets/螢幕快照 2017-04-24 上午8.46.12.png)

接下來，點一下 app 那行旁邊那個小小的 P ，然後再彈出的輸入框中輸入「App」，再按 ok 即可。

![](/assets/螢幕快照 2017-04-24 上午8.51.35.png)

最後再設定一個把 public 的資料夾改為 Resource Root。

![](/assets/螢幕快照 2017-04-24 上午8.56.06.png)

完成～

簡單說一下這麼做的好處在哪

1. 之後在每個資料夾下面按 `command + n` 後可以選擇 new 一個 PHP class ，而且 new 起來的 class，namespace 都會幫你打好！！（不用再每次卡在資料夾名稱跟namespace不一樣的 bug 了）
2. 寫在 blade 裡面的 css 跟 js 路徑再也不會找不到檔案了， command 鍵按著就可以指進去那隻 css 或 js 檔了。



