---
title: "從 Prompt 到 Harness，再到 AI Work System：我怎麼讓 AI 從會回答問題，變成能長期工作的系統？"
subtitle: "從 Context、GitHub 外部記憶，到可跨平台接軌的 Agent Harness"
status: review
platform:
  - linkedin
content_type: article
topics:
  - ai-agents
  - agent-harness
  - context-engineering
  - ai-work-system
  - github
created_at: 2026-10-07
published_at:
linkedin_url:
---

# 從 Prompt 到 Harness，再到 AI Work System：我怎麼讓 AI 從會回答問題，變成能長期工作的系統？

> **從 Context、GitHub 外部記憶，到可跨平台接軌的 Agent Harness**

大概一年前，我看到很多人在教 AI 的時候，最常出現的開頭大概都是：
> 「你是一個資深軟體工程師，請幫我……」
> 「你是一個專業攝影師，請根據以下需求……」
> 「你是一名專業的IG經營網紅」

這樣的提詞，剛開始接觸ChatGPT的時候，我確實也有用過
但是用著用著總覺得...好像沒差?

如果現在再問我一次：
> **「AI 到底要怎麼用得更好？」**

我已經不太會先從 Prompt 開始回答了。
因為這一年真正讓我感受最深的事情是：

**模型能力一直在變強，但如果工作方式沒有跟著變，AI 最後還是只會停留在「幫我做一段」的工具。**

所以我自己使用 AI 的方式，也一路從：
```text
Prompt → Context → Harness → AI Work System
```

慢慢往前走。

如果要很簡單地講：
- **Prompt**：這一次我要你做什麼？
- **Context**：你現在到底在哪個世界工作？
- **Harness**：你要在什麼規則、邊界與驗證下工作？
- **AI Work System**：怎麼讓這整套能力可以長期存在、版本化，而且換一個 AI 平台也能繼續用？

這篇不是要說 Prompt 已經沒用了。

我比較想整理的是：

> **當 AI 從「回答問題」開始走向「真正參與工作」，使用者需要設計的東西到底發生了什麼變化？**

---

# 第一階段：Prompt —— 這一次要做什麼？

Prompt 很直覺。

今天我要寫 Code：
> 你是一名 Senior Software Engineer，請幫我設計……

今天我要做 Code Review：
> 請以資深 Reviewer 的角度，檢查以下程式……

今天我要整理需求：
> 請扮演 PM，幫我把以下內容整理成 User Story……

這類方法在 AI 剛開始普及的時候非常有用。
因為我們最先需要解決的問題就是：

**AI 聽不聽得懂我要什麼？**

所以大家開始研究：

- Role 要怎麼設定？
- 指令要怎麼寫？
- Output Format 怎麼限制？
- 要不要給 Example？
- 怎麼避免 AI 自己發散？
- 怎麼讓 Prompt 更精準？

這些事情到現在都還有價值。
但我後來很快碰到一個問題。
Prompt 再完整，它通常還是在回答：

> **「這一次，你要做什麼？」**

它不一定知道：

- 這個專案以前為什麼這樣設計？
- 哪一版規則才是現在有效的？
- 哪些 Coding Convention 必須遵守？
- 這個功能之前踩過什麼坑？
- 哪些地方可以改？
- 哪些地方不能碰？
- 做到什麼程度才算真的完成？

所以我後來開始覺得：
**Prompt 解決的是 Instruction，但還沒有解決 Working Context。**

---

# 第二階段：Context —— 你現在到底在哪個世界工作？
同一句：
> 「幫我修改這個 API。」

如果 AI 只看到這句，它當然可以開始寫。
但如果它同時知道：

- 專案架構
- Coding Convention
- Feature Boundary
- API Contract
- 過去的 Architecture Decision
- 測試方式
- 部署限制
- 現在真正有效的規則

結果通常會差很多。
這也是為什麼後來大家開始談：
**Context Engineering。**

Prompt 比較像是在告訴 AI：
> **現在要做什麼。**

Context 則是在告訴 AI：
> **你現在站在哪裡。**

