# Windows11 跳過聯網引導

如果你是預裝Win11或者升級到Win11的用戶，在首次激活系統的時候，
你有沒有被它繁瑣的激活流程勸退了一波？一套組合拳下來少說也有五六分鐘了。

那麼有沒有辦法跳過聯網，直接激活系統呢？

答案是有的，而且非常簡單，跟著操作，至少為你節省一半的時間。

> 注意：**操作方法（二）**在Windows更新了**22H2**後已經失效，更新的**操作方法（一）**可以正常跳過聯網激活

## 操作方法（一）

1.快速跳過前面兩項（語言）設置，直到選擇聯網頁面，**切記不要連接網線和WIFI**。

<img src="https://s2.loli.net/2023/12/10/WYxRuza9ieJ8nIE.jpg" width="660">

2.先進入需要連網的介面，按下鍵盤上的**「shift + f10」**，可以看到CMD窗口。

<img src="https://s2.loli.net/2023/12/10/rvptB7ioenFIxMf.jpg" width="660">

3.按下後會打開命令提示符，在其中輸入“oobe\bypassnro”並按下回車。

```bash
oobe\bypassnro
```

<img src="https://s2.loli.net/2023/12/10/SbPw1zxjnWXJy3E.jpg" width="660">

3.若失敗，可以重複上面的方法打開cmd，輸入“OOBE\BypassNRO.cmd”再回車。

4.使用上述指令後會重新啟動。

<img src="https://s2.loli.net/2023/12/10/VMxk4P3RjwQthGK.jpg" width="660">

5.再進入連網介面後可以發現，右下角多了一個「我沒有internet連線」。

<img src="https://s2.loli.net/2023/12/10/jZtVsEYKP3evgh1.jpg" width="660">

6.點擊它之後進入下圖介面，再點擊“繼續執行受限設定”，就可以跳過連網激活，進行後續的設定登入。

<img src="https://s2.loli.net/2023/12/10/ViAxIX1eoSuaBOz.jpg" width="660">


## ~~操作方法（二）~~ 已失效

在聯網界面時，首先按下Shift+F10或者是Fn+Shift+F10快捷鍵調出命令提示符窗口(CMD)，然後輸入taskmgr命令，並按下回車鍵。

``` bash
taskmgr
```

<img src="https://s2.loli.net/2022/11/14/ciEbZFOSVle5yqG.jpg">

接下來調出任務管理器頁面後，我們默認看到的是簡略信息狀態，此時需要我們點擊軟件界面頂端的“詳細信息”。

<img src="https://s2.loli.net/2022/11/14/q2BTHt5eRp87OlY.jpg">

然後找到“Network Connection Flow”進程或者是“網絡連接流”進程，選中後點擊“結束任務”，這樣就可以跳過聯網了。

<img src="https://s2.loli.net/2022/11/14/VE18uTAS2hwgBNM.jpg">

進入桌面後，在開始菜單中可能有部分圖標顯示空白或者灰色，這時候連接網絡，會自動下載這部分內容，並且聯網後也不需要綁定微軟賬號。

此外需要提醒大家，在進行到第二步輸入taskmgr命令時，我們也可以只輸入“taskkill /F /IM oobenetworkconnectionflow.exe”命令，按下回車鍵即可快速結束聯網進程，只是這個命令有點長容易輸錯，還是建議大家直接通過任務管理器來結束聯網過程吧。

``` bash
taskkill /F /IM oobenetworkconnectionflow.exe
```

<img src="https://s2.loli.net/2022/11/14/sGqYoigpjRFm81d.jpg">