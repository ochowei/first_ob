# 常用 Prompts

收藏日常工作中常用的 Prompt，方便快速取用。

---

## Prompt 範例


### 分析 Codebase Domain
**用途：** 讓 AI Agent 分析 Codebase 的 Domain (DDD 中的 Domain)

```
「請分析這個 repo,列出你觀察到的主要 domain(例如 auth、billing、notification、user-profile...)。針對每個 domain 告訴我:1) 相關的目錄/檔案 2) 估計的複雜度 3) 是否有明顯的對外 API 或行為介面。先不要寫 spec。」
```
