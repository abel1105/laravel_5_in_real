# Linux 指令

### 1. SSH

```sh
ssh remote_user@remote_ip -i ssh_pub_key_path
```

### 2. SCP

```sh
# 把檔案從 remote 下載下來
scp -i ssh_pub_key_path remote_user@remote_ip:remote_file_path local_file_path

# 把檔案傳到 remote 去
scp -i ssh_pub_key_path local_file_path remote_user@remote_ip:remote_file_path
```

r ：目錄

i ：SSH public key

### 3. sudo 使用 www-data 使用者權限

```sh
sudo su -s /bin/bash www-data
```

### 4. 更改檔案權限

把密鑰檔權限調小

```sh
chmod -R 700 local.pem
```

### 5. 更改檔案所有人

```sh
chown root:root local_file_path
```

### 6. 把硬碟轉成記憶體 SWAP 1G

```sh
sudo /bin/dd if=/dev/zero of=/var/swap.1 bs=1M count=1024
sudo /sbin/mkswap /var/swap.1
sudo /sbin/swapon /var/swap.1
```

###### 如果要2G 可以把 count 後面調成 2048 以此類推

### 7. TOP 指令

```sh
top
```

按 1 可以看每個 CPU 狀態

按 u 後，輸入使用者名稱可以篩選使用者

按 f 可以進到 管理排序頁面 s 可以選取要用哪欄來進行排序，d 或 space 可以決定要顯示哪些欄位

### 8. ln 指令

```sh
# 硬連結 佔記憶體 不可以使用目錄
ln log-2013.log 2013link

# 軟連結 不佔記憶體 可以使用目錄
ln -s log-2013.log 2013link
```



