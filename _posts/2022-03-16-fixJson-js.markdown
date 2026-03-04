---
layout: post
title: "🛠️ fixJson.js：修復不正常 JSON 資料格式的利器"
excerpt: "解決 JSON 解析失敗的困擾！fixJson.js 提供強大的錯誤偵測與自動修復功能，精準定位語法錯誤，支援補齊引號、逗號及多種邊界情況，內建 TypeScript 與 CLI 支援。"
date: 2022-03-16 00:00:00 +0800
categories: jekyll update
---

## 🛠️ fixJson.js：告別手動除錯的繁瑣

### 引言：不再為 JSON 解析失敗而煩惱

當你遇到格式錯誤的 JSON 導致解析失敗時，不需要再辛苦地開啟 IDE 或其他工具進行偵錯。**fixJson.js** (`fix-json-format`) 的誕生，正是為了解決這個痛點！它不僅能自動修復各種常見的 JSON 格式錯誤，更提供了強大的偵錯提示功能，能夠在修復失敗或遇到語法錯誤時，精準指出錯誤發生的行號與位置，幫助你快速定位問題！

本專案支援多種執行環境，無論是 Node.js (CommonJS / ESM)、TypeScript 還是命令列工具 (CLI)，都能輕鬆整合進你的工作流程中。

---

### 🌟 核心功能：強大的修復與偵錯能力

- **✨ 自動修復常見錯誤**：
  - 自動修正缺少引號的 key/value。
  - 修正缺少逗號或多餘逗號的問題。
  - 修正不平衡的括號。
  - 修復空值欄位，並支援 `null`/`true`/`false` 布林值與數字欄位。
- **💡 智能偵錯提示**：修復失敗時，精準顯示錯誤發生的行號與位置，拒絕無意義的解析報錯。
- **🌐 廣泛格式支援**：支援時間格式 (ISO/一般格式)、IP 格式 (`::ffff:x.x.x.x`) 以及多行 JSON 的處理。
- **⚡ 性能優化**：透過減少重複的正則替換次數，提升大量資料修復時的執行效能。
- **🚀 多環境相容**：提供完整的 TypeScript 類型定義，支援 ESM 與 CommonJS 模組系統，並內建 CLI 工具。

---

### 📦 快速開始：安裝與使用

#### 安裝套件

使用 npm 輕鬆安裝至你的專案中：

```bash
npm install fix-json-format
```

#### 各環境使用範例

**1. CLI 命令列工具**

```bash
# 從檔案讀取
fix-json-format input.json

# 從標準輸入讀取
cat input.json | fix-json-format

# 輸出到檔案
fix-json-format input.json -o output.json

# 顯示說明
fix-json-format --help
```

**2. Node.js (ESM / TypeScript)**

```javascript
import { fix_json } from "fix-json-format";

// 回傳物件格式 (預設) - 包含錯誤資訊
const { result, error } = fix_json(str);

if (error) {
  console.error(error);
  // 輸出: JSON Syntax Error at line 1, column 10: ...
}

// 向後相容 - 直接回傳字串
const strResult = fix_json(str, { returnObject: false });
```

**3. Node.js (CommonJS)**

```javascript
const { fix_json } = require("fix-json-format");
```

---

### 🧪 測試與穩定性

專案持續維護完善的測試案例，確保自動修復邏輯的可靠性：

```bash
# 執行 Jest 單元測試
npm test

# 執行原有測試
npm run test:legacy
```

---

### 結語：提升開發效率的必備小幫手

在處理第三方 API 回傳的不標準資料，或是清理爬蟲抓取下來的殘缺 JSON 時，**fixJson.js** 能大幅減少手動介入的時間成本，讓程式碼的容錯率變得更高。

歡迎造訪 [chiisen/fixJson.js](https://github.com/chiisen/fixJson.js) 探索更多源碼細節、回報 Issue，或者給我們一顆星星 ⭐！

---

<!-- Badges -->

![NPM Version](https://img.shields.io/npm/v/fix-json-format?style=for-the-badge&logo=npm)
![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-chiisen%2FfixJson.js-%23181717?style=for-the-badge&logo=github&logoColor=white)
