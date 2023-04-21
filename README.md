# ![](https://drive.google.com/uc?id=10INx5_pkhMcYRdx_OO4rXNXxcsvPtBYq) Error: Client does not support authentication protocol requested by server; consider upgrading MySQL client
> ##### 問題記錄.

<br>

<!--ts-->
## 目錄
* [簡介](#簡介)
* [參考資料](#參考資料)
<!--te-->

---
<br>

## 簡介
由於之前在安裝跟使用MySQL都是在Mac的環境上，剛好今天要在Windows上安裝並使用MySQL，
但是卻跑出"客戶端不支持服務器請求的認證協議"的錯誤，後來一查，發現只有在MySQL8.0版本之後的版本才會有這個問題.

目前這個問題最快的解法就是，如下:
- 開啟MySQL Workbench.
- 開啟Query頁面，並將以下語法打上去，並且按下查詢鍵.
> ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password'; <br>
  > 請記得'root'跟'password'需要替換成當初所設定的使用者帳號跟密碼.<br>
  > 'localhost'則是你要設定的url位置.
- 執行完後，在輸入以下語法，刷新權限即可.
> flush privileges;

---
<br>

## 參考資料
* [MySQL 8.0 - Client does not support authentication protocol requested by server; consider upgrading MySQL client](https://stackoverflow.com/questions/50093144/mysql-8-0-client-does-not-support-authentication-protocol-requested-by-server) <br>

---
<!--ts-->
#### [目錄 ↩](#目錄)
<!--te-->
---
