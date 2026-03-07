---
layout: post
title:  "✅ 試做一個【語音助理】：結合 Python 與 Qwen3 的智慧互動體驗"
title_image: /image/github.io/voice-activated-assistant-py.png
excerpt: 結合 Python、Qwen3-ASR 與 Qwen3-TTS 技術，打造高效能、隱私優先且具備 AI 對話能力的個人化語音助理。實現流暢的語音指令識別與自動化回應。
date:   2026-03-06 00:00:00 +0800
categories: jekyll update
---

## ✅ 試做一個【語音助理】 (Voice-Activated Assistant)
![Voice-activated_assistant_py](/image/github.io/voice-activated-assistant-py.png)

### 引言：讓電腦「聽懂」且「回應」您的每一句話

隨著語音辨識與合成技術的成熟，打造一個專屬的語音助理已不再是難事。**Voice-Activated Assistant** 是一個基於 Python 開發的開源專案，利用 Qwen3-ASR 模型實現精準的語音轉文字（STT），並結合 Qwen3-TTS 技術提供即時的語音回覆。

本專案的核心目標在於「極致的互動感」與「隱私優先」。語音轉文字 (ASR) 結果僅暫存於記憶體，程式結束後自動釋放，不留任何磁碟紀錄，確保您的資料安全。

--------------------------------------------------------------------------------

### 🌟 核心特性：追求流暢與純淨的互動

為了提供如同真人般的對話體驗，我們在程式架構上進行了多項深度優化：

1.  **🚀 極速本地推論**：
    *   使用 Qwen3-ASR 與 Qwen3-TTS，支援串流輸出，具備極低首包延遲。

2.  **🗣️ 純淨自然發音**：
    *   內建 OpenCC 簡繁轉換機制，避免 TTS 模型朗讀繁體中文時產生混淆，確保發音皆為標準的國語/普通話。同時排除帶有強烈方言口音的角色，保障溝通無礙。

3.  **🧠 智慧停頓偵測 (VAD)**：
    *   使用 Silero VAD，內建連續靜音判斷，精準識別一段話的結束點。

4.  **🚦 狀態機協調**：
    *   當 TTS 播放時自動暫停 ASR 監聽，完美解決「自己聽到自己講話」的自我回饋問題。

5.  **🤫 隱私與安全**：
    *   ASR 處理結果全在記憶體運作，不落定磁碟。

--------------------------------------------------------------------------------

### 🎮 功能亮點

*   **多模型支援**：支援自動下載 Qwen3-ASR 的不同參數量模型 (0.6B, 1.7B)。
*   **JSON 驅動規則 (rules.json)**：您可以透過設定檔自定義關鍵字、優先序與多樣化的回覆模式。
*   **多種語音角色**：可隨時切換男女聲或特色聲音（如 vivian, serena, ryan 等）。
*   **Mock 測試模式**：支援純文字模擬互動，無需麥克風即可快速測試對話邏輯。

--------------------------------------------------------------------------------

### 🛠️ 技術棧

*   **開發環境**：Python 3.10+
*   **核心引擎 (ASR)**：Qwen3-ASR (1.7B / 0.6B)
*   **語音合成 (TTS)**：Qwen3-TTS
*   **語音偵測 (VAD)**：Silero VAD
*   **併發處理**：Threading + Python Queue

--------------------------------------------------------------------------------

### 🚀 快速啟動

只需幾個簡單步驟即可在本地運行：

1.  確認安裝 **Python 3.10+** 及依賴（推薦使用 `uv sync`）。
2.  複製專案並執行：
    ```bash
    python src/main.py --rules config/rules.json
    ```
3.  預設會自動下載推薦模型並開始聆聽。

--------------------------------------------------------------------------------

### 結語：AI 助理的無限可能

Voice-Activated Assistant 不僅是一個工具，更是一個展示 Python 敏捷開發與整合強大開源模型的實踐。無論是作為智慧家居的控制核心，還是日常工作中的語音助手，它都展示了 AI 落地本地端並保護隱私的最佳可能性。

歡迎造訪 [chiisen/voice-activated-assistant.py](https://github.com/chiisen/voice-activated-assistant.py) 探索更多細節！🚀✨

---

<!-- Badges -->
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Qwen](https://img.shields.io/badge/AI-Qwen3-000000?style=for-the-badge&logo=openai&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-chiisen%2Fvoice--activated--assistant.py-%23181717?style=for-the-badge&logo=github&logoColor=white)

---
