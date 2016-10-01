# 設定 GitHub SSH

首先，先假設你把 Laravel 都放在你的 Git 上，你打算把原本你寫好的 Laravel 移到 Server 上。

因為現在這台 Server 上還沒有 SSH key，可供你 github 來使用。

所以我們先來替 www-data 這個使用者，新增 SSH Key。

你可能會好奇，為什麼要用 ```www-data```，而不要用 ```root``` 使用者來新增。其實是因為，之後使用者照訪你的網站時，他會透過 nginx 來訪問，而 nginx 預設的使用者，即是 ```www-data```。而為了要讓你的網站資料夾，可以讓 ```www-data``` 的權限來讀取，所以 Laravel 的權限也得是 **www-data:www-data**。因此 git 也用 ```www-data``` 來讀取或寫入的話，更是再好不過了，要不然之後就會看到很多 ```no permission``` 的錯誤。

## 新增 /var/www/.ssh 的目錄

	mkdir /var/www/.ssh
	
因為 ```www-data``` 的 ssh key 是放在 /var/www/.ssh 下面，所以先用 ```root``` 幫他新增一個資料夾。	
	
## 把 /var/www/.ssh 的目錄權限改為 www-data:www-data

	chown www-data:www-data /var/www/.ssh
	
再把 /var/www/.ssh 的目錄權限改成 ```www-data:www-data``` ，等下用 www-data  新增 SSH key 時，才能正常寫入。

## 切換使用者至 www-data

	sudo su
	su -s /bin/bash www-data
	
這裡透過 ```su``` 來模擬 ```www-data``` 使用者。	
## 先檢查有沒有在使用的 SSH key

	ls -al ~/.ssh
	
有的話就可以跳過生成 ssh 的步驟

## 產生新的 SSH Key

	ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

your_email@example.com 建議輸入你自己 github 的 email

中間停頓的點，一直按 enter 就可以了，或是你也可以自己輸 SSH 的保護密碼。

## 新增 SSH key 到 ssh-agent

	eval "$(ssh-agent -s)"
	
	ssh-add ~/.ssh/id_rsa
	
## 複製 public key 裡面的資料

	vim ~/.ssh/id_rsa.pub

用滑鼠把全部選起來再按 Ctrl + C (Cmd + C)，就複製完畢了

vim 全選複製的指令是：

	: % y +	

## 到你自己的 Github 把複製的貼上去

![image/01.png](前往帳戶的設定)

前往你自己 github 的設定區塊

![iamge/02.png](選SSH and GPG keys)

在左邊的導覽列選擇 SSH and GPG keys

![image/03.png](新增ssh key)

點擊新增 SSH Key

![image/04.png](貼上剛剛複製的public key)

貼上剛剛複製的 public key

![iamge/05.png](完成後再按Add SSH Key)

完成後再按 Add SSH Key 的按鈕

## 回到 Server 測試 是否成功

	ssh -T git@github.com
	
檢查看看回傳的資料是否有你的 github 帳號名字


這樣就完成囉！	








