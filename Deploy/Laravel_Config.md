# 設定 Laravel	
	
	
## 設定根目錄資料夾權限


### 修改權限為 www-data:www-data

	sudo chown -R www-data:www-data /var/www/laravel
	
目前假設你把 /var/www/laravel 當你的根目錄


### 修改 Storage 的資料夾的權限為 775

	sudo chmod -R 775 /var/www/laravel/storage