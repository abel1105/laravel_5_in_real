## Laravel 使用 Gmail 當發信系統設定

> **注意：** 目前使用 Laravel 5.3

如果打開 config/mail.php，忽略掉註解不看的話，大該內容是這樣
	
	<?php
	
	return [
    
	    'driver' => env('MAIL_DRIVER', 'smtp'),
	    
	    'host' => env('MAIL_HOST', 'smtp.mailgun.org'),
	
	    'port' => env('MAIL_PORT', 587),
	
	    'from' => [
	        'address' => 'hello@example.com',
	        'name' => 'Example',
	    ],
	
	    'encryption' => env('MAIL_ENCRYPTION', 'tls'),
	
	    'username' => env('MAIL_USERNAME'),
	
	    'password' => env('MAIL_PASSWORD'),
	
	    'sendmail' => '/usr/sbin/sendmail -bs',
    
    ]
    
裡面全部包含所有發信系統的設定，你可以看到他預設幾乎全部都可以用 env 檔來設定，而在Laravel 預設的 env 檔，與信件相關的設定如下：

	MAIL_DRIVER=smtp
	MAIL_HOST=mailtrap.io
	MAIL_PORT=2525
	MAIL_USERNAME=null
	MAIL_PASSWORD=null
	MAIL_ENCRYPTION=null
		
把他修改成：

	MAIL_DRIVER=smtp
	MAIL_HOST=smtp.gmail.com
	MAIL_PORT=587
	MAIL_USERNAME=你的Gmail帳號
	MAIL_PASSWORD=你的Gmail密碼
	MAIL_ENCRYPTION=tls
	
接下來，因為你要讓你的帳號供 Laravel 存取，所以要把你輸入的Gmail帳號的安全性調低，在瀏覽器登入 Google 的情況下，造訪

[https://www.google.com/settings/security/lesssecureapps](https://www.google.com/settings/security/lesssecureapps)


把 **安全性較低的應用程式存取權限** 設定為 **開啟**，同時在頁面上Google 會提醒你


