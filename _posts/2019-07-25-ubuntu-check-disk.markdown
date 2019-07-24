---
layout: post
title:  "在 Ubuntu 用 Shell Script 監測硬碟使用量並在容量過低時利用 team 通訊軟體通知"
date:   2019-07-25 0:01:00 +0800
categories: jekyll update
---

前陣子 EC2 掛了一台  
查了一下資料  
發現有蠻方便的監控方式，來源網址：[Shell Script 監測硬碟使用量](https://www.opencli.com/linux/shell-script-check-harddisk-usage)  

```bash
#!/bin/bash
 
echo "== Ubuntu == run check-disk =="
team_url=【你 team 的 url】
alert=50
 
df -H | grep -vE '^Filesystem|tmpfs' | awk '{ print $5 " " $6 }' | while read output;
do
        usepercent=$(echo $output | awk '{ print $1}' | cut -d'%' -f1  )
        partition=$(echo $output | awk '{ print $2 }' )
        if [ $usepercent -ge $alert ]; then
   if [ $partition = '/' ]; then
    curl -H "Content-Type: application/json" -d "{\"text\":\"$(date) $(hostname) Disk Space Alert= $partition($usepercent%) \"}" $team_url
    break
   fi
        fi
done
echo "== Ubuntu == stop check-disk =="
```

如果沒安裝 curl 請安裝（Shell Script 需要 curl 才能跟 team 溝通）  
參考網址：[How to add connectors in Microsoft Teams](https://docs.microsoft.com/zh-tw/microsoftteams/platform/concepts/connectors/connectors-using)  
安裝方法如下：  
 
```bash
sudo apt-get update
sudo apt install curl
```

記得找一下 team 頻道的 Webhook url 取代上面的【你 team 的 url】  
參考網址：[Microsoft Teams 使用Webhook傳訊息到Teams頻道](https://dotblogs.com.tw/lapland/2017/04/13/145208)  
方法如下：  

![Alt text](/image/github.io/team00.png)

點擊「連接器」  

![Alt text](/image/github.io/team01.png)

點擊「已設定」與「管理」（如果沒安裝「傳入 Webhook」請安裝）  

![Alt text](/image/github.io/team02.png)

按下「複製」鈕就能取得網址  

如果想每天定時監控與通知  
可以利用 crontab 定時通知  
記得給 check-disk.sh 管理權限(有權限 ls 看到會是綠色的)  

```bash
chmod +x check-disk.sh
```
每天半夜 12 點定時通知  
```bash
0 0 * * * /home/ubuntu/check-disk.sh >> ~/disk.log
```

每小時定時通知  
```bash
0 * * * * /home/ubuntu/check-disk.sh >> ~/disk.log
```
這邊建議設定一下時區  
```bash
sudo timedatectl set-timezone "Asia/Taipei"
```
crontab 設定的啟動時間才會準確  

現在可以另用 crontab -e 新增排程了  

排程設定好了  
記得執行  
```bash
sudo service cron restart
```
重置一下 crontab  