但這時候又會出現下一個很直覺的做法：
> 「那我把所有資料都塞給 AI 不就好了？」

可以。

然後你的**Token 開始燃燒。**

但我後來越來越在意的，其實還不只是 Token。

而是：
> **Context 不是越多越好。**

今天明明只是在改一個 API，
結果我把三個月以前的舊版規格、另外兩個專案、已經失效的架構討論，甚至完全無關的歷史資料全部一起塞進去。
AI 不一定因此變聰明。
有時候反而開始判斷得更亂。

所以我後來慢慢把兩件事情分開：
```text
現在真正有效的是什麼 ≠ 以前所有發生過的事情
```

以及：
```text
Source of Truth ≠ 所有曾經存在過的資料
```

這個差別很重要。

因為我真正需要的已經不是：
> **「讓 AI 記住全部。」**

而是：
> **「讓 AI 知道現在應該去哪裡找。」**

---

# 我後來開始把 GitHub 當成 AI 的外部記憶

這也是我現在很常使用的一個方法。
我有自己的 Private Repository。
但它不是單純拿來把所有對話、文件全部堆進去而已。
因為如果 AI 每次一進來就：
> 「好，我先把整個 Repository 掃一遍。」
那其實跟每次把全部 Context 一次塞爆沒有差太多。

所以我後來開始替 AI 做一張「地圖」。

概念大概是：
```text
PROJECT_INDEX
      ↓
判斷這次是什麼任務
      ↓
找到對應 Domain / README / Rules
      ↓
找到目前有效的 Source of Truth
      ↓
只讀這次真正需要的 Context
      ↓
真的需要歷史
      ↓
再去翻 History / Archive
```

我甚至真的把這個流程叫做：

**「回家」。**

新的 Chat。
隔了一段時間。
Context 已經被壓縮很多。
甚至有一天換了一個 AI 平台。

都沒關係。

先回家。

先找地圖。

再找這一次真正需要的資料。

---

# 平台 Memory 跟 GitHub 外部記憶，我會怎麼分？

我自己現在比較傾向這樣理解：

```text
Platform Memory
  → 記得「我是誰」

GitHub
  → 保存「我們做過什麼」
  → 保存「現在真正有效的是什麼」

Index
  → 告訴 AI「現在該去哪裡找」
```

這三個東西不是互相取代。

它們解決的是不同問題。

平台自己的 Memory 很適合保留：
- 穩定偏好
- 長期習慣
- 常用語言
- 比較不容易變動的個人資訊

但當資料開始涉及：
- 專案規則
- Workflow
- Architecture Decision
- Content
- History
- Current State
- Version
- Source of Truth

我就會更希望它存在一個：**自己可以控制、可以查、可以修改、可以版本追蹤的地方。**

GitHub 剛好很適合做這件事。

---

# 但 AI 有了記憶，還是不代表它會把事情做好

做到這一步之後，我很快又碰到下一個問題。
AI 現在知道資料在哪裡。
也讀到了正確的 Context。

然後呢？

它還是可能：
- Code 寫完就直接說完成
- Build 根本沒過
- Test 沒跑
- API Contract 被改壞
- Architecture Boundary 被穿透
- 文件忘記同步
- 改了一堆原本根本沒有授權它碰的東西

這也是我現在為什麼越來越在意：

**Harness。**

---

# 第三階段：Harness —— AI 越強，我反而越想替它加限制器

這件事情一開始聽起來可能有點矛盾。
AI 都越來越強了，
為什麼還要限制它？

因為我真正想要的並不是：
> **「AI 可以做很多事情。」**

而是：
> **「AI 可以在正確的範圍內，把事情做完。」**

這兩句差非常多。
如果把模型本身想像成一顆越來越強的 Engine，

Harness 做的事情不是把馬力拿掉。
而是開始替它補上：
- 路線
- 邊界
- 權限
- 煞車
- 儀表板
- 驗證方式
- 出錯之後怎麼回復

所以我現在理解的 Harness，比較接近：
```text
Context + Rules + Tools + Workflow + Memory + Validation + Guardrails
```

模型本身負責：
> **判斷、規劃、生成。**

