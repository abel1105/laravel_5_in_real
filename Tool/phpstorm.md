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

## 二、安裝 Laravel Plugin

一樣先進去 perference 裡面，在 plugin 的目錄下，先搜尋「laravel」，他會先跟你說「No plugins found.」，這時候就點旁邊的 Search in repositories，就可以找到了，再按照上面的指令安裝，然後重啟 PHPStorm 即可。

重啟後，這個 plugin 並沒有預設對每個專案\(project\)都開啟，要先到 perference 下去搜尋「laravel」，然後在 Languages & Frameworks &gt; PHP &gt; Laravel 下面，把「Enable plugins for this project」打勾才行。

![](/assets/螢幕快照 2017-04-24 上午9.08.37.png)

好處：

1. 在寫 Route 時，Controller 跟 action 都可以 auto-complete !!
2. 在寫 Blade 時，輸入 @ 後，都會有一堆 auto-complete 等著你去用 
3. view\(\)、route\(\)、config\(\) ...這些laravel預設就有的 helper function，都可以 auto-complete 裡面的參數 !!
4. 好處實在是太多了，有興趣的話再去 plugin 裡面細看說明。





