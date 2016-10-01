# 安裝 Laravel

下面分成兩種方式安裝 Laravel

1. 採用 Github 安裝 Laravel
2. 直接安裝 Laravel


# 1. 採用 Github 安裝 Laravel

如果你不是要用 Github 安裝的話，請跳過直接到到下面的「直接安裝 Laravel」

## 照訪 Github 上的 Repository

首先，先用瀏覽器照訪你 Github 上面的 Repo。

## 點選 Clone or Download 按鈕

![按Clone or Download](image/06.png)

## 複製 Clone with HTTPS 裡面的 link

![複製 Clone with HTTPS 裡面的 link](image/07.png)

## 把使用者改為 www-data

	sudo su
	su -s /bin/bash www-data	

## 輸入移動指令到你想要安裝的地方

	cd /var/www
	
我這裡用 /var/www 為範例

## Git Clone

	git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY
	
https://github.com/YOUR-USERNAME/YOUR-REPOSITORY 這裡取代成你剛剛複製的，Clone with HTTPS 裡面的 link

這樣就 okay 了～	


# 2. 直接安裝 Laravel

	sudo composer create-project laravel/laravel /var/www/laravel

如果我要在 /var/www/laravel 裡面安裝我的 Laravel 的空白專案的話，這樣輸入就可以了，他會自動幫你安裝最新版本的 Laravel。

如果你想要安裝特定版本的 Laravel 的話，直接在後面接著輸入版本好就好了

	sudo composer create-project laravel/laravel /var/www/laravel 5.3
	
	
這樣就 okay 了	
