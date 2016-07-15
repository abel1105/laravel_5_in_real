一般正常我們在Laravel Debug 時都會用

```dd()``` 或是 ```var_dump()``` 方法來進行 Debug

查看目前的變數裡面到底存什麼

當然這個方法非常直覺，想要看什麼，直接把那個變數帶進去就知道了

但當程式越來越複雜，你得把一個個商業邏輯都是抽得乾乾淨淨。可能你每次跑一個Controller Action 都要跑超過三四隻 php 檔，可能是 Service、Repository 檔案。

這時候你很容易忘記把 ```dd()``` 或是 ```var_dump()```加在哪裡。或是每次Debug都要，加```dd()```、刪```dd()```、加```dd()```、刪```dd()```、加```dd()```、刪```dd()```，一直重複寫這些code。

如果你有以上困擾，建議你開始使用 Xdebug。

首先先在你主機的php加上Xdebug，如果你是用 MAMP PRO 來開發的話，在 PHP 的標籤就可以直接打勾起來使用Xdebug了。

如果不是的話建議使用 Homebrew 來安裝。

```
brew install php<version number>-xdebug
```
例如我是 PHP 7.0版，就輸入

```
brew install php70-xdebug
```

全部安裝好後，輸入一下

```
php -v
```
看以下有沒有下面類似的字
	
```
with Xdebug v2.4.0RC2, Copyright (c) 2002-2015, by Derick Rethans
```

如果有就是安裝好了

> *小提醒：在使用 Composer 功能前（例如 composer update 、 composer install）輸入```php --ini```，找到目前吃到的 php.ini 檔，將下面這行前面加上```;```，把它註解掉，這樣 Composer 才不會跑太久～
> 
> ```
> zend_extension="/.../xdebug.so"
> ```
> 當然比較方便的做法是跑 composer 跟跑你專案的 php 是不一樣一個，像是你在 Homebrew 上裝 Xdebug，然後用 Mac 上原生 php 用來跑 Composer;或是你下載 MAMP 並在上面裝 Xdebug，然後一樣用 Mac 上原生 php 用來跑 Composer。注意兩個php版本盡量一致。




參考資源：

1. http://confluence.jetbrains.com/display/PhpStorm/Xdebug+Installation+Guide
2. https://laracasts.com/series/how-to-be-awesome-in-phpstorm/episodes/20