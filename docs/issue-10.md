# Windows10/11 KMS最純淨的激活方式

## 前言

- KMS激活是需要聯網的
- 此激活教程僅支持官方原版 Windows，原版Windows安裝請查看往期[教程](docs/issue-8.md "教程")

## 教程

1.進入[微軟官方KMS文檔](https://learn.microsoft.com/zh-cn/windows-server/get-started/kms-client-activation-keys "微軟官方KMS文檔")，找到對應系統版本的`key`，這裏以Windows10 Pro 為例
```bash
W269N-WFGWX-YVC9B-4J6C9-T83GX
```
p1

2.訪問 [KMS服務器列表](https://www.coolhub.top/tech-articles/kms_list.html "KMS服務器列表")，拿到KMS服務器地址
p2

3.右鍵win，打開**Windows PowerShell (Admin)**
p3

4.ping一下KMS服務器的地址，篩選出 一個成功的`kms server`地址
```bash
ping kms.loli.best
```
p4


5.這樣我們得到了`key`和 `kms server`，成功了90%

------------

6.卸載當前的key，PowerShell (Admin)輸入**slmgr.vbs /upk**，等待彈出視窗顯示**已成功卸載了**
```bash
slmgr.vbs /upk
```
p6

7.將`key`放入到Windows裡面，PowerShell (Admin)輸入**slmgr /ipk [key]**，例如：
```bash
slmgr /ipk W269N-WFGWX-YVC9B-4J6C9-T83GX
```
p7

8.修改Windows的`kms server`，PowerShell (Admin)輸入**slmgr /skms [kms server]**，例如：
```bash
slmgr /skms kms.loli.best
```
p8

9.激活，PowerShell (Admin)輸入**slmgr /ato**，等待一段時間，彈出成功激活提示
```bash
slmgr /ato
```
p9