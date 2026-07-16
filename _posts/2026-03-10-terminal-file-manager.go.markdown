---
layout: post
title:  "✅ 試做一個【終端機檔案管理器】：Go 語言實現的高效與直覺 (gofm)"
title_image: /image/github.io/Terminal_File_Manager.png
excerpt: 基於 Go 語言與 Bubble Tea 框架打造的終端機檔案管理器 gofm。具備極速導航、Fuzzy 搜尋、Git 整合與檔案預覽功能，讓終端機操作比 GUI 更快、比 ls 更直覺。
date:   2026-03-10 00:00:00 +0800
categories: jekyll update
---

## ✅ 試做一個【終端機檔案管理器】 (Terminal File Manager)
![Terminal-file-manager-go](/image/github.io/Terminal_File_Manager.gif)

### 引言：在終端機中享受「指尖起舞」的檔案導航

對於開發者而言，頻繁地在終端機 (Terminal) 中切換目錄、檢查檔案是家常便飯。然而，傳統的 `ls` 與 `cd` 指令在面對大型目錄或複雜操作時，往往顯得不夠直覺且效率低下。**gofm** (Terminal File Manager) 正是為了打破這一限制而生，它旨在提供一個比 GUI 檔案總管更快、比傳統命令列更直覺的互動環境。

本專案利用 Go 語言的高效併發能力與 [Bubble Tea](https://github.com/charmbracelet/bubbletea) 框架，打造出一個兼顧美學與實用性的終端機介面，即使面對超過 10,000 個檔案的大型目錄，也能保持絲滑順暢的導航體驗。

--------------------------------------------------------------------------------

### 🌟 核心特性：極速、輕量、擴展性

gofm 不僅僅是一個簡單的列表選單，它在底層設計上融入了多項提升生產力的核心功能：

1.  **🚀 極速導航與 Lazy Load**：
    *   採用非同步載入機制，目錄內容與檔案詳細資訊（如大小、權限）獨立載入。即使在處理極大目錄時，介面依然能瞬間反應。

2.  **📂 直覺的檔案操作全家桶**：
    *   完整的檔案生命週期管理：複製 (y)、貼上 (p)、刪除 (d)、重新命名 (r) 與新增檔案/目錄 (a/A)，讓操作流暢無比。

3.  **🔍 全方位 Fuzzy 搜尋**：
    *   只需按下 `/` 即可進入全文檢索模式，根據關鍵字即時篩選檔案，精確定位。

4.  **📦 Git 深度整合**：
    *   自動偵測 Git 倉庫狀態，直接在檔案列表顯示變更標記 (M: Modified, A: Added, D: Deleted)，讓開發進度一目了然。

5.  **🌐 遠端存取支援 (SSH/SFTP)**：
    *   內建 SSH/SFTP 支援，讓您像操作本地檔案一樣輕鬆管理遠端伺服器上的資源。

--------------------------------------------------------------------------------

### 🎮 功能亮點

*   **即時預覽面板**：
    *   **文字檔案**：直接查看程式碼與純文字內容。
    *   **圖片資訊**：支援解析多種格式 (PNG, JPEG, GIF, BMP, WebP, ICO) 的元數據。
    *   **二進制檔案**：自動偵測並標示二進制資訊，避免誤開造成的意外。
*   **智慧排序機制**：支援檔名、大小、類型與修改時間的循環切換。
*   **外掛系統**：支援透過 `~/.config/gofm/plugins` 擴充功能，打造專屬您的檔案管家。
*   **健全的錯誤處理**：針對 Permission denied 提供提示，並在檔案變動後自動刷新列表。

--------------------------------------------------------------------------------

### 🛠️ 技術棧

*   **核心語言**：Go (Golang)
*   **TUI 框架**：[Bubble Tea](https://github.com/charmbracelet/bubbletea) (Model-Update-View 模式)
*   **樣式引擎**：[Lip Gloss](https://github.com/charmbracelet/lipgloss) (靈活的 UI 佈局)
*   **遠端協定**：SSH/SFTP (golang.org/x/crypto/ssh, github.com/pkg/sftp)
*   **併發處理**：Goroutines + Channels (非同步檔案讀取與預覽)

--------------------------------------------------------------------------------

### 🚀 快速啟動

只需幾個簡單步驟即可在您的本地端運行：

1.  **Clone 專案並編譯**：
    ```bash
    git clone https://github.com/chiisen/terminal-file-manager.go
    cd terminal-file-manager.go
    go build -o gofm ./cmd/gofm
    ```
2.  **執行 gofm**：
    ```bash
    # 在目前目錄開啟
    ./gofm
    # 指定特定目錄開啟
    ./gofm /path/to/your/folder
    ```
3.  **快捷鍵指引**：
    *   `↑ / ↓`：移動游標
    *   `Enter / l`：進入目錄或開啟檔案
    *   `h`：回上一層目錄
    *   `s / S`：切換排序方式

--------------------------------------------------------------------------------

### 結語：為開發者而生的終端機利器

gofm 的開發初衷是將圖形化管理器的便利性帶入終端機。透過 Go 語言的強大效能，我們得以在傳統的文字介面中實現複雜的非同步行為與華麗的 UI。無論您是追求極速的命令行達人，還是尋找更直覺導航工具的開發者，gofm 都將是您工具箱中不可或缺的一員。

歡迎造訪 [chiisen/terminal-file-manager.go](https://github.com/chiisen/terminal-file-manager.go) 下載、點亮 ⭐ 並參與專案開發！🚀✨

---

<!-- Badges -->
![Go](https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white)
![Bubble Tea](https://img.shields.io/badge/TUI-Bubble%20Tea-EE4D2D?style=for-the-badge&logo=github&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-chiisen%2Fterminal--file--manager.go-%23181717?style=for-the-badge&logo=github&logoColor=white)

---
