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

## 6. LinkedIn Editor 搬運方式

Repository 內的 Article **一律保留標準 Markdown 格式**，不另外插入 `【H1】`、`【QUOTE】`、`【CODE】` 之類的搬運標記。

原因：

- Markdown Reader 可以直接把 `# / ## / ###`、粗體、引用、清單、Code Block 渲染成清楚的文章結構。
- Repository 本身仍維持乾淨、可閱讀、可版本控管的 Source of Truth。
- 未來要轉其他平台、產生 PDF、網站或課程內容時，不需要先清除平台專用 Marker。
- LinkedIn Article 雖然不會自動解析 Markdown，但搬運時可以直接參考 Markdown Reader 的視覺結果，逐段套用 Rich Text 格式。

### 建議搬運流程

```text
1. 用 Markdown Reader 開啟 Repository 文章
2. 將 Title 貼到 LinkedIn Article 標題欄
3. 正文分段複製到 LinkedIn Editor
4. 依 Markdown Reader 顯示結果套用：
   #   → 主要 Heading
   ##  → 次級 Heading
   ### → 小節標題 / Bold
   >   → Quote
   code fence → Code Block
   - / 1. → Bullet / Numbered List
5. 視需要加入 Divider、圖片或封面
6. 最後做一次 LinkedIn 實際閱讀檢查
```

### Markdown 與 LinkedIn 格式對照

| Repository Markdown | LinkedIn Editor |
| --- | --- |
| `# Heading` | 主要 Heading |
| `## Heading` | 次級 Heading |
| `### Heading` | 小節標題或 Bold |
| `**重點**` | Bold |
| `> 引用` | Quote |
| fenced code block | Code Block |
| `- item` | Bullet List |
| `1. item` | Numbered List |
| `---` | Divider |

### 原則

- Repository 不為 LinkedIn 犧牲 Markdown 可讀性。
- 不建立第二份只為 LinkedIn 搬運存在的正文，避免兩份內容逐漸不同步。
- LinkedIn 的排版屬於「發布層」，Markdown 內容屬於「內容層」。
- 若 Article 很長，優先靠 Markdown 的 Heading 層級與留白降低閱讀負擔。

核心原則：

> **Markdown 保存內容與結構；LinkedIn Editor 只負責最後的呈現。**

