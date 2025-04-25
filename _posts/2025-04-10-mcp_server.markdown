---
layout: post
title:  "🔗 自己為 Claude 寫本地端 MCP Server (JavaScript版)"
title_image: /image/github.io/Claude_MCP.gif
excerpt: MCP Server 就像「AI 的 USB 插槽」，讓 AI 能安全地連接外部資料或工具。
舉例：AI 想查電腦檔案或查詢股票價格，MCP Server 就負責幫 AI 取得這些資料或執行操作。
date:   2025-04-10 00:00:00 +0800
categories: jekyll update
---

## 自己為 Claude 寫本地端 MCP Server (JavaScript版)
MCP Server 就像「AI 的 USB 插槽」，讓 AI 能安全地連接外部資料或工具。
舉例：AI 想查電腦檔案或查詢股票價格，MCP Server 就負責幫 AI 取得這些資料或執行操作。

### AI 有了 MCP（模型上下文協定）後，將產生以下重大影響：

- AI 不再只是「建議者」，而能主動執行任務。例如，AI 不僅能告訴你怎麼查資料，還能直接幫你查詢資料庫、整理報表、發送郵件，甚至控制智慧家電  
- AI 可即時存取外部資料與工具，突破只能依賴訓練知識的限制，能根據最新數據做出回應，如即時天氣、最新財經資訊等  
- AI 回答更精確，能減少「幻覺」問題，因為可直接查證外部資料來源  
- 開發者只需一次整合 MCP，AI 就能連接多種工具和資料，開發效率大幅提升  
- 用戶資料安全性提升，因為存取權限可細緻控管，且多數操作在本地端執行  
總結：MCP 讓 AI 從只能「說」進化到能「做」，大幅擴展應用範圍與價值，推動 AI 進入真正的智能代理（AI Agent）時代  

### Weather MCP Server
這是用來給 Claude 查詢指定地區的天氣資訊  
[🔗 我的 Github 範例專案: 【ClaudeLocalMCP.js】](https://github.com/chiisen/ClaudeLocalMCP.js)

---