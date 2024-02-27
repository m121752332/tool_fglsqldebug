# FGLSQLDEBUG log viewer

## 工具描述

本工具可以讀取FGLSQLDEBUG輸出，並在圖形介面中顯示日誌記錄。  
然後，您可以對日誌記錄進行排序、搜尋和過濾，以找到您要尋找的內容。

![FGLSQLDEBUG viewer (GDC)](https://github.com/m121752332/tool_fglsqldebug/blob/master/docs/fglsqldebug-screen-001.png)

## 使用需求

* Genero BDL 2.40+
* Genero Desktop Client 2.40+
* Genero Studio 2.40+
* GNU Make

## 指令視窗用法

1. make clean all

## Genero Studio開發工具用法

1. 讀取 fglsqldebug.4pw 專案檔
2. 編譯整個專案包

## 用法

1. 取得 FGLSQLDEBUG 記錄檔做於後續分析，TIPTOP可用r.r2d 收集執行後的結果
2. 設置 FGLSOURCEPATH 環境變數把4gl的目錄添加用於產生 FGLSQLDEBUG 後的紀錄
3. 執行工具語法 fglrun fglsqldebug [-f logfile [-r]]
4. 畫面的第一行可以挑選LOG檔讀取產生的紀錄
5. 使用過濾器可以塞選LOG的紀錄
6. Run profiling statistics for find time consuming SQL statements

The log records are loaded into an SQLite database created automatically if it does not exist.
One database file is created for each log.
By default, the tool does not re-parse the log file if the database exists already.
你也能強制重取LOG檔透過 -r 參數處理

若 FGLSOURCEPATH 環境變數有做好定義，本工具也能檢閱程式碼

## 請參考原廠文件

參考 [Genero BDL documentation](http://www.4js.com/download/documentation) 
更多詳細用法關於 FGLSQLDEBUG 和 FGLSOURCEPATH 環境變數介紹


## 中文化

已繁體中文處理，使用於TIPTOP GP 5.3除錯過

## 畫面修改

若自行編輯畫面後，可透過原廠指令編譯畫面
```程式類型=
gsform -M -i -dbname ds -keep fglsqldebug.4fd
gsform -M -i -dbname ds -keep stmtstats.4fd
gsform -M -i -dbname ds -keep showtext.4fd
gsform -M -i -dbname ds -keep drvmsgs.4fd
```

參考: [gsform語法](https://4js.com/online_documentation/fjs-gst-manual-html/index.html#gst-topics/c_gst_formdesigner_designform_012.html)
