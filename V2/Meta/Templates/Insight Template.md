<%*
let title = await tp.system.prompt("Insight 題目");

let category = await tp.system.suggester(
[
    "Market / Business (市場與商業)",
    "Technology / AI (技術與 AI)",
    "Product / Design (產品與設計)",
    "Workflow / Productivity (工作流與效率)",
    "Personal / Life (個人成長與生活)",
    "Other (其他)"
],
[
    "market_business",
    "tech_ai",
    "product_design",
    "workflow_productivity",
    "personal_life",
    "other"
]
);

let safeTitle = title.replace(/[\\/:*?"<>|]/g, "").trim();

await tp.file.rename(`Insight - ${safeTitle}`);
-%>
---
created: <% tp.date.now("YYYY-MM-DD HH:mm") %>
kind: insight
category: <% category %>
status: active
confidence: high
---

# <% title %>

## TL;DR / Summary

用 1-2 句話精煉這個洞察的核心結論。

- 

## The Core Concept / Principle

這個洞察/模型/原則的核心是什麼？請詳細描述。

- 

## Evidence / Supporting Clues & Explorations

這個洞察是基於哪些線索（Clues）、探索（Explorations）或觀察所推導出來的？（建議連結至相關筆記）

- 

## Actionable Takeaways / Applications

我該如何應用這個洞察？有哪些具體行動或指導原則？

- [ ] 

## Unresolved Questions / Future Iterations

關於這個洞察，還有哪些不確定、待驗證或需要隨時間持續修正的地方？

- 
