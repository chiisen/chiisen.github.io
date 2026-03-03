---
layout: post
title:  "🤖 MiniBot.go：極致輕量的 Go 語言 AI Agent 助理"
excerpt: 使用 Go 語言打造的 15MB 單一執行檔，具備沙箱工具呼叫、Telegram 整合與網頁搜尋能力的極簡 AI Agent。
date:   2026-02-22 00:00:00 +0800
categories: jekyll update
---

## 🤖 MiniBot.go：極致輕量的 Go 語言 AI Agent 助理

### 引言：追求極致效能與零依賴的 AI 實作

繼 Python 版的 mini_bot 之後，為了追求更快的啟動速度、更低的資源佔用以及更簡單的部署流程，**MiniBot.go** 應運而生。這是一個從零開始，使用 Go 語言撰寫的「最小可執行（MVP）」AI Agent 專案。

不同於 Python 版本需要處理複雜的環境依賴，MiniBot.go 編譯後僅需一個不到 15MB 的執行檔，即可在沒有安裝任何 Runtime 的環境下運行，並保持極低的記憶體消耗（RAM < 10MB）。

--------------------------------------------------------------------------------

### 🌟 核心特色：輕量但不失強大

MiniBot.go 在保持小巧的同時，整合了多項進階功能：

1.  **🐹 純 Go 實作**：除了標準函式庫外，零第三方肥大框架依賴，確保穩定與安全。
2.  **🔐 安全沙箱工具 (Sandbox)**：內建沙箱機制，允許 AI 安全地執行讀寫檔案、瀏覽目錄及終端機指令。
3.  **🔍 內建網頁搜尋**：透過 DuckDuckGo API，讓 Agent 具備即時上網找資料的能力，無需額外的 API Key。
4.  **🤝 標準化介面 (OAI Compatible)**：支援 OpenAI、DeepSeek、MiniMax、Groq 與本地的 Ollama 等多種 Provider。
5.  **📲 Telegram 深度整合**：內建 Long Polling 接收器與白名單過濾機制，讓手機也能成為控制中心。
6.  **📦 跨平台部署**：支援 Windows/Linux/macOS 交叉編譯，並提供極小型 Alpine Docker 映像檔。

--------------------------------------------------------------------------------

### 🎮 多元的使用模式

為了適應不同場景，MiniBot.go 設計了三種靈活的運行模式：

*   **🎯 模式一：單次指令 (Single Shot)**
    快速執行單一任務並返回結果，適合與其他腳本串接。
    `./app agent -m "目前的系統負載如何？"`

*   **💬 模式二：互動對話 (Interactive Mode)**
    啟動本地對話迴圈，適合複雜任務的協作與即時工具呼叫（如：請幫我分析這個專案結構）。

*   **🌐 模式三：網關伺服器 (Gateway Mode)**
    啟動常駐程式並掛載 Telegram 服務，讓您可以遠端與自己的 AI Agent 互動。

--------------------------------------------------------------------------------

### 🛠️ 快速開始：編譯即運行

Go 語言的優勢在於其極簡的建置流程：

1.  **編譯專案**：使用 `go build -o app` 即可產生跨平台執行檔。
2.  **初始化環境**：執行 `./app onboard` 自動掃描並導引關鍵設定。
3.  **設定設定檔**：在 `config.json` 中填入你的 API Key 即可啟動。

--------------------------------------------------------------------------------

### 結語：為技術玩家打造的 AI 指揮中心

MiniBot.go 代表了對「工具」本質的追求：快速、可靠、且不浪費資源。對於希望在本地端部署個人 AI 助手，或是需要在資源受限環境（如樹莓派、NAS）執行 Agent 的開發者來說，這是一個絕佳的起點。

現在就前往 [chiisen/mini_bot.go](https://github.com/chiisen/mini_bot.go) 探索更多可能吧！

---

<!-- Badges -->
![Go](https://img.shields.io/badge/Go-1.22%2B-00ADD8?style=for-the-badge&logo=go&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-Supports-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-chiisen%2Fmini__bot.go-%23181717?style=for-the-badge&logo=github&logoColor=white)

---
