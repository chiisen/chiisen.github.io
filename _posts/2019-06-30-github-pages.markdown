---
layout: post
title:  "WSL 安裝 Jekyll"
date:   2019-06-29 23:44:25 +0800
categories: jekyll update
---
**更新套件列表**   
`sudo apt-get update -y && sudo apt-get upgrade -y`  

**加入 BrightBox 的 ppa**  
`sudo apt-add-repository ppa:brightbox/ruby-ng`  
`sudo apt-get update`  

**安裝**    
`sudo apt-get install ruby2.3 ruby2.3-dev build-essential`  

**更新一下 Ruby gems**  
`sudo gem update`  

**安裝 Jekyll 和 bundler**  
`sudo gem install jekyll bundler`  

**看 Jekyll 版本**  
`jekyll -v`  

**安裝個 bundle**  
`bundle install`  

**運行 jekyll**  
`bundle exec jekyll server`  

**在網頁目錄輸入**  
`jekyll new . `
如果目錄已經有簽入 Git 可以輸入  
`jekyll new . --force`  
建立 jekyll 網頁框架  

**測試運行結果**  
`http://127.0.0.1:4000`  
這邊本人親自測試過是無法連線  
但是簽入 GitHub 用 GitHub Pages 就可以瀏覽。  
`https://chiisen.github.io/`  

