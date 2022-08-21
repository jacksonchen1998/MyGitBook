# GIT 的基本使用教學

### Notes

![](<../../.gitbook/assets/image (13).png>)

#### 安裝 Git

`sudo apt install git`&#x20;

#### 設定名稱

`git config --global user.name Github使用者名稱`&#x20;

#### 設定信箱

`git config --global user.email Github電子信箱`

#### 初始化Git專案

`git init`

#### 顯示當前版本狀態

`git status`

#### 新增檔案至 Git stage

`git add 檔名`

#### 紀錄 Git 當前改動

`git commit`

`git commit -m "The message that you want to describe about the commit"`

![第一行為改動標題，下方為此改動的註解](<../../.gitbook/assets/image (8).png>)

#### 檢視 Git 提交紀錄

`git log`

#### 宣告要讓 Git 忽略那些檔案

`vim .gitignore`

#### 顯示 commit 改動細節 (hash code comes from `git log`)

`git show "hash code"`

#### 返回 Git 指定版本

`git reset "hash code"`

#### 更改先前 commit 檔案

`git commit --amend`

#### 從原先`master`拉出分支

`git checkout -b 分支名稱`

#### 切換分支

`git checkout 分支名稱`

#### 整合指定分支

`git merge 分支名稱`

### Reference

[My medium blog for How to use Git](https://medium.com/@jackson1998/note-git-tutorial-for-beginners-259a75043817)

