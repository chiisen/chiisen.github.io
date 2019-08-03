---
layout: post
title:  "Windows 10 下 安裝 RabbitMQ"
date:   2019-08-2 13:21:00 +0800
categories: jekyll update
---

由於 RabbitMQ 是由 Erlang 開發的

安裝 Erlang
https://www.erlang.org/
點選Download Erlang/OTP下載按鈕

安裝 RabbitMQ
https://www.RabbitMQ.com

安裝 RabbitMQ 後會有一個捷徑 RabbitMQ Command Prompt (sbin dir)
執行捷徑 RabbitMQ Command Prompt (sbin dir)
會出現 CMD 命令列

![Alt text](/image/github.io/RabbitMQ02.png)

輸入指令啟用外掛（有網頁介面）：
RabbitMQ-plugins.bat enable RabbitMQ_management
輸入指令重啟伺服器：
net stop RabbitMQ ＆＆ net start RabbitMQ

停止服務，必須手動關閉！
輸入指令關閉伺服器：
RabbitMQ-server stop

不關閉下次還會開啟 RabbitMQ

測試一下是否安裝成功
瀏覽 http://localhost:15672/#/
或
http://「你的 VM 的 IP」:15672/#/

![Alt text](/image/github.io/RabbitMQ00.PNG)

預設賬號：guest      
預設密碼：guest

PS.為了安全性的問題，可以在 admin 新增 user 並刪除 guest 帳號，之後登入就用新帳號登入  

預設 Web 的 Port 是 15672
預設 MQ 的 Port 是 5672
不要搞混了

![Alt text](/image/github.io/RabbitMQ01.PNG)

常用指令：  
RabbitMQ-plugins enable RabbitMQ_management 開啟外掛  
RabbitMQ-service remove 移除服務  
RabbitMQ-service install 安裝服務  
RabbitMQ-service start 或者 net start RabbitMQ 啟動服務  
RabbitMQ-service stop 或者 net stop RabbitMQ 停止服務  
RabbitMQctl status 檢視服務狀態  
RabbitMQ-server restart 重啟服務  

特別提一下在 Windows 10 下安裝 RabbitMQ ，如果使用者名稱是中文的，則會出現啟動失敗的情況。
網路上有教學，需要可以去查一下（我沒測試過，所以這邊不說明）。
