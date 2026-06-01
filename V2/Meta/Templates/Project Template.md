<%*
let project = await tp.system.prompt("Project 名稱");

let safeProject = project.replace(/[\\/:*?"<>|]/g, "").trim();

await tp.file.rename(`Project - ${safeProject}`);
-%>
---
created: <% tp.date.now("YYYY-MM-DD HH:mm") %>
kind: project
project: <% project %>
tags: 
in-progress: true
archived: false
priority: medium
reviewed: false
reviewed_at: 
---

# <% project %>

## 📌 Context & Goals / 專案脈絡與目標

- **Core Objective:** 說明此項子任務/模組開發在 [<% project %>] 中的核心目的與預期成效。
- **Background:** 記錄背景脈絡、目前的系統狀態、或者觸發此需求的前置事件。

---

## 💡 Brainstorm & Design Decisions / 設計決策與腦力激盪

> [!NOTE]
> 開發與設計應遵循以下標準工作流流程：
> **Brainstorm 🧠 ➔ Write Plan 📝 ➔ Execute Plan 🛠️ (Subagent-driven)**

### 1. Key Questions & Trade-offs / 關鍵考量與權衡

- **解析度與架構:** (例如：32x32 vs 16x16 的細節取捨、模組命名衝突防範、i18n UI 層與 Canvas 渲染層解耦等)
- **架構設計:** 
- **潛在風險:** 

### 2. Proposed Plan / 預計方案

- [ ] 

---

## 📓 Execution Log & Notes / 執行記錄與細節筆記

### <% tp.date.now("YYYY-MM-DD") %>

#### 🔨 進度與變更記錄
- 

#### 🔍 驗證與測試
- **煙霧測試 (Smoke Test):** 
- **視覺驗證重點 (Visual Check):** 

---

## 🔗 References & Assets / 參考資料與專案資產

### 🌐 程式庫與工具連結
- **Repository:** 
- **Design Spec:** 

### 📚 Dataview 參考卡片
- [title:: 相關工具或規格書]
  [url:: [Link](https://example.com)]
  [category:: reference]
  [tags:: tool]
  [comment:: 說明此參考資料的用途]
  [create:: [[<% tp.date.now("YYYY-MM-DD") %>]]]

---

## 🎯 Next Actions / 下一步行動

- [ ] 
