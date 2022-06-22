# Git 常用指令

[Toc]

## 設置本地(local)資料庫的前置作業
### 1. 建立新資料庫

```
git init           //新增.git資料夾，擺放git需要用到的資訊和檔案
```
### 2. "連結"本地(local)和雲端(remote)資料庫
```
git remote add origin <url, github資料庫的link>
//連結local-remote 雲端資料庫簡寫為origin
```

## 本地資料庫(local)的基本操作
### 1. "儲存"至本地資料庫(local)
```
git add .                          //依據.gitignore追蹤檔案 (不會列出訊息)
git commit -m "<commit message>"   //存檔至local的版本紀錄中(會列出新增而要被追蹤的檔案)
```

### 2. "上傳"local版本至雲端資料庫(remote)
```
git push origin <chosen branch>    //上傳local的版本至github端
```


### 3. 刪除git的追蹤檔案

有時我們會想在.gitignore檔案中加入新的排除條件，但因為git會持續追蹤**已加入**追蹤名單的檔案，因此我們需要清空追蹤名單

```
git rm -r --cached .    //清空追蹤名單(會列出之前有被追蹤的所有檔案)
git add .               //依據新.gitignore追蹤檔案 (不會列出訊息)
```

### 4. "下傳"雲端(remote)版本至本地資料庫(local)
```
git pull    //下傳github端的版本至local端
```