Harness 負責：
> **限制、路由、權限、驗證與流程。**

人則負責：
> **邊界、風險與最後的 Acceptance。**

我會刻意把這三個角色拆開。
因為如果所有事情都只交給 Model 自己記得，
最後其實還是：
> 「希望它這次記得做對。」

那本質上跟以前只靠一段很長的 Prompt，沒有差太多。

---

# 我不希望人永遠是 AI Workflow 的每一個中繼站

以前我自己很多工作其實也是這樣：
```text
人分析
↓
AI 做
↓
人檢查
↓
AI 再做
↓
人再檢查
↓
AI 再做
```

這確實已經比全部自己做快很多。
但仔細看就會發現：
**人還是每一步的中繼站。**

AI 做完一段，要等我。
我看完，再叫它做下一段。
它又做完，再等我。
所以我現在更想做的是：

```text
Context
↓
Plan
↓
Execute
↓
Verify
↓
Fail
↓
Repair
↓
Verify
↓
Pass
↓
Report
```

真的遇到：

- 高風險決策
- 規則衝突
- 權限不足
- 資訊缺失
- 無法自動驗證的結果

才回到 Human Gate。

這時候 AI 才不只是：
**Coding Assistant。**
它開始變成 Workflow 裡真正可以獨立工作的節點。

---

# 我現在怎麼把這一套放進 GitHub？

如果只看概念，我現在會把 Repository 大概分成幾種角色。
它不一定非得照這個資料夾名稱做，但責任最好分得出來：

```text
Repository
├─ PROJECT_INDEX
│  └─ AI 進來之後先去哪裡
│
├─ Rules / Governance
│  └─ 哪些規則現在有效
│
├─ Domains / Projects
│  ├─ README
│  ├─ Current State
│  └─ Source of Truth
│
├─ Workflows
│  └─ 一件事情應該怎麼被做完
│
├─ Validation
│  └─ 怎麼判斷真的完成
│
└─ History / Archive
   └─ 以前發生過什麼
```

這裡我很在意一件事：

**History 跟 Current State 要分開。**

例如以前某個專案確實用過 A 規則。
後來改成 B。

歷史不能因為今天改成 B，就把以前的 A 全部改掉。
不然未來回頭看：

> 「我們當時到底為什麼會做這個決定？」

就會失去脈絡。

但 AI 在回答「現在怎麼做」的時候，也不能因為翻到舊紀錄就把 A 當成現在有效規則。
所以我會讓：

**Source of Truth 回答現在。**
**History 回答以前。**

Index 則負責告訴 AI：
> **這次到底該讀哪一個。**

---

# Repository 不只是 Memory，慢慢會變成 Agent 的 Operating Layer

做到這裡之後，我開始發現：
GitHub 對我來說已經不只是「外部記憶」。

它慢慢開始同時保存：
- Context
- Rules
- Source of Truth
- Workflow
- Validation
- History
- Agent 使用說明

這時候它其實更接近一個 **AI Operating Layer。**

或者我現在暫時比較喜歡叫 
# AI Work System

因為真正有價值的東西，開始不再只存在某一個 ChatGPT Conversation 裡。
而是被抽到 AI 平台外面。

---

# 第四階段：AI Work System —— Model 可以換，但我的世界不用重建

這件事情對我來說很重要。
因為我不希望我的 AI 工作方式最後變成：

```text
ChatGPT Memory + ChatGPT Prompt + ChatGPT Rules + ChatGPT 專屬 Workflow
```

然後有一天換一個平台：
> 「好，全部重新養一次。」

這個成本太高了。

我更希望長成：
```text
                    ┌─ ChatGPT
                    │
GitHub / Rules ─────┼─ Claude
Source of Truth     │
Workflow / Harness  ├─ Codex
Validation          │
                    └─ Future Model
```

模型變成可以替換的執行元件。
真正屬於我的東西留在外面。

今天 ChatGPT 可以透過 Connector 或 Tool 讀這個 Repository，
那就讓 ChatGPT 回家。

