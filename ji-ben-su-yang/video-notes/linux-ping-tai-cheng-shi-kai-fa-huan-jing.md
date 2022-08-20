# Linux 平台程式開發環境

### 如何安裝 Linux OS

1. 連線 Server
2. 安裝虛擬機
3. Windows subsystem for Linux
4. 直接安裝 OS 到電腦上

### [Basic Linux Command](https://www.hostinger.com/tutorials/linux-commands)

1. pwd: 顯示當前位置
2. cd: 進入/離開資料夾(路徑名稱可以按 Tab 補齊名稱)
3. ls: 顯示當前位置檔案
4. cat: 看指定檔案內容
5. cp: 複製
6. mv: 把檔案移動至其他位置 / 重新命名檔案
7. mkdir: 新增資料夾
8. rmdir: 刪除資料夾
9. rm: 刪除檔案(參數可以接 -r 、 -rf)
10. touch: 建立空白資料夾
11. locate: 找資料
12. find: 找資料(與 locate不同處在於依給定目錄中找資料)
13. grep: 找某個檔案中的特定字串，或是找給定名稱的檔案
14. sudo: 以管理員身分執行指令
15. df: 輸出系統空間大小
16. diff: 比對檔案內容差異
17. tar: 壓縮檔案
18. chown: 改變檔案所有人
19. kill: 把指定執行序刪除
20. top: 看當下程式執行狀態
21. ping: 觀察網站連線狀態
22. wget: 下載檔案

![grep](<../../.gitbook/assets/image (4).png>)

[pipes](https://thoughtbot.com/blog/input-output-redirection-in-the-shell#pipes) (symbol: |) 它可以把在前方的指令輸出，傳給後方指令使用&#x20;

.bashrc 可以更改環境變數(source .bashrc 重新執行，以變更環境變數)

![.bashrc](<../../.gitbook/assets/image (5).png>)
