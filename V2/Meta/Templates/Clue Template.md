<%*
let source = await tp.system.suggester(
    ["URL", "YouTube", "Social Media", "Screenshot", "Text", "Conversation"],
    ["url", "youtube", "social_media", "screenshot", "text", "conversation"]
);

let title = await tp.system.prompt("Clue 標題");

let id = tp.date.now("YYYYMMDD");
let safeTitle = title.replace(/[\\/:*?"<>|]/g, "").trim();

await tp.file.rename(`Clue-${id} - ${safeTitle}`);
-%>
---
created: <% tp.date.now("YYYY-MM-DD") %>
kind: clue
source_type: <% source %>
needs_browsing: false
reviewed: false
last_reviewed:
---

# <% title %>

## Raw Capture

## Notes

## Possible Follow-up
