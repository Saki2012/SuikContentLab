# Articles

這個資料夾保存 SuikContentLab 的技術文章與公開內容。

目前以 **LinkedIn** 為主要發布平台，內容定位偏向軟體工程、架構設計、RD 專業工作與工程實務。

## 內容定位

這裡不是一般生活型社群內容，也不是單純把文件或技術筆記貼到 LinkedIn。

希望每篇內容至少能呈現其中一項：

- 一個真實工程問題
- 一個值得討論的技術判斷
- 一個架構上的取捨
- 一個從實務經驗得到的觀察
- 一套可被其他工程師理解與檢驗的方法

核心不是證明「知道多少名詞」，而是留下：

> 我怎麼理解問題、怎麼做決策，以及為什麼最後選擇這個做法。

## LinkedIn 的角色

LinkedIn 是主要的公開發布介面。

SuikContentLab 則負責保存：

- 原始想法
- 草稿
- 正式發布版本
- 延伸說明
- 參考資料
- 相關文章之間的關係
- 後續可能發展的題目

因此 LinkedIn 上的文章即使未來被修改、平台格式改變，核心內容仍然可以在這裡被追蹤。

## 一篇文章可以包含什麼

不要求每篇都使用相同格式，但可以視需要包含：

```text
題目 / Working Title

背景與問題
Hook
核心觀點
案例或實務情境
解法 / Framework
Trade-off
結論
CTA
延伸筆記
相關文章
LinkedIn 發布連結
```

其中 Hook 與 CTA 是發布策略的一部分，不代表文章必須寫成制式行銷文。

技術內容與真實判斷仍然優先。

## 文章狀態

初期不急著用大量資料夾分類，可以先透過文章內的 Metadata 或標記區分狀態，例如：

- `idea`：只有題目或零散想法
- `draft`：正在整理
- `review`：內容大致完成，等待最後檢查
- `published`：已正式發布
- `archived`：保留但暫不使用

等文章數量真的增加，再決定是否需要依狀態、主題或系列建立子資料夾。

## 建議 Metadata

未來可以在 Markdown 開頭加入簡單 Front Matter：

```yaml
---
title: "文章名稱"
status: draft
platform:
  - linkedin
topics:
  - architecture
created_at: YYYY-MM-DD
published_at:
linkedin_url:
---
```

不必為了補欄位而補欄位，只保留真正有助於搜尋、追蹤與 AI 讀取的資訊。

## 內容主題

目前可自然涵蓋：

- Software Architecture
- .NET / ASP.NET Core
- React / Frontend Architecture
- Legacy System
- Migration
- Modularization
- Source of Truth
- Knowledge Transfer
- Engineering Process
- Debugging / Incident Analysis
- AI-assisted Engineering
- 其他真實 RD 工作中值得留下的工程問題

分類不需要現在一次定死；實際內容累積後再長出結構。
