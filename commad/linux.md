# Linux 指令

\#\#\# 1\. SSH



\`\`\`sh

ssh ubuntu@54.199.249.177 -i ~/projects/tnl\_frontend\_key.pem

\`\`\`



\#\#\# 2\. SCP



\`\`\`sh

scp -r -i ~/projects/tnl\_frontend\_key.pem ubuntu@54.249.60.168:/home/web/tnl\_frontend\_laravel/storage/framework/views ~/Downloads

scp -i ~/projects/key\_ec2\_for\_able.pem /Users/abel/Downloads/Server/IntelliJIDEALicenseServer\_linux\_amd64 ubuntu@54.238.189.131:~/

\`\`\`



r ：目錄



\#\#\# 3\. sudo 使用 www-data 使用者權限



\`\`\`sh

sudo su

su -s /bin/bash www-data

\`\`\`



\#\#\# 4\. 更改檔案權限



把密鑰檔權限調小



\`\`\`sh

chmod -R 700 ~/Downloads/XXX.pem

\`\`\`



\#\#\# 5\. 更改檔案所有人



\`\`\`sh

chown root:root initial-setup-ks.cfg

\`\`\`



\#\#\# 6\. 把硬碟轉成記憶體 SWAP 1G



\`\`\`sh

sudo /bin/dd if=/dev/zero of=/var/swap.1 bs=1M count=1024

sudo /sbin/mkswap /var/swap.1

sudo /sbin/swapon /var/swap.1

\`\`\`



\#\#\# 7\. TOP 指令



\`\`\`sh

top

\`\`\`



按 1 可以看每個 CPU 狀態



按 u 後，輸入使用者名稱可以篩選使用者



按 f 可以進到 管理排序頁面 s 可以選取要用哪欄來進行排序，d 或 space 可以決定要顯示哪些欄位



\#\#\# 8\. ln 指令



\`\`\`sh

\# 硬連結 佔記憶體 不可以使用目錄

ln log-2013.log 2013link

\# 軟連結 不佔記憶體 可以使用目錄

ln -s log-2013.log 2013link

\`\`\`

