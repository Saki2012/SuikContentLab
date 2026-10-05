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
