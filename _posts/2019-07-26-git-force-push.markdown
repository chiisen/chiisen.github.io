---
layout: post
title:  "Azure DevPos Git 的 ForcePush 產生錯誤訊息 TF401027: You need the Git 'ForcePush' permission to perform this action. 的解決方法"
date:   2019-07-26 12:08:00 +0800
categories: jekyll update
---

最近在刪除 Git 上的敏感資料  
使用到 Git 的 ForcePush 產生錯誤訊息

git push origin HEAD:master --force

![Alt text](/image/github.io/ForcePush02.png)

```
 ! [remote rejected] HEAD -> master (TF401027: You need the Git 'ForcePush' permission to perform this action. Details: identity 'Windows Live ID\user@mail.com', scope 'branch'.)
error: failed to push some refs to 'https://xxxx@dev.azure.com/xxxx/xxxx/_git/project.xxxx'

```  

看起來應該是權限不足  
上去 Azure DevPos 找了一下設定  

![Alt text](/image/github.io/ForcePush00.png)

點選 Manage repositories  

![Alt text](/image/github.io/ForcePush01.png)

Force push (rewrite history, delete branches and tags) 設定為 Allow  

PS.群組我選 Project Collection Administrators 視需求每人選的有所不同  
