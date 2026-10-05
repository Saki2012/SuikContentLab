---
title: "SysCore / Feature / SpecFeature，我自己到底怎麼分？"
status: review
platform:
  - linkedin
content_type: post
topics:
  - architecture
  - modularization
  - system-design
  - maintainability
created_at: 2026-10-06
published_at:
linkedin_url:
---

🧩 SysCore / Feature / SpecFeature，我自己到底怎麼分？

上一篇講到，如果是一套「未來還會繼續長」的系統，我自己至少會先守住：

SysCore / Feature 這兩層，也就是系統核心跟業務邏輯。

如果還有標準版、客製版或特殊需求，再考慮 SpecFeature。

但這三個到底差在哪？

我自己其實只先問一個問題：

「這一塊能力，到底是在服務整個系統，還是在服務某個業務？」

1️⃣ SysCore：可以帶去其他系統的基礎能力

我心裡的 SysCore，不是一個超大的 Common 資料夾。

它比較像是一組一組有明確責任的系統模組。

例如：

• Log：統一格式、Trace、Audit、輸出方式  
• Security：Authentication、Authorization、Token、Permission  
• Cache：Local / Distributed Cache、Expiration、Invalidation  
• DB、Exception、File Storage、Tracing……

但我自己判斷 SysCore 最重要的一點是：

👉 重點！它最好是「帶得走」的。

今天從 CMS 換成合約系統、會員系統甚至 ERP，

Log 還是 Log。  
Security 還是 Security。  
Cache 還是 Cache。

差別只在這套系統到底需要用多重。

如果只是一台 Local Machine 在跑，根本沒有 Distributed Cache 或 Load Balance 的需求，那相關能力就不要放進來。

需要的拿進來，不需要的拔掉。

所以 SysCore 對我來說不是「共用 Code 集合」，而是一組有邊界、可替換、可選用的系統能力。

2️⃣ Feature：跟著產品長出來的業務模組

Feature 就很不一樣。

它回答的是：

👉 這個產品到底要做什麼？

例如 CMS 可能有：

• Announcement  
• Page Management  
• Site Menu  
• Category

合約系統則可能是：

• Contract  
• Approval Flow  
• Renewal  
• Termination

Feature 裡面會跟著實際產品去設計：

Domain Model、Business Rule、API、DTO、流程、狀態轉換等等。

所以我會把兩者簡單記成：

SysCore：系統怎麼運作。

Feature：產品要做什麼。

3️⃣ SpecFeature：標準產品之外的特殊延伸

這層不是每個系統都需要。

例如我已經有一套標準 Contract Feature，

但 A 客戶多一段特殊流程，B 客戶又有另一組規則。

我又不希望這些客製邏輯一直污染標準 Feature，

這時候才會考慮把它拉成 SpecFeature。

所以它比較像特定客戶、版本或情境才存在的延伸。

如果今天根本沒有產品化或客製需求，就不用硬生這層。

架構不是資料夾越多越高級。

所以最後我自己會記成：

🧱 SysCore：可被其他系統帶走的技術能力。  
📦 Feature：依照產品 Domain 長出來的業務模組。  
🧩 SpecFeature：標準產品之外的特殊需求。

切到最後，其實已經不只是資料夾分類。

而是在替整個專案建立一套共同語言：

「這個責任，到底應該放在哪裡？」

💬 你手上的專案會怎麼切「系統能力」跟「業務功能」？

歡迎底下留言分享一下。

#SoftwareArchitecture #SoftwareEngineering #SystemDesign #ModularArchitecture
