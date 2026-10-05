# LinkedIn 文章格式處理

這份文件定義 SuikContentLab 在準備 LinkedIn 文章時的「發布格式處理」規則。

核心原則：

> Repository 可以使用 Markdown 保存與管理內容，但 LinkedIn 發布版本應優先確保「純文字貼上後仍然好讀」。

因此，LinkedIn 版本不應依賴 Markdown 的 `#`、`**粗體**`、表格或其他語法才能成立。

文章本身仍遵循：

```text
Hook
  ↓
Content / Resolve
  ↓
CTA
```

格式處理的任務，是讓這個結構在 LinkedIn 的純文字環境裡仍然清楚。

---

## 1. Plain Text First

LinkedIn 文章 / 貼文的正文，優先使用純文字就能成立的格式。

### 不依賴

- `# 標題`
- `**粗體**`
- Markdown Table
- Markdown Quote
- 複雜巢狀清單
- 必須靠語法渲染才看得懂的結構

### 優先使用

- 空行
- 短段落
- 獨立成行的重點句
- Unicode 符號
- 適量 Emoji
- `1️⃣ / 2️⃣ / 3️⃣`
- `•` 項目符號
- 引號「」
- 清楚的前後文節奏

目的不是把文章做得花俏，而是讓讀者在手機或 LinkedIn Feed 中快速掃讀。

---

## 2. Emoji 的角色

Emoji 應該是「視覺路標」，不是裝飾。

一篇長文通常只需要少量、有固定語意的 Emoji。

建議用途：

- 💡：主題、核心觀察、Hook
- 🧩：架構、組成、分類
- ⚠️：問題、風險、踩坑
- 1️⃣ 2️⃣ 3️⃣：需要明確分項的重點
- 🤖：AI / Agent 相關段落
- 🔍：分析、判斷、排查
- 👉：下一步、延伸閱讀、Continuation CTA
- 💬：討論、留言、交流 CTA

### Emoji 原則

- 不需要每一段都放。
- 一個 Emoji 最好有固定角色。
- 不要讓 Emoji 比內容更搶眼。
- 技術深度高的文章仍應維持專業感。
- 若拿掉 Emoji，文章本身仍然必須成立。

---

## 3. 標題 / Hook

LinkedIn 版本不要依賴 Markdown Heading。

例如 Repository 原稿可能是：

```md
# 一個系統能跑，不代表它真的適合一直長大
```

LinkedIn 版本可以寫成：

```text
💡 一個系統能跑，不代表它真的適合一直長大
```

標題後直接進入 Hook，不需要額外寫「前言」。

Hook 的目標仍然是讓對的人快速辨識：

> 「這篇正在講我遇過的問題。」

---

## 4. 段落節奏

LinkedIn 以 Feed 閱讀為主，段落不要塞得太滿。

建議：

- 一個段落 1～3 句為主。
- 關鍵句可以獨立成行。
- 一個概念講完再換段。
- 長段落應拆開，而不是用更多標點硬撐。
- 技術名詞可以保留，不需要為一般讀者刻意稀釋。

例如：

```text
功能都有，系統也能跑。

但東西散得到處都是。

這通常不是第一天就會出問題，而是在系統開始長大、開始維護之後才慢慢爆出來。
```

---

## 5. 重點強調

因為純文字沒有粗體，優先使用以下方式強調：

### A. 獨立成行

```text
至少、至少，要先分得出「系統核心」跟「業務功能」這兩層。
```

### B. Emoji + 短句

```text
⚠️ 問題不是功能不能跑，而是每個地方都開始長出自己的版本。
```

### C. 編號

```text
1️⃣ 一直重複寫
2️⃣ 每一份都開始長得不一樣
```

### D. 引號

```text
「……這一坨到底怎麼改啊 ˊ_>ˋ」
```

避免為了強調而使用大量全形符號、驚嘆號或 Emoji。

---

## 6. 技術內容的可讀性

技術文章不需要刻意寫成大眾科普。

目標讀者如果是 RD、Senior Engineer、Tech Lead、Architect、Engineering Manager，就可以直接使用：

- Repository
- Domain
- Feature
- Framework
- Log
- Cache
- DB
- SysCore
- SpecFeature

但仍需保持句子好讀，不要連續堆疊名詞。

若一段同時出現太多概念，優先拆段，而不是加更多解釋。

---

## 7. CTA 格式

CTA 仍依照「文章結構」中的三種類型：

### Conversation CTA

```text
💬 你們現在是怎麼切系統核心跟業務功能的？
```

### Continuation CTA

```text
👉 下一篇我會再來拆 SysCore / Feature / SpecFeature 到底怎麼分。
```

### Service CTA

```text
如果你手上的專案也正在整理類似問題，也可以留言或私訊我聊聊。
```

CTA 不需要全部同時出現。

可以自然混合，例如：

```text
👉 下一篇我會再講實際怎麼切。

💬 如果你手上的專案也有類似狀況，也可以留言或私訊我聊聊。
```

---

## 8. Repository 與 LinkedIn 版本

Repository 仍可以保留 Front Matter：

```yaml
---
title: "文章名稱"
status: review
platform:
  - linkedin
---
```

但 Front Matter 以下的「發布正文」，應盡量直接就是可貼到 LinkedIn 的純文字版本。

也就是：

```text
Metadata
↓
LinkedIn-ready Body
```

如此一來：

- GitHub 保留 Source of Truth
- AI 可以直接讀取與修改
- 發文時不需要再清理 Markdown
- 未來要轉其他平台時仍能保留原始內容

---

## 9. 發布前格式檢查

發布前快速確認：

- 複製正文後，有沒有殘留 `#`、`**` 等 Markdown 語法？
- 第一屏能不能快速看懂主題？
- 段落是否太長？
- 關鍵句是否有足夠留白？
- Emoji 是否有語意，而不是純裝飾？
- 編號是否真的代表分項？
- 技術名詞是否保持原本精準度？
- CTA 是否自然？
- 純文字貼上 LinkedIn 後，文章是否仍然完整？

最後原則：

> **格式只負責讓內容更容易被讀，不能取代內容本身。**
