# chiisen.github.io  
歡迎來到 chiisen 的免費 Jekyll GitHub Pages！  
網址： https://chiisen.github.io  

## GitHub Pages 
GitHub 提供的免費靜態網站託管服務，讓你可以輕鬆部署網站，簡直是開發者的福音！  
適合用來展示個人作品集、項目文件、開源專案文件和靜態網站。  

### GitHub Pages 的特點
1. **免費且易於使用**：直接從 GitHub 儲存庫部署，不需要額外的伺服器或設定，簡直是懶人福音！
2. **支援 Markdown & Jekyll**：用 Markdown 編寫內容，Jekyll 轉換成靜態網站，讓你寫得開心，看得舒心。
3. **自訂網域**：可以使用 GitHub 提供的 yourusername.github.io，或者綁定自己的自訂網域，讓你的網站更有個性。
4. **自動部署**：更新儲存庫的特定分支（如 main 或 gh-pages）時，GitHub Pages 會自動重新部署網站，讓你省心省力。

### 如何使用 GitHub Pages
1. **透過儲存庫建立 GitHub Pages**
    1. 創建一個新的 GitHub 儲存庫（或使用現有的）。
    2. 上傳靜態網站的 HTML、CSS 和 JavaScript 文件。
    3. 進入 Repository Settings → Pages。
    4. 在 `Build and deployment` 部分：
        * 選擇 Branch（例如 main 或 gh-pages）。
        * 點擊 Save，GitHub 會自動部署網站。
    5. 幾分鐘後，你可以透過 `https://yourusername.github.io/repository-name` 存取網站。
2. **透過 Jekyll 生成 GitHub Pages**
    如果希望使用 Jekyll（靜態網站生成器），可以：
    1. 在專案根目錄建立 `_config.yml` 來設定 Jekyll。
    2. 使用 Markdown（.md）撰寫內容，Jekyll 會轉換成 HTML。
    3. 依照前述步驟啟用 GitHub Pages。
3. **使用 GitHub Pages 作為個人或組織網站**
    如果希望 GitHub Pages 託管個人網站：
    1. 建立一個名為 `yourusername.github.io` 的儲存庫。
    2. 上傳你的網站文件。
    3. 啟用 GitHub Pages，然後訪問 `https://yourusername.github.io/`。

### GitHub Pages 適用於哪些情境？
* 個人作品集或部落格
* 專案文件（如 API 文檔）
* 開源專案展示頁
* 小型靜態網站或 Demo 頁面

如果你想建立動態網站（如帶有後端的應用程式），GitHub Pages 可能不適合，因為它僅支援靜態文件。這時候，你可以考慮使用 Netlify 或 Vercel 等平台。

## Jekyll
Jekyll 是一個靜態網站生成器（Static Site Generator, SSG），用 Ruby 語言編寫，主要用於建立部落格、個人網站和文件網站。它能將 Markdown、Liquid（模板語言）、HTML 和 CSS 組合，生成靜態網頁，然後部署到任何提供靜態網頁託管的服務，例如 GitHub Pages。

### Jekyll 的特點
1. **靜態網站生成**：Jekyll 會將你的 Markdown 檔案和 HTML 模板轉換為純 HTML 網頁，無需後端伺服器或資料庫。
2. **與 GitHub Pages 無縫整合**：可以直接將 Jekyll 網站部署到 GitHub Pages，免費託管。
3. **支援 Markdown**：適合撰寫技術部落格、文件網站等，內容撰寫簡單。
4. **Liquid 模板語言**：提供變數、條件判斷、迴圈等功能，讓內容更靈活。
5. **插件與擴展**：可以透過 Ruby Gems 安裝外掛，擴展 Jekyll 的功能，如 RSS、標籤系統、搜尋功能等。

### Jekyll 的基本運作方式
1. **撰寫內容**：
    * 使用 Markdown 撰寫文章（放在 _posts/ 資料夾）。
    * 設定網站的 `_config.yml` 來管理全站設定。
    * 建立 `layouts/` 和 `includes/` 來定義 HTML 結構。
2. **執行 Jekyll**：
    * 在專案目錄執行 `jekyll serve`（本地預覽）。
    * Jekyll 會將內容轉換成靜態 HTML，並放在 `_site/` 資料夾。
3. **部署網站**：
    * 可直接推送到 GitHub Pages，或上傳至其他靜態網站託管服務。

### Jekyll 的適用場景
* 個人部落格（如技術部落格、日記等）。
* 文件網站（如 API 文件、教學指南）。
* 企業或個人簡介網站。
* 作品展示網站（Portfolio）。

如果你想建立一個輕量級、易於維護的網站，而不想使用像 WordPress 這樣的動態 CMS，Jekyll 是一個很好的選擇！ 🚀

## Windows 安裝 Ruby
Jekyll 是基於 Ruby 的，所以首先需要安裝 Ruby
```shell
winget install -e --id RubyInstallerTeam.Ruby.3.1
```
PS.目前是用下載方式安裝 Ruby 3.4

### 安裝 Jekyll
```shell
gem install jekyll bundler
```
報錯
```shell
MSYS2 could not be found. Please run 'ridk install'
or download and install MSYS2 manually from https://msys2.github.io/
```
使用 winget 安裝 MSYS2
```shell
winget install MSYS2.MSYS2
```
報錯
```shell
gem install jekyll bundler
Temporarily enhancing PATH for MSYS/MINGW...
Building native extensions. This could take a while...
ERROR:  Error installing jekyll:
        ERROR: Failed to build gem native extension.

    current directory: C:/Ruby31-x64/lib/ruby/gems/3.1.0/gems/http_parser.rb-0.8.0/ext/ruby_http_parser
C:/Ruby31-x64/bin/ruby.exe -I C:/Ruby31-x64/lib/ruby/3.1.0 -r ./siteconf20250219-48388-1mi9ak.rb extconf.rb
creating Makefile
```
你在 Windows 上安裝 Jekyll 時遇到了 `http_parser.rb` 的原生擴展編譯錯誤，這通常與 Ruby 版本或缺少開發工具有關。以下是解決方法：
1. 安裝必要的依賴  
請確保你的系統安裝了 MSYS2 和相關的開發工具：

    * 執行以下命令安裝 Ruby DevKit
        ```shell
        ridk install
        ```
        選擇 1、2、3 全部安裝。  

    *  更新 Bundler 和 Gems
        ```shell
        gem update --system
        gem install bundler
        ```

### 檢查 Jekyll 版本確認安裝成功
```shell
jekyll -v
```

### 創建新 Jekyll 站點
```shell
jekyll new my-website
cd my-website
bundle exec jekyll serve
```
這會在本地伺服器（通常是 http://localhost:4000）啟動您的 Jekyll 網站。

## Jekyll 的目錄結構
.  
├── `README.md` // 說明文件  
├── `_config.yml` // ！主配置文件，Jekyll的配置依據  
├── `index.md` // ！博客索引文件，首頁  
├── `about.md` // ！網站說明頁  
├── `404.html` // ！網站404頁面  
├── `Gemfile` // bundle配置文件  
├── `Gemfile.lock` // bundle配置文件  
├── `_posts` // ！博客文章文件夾，放置創作的文章  
└──--------- 2019-06-29-welcome-to-jekyll.markdown // 最開始的一篇文章  

## Jekyll 的發佈
```shell
bundle install

jekyll clean
jekyll build
jekyll serve
```
可能需要 bundle install

###### tags: `hackmd`
