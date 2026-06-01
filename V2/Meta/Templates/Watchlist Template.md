<%*
let topic = await tp.system.prompt("Watchlist 題目");

let domain = await tp.system.suggester(
[
    "AI Tool",
    "Code / Dev Tool",
    "Market / Opportunity",
    "Game Dev",
    "Legal / Risk",
    "Research Topic",
    "Other"
],
[
    "ai_tool",
    "dev_tool",
    "opportunity",
    "game_dev",
    "legal_risk",
    "research",
    "other"
]
);

let cadence = await tp.system.suggester(
[
    "Weekly",
    "Biweekly",
    "Monthly",
    "Ad hoc"
],
[
    "weekly",
    "biweekly",
    "monthly",
    "ad_hoc"
]
);

let id = tp.date.now("YYYYMMDD-HHmmss");
let safeTopic = topic.replace(/[\\/:*?"<>|]/g, "").trim();

await tp.file.rename(`Watchlist - ${safeTopic}`);
-%>
---
created: <% tp.date.now("YYYY-MM-DD HH:mm") %>
kind: watchlist
domain: <% domain %>
cadence: <% cadence %>
in-progress: true
archived: false
reviewed: false
reviewed_at:
last_surveyed:
---

# <% topic %>

## Why Track This?

這個題目為什麼值得追蹤？

## Current Understanding

目前我已經知道什麼？

## Tracking Boundary

### 我要追蹤

- 

### 暫時不追蹤

- 

## Key Questions

- 

## Related Clues

- 

## Survey Log

### <% tp.date.now("YYYY-MM-DD") %>

- Summary:
- New findings:
- Decision:
- Next action:

## Next Actions

- [ ]
