# Agent Harness

這個資料夾保存 SuikContentLab 使用的 AI Agent Harness 設計、規則與實驗。

它的目的不是單純「叫 AI 幫忙寫文」，而是逐步建立一套可重複、可檢查、可版本追蹤的內容工作流程。

## 目標

Agent Harness 未來可以協助處理：

- 從零散想法整理出可發展的題目
- 從既有 Repository 找回相關文章與歷史脈絡
- 建立 Article Brief
- 整理 Hook、核心論點與 CTA
- 產生或重構草稿
- 檢查文章是否過度 AI 化、空泛或失去作者原本語氣
- 檢查與既有文章是否重複或矛盾
- 將長文轉換成 LinkedIn 等平台需要的形式
- 發布後把正式版本與相關資訊回存 Repository

## 基本原則

### 1. Human in the Loop

AI 可以協助整理、產生與檢查，但最後的工程判斷、立場與發布決策仍由作者負責。

### 2. Repository as Source of Truth

重要的文章、規則與工作流程應保存於 Repository。

平台上的內容是發布結果，不應成為唯一資料來源。

### 3. Grounded by Existing Content

當 Agent 可以取得既有文章、技術文件或原始素材時，應優先依據這些資料工作，而不是重新憑空生成一套說法。

### 4. Draft 與 Published 必須可區分

「曾經想過」和「正式公開說過」是兩件不同的事情。

Harness 在引用舊內容時，應能辨識草稿與正式發布版本。

### 5. 保留作者聲音

AI 的任務是放大與整理 Suik 原本的思考，而不是把所有文章改寫成同一種制式的 AI 文體。

### 6. 先解決真實需求，再增加流程

不為了做 Agent 而做 Agent。

只有當一個步驟真的重複、耗時、容易遺漏或值得標準化時，才把它加入 Harness。

## 預想的內容流程

```text
想法 / 實務事件
        ↓
題目整理
        ↓
Article Brief
        ↓
草稿
        ↓
技術與論述檢查
        ↓
平台版本整理
        ↓
人工確認
        ↓
發布
        ↓
Published 版本回存
        ↓
成為下一篇內容可引用的知識
```

這套流程會隨實際使用持續修改，不把第一版當成永久規格。

## 未來可能包含

等需求出現後，可以逐步加入：

```text
Agent-harness/
├─ prompts/
├─ workflows/
├─ agents/
├─ evals/
├─ examples/
└─ docs/
```

目前不急著把這些資料夾全部建立起來。

先從實際寫文章與整理內容開始，等真正需要時再擴充。
