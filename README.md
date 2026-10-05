# SuikContentLab

SuikContentLab 是我用來累積、整理與實驗技術內容的公開內容實驗室。

目前主要聚焦在兩件事：

1. **軟體工程內容**：保存準備發布或已發布於 LinkedIn 的技術文章、工程觀點與延伸筆記。
2. **AI Agent Harness**：整理 AI 協助內容規劃、撰寫、校對、轉換與發布流程時所使用的規則、Prompt、Workflow 與實驗紀錄。

> **LinkedIn 是主要的發布介面；SuikContentLab 是內容與方法的 Source of Truth。**

這個 Repository 不只用來備份文章，也希望讓每一份技術思考都能被搜尋、版本追蹤、重新組合，並在未來延伸成教學內容、工具、課程或其他技術服務。

## Repository 結構

```text
SuikContentLab/
├─ README.md
├─ Articles/
│  └─ README.md
└─ Agent-harness/
   └─ README.md
```

目前先維持簡單結構，等內容累積後再依實際需求拆分；不為了「看起來完整」而過早建立大量資料夾。

## Articles

`Articles/` 保存以軟體工程為主的公開內容，包括：

- LinkedIn 技術文章
- 架構與工程實務觀點
- 草稿與延伸筆記
- 已發布文章的備份
- 未來可能整理成教學或課程的內容素材

內容可以非常技術導向，不要求一般讀者都能理解。

主要希望讓 Senior Engineer、Tech Lead、Architect、Engineering Manager、技術型創業者，以及需要評估工程能力的人，可以從文章理解我的：

- 工程判斷
- 架構思考
- 問題拆解方式
- Trade-off 分析
- 實務經驗

詳見 [Articles/README.md](./Articles/README.md)。

## Agent Harness

`Agent-harness/` 用來保存 AI-assisted content workflow 的設計與實驗。

目標不是讓 AI 取代作者，而是讓 AI 協助：

- 整理零散想法
- 找回既有內容與脈絡
- 建立文章草稿
- 檢查論述與結構
- 維持長期寫作風格與內容一致性
- 將同一份核心內容轉換成不同發布形式
- 降低重複整理與人工搬運的成本

詳見 [Agent-harness/README.md](./Agent-harness/README.md)。

## 內容原則

這個 Repository 會優先保留「為什麼這樣做」，而不只是最後的答案。

技術內容盡量包含：

- 實際問題或痛點
- 當時的限制與背景
- 判斷過程
- 採用的解法
- Trade-off
- 哪些情境不適用
- 後續可以延伸的問題

比起單純整理技術知識，更重視 **Engineering Judgment** 與真實工程情境。

## 長期方向

SuikContentLab 目前從 LinkedIn 技術內容與 AI Agent Harness 開始。

未來若自然累積出足夠內容，可能延伸為：

- 公開技術文件
- GitHub 範例專案
- 免費教學
- 付費課程
- Architecture / Code Review 服務
- AI 輔助內容工具
- 其他由技術能力延伸出的產品或服務

這些都是可能的演進方向，不是目前必須一次完成的目標。

目前最重要的事情只有一件：

**持續把值得留下的技術思考，變成可以被搜尋、引用、版本追蹤與再次利用的資產。**

## Git LFS

SuikContentLab 使用 Git LFS 管理不適合直接進入一般 Git history 的二進位素材。

目前 `.gitattributes` 會將以下類型交由 Git LFS 追蹤：

- 圖片：PNG、JPG / JPEG、GIF、WebP、AVIF、BMP、TIFF、ICO、SVG
- PDF：PDF
- Microsoft Office：Word、Excel、PowerPoint 及常見範本 / Macro 格式

本機第一次使用此 Repository 前，需先安裝並初始化 Git LFS：

```bash
git lfs install
```

之後正常使用 `git add / commit / push` 即可，符合規則的新檔案會自動以 LFS Pointer 方式提交。

> `.gitattributes` 只會讓「之後加入 / 重新加入 Git 的檔案」進入 LFS；若 Repository 未來已存在大型二進位檔並需要把既有 Git history 一併遷移，需另外使用 `git lfs migrate`，不要直接改寫公開歷史。

