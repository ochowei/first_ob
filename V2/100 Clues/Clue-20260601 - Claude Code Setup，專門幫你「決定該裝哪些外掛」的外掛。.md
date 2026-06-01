---
created: 2026-06-01
kind: clue
source_type: text
needs_browsing: false
reviewed: true
last_reviewed:
---

# 「Claude Code Setup」的外掛，專門幫你「決定該裝哪些外掛」的外掛。

## Raw Capture

不知道該裝哪些 Claude Code 外掛嗎？來裝這個外掛取得適合你的外掛推薦名單！

Anthropic 官方自己推出了一個叫做「Claude Code Setup」的外掛，專門幫你「決定該裝哪些外掛」的外掛。

它的運作邏輯很簡單，你在專案資料夾打開 Claude Code，跟它說「recommend automations for this project」，它就會掃描你的 codebase，看看你用什麼語言、什麼框架、package.json 裡有什麼依賴，再從五大類中挑出最適合你的選項。

五大類分別是 MCP Servers、Skills、Hooks、Subagents，以及 Slash Commands。預設每類給你一到兩個最有價值的推薦，指定類別則會給三到五個更完整的清單。

實例上，如果你是 React 專案，它會推薦 Playwright MCP；如果偵測到驗證相關程式碼，就會建議加上 security-reviewer 子代理。這種「根據你的程式碼說話」的推薦方式，比起一般 marketplace 條列瀏覽精準很多，新手不會被選項淹沒，老手也能挖到之前沒注意到的好工具。

## Notes

## Possible Follow-up
