<%*
const title = await tp.system.prompt("Seed Title");
await tp.file.rename(title);
-%>
---
type: seed
status: active
created: <% tp.date.now("YYYY-MM-DD HH:mm") %>
updated: <% tp.date.now("YYYY-MM-DD HH:mm") %>
source:
review: false
latest_review: <% tp.date.now("YYYY-MM-DD HH:mm") %>
tags:
  - seed
---

# Summary

一句話描述這個 Seed。

# Spark

# Why Interesting?

# Hypothesis

# Possible Directions

# Trigger To Explore

# Notes
