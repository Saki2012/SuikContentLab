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

## 7. Article 封面與「澪」看板娘

LinkedIn Article 的封面圖不只負責說明主題，也負責建立 SuikContentLab 的長期視覺辨識。

目前 Article 封面的預設角色設定為：

> **「澪 / Mio」作為 SuikContentLab 的固定看板娘與視覺入口。**

也就是說，人物本身可以是封面的第一視覺記憶點；技術主題則透過標題、圖示、架構圖或場景元素完成第二層辨識。

這不是要求所有封面都做成完全相同的模板，而是建立一個可以反覆辨識的視覺角色。

### 封面目標

封面最好同時完成三件事：

1. **先讓人停下來**：澪作為固定人物與記憶點。
2. **讓人快速知道主題**：標題或主要技術關鍵字必須清楚。
3. **保留文章本身的專業感**：人物是入口，不應讓技術主題完全消失。

可以理解成：

```text
Mio / 澪
→ 視覺辨識、人物記憶點

Article Title / Keyword
→ 這篇在講什麼

Diagram / Code / Architecture Element
→ 這篇的技術語境
```

### 視覺方向

Article 封面可依文章主題改變場景，但優先維持：

- 澪固定作為主角或明顯視覺元素。
- 技術文章可以搭配工作桌、程式碼、架構藍圖、模組積木、流程圖、伺服器、Agent 等視覺語彙。
- 整體偏乾淨、成熟、有設計感，不做成廉價廣告 Banner。
- 標題需要在縮圖尺寸下仍有足夠辨識度。
- 不必把文章所有資訊塞進封面；只保留 Hook 與核心主題。
- 可依不同內容分類調整色調、場景與道具，但角色辨識盡量保持一致。

### 看板娘不是裝飾，而是入口

人物比技術圖更搶眼不一定是問題。

如果策略本來就是先建立角色記憶，封面可以允許：

> **先記住澪，再透過標題進入 Suik 的技術內容。**

因此不要為了「看起來更像企業技術文章」而刻意把人物縮到失去辨識度。

但仍要避免：

- 人物與文章主題毫無關聯。
- 技術標題小到看不清楚。
- 視覺內容過度複雜，使縮圖失去焦點。
- 封面只剩角色圖，完全無法辨識文章主題。

### 範例圖

封面範例圖統一放在：

`Agent-harness/Assets/LinkedIn-Article-Cover/`

未來在生成新封面前，若該資料夾已有參考圖，應先參考既有角色外觀、構圖語言與整體品牌感，再依當篇 Article 主題產生新的封面。

範例圖是 **視覺一致性的參考**，不是要求每篇完全複製同一個構圖。

### Repository 保存

封面圖、插圖與其他二進位素材應由 Git LFS 管理。

Article 本文仍保存為 Markdown；圖片則以相對路徑引用或在 metadata 中紀錄，避免把圖片內容轉成 Base64 塞進 Markdown。

核心原則：

> **澪負責讓人記住，標題負責讓人知道在講什麼，文章內容負責證明專業。**

