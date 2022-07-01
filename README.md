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

### (check)3. "連結"本地(local)和雲端(remote)資料庫
:::spoiler 參考教學
https://ithelp.ithome.com.tw/articles/10227181
:::
如果該電腦為第一次與GitHub進行連結，則需要將該電腦的**該帳戶ssh公鑰**儲存至GitHub的SSH keys設定區。

::: info
查看ssh公私鑰筆記

:arrow_right: [ssh連線](/YmPbq0sURYKy4n3NpE46Gg)
:::


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

### 3. "下傳"雲端(remote)版本至本地資料庫(local)
```
git pull    //下傳github端的版本至local端
```

### 4. 刪除git的追蹤檔案

有時我們會想在.gitignore檔案中加入新的排除條件，但因為git會持續追蹤**已加入**追蹤名單的檔案，因此我們需要清空追蹤名單

```
git rm -r --cached .    //清空追蹤名單(會列出之前有被追蹤的所有檔案)
git add .               //依據新.gitignore追蹤檔案 (不會列出訊息)
```

### 5. 上傳版本遇到衝突
有時，有合作者會push更新的版本到remote端，此時：


雲端 版本: 1 -> 2 -> 3 -> 4

本地 版本: 1 -> 2 

所以會讓local無法順利push上github(remote)端，此時有兩種方法

#### 5-1. 先拉再推
```
git pull --rebase                //下傳"並整合"github端的版本至local端
git push origin <chosen branch>
```

#### 5-2. 強制上傳(不管你就是要聽我的)
```
git push -f origin <chosen branch>   // -f==-force
```


