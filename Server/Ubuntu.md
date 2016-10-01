## Laravel in Linode Ubuntu 16.04

我們將安裝下列配置，照順序在 Ubuntu 16.04 上安裝起來

1. PHP 7.0
2. Nginx 1.10.0
3. MySQL 5.7
4. Git
3. Redis
4. Composer

讓我們開始吧！

## 更新軟體資料庫

 	sudo apt-get update

先將 Server 更新軟體資料庫，記得在每次安裝軟體時，都養成好習慣先輸入這個指令

## 解決 Locale 語言問題

	locale-gen
	sudo locale-gen --lang zh_TW.UTF-8

如果再跑上面的指令時，一直看到下面這串文字，或是進到 Server 時也有看到的話

Cannot set LC_CTYPE to default locale: No such file or directory

就先來解決他吧，基本上不會有什麼大問題，但一直看到也是挺煩的

 
輸完上面兩個指令後，可以再輸入下面這個指令檢查他還不會出錯

	locale

## 新增可以讀取套件資源庫的軟體

	sudo apt-get install software-properties-common

因為目前 php7 沒有在 Ubuntu 的預設套件庫中，所以要先安裝可以用來安裝 Personal Package Archive (PPA) 的軟體，然後再透過它來安裝 php7
	
## 加入 PHP 7 的套件資源庫	

	sudo add-apt-repository ppa:ondrej/php

先加入這個 ondrej 的安裝包

相關介紹：[https://launchpad.net/~ondrej/+archive/ubuntu/php](https://launchpad.net/~ondrej/+archive/ubuntu/php)

## 更新軟體資料庫

	sudo apt-get update

引入後，再次更新軟體資料庫

## 安裝 PHP 7.0 相關套件	
	
	sudo apt-get install php7.0 php7.0-cli php7.0-fpm php7.0-mbstring php7.0-mcrypt php7.0-xml php7.0-zip php7.0-common php7.0-opcache php7.0-soap php7.0-gd php7.0-imap php7.0-curl php7.0-tidy php7.0-mysql php7.0-bcmath php7.0-intl
	
安裝的這些套件，參考自 Laravel 官方替 Homestead 安裝的套件，以下套件的詳細說明都可以在 [http://php.net/manual/zh/funcref.php](http://php.net/manual/zh/funcref.php) 這裡找到。

php7.0：php 主程式 *

php7.0-cli：php command line extension *

php7.0-fpm：FastCGI Process Manager *

php7.0-mbstring：php 處理多字元字集 extension *

php7.0-mcrypt：php 加密 extension *

php7.0-xml：php XML 操作 extension *

php7.0-zip：php 壓縮 extension（composer 安裝必須）*

php7.0-common：php 常見的 extension，包含 Tokenizer、phar、posix、shmop、ctype、sysvshm、sockets、ftp、pdo、gettext、fileinfo、sysvmsg、calendar、sysvsem、iconv、exif *

php7.0-opcache：php Opcache extension

php7.0-soap：php Simple Object Access Protocol（soap）extension

php7.0-gd：php 圖片處理 extension

php7.0-imap：php 圖片處理 extension

php7.0-curl：php 發送 curl extension

php7.0-tidy：php 修正 HTML 錯誤 extension

php7.0-mysql：php MySQL extension

php7.0-bcmath：php 任意精度數學 extension

php7.0-intl：php 國際化與字符編碼支持 extension
 
**有加「＊」** 的是 Laravel 一定要加的套件，這邊要注意一下，如果沒裝的話，Laravel 一定會出錯。




## 移除預設 Apache

	sudo apt-get remove apache2*

有些 Server 供應商，例如：linode 會預裝 apache2，再安裝 nginx 時兩個會衝突，確認方法是下面兩個指令選一個，檢查有沒有 apache 被安裝起來

第一個：

	apt list --installed | grep apache

第二個：

	ps ax | grep apache


	
## 安裝 nginx

	sudo apt-get install nginx

## 把原本 apache 測試頁面覆蓋

把原本安裝的apache index.html 移掉換成 nginx 預設的 index.nginx-debian.html

	mv /var/html/index.nginx-debian.html /var/html/index.html

## 安裝 MySQL

安裝 Server MySQL，會跳出互動世界介面，供你輸入 root 密碼

	sudo apt-get install mysql-server

## 安裝 Git

	sudo apt-get install git

## 安裝 redis-server

	sudo apt-get install redis-server

## 安裝 Composer

	curl -sS https://getcomposer.org/installer | php
	
## 將 Composer 執行檔移到系統預設的環境變數路徑	
	sudo mv composer.phar /usr/bin/composer