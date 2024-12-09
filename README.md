# db-migrate-startkit

## 事前準備

下載安裝Docker Desktop
* [Windows版](https://desktop.docker.com/win/main/amd64/Docker%20Desktop%20Installer.exe?utm_source=docker&utm_medium=webreferral&utm_campaign=dd-smartbutton&utm_location=module&_gl=1*1x0tato*_gcl_au*NDk4NzQwNjM1LjE3MjczMzQ0NDY.*_ga*MTkxMzI2NzM5NC4xNjU5OTM4NTcy*_ga_XJWPQMJYHQ*MTcyNzMzMzcxNy4xNTYuMS4xNzI3MzM0NDY4LjM3LjAuMA..)
* Mac版
  * [Intel處理器](https://desktop.docker.com/mac/main/amd64/Docker.dmg?utm_source=docker&utm_medium=webreferral&utm_campaign=dd-smartbutton&utm_location=module&_gl=1*sjadaf*_gcl_au*NDk4NzQwNjM1LjE3MjczMzQ0NDY.*_ga*MTkxMzI2NzM5NC4xNjU5OTM4NTcy*_ga_XJWPQMJYHQ*MTcyNzMzMzcxNy4xNTYuMS4xNzI3MzM0NDY4LjM3LjAuMA..)
  * [M系列處理器](https://desktop.docker.com/mac/main/arm64/Docker.dmg?utm_source=docker&utm_medium=webreferral&utm_campaign=dd-smartbutton&utm_location=module&_gl=1*sjadaf*_gcl_au*NDk4NzQwNjM1LjE3MjczMzQ0NDY.*_ga*MTkxMzI2NzM5NC4xNjU5OTM4NTcy*_ga_XJWPQMJYHQ*MTcyNzMzMzcxNy4xNTYuMS4xNzI3MzM0NDY4LjM3LjAuMA..)

下載並安裝Node.js
* [下載連結](https://nodejs.org/zh-tw)

下載並安裝Dbeaver Community
* [Windows版](https://dbeaver.io/files/dbeaver-ce-latest-x86_64-setup.exe)
* Mac版
  * [Intel處理器](https://dbeaver.io/files/dbeaver-ce-latest-macos-x86_64.dmg)
  * [M系列處理器](https://dbeaver.io/files/dbeaver-ce-latest-macos-aarch64.dmg)

## 開始使用

### 安裝套件

>執行前請確保已經安裝了Node.js

打開終端機並輸入以下指令
```
$ npm i
```

### 首次在本機開啟資料庫並執行遷移

> 請確保Docker Desktop已經正常啟動，並能夠看到容器頁面(Containers)

打開終端機並輸入以下指令，程式將自動啟動資料庫，並運行遷移
```
$ npm run start
```

啟動後，請檢查Docker Desktop程式界面中裡是否新增db-migrate-startkit的容器堆疊，該堆疊裡了有兩個容器：
* db_migrate-1：執行遷移檔案的容器，執行後會自動關閉（狀態（STATUS）為Exited）。請務必進入檢查查看遷移的執行結果，確保遷移執行成功。
* postgres-1：資料庫容器，狀態應為Running

### 重新啟動資料庫
```
$ npm run restart
```
### 關閉資料庫
```
$ npm run stop
```

### 關閉資料庫並清除資料
```
$ npm run clean
```
DBeaver 操作
1. 在 DBeaver 資料庫中的資料夾右鍵，選擇 Refresh 刷新。
2. 重新開啟 SQL 腳本進行檢查。

## 使用 DBeaver 連接本地端 PostgreSQL 資料庫

### 開啟 DBeaver 並建立連線

1. 啟動 DBeaver，點擊左上角插頭圖標。
2. 選擇 PostgreSQL（大象圖標），點擊下一步。
3. 設定連線參數
4. 測試連線: 點擊左下角的測試連線，確保連線成功。
5. 點擊 Finish 完成設定

### 資料庫操作

1. 資料庫瀏覽器中會顯示新建立的連線。
2. 右鍵資料夾，選擇 SQL 編輯器 -> 開啟 SQL 腳本，即可執行 SQL 指令。

## 提交專案至 GitHub

1. 開啟 GitHub Actions
2. 確認專案已提交至 GitHub。
3. 開啟 GitHub Actions 頁面，檢查測試指令是否有錯誤。