明天其他平台可以透過 MCP、API、Repository Checkout 或其他整合方式取得同一份資料，
那就讓它讀同一套 Source of Truth。
每個平台實際接法不會完全一樣。
模型能力也不會完全一樣。

所以我說的「無痛接軌」並不是：
> **換一顆模型之後，所有行為會 100% 相同。**

我真正想降低的是：
> **重新建立 Context、規則、資料與 Workflow 的成本。**

這才是我覺得跨平台最有價值的地方。
---

# Agent 不應該等於某一顆 Model

這也是我現在看 AI Agent 時，很在意的一個觀念。
我不太希望一個 Agent 最後只是：
> GPT-XX + 一段超長 System Prompt

如果它真的要變成可以長期工作的東西，
我比較希望它是：

```text
Model + Context + External Memory + Tools + Workflow + Validation + Guardrails
```

Model 只是其中一個元件。
今天這顆模型規劃比較強，可以讓它負責 Plan。
另一顆模型寫 Code 比較穩，可以把 Execute 交給它。
有些工作甚至不用 LLM，直接交給 deterministic tool：
```text
Build
Test
Lint
Type Check
Schema Check
Diff Check
```

我反而會希望：
**能 deterministic 的地方，就不要硬叫 Model 猜。**

Model 應該把能力花在：
- 判斷
- 規劃
- 生成
- 推理
- 不確定情境

而不是連：
> 「Build 到底有沒有過？」

都靠它自己看著螢幕感覺。

---

# Verify 這一層，我現在覺得比 Generate 還重要

AI 很會 Generate。
現在真正麻煩的反而是：

> **它說完成了，到底算不算完成？**

所以我現在會很想把 Definition of Done 變成機器可以理解的東西。

例如一個 Coding Task：
```text
Implement
↓
Build
↓
Unit Test
↓
Type Check
↓
Lint
↓
API Contract Check
↓
Architecture Rule Check
↓
Git Diff Review
↓
Report
```

如果其中一個 Fail：

```text
FAIL
↓
Repair
↓
Verify Again
```

而不是：
> 「我已經修改完成，請您自行確認。」

如果每件事情最後還是要人從頭驗一遍，
那 Agent 就還沒有真的拿走多少 Workflow。

---

# Human in the Loop，不代表 Human in Every Step

這也是我現在對 Human Gate 的理解。
Human in the Loop 很重要。
但不代表：

**每一步都要人按一次 Yes。**

如果每一個動作都要我確認：

```text
可以讀檔嗎？
可以改檔嗎？
可以 Build 嗎？
可以 Test 嗎？
可以修錯嗎？
```

那人還是 Bottleneck。

我比較希望真正保留給人的 Gate 是：

- 高風險變更
- 不可逆操作
- 權限升級
- 商業 / 架構重大決策
- 規則彼此衝突
- 沒有明確驗證方式
- 最終 Acceptance

其他可以安全驗證的流程，
就讓 Harness 自己跑完。

所以 Harness 的目的不是：
> **把人移出流程。**

而是：

> **重新決定哪一些地方，真的需要人。**

---

# 那 Harness 之後到底是什麼？

這是我最近開始想的一個問題。

如果把整個演化拉長，大概會變成：

```text
Prompt Engineering
│
│ 怎麼讓 AI 聽懂我要什麼？
↓
Context Engineering
│
│ 怎麼讓 AI 拿到正確資訊？
↓
Harness Engineering
│
│ 怎麼讓 AI 在正確邊界裡把事情做完？
↓
AI Work System
│
│ 怎麼讓記憶、規則、Workflow、Validation
│ 可以版本化、持續存在、跨模型使用？
↓
AI-Native Workflow / Organization
```

最後那一層，我覺得才是真正有趣的地方。
因為當 AI 已經知道：
- 去哪裡拿資料
- 哪份才是 Source of Truth
- 自己能做什麼
- 哪些事情不能碰
- 怎麼驗證
- 失敗怎麼 Repair
- 什麼時候一定要找人

我們真正開始改變的，就不只是：

**一個工程師寫 Code 的速度。**

而是：

**整個工作的結構。**

---

# 從 Coding Speed，到 Workflow Design，再到 Team Design

