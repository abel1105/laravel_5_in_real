# 設定 Laravel	
	
	

## 修改權限為 www-data:www-data

~~~bash
sudo chown -R www-data:www-data /var/www/laravel
~~~
	
設定根目錄資料夾權限，目前假設你把 /var/www/laravel 當你的根目錄


## 修改 Storage 的資料夾的權限為 775

~~~bash
sudo chmod -R 775 /var/www/laravel/storage
~~~	

## 新增 .env 檔在根目錄

~~~bash
cd /var/www/laravel
vim .env
~~~
	
直接用 vim 編輯，如果本來不存在，就會新增一個檔案	
	
## 把 local 的 .env 複製過來

如果你已經在本機開發過的話，把 .env 裡面的內容直接複製過來貼上

如果你之前沒有在本機開發的話，可以到 ```.env.example``` 把裡面的內容全部複製過來。

~~~bash
vim .env.example
~~~
	
## 修改 .env 檔

記得因為你現在是放在 Server，要把裡面的

~~~
APP_ENV=local
APP_DEBUG=true
~~~

改成

~~~
APP_ENV=production
APP_DEBUG=false
~~~
	
這樣才不會把錯誤資訊都顯示出來，另外也可以跟 local 區分環境，程式就可以針對環境不一樣去跑不一樣的程式邏輯。

## Composer install

~~~bash
composer install --no-dev
~~~

如果你現在就去照訪網頁，還是會看到 500 的錯誤，因為還忘記下 composer install，輸入完上面的指令，才算完成。
而這邊的 ```--no-dev``` 用意是不要裝一些在開發環境才要裝的函式庫，例如：phpunit 測試...等，而這些開發環境的函式庫，都寫在 ```composer.json``` 裡面的 ```require-dev``` 裡面。


## 訪問 http://server_domain_or_IP

~~~
http://server_domain_or_IP
~~~

接著就可以，訪問你自己的 domain 或是 ip 來看有沒有成功囉～