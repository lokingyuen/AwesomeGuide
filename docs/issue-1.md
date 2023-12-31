# Bat：批量創建與文件同名的文件夾，並將文件移動到相應的文件夾內


特殊案例：最近發現有哋同學整理數據時，需要為每個文件創建一個與文件同名的文件夾（同名不同後綴的文件也只創建一個文件夾），並且將文件移動到相應的文件夾中。

這種Windows文件重複性工作，我哋可以善用 .bat 腳本以提高效率。

## 操作示範
新建一個記事本文件（txt文件），然後將下列代碼複製到新建的 txt 文件中（注意修改將文件路徑以及文件後綴名改成自己的），然後將**txt**後綴名改成 **bat**，最後運行。

``` bash
@echo off
for /r "C:\test2" %%i in (*.jpg) do (
md "C:\test2\%%~ni\"
move "%%i" "C:\test2\%%~ni\"
)
pause
```


## 代碼解釋
“C:\test2”要改為需操作的文件夾路徑， (*.jpg)要改為文件的 後綴名。

``` bash
for /r "C:\test2" %%i in (*.jpg) do (
```
**也可以改成相對應的路徑**，比如：“C:\***\%%~ni\”

``` bash
md "C:\***\%%~ni\"
move "%%i" "C:\***\%%~ni\"
```


## 效果展示
運行前 ----->運行后<br>

<img src="https://s2.loli.net/2022/10/05/FBd6ARsWfVq9ylL.jpg" width="660">

</br>


<img src="https://s2.loli.net/2022/10/05/UzKLS2YDeMGOqls.jpg" width="660">

</br>


其實這是 腳本（.bat）的其中一項小功能，同學們要勇於發掘，善用Google老師，科技改變生活。