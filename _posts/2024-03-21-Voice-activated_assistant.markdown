---
layout: post
title:  "✅ 試做一個【語音助理】：結合 .NET 10 與 Whisper 的智慧互動體驗"
title_image: /image/github.io/Voice-activated_assistant.gif
excerpt: 結合 .NET 10 與 OpenAI Whisper 模型，打造高效能、零磁碟佔用且具備 AI 對話能力的個人化語音助理。支援繁體中文微調模型與自定義關鍵字回應。
date:   2024-03-21 00:00:00 +0800
categories: jekyll update
---

## ✅ 試做一個【語音助理】 (Voice-activated Assistant)
![Voice-activated_assistant](/image/github.io/Voice-activated_assistant.gif)

### 引言：讓電腦「聽懂」且「回應」您的每一句話

隨著語音辨識技術的成熟，打造一個專屬的語音助理已不再是難事。**Voice-activated Assistant** 是一個基於 .NET 10 開發的開源專案，利用 OpenAI 的 Whisper 模型實現精準的語音轉文字（STT），並結合 TTS 技術提供即時的語音回覆。

本專案的核心目標在於「極致的互動感」與「系統資源的高效利用」。透過多項底層優化，這款助理能像影子一樣常駐在您的電腦背景，隨時待命。

--------------------------------------------------------------------------------

### 🌟 核心優化：追求流暢與靈敏的互動

為了提供如同真人般的對話體驗，我們在程式架構上進行了多項深度優化：

1.  **💾 完全記憶體運作 (Zero-Disk Usage)**：
    *   移除傳統的 .wav 檔案寫入流程，音訊數據直接在記憶體中處理。
    *   轉錄完成後自動釋放，不僅保護隱私，更消除了硬碟 I/O 帶來的延遲。

2.  **🎤 進階語音偵測 (Adaptive VAD)**：
    *   **動態底噪追蹤**：自動學習環境噪音，不論在安靜或吵雜環境皆能保持最佳靈敏度。
    *   **Pre-roll Buffer (600ms)**：循環緩衝最近 600ms 的音訊，確保捕捉到開頭的第一個單詞。

3.  **⚡ 非同步流水線 (Producer-Consumer Pattern)**：
    *   實作「一邊轉譯上一句話、一邊錄製下一句話」的完全非阻塞體驗，適合高頻率的連續對話。

4.  **🧠 幻覺抑制與精準度**：
    *   鎖定 Temperature 為 0.0，強制模型僅輸出高信心度的字詞，大幅降低無中生有的幻覺文字。

--------------------------------------------------------------------------------

### 🎮 功能亮點

*   **多模型支援**：內建 OpenAI 官方模型（Tiny 到 Medium），並支援專為台灣使用者優化的 **繁體中文微調版本 (Tiny-zh-TW)**。
*   **關鍵字互動 (keyword_responses.json)**：您可以自定義回應清單，當辨識到特定關鍵字時，助理會自動進行語音回覆。
*   **靜音自動斷句**：感應到 1.5 秒的靜音後自動觸發轉譯，無需手動按鍵。
*   **背景長駐優化**：智慧調度處理序優先權（BelowNormal），確保在掛載時不干擾遊戲或辦公軟體的執行。

--------------------------------------------------------------------------------

### 🛠️ 技術棧

*   **開發環境**：.NET 10 SDK
*   **核心引擎**：OpenAI Whisper (via Whisper.net)
*   **音訊處理**：CSCore / Memory Stream
*   **語言支援**：C# / 繁體中文

--------------------------------------------------------------------------------

### 🚀 快速啟動

只需幾個簡單步驟即可在本地運行：

1.  確認安裝 **.NET 10 SDK**。
2.  複製專案並執行：
    ```powershell
    cd Voice-activated_assistant
    dotnet run
    ```
3.  選擇模型（推薦選項 2 為繁體中文優化版）。

--------------------------------------------------------------------------------

### 結語：AI 助理的無限可能

Voice-activated Assistant 不僅是一個工具，更是一個展示 .NET 強大效能與結合 AI 模型的實踐。無論是作為智慧家居的控制核心，還是日常工作中的語音助手，它都展示了「低成本、高效率」的 AI 落地可能性。

歡迎造訪 [chiisen/Voice-activated_assistant](https://github.com/chiisen/Voice-activated_assistant) 探索更多細節！🚀✨

---

<!-- Badges -->
![.NET 10](https://img.shields.io/badge/.NET-10-512BD4?style=for-the-badge&logo=dotnet&logoColor=white)
![C#](https://img.shields.io/badge/C%23-A8B9CC?style=for-the-badge&logo=csharp&logoColor=white)
![Whisper](https://img.shields.io/badge/AI-Whisper-000000?style=for-the-badge&logo=openai&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-chiisen%2FVoice--activated__assistant-%23181717?style=for-the-badge&logo=github&logoColor=white)

---
