# LinkedIn Article 格式處理

這份文件定義 SuikContentLab 對 LinkedIn 長篇 Article 的基本處理方向。

Article 與 Post 的角色不同：

```text
Post
→ Feed 入口
→ 快速傳達一個主要觀點
→ 建立認知、討論與後續行動

Article
→ 深度內容
→ 完整處理一個較大的主題
→ 建立專業深度與可長期引用的內容資產
```

## 1. 什麼情況適合 Article

當內容出現以下情況時，優先考慮 Article：

- 一個主題需要多個子問題才能完整說明。
- 需要交代背景、限制、設計原則與 Trade-off。
- 需要放較完整的架構圖、程式碼、案例或比較。
- 拆成 Post 後雖然可以閱讀，但讀者仍需要一份完整整理版。
- 多篇相關 Post 已經形成同一個系列，可以重新整理成長文。

Article 不是因為「字很多」才叫 Article。

重點是：

> **這個題目是否值得一份完整、可長期引用的論述。**

## 2. 建議結構

Article 可以比 Post 更完整：

```text
Title
↓
摘要 / 為什麼值得看
↓
背景與問題
↓
核心觀點
↓
分段展開
↓
案例 / Framework / Diagram
↓
Trade-off / 不適用情境
↓
結論
↓
延伸閱讀 / CTA
```

不要求每篇完全一致，但需要有清楚層次。

## 3. 閱讀負擔

Article 可以長，但仍然不能只是把多篇 Post 黏在一起。

長文應使用：

- 明確 Heading
- 短段落
- 清楚的小節
- 必要的清單
- 圖、Code 或範例
- 小節之間的推進關係

技術深度可以高，但每一節都應回答一個明確的小問題。

## 4. 與 Post 的關係

同一個題目可以先用 Post 驗證與累積，再整理成 Article。

例如：

```text
Post 1：為什麼系統核心與業務功能要分開？
Post 2：SysCore / Feature / SpecFeature 怎麼切？
Post 3：Feature 為什麼容易長成 Shared / Common？
        ↓
Article：我如何規劃一套能持續成長的系統模組邊界
```

Article 可以引用 Post 已驗證過的觀點，但應重新組織，而不是逐篇直接拼接。

## 5. CTA

Article 的 CTA 可以比 Post 更輕。

優先方向：

- 延伸到其他 Article / Post
- 引導查看 GitHub / Example
- 邀請討論
- 若內容與實際能力或服務高度相關，再自然加入 Service CTA

核心仍然是：

> **先讓 Article 本身值得保存與引用，再談下一步。**

## 6. LinkedIn Editor 搬運格式

LinkedIn Article 使用 Rich Text Editor，Repository 內的 Markdown 標題、引用、粗體與 Code Fence 不會在貼上後自動轉成對應格式。

因此，準備「要實際搬進 LinkedIn Editor 的版本」時，應使用一套暫時性的 **Editor Transfer Marker**。

目標不是讓標記本身出現在正式文章，而是讓搬運時可以快速掃過全文，知道每一段要套用什麼格式。

### Marker 規則

```text
【TITLE】文章標題
【H1】主要章節
【H2】次要章節
【BOLD】需要整段加粗的重點 / 小節標題
【QUOTE】引用或核心判斷
【CODE:ts】程式碼區塊
...
【/CODE】
【DIVIDER】
```

其中：

- `【TITLE】`：貼到 LinkedIn 的文章標題欄，不留在正文。
- `【H1】`：在 LinkedIn Editor 套用主要 Heading。
- `【H2】`：套用次級 Heading。
- `【BOLD】`：整行或整段套 Bold；也可以拿來代替沒有必要再細分的 H3。
- `【QUOTE】`：套用 Quote。
- `【CODE:<lang>】...【/CODE】`：整段套用 Code Block；`<lang>` 只供搬運時辨識，不需要留在 LinkedIn。
- `【DIVIDER】`：插入 Divider / Horizontal Rule。

普通段落、`-` 清單與數字清單可以保留純文字；若 LinkedIn Editor 的清單格式值得套用，再整段選取後轉成 Bullet / Numbered List。

### 搬運流程

```text
1. Repository 保留文章 metadata 與 Editor Transfer Marker
2. 【TITLE】內容貼到 LinkedIn Title 欄
3. 正文整段貼入 LinkedIn Article Editor
4. 由上往下搜尋「【」
5. 依 Marker 套用 Heading / Bold / Quote / Code / Divider
6. 套完後刪掉 Marker
7. 最後做一次閱讀與排版檢查
```

這樣做的目的是把「重新理解 Markdown 結構」變成「照標記加工」，降低長篇 Article 的搬運成本。

### Marker 使用原則

- Marker 只存在 Repository / 搬運稿，**正式 LinkedIn Article 不應保留 Marker**。
- 不需要為每一句粗體都增加 Marker；只標示真正影響閱讀層級的內容。
- Inline emphasis 若不是必要，可以直接保留成一般文字，避免搬運工作量過高。
- Code Block、Heading、Quote 與 Divider 優先標示，因為它們最影響長文閱讀體驗。
- Article 很長時，寧可讓 Marker 清楚，也不要靠記憶一段一段猜原本的 Markdown 層級。

核心原則：

> **Repository 負責保存內容結構；Transfer Marker 負責降低 LinkedIn Editor 的人工排版成本。**