這其實也回到我最近一直在想的問題。
如果 AI 可以自己走完：

```text
Context
→ Plan
→ Execute
→ Verify
→ Repair
```

那接下來要問的事情就會慢慢變成：

- 哪些工作真的還需要工程師親手做？
- 哪些角色主要在做資訊搬運？
- 哪些等待可以直接消失？
- 哪些 Review 可以往前移？
- Human Gate 應該放在哪裡？
- 原本需要多人反覆交接的 Workflow，是不是可以重新設計？

這時候 AI 帶來的提升就不只是：

**Coding Speed。**

而開始變成：

**Workflow Design。**

甚至再往後：

**Team Design。**

這也是我現在覺得 AI 真正有趣的地方。

---

# 這一套不是沒有代價

我不會說把 GitHub 當外部記憶、再加一套 Harness，就可以解決所有 AI 問題。
它的成本其實也很明顯。

## 1. Repository 本身要有人整理

如果資料本身就是亂的，
AI 只會更快地讀到一堆亂的資料。

所以：

> **External Memory 不代表可以不做 Information Architecture。**

## 2. 規則會過期

Rules / README / Source of Truth 如果沒有人維護，
最後 AI 只會很認真地照著舊規則做錯事。

## 3. Token 不會消失

GitHub 外部記憶不是魔法。
AI 真正把資料讀進 Context 時，一樣會消耗 Token。

差別只是：

> **不要每次把整間房子搬過來，而是讓它自己拿這次需要的那一份。**

## 4. 不同平台的 Tool 能力不同

有的平台可以直接操作 Repository。
有的平台只能讀。
有的平台可以透過 MCP。
有的平台需要 API 或其他 Connector。

所以 Work System 應該盡量不要把核心規則綁死在某一個平台的私有功能裡。

## 5. Secrets 不應該因為 GitHub 是記憶就全部丟進去

這一點我會特別分開。

```text
External Memory ≠ External Secrets Store
```

API Key、Access Token、Password、Private Key、Recovery Code 等真正的 Secret，
還是應該交給正確的 Secrets Management。
不是因為 AI 要「記得」，就把所有東西都寫進 Repository。

---

# 最後：如果現在再問我一次「AI 要怎麼用得更好？」

一年前，我可能會開始講：
- Prompt 要怎麼寫。
- Role 要怎麼設。
- Instruction 怎麼下。

現在我反而會先問：
- 你的資料放在哪？
- 哪份才是 Source of Truth？
- AI 怎麼知道這次該讀什麼？
- 做錯了怎麼發現？
- Definition of Done 是什麼？
- 失敗能不能自己修？
- 什麼事情它不能決定？
- Human Gate 在哪裡？
- 如果明天換一顆 Model，這套工作方式還能不能繼續用？

因為我現在越來越覺得：

> **Prompt 是操作 AI。**

> **Context 是讓 AI 看懂現在的世界。**

> **Harness 是設計 AI 怎麼工作。**

而 AI Work System

是在設計：

> **AI 要怎麼長期存在於你的工作裡。**

這大概就是我現在理解的：

**AI 使用者的下一次演化。**

---

如果要把這整篇再濃縮成一句話，我會留這句：

> **模型越來越強之後，真正稀缺的能力可能不再是「怎麼叫 AI 做事」，而是「怎麼替 AI 建立一個它可以安全、持續、可驗證地工作的世界」。**

---

如果你也開始把 AI 從「問問題的工具」往日常 Workflow 裡放，我滿好奇你現在走到哪一層：

```text
Prompt？Context？Harness？
還是已經開始做自己的 AI Work System？
```

之後有空我也會再把其中幾塊拆開寫：

- GitHub 的 Index / Rules / Source of Truth / History 實際怎麼分
- Verify / Repair Loop 怎麼放進 Harness
- Human Gate 到底應該留在哪
- 怎麼讓同一套 AI Workflow 降低跨模型與跨平台的遷移成本

歡迎留言交流。

#AIAgents #AgentHarness #ContextEngineering #SoftwareEngineering #AIEngineering
