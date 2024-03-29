[English](./README.md) | 繁體中文 
# FGLSQLDEBUG log viewer

## 工具描述

本工具可以讀取FGLSQLDEBUG輸出，並在圖形介面中顯示日誌記錄。  
然後，您可以對日誌記錄進行排序、搜尋和過濾，以找到您要尋找的內容。

![FGLSQLDEBUG viewer (GDC)](https://github.com/m121752332/tool_fglsqldebug/blob/master/docs/fglsqldebug-screen-001.png)

## 工具版本需求

* Genero BDL 2.40+
* Genero Desktop Client 2.40+
* Genero Studio 2.40+
* GNU Make

## 指令視窗用法

1. make clean all

## Genero Studio開發工具用法

1. 讀取 fglsqldebug.4pw 專案檔
2. 編譯整個專案包

## 操作說明

1. 取得 FGLSQLDEBUG 記錄檔做於後續分析，TIPTOP可用r.r2d 收集執行後的結果
2. 設置 FGLSOURCEPATH 環境變數把4gl的目錄添加用於產生 FGLSQLDEBUG 後的紀錄
3. 執行工具語法 fglrun fglsqldebug [-f logfile [-r]]
4. 畫面的第一行可以挑選LOG檔讀取產生的紀錄
5. 使用過濾器可以塞選LOG的紀錄
6. 執行分析統計以尋找耗時的 SQL 語句

如果log記錄不存在資料庫中，則會將log檔轉載入到TIPTOP的ds資料庫中，並且為每個日誌建立成一個檔案集，
預設情況下，如果資料庫內已存在LOG資料，該工具不會重新解析日誌檔案內容，
因此你也能強制重取LOG檔透過 -r 參數處理。

若 FGLSOURCEPATH 環境變數有做好定義，本工具也能檢閱程式碼!!
![檢視](https://github.com/m121752332/tool_fglsqldebug/blob/master/docs/fglsqldebug-screen-003.png)

## 請參考原廠文件

參考 [Genero BDL documentation](http://www.4js.com/download/documentation) 
更多詳細用法關於 FGLSQLDEBUG 和 FGLSOURCEPATH 環境變數介紹


## 繁體中文

已繁體中文處理，使用於TIPTOP GP 5.3除錯過

## 程式修改說明

方法一: TIPTOP中請用開發LICENSE去編譯fglsqldebug.4gl
```console
tiptop@server:~$ fglcomp fglsqldebug
```

方法二: 使用shell r.cs 指定開發目錄也能編譯 [default is (/u1/genero/fgl.dev]
```console
tiptop@server:~$ r.cs fglsqldebug
Please specify your genero development path

default is (/u1/genero/fgl.dev):
```

## 畫面修改說明

若自行編輯畫面後，可透過原廠指令編譯畫面
```console
gsform -M -i -dbname ds -keep fglsqldebug.4fd
gsform -M -i -dbname ds -keep fgltprogress.4fd
gsform -M -i -dbname ds -keep stmtstats.4fd
gsform -M -i -dbname ds -keep showtext.4fd
gsform -M -i -dbname ds -keep drvmsgs.4fd
```

參考: [gsform語法](https://4js.com/online_documentation/fjs-gst-manual-html/index.html#gst-topics/c_gst_formdesigner_designform_012.html)

## 貢獻作者

This project exists thanks to all the people who contribute. 

<a href="https://github.com/m121752332/tool_fglsqldebug/graphs/contributors"><img src="https://avatars.githubusercontent.com/u/45743812?s=400&u=3e682d4414cb5ca57079bb74219cce675e9e0639&v=4" /></a>

