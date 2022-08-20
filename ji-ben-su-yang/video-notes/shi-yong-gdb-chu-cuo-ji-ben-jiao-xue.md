# 使用 GDB 除錯基本教學

![](<../../.gitbook/assets/image (14).png>)

透過 `sudo apt install gdb` 安裝

使用 `gdb` 後面接目標文件名稱就可以進入

輸入`run`可以執行該指定目標文件

輸入`b 程式檔名:行數`可以新增中斷點，之後輸入 `run` 便可暫停執行在中斷點

`p 變數名稱`可以輸出當時階段變數裡存的值

`c` 可以繼續執行

`i b` 可以條列出所有的中斷點

`d 中斷點Num` 可以刪除指定中斷點

`bt` backtrace 可以顯示當下執行到哪裡

`frame 指定層`可以切換當下執行區段，也可以透過 `up` 或 `down` 切換

`step` 代表執行下一行程式

Watch more on [gdb Documentation](https://sourceware.org/gdb/current/onlinedocs/gdb.pdf)
