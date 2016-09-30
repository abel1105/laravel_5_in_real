## Laravel in Linode Ubuntu 16.04

我們將安裝下列配置

1. PHP 7.0
2. Nginx
3. MySQL
3. Redis
4. Composer
5. Git

開始吧！

1. ```sudo apt-get update```
> 先將 Server 更新軟體資料庫，記得在每次安裝時，都養成好習慣輸入這個

2. ```sudo apt-get install software-properties-common```
> 因為目前 php7 沒有在 Ubuntu 的預設套件庫中，所以要先安裝可以用來安裝 Personal Package Archive (PPA) 的軟體，然後再透過它來安裝 php7

3. ```sudo add-apt-repository ppa:ondrej/php```
> 使用這個 ondrej 的安裝包，相關介紹：https://launchpad.net/~ondrej/+archive/ubuntu/php

4. ```sudo apt-get update```
> 引入後，再次更新軟體資料庫

5. ```sudo apt-get install php7.0 php7.0-cli php7.0-fpm php7.0-gd php7.0-mbstring php7.0-mysql php7.0-mcrypt php7.0-common```
> php7.0：php 主程式 *****
> 
> php7.0-cli：php command line extension *****
> 
> php7.0-fpm：FastCGI Process Manager *****
> 
> php7.0-curl：Curl extension 發送請求
> 
> php7.0-gd：php 圖片處理 extension
> 
> php7.0-mbstring：php 處理多字元字集 extension *****
> 
> php7.0-mysql：php mysql extension 
> 
> php7.0-mcrypt：php 加密 extension *****
> 
> php7.0-common：php 常見的 extension，包含 Tokenizer、phar、posix、shmop、ctype、sysvshm、sockets、ftp、pdo、gettext、fileinfo、sysvmsg、calendar、sysvsem、iconv、exif *****
> 
> **有加 * **的是 Laravel 一定要加的套件，這邊要注意

6. ```sudo apt-get remove apache2*```
> 有些 Server 供應商，例如：linode 會預裝 apache2，再安裝 nginx 時兩個會衝突，確認方法是下面兩個指令選一個
> 
> `apt list --installed | grep apache`
> 
> `ps ax | grep apache`
> 
> 檢查有沒有 apache 被安裝起來

7. ```sudo apt-get install nginx```
> 安裝 nginx

8. ```mv /var/html/index.nginx-debian.html /var/html/index.html```
> 把原本安裝的apache index.html 移掉換成 nginx 預設的 index.nginx-debian.html

9. ```sudo apt-get install mysql-server```
> 安裝 Server MySQL，會跳出互動世界介面，供你輸入 root 密碼

10. ```sudo apt-get install git```
> 安裝 Server git

11. ```sudo apt-get update```
> 再次更新軟體資料庫

14. ```sudo apt-get install redis-server```
> 安裝 redis-server
