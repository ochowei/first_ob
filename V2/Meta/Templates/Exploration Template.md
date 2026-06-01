<%*
let title = await tp.system.prompt("Exploration 題目");

let category = await tp.system.suggester(
[
    "Business Opportunity",
    "Content Creation",
    "AI Workflow",
    "Product Idea",
    "Market Insight",
    "Research Question",
    "Other"
],
[
    "business",
    "content",
    "ai_workflow",
    "product",
    "market",
    "research",
    "other"
]
);

let safeTitle = title.replace(/[\\/:*?"<>|]/g, "").trim();

await tp.file.rename(`Exploration - ${safeTitle}`);
-%>
---
created: <% tp.date.now("YYYY-MM-DD HH:mm") %>
kind: exploration
category: <% category %>

in-progress: true
archived: false
confidence: low

promote_to_watchlist: false
promote_to_project: false
---

# <% title %>

## Trigger

什麼事件、文章、影片或觀察促使我開始思考這件事？

## Observation

我觀察到了什麼？

-

## Hypothesis

我的猜測是什麼？

-

## Why Might This Matter?

如果這個想法成立，價值在哪裡？

-

## Examples

有哪些案例支持這個想法？

-

## Counter Examples

有哪些案例反對這個想法？

-

## Questions

有哪些問題還沒有答案？

-

## Experiments

我可以如何快速驗證？

- [ ]

## Related Clues

-

## Decision

### Promote to Watchlist

條件：

-

### Promote to Project

條件：

-

### Discard

條件：

-
