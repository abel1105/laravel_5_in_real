

### 1\. 回復到先前的Commit，使用時機 PULL 最新的後Server掛掉

```sh
git checkout HEAD~2
```

最後的數字代表到第幾個

```sh
HEAD, HEAD^, and HEAD~2
```

### 2\. 套用最新的Commit

```sh
git pull 
git pull origin master
```

### 3\. 更新 submodule

```sh
git submodule update
```

### 4\. 檢查 git 狀態

```sh
git status
```

### 5\. 重設 git 到 最新

```sh
git reset --hard
```

### 6\. 取得目前 HEAD Commit 代號

```sh
git rev-parse HEAD
```
