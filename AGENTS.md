# AGENTS.md — 給 AI Agent 的協作指南

> 本文件說明如何在 `chiisen.github.io`（Jekyll + GitHub Pages 部落格）新增一篇文章。
> 如果你是 AI agent，請依照本指南操作；若發現內容與實際專案狀態不符，請以 `_posts/` 內最新文章與 `git log` 為準。

---

## 1. 專案基本資訊

| 項目 | 內容 |
| --- | --- |
| 框架 | Jekyll（靜態網站產生器） |
| 主題 | minima（含自訂的 `_layouts/`） |
| 部署 | GitHub Pages（push 後自動部署） |
| 設定檔 | `_config.yml` |
| 時區 | `Asia/Taipei`（`+0800`） |
| 主要分支 | `main` |

文章目錄結構（與本指南相關的部分）：

```text
.
├── _config.yml          # Jekyll 設定
├── _layouts/            # 版面樣板（含自訂的 post.html）
├── _posts/              # ⭐ 所有部落格文章放這裡
│   └── YYYY-MM-DD-title.markdown
└── image/
    └── github.io/       # ⭐ 文章圖片放這裡（title_image 與內文插圖）
```

---

## 2. 新增一篇文章的標準流程

### 步驟 1：決定檔名

檔名遵守 Jekyll 規範：**`YYYY-MM-DD-slug.markdown`**

- **日期前綴**：`YYYY-MM-DD-`（月份與日期個位數不補 0 也行，例如 `2024-09-1-`，但建議補 0 保持一致）。
- **slug 部分**：實際專案用法很自由，底下幾種都看過：
  - kebab-case：`2026-04-15-my-new-post`
  - 底線：`2026-04-15-mcp_server_ts`（多語言 / 多框架時用）
  - PascalCase：`2026-04-15-NanoBananaPro`（套件 / 品牌名）
  - 內含副檔名：`2026-04-15-terminal-file-manager.go`
- **不要**用：中文、空格。
- 不確定時，看一下 `_posts/` 裡現有檔案最接近的命名風格來跟。
- 範例：

  ```text
  _posts/2026-04-15-my-new-post.markdown
  _posts/2026-04-15-react-tutorial.markdown
  _posts/2026-04-15-NanoBananaPro.markdown
  ```

### 步驟 2：寫入 Front Matter（YAML）

每篇文章**開頭必須**有以下 YAML front matter（`---` 包夾）：

```yaml
---
layout: post
title:  "📝 你的文章標題（可以含 emoji）"
title_image: /image/github.io/your-cover.png   # 選填：給首頁列表顯示用
excerpt: 一句話摘要，會顯示在首頁與 SEO 中。
date:   2026-04-15 00:00:00 +0800              # ⚠️ 要與檔名日期一致
categories: jekyll update                       # ⚠️ 維持原樣
---
```

欄位說明：

- `layout: post`：使用 `_layouts/post.html`。
- `title`：會被 escape 後作為頁面 H1。建議保持「emoji + 簡短標題」。
- `title_image`：**選填**。若提供，會在首頁文章列表中顯示縮圖。路徑相對於網站根目錄。
- `excerpt`：必填，1 句話總結。
- `date`：時區固定 `+0800`，日期必須與檔名一致。
- `categories`：保持 `jekyll update`（這是 minima 主題預設值，**不要亂改**，否則首頁分類會跑掉）。

### 步驟 3：撰寫內文（Markdown）

Front matter 之後直接接 Markdown 內文。可使用：

- 標準 Markdown：`## 標題`、`**粗體**`、`[連結](url)`。
- 程式碼區塊：```` ```語言 ````。
- 內文圖片：`![alt 文字](/image/github.io/your-image.png)`。
- YouTube 內嵌：

  ```html
  <iframe width="560" height="315" src="https://www.youtube.com/embed/XXXX"
          frameborder="0" allowfullscreen></iframe>
  ```

### 步驟 4：放置圖片（如有）

圖片統一放到 `image/github.io/`：

```text
image/github.io/your-cover.png
image/github.io/your-demo.gif
```

引用時路徑固定為 `/image/github.io/...`。

> 不用本地預覽 — push 後 GitHub Pages 會自動 build & deploy，只要格式正確就會正常顯示。

---

## 3. 完整範本

把以下內容存成 `_posts/YYYY-MM-DD-my-topic.markdown`（記得改日期與標題）：

```markdown
---
layout: post
title:  "🚀 我的新文章標題"
title_image: /image/github.io/my-topic.png
excerpt: 用一句話說明這篇文章在講什麼、為什麼值得讀。
date:   2026-04-15 00:00:00 +0800
categories: jekyll update
---

## 引言

一句話點出讀者會得到什麼。

## 重點 1

內文...

## 重點 2

內文...

![示意圖](/image/github.io/my-topic.png)

## 結語

一句話總結。
```

---

## 4. Commit 訊息規範

從 `git log` 觀察到常見的 Conventional Commits 寫法：

| 類型 | 範例 |
| --- | --- |
| 新增文章（中英混用） | `feat: add blog post about terminal file managers` |
| 加上範圍 | `feat(blog): add new blog post about <topic>` |
| 文章 + 圖片 | `✨ feat: 新增 <標題> 文章及相關圖片` |
| 純中文 | `📝 docs: 新增一篇關於 <topic> 的部落格文章` |

**推薦寫法**（與現有 commit 風格一致）：

```text
feat: add blog post about <簡短主題>
✨ feat: 新增 <標題> 文章及相關圖片，<一句話說明>
```

emoji 不是必要的，但作者偏好 `✨`、`📝`、`feat` 等前綴。

---

## 5. 檢查清單（送出前自我驗證）

送出 commit 之前，請逐項確認：

- [ ] 檔名是 `YYYY-MM-DD-xxx.markdown` 格式，且放在 `_posts/`
- [ ] Front matter 完整：`layout: post`、`title`、`excerpt`、`date`（含 `+0800`）、`categories: jekyll update`
- [ ] `date` 與檔名的日期一致
- [ ] 若有 `title_image`，圖片實際存在於 `image/github.io/`
- [ ] 內文所有圖片路徑都是 `/image/github.io/...`
- [ ] 沒有修改 `_config.yml`、`_layouts/`、`Gemfile`（除非被明確要求）
- [ ] Commit 訊息符合 Conventional Commits（`feat:` / `feat(blog):` …）

---

## 6. 常見錯誤

| 錯誤 | 修正 |
| --- | --- |
| 檔名用中文或空白 | 改用英文 / `-` / `_` |
| 忘了 `+0800` 時區 | 統一加 `+0800` |
| `categories` 亂填 | 保持 `jekyll update` |
| 圖片放到 `_posts/` | 圖片統一放 `image/github.io/` |
| `date` 與檔名日期不一致 | 兩邊改成同一個日期 |

---

## 7. 參考來源（如何自行驗證本指南是否過時）

如果未來不確定，請用以下指令自行驗證：

```shell
# 看最近新增文章的 commit 風格
git log --oneline -- _posts | head -20

# 看某篇文章的完整 front matter 怎麼寫
head -15 _posts/<最新文章檔名>

# 看圖片放在哪裡
ls image/github.io/

# 看是否有特殊 layout 被使用
ls _layouts/
```

本指南的內容來自實際讀取 `README.md`、`_config.yml`、`_layouts/post.html`、`_posts/` 內多篇文章，以及 `git log` 觀察到的 commit 模式而來；若專案結構改變，請同步更新本檔。
