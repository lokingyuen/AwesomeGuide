# Windows10/11 KMS最純淨的激活方式

## 前言

- KMS激活是需要聯網的
- 此激活教程僅支持官方原版 Windows，原版Windows安裝請查看往期[教程](docs/issue-8.md "教程")

## 教程

1.進入[微軟官方KMS文檔](https://learn.microsoft.com/zh-cn/windows-server/get-started/kms-client-activation-keys "微軟官方KMS文檔")，找到對應系統版本的`key`，這裏以Windows10 Pro 為例

```bash
W269N-WFGWX-YVC9B-4J6C9-T83GX
```

</br>

<img src="https://s2.loli.net/2023/12/12/QxEuvb2sT51BFMl.jpg" width="660">

</br>

2.訪問 [KMS服務器列表](https://www.coolhub.top/tech-articles/kms_list.html "KMS服務器列表")，拿到KMS服務器地址

<img src="https://s2.loli.net/2023/12/12/QCUHLovKw49e25p.jpg" width="660">

</br>

3.右鍵win，打開**Windows PowerShell (Admin)**

<img src="https://s2.loli.net/2023/12/12/K2ExJZRz8M5Wgyv.jpg" width="660">

</br>

4.ping一下KMS服務器的地址，篩選出 一個成功的`kms server`地址
```bash
ping kms.loli.best
```

<img src="https://s2.loli.net/2023/12/12/ocYzmwktrMGx31g.jpg" width="660">

</br>

5.這樣我們得到了`key`和 `kms server`，成功了90%

</br>

------------

6.卸載當前的key，PowerShell (Admin)輸入**slmgr /upk**，等待彈出視窗顯示**已成功卸載了**
> 如果提示找不到key，不用管，直接跳到下一步
```bash
slmgr /upk
```

<img src="https://s2.loli.net/2023/12/12/v1ujoVNJb9zF7f3.jpg" width="660">

</br>

7.將`key`放入到Windows裡面，PowerShell (Admin)輸入**slmgr /ipk [key]**，例如：
```bash
slmgr /ipk W269N-WFGWX-YVC9B-4J6C9-T83GX
```

<img src="https://s2.loli.net/2023/12/12/S3CztT2rB6QMmRn.jpg" width="660">

</br>

8.修改Windows的`kms server`，PowerShell (Admin)輸入**slmgr /skms [kms server]**，例如：
```bash
slmgr /skms kms.loli.best
```

<img src="https://s2.loli.net/2023/12/12/OhVWTb4du1Dlk83.jpg" width="660">

</br>

9.激活，PowerShell (Admin)輸入**slmgr /ato**，等待一段時間，彈出成功激活提示
```bash
slmgr /ato
```

<img src="https://s2.loli.net/2023/12/12/siWYcPT63veEyBj.jpg" width="660">

</br>

```bash
slmgr /xpr
//查看激活過期時間:
slmgr /dlv
//查看激活訊息
slmgr /ipk VK7JG-NPHTM-C97JM-9MPGT-3V66T
//Windows家庭版升級專業版（先斷網）

```