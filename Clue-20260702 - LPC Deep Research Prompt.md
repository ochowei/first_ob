---
created: 2026-07-02
kind: clue
source_type: conversation
needs_browsing: false
reviewed: false
last_reviewed:
---

# LPC Deep Research Prompt

## Raw Capture

我認為這是目前最值得做的一步。

**不要只是讓 Deep Research「自由發揮」。**

要把它當成你的 **Research Team**。

每一份 Research 都有明確的目標、產出格式、決策問題，而且都要以 **LPC Toolkit** 為中心，而不是只介紹 LPC。你的專案目前已經有完整的 core / web 架構、Export、License、Preset、Layer、Asset Snapshot 等能力，可以把這些能力作為研究背景。

---

# Research 01：LPC Ecosystem Report（第一個一定要做）

> ⭐⭐⭐⭐⭐
> 
> 這份是整個研究計畫最重要的一份。

---

## Prompt

```text
# Role

You are an Open Source ecosystem researcher.

I am developing a brand new open source project called "LPC Toolkit".

It is NOT just another fork of the original Universal LPC Generator.

The project already has:

- modular architecture
- browser UI
- reusable core engine
- attribution generation
- export pipeline
- offline asset support
- custom assets
- presets
- URL sharing
- license handling
- release snapshot
- future CLI support

I want to understand the entire LPC ecosystem before releasing it.

---

Please perform a deep research report about the LPC ecosystem.

Include:

1. History of Liberated Pixel Cup

2. Timeline

3. Important repositories

4. Important maintainers

5. OpenGameArt relationship

6. Major asset contributors

7. Current active projects

8. Abandoned projects

9. Related tools

10. Current community activity

11. Existing pain points

12. Opportunities for new projects

13. Risks of creating another generator

14. Ecosystem map

15. Future trends

---

Output

Generate a report with:

- Executive Summary

- Ecosystem Overview

- Timeline

- Community Map

- Major Projects

- Major Contributors

- Opportunities

- Threats

- Recommendations for LPC Toolkit

- Sources

Include diagrams and tables whenever appropriate.

Do not simply describe LPC.

Focus on helping a new open source project decide its future direction.
```

---

# Research 02：Community Pain Point Survey

> ⭐⭐⭐⭐⭐

這份我認為比 Ecosystem 還重要。

---

## Prompt

```text
Research every discussion related to:

- Universal LPC Generator
- Liberated Pixel Cup
- OpenGameArt
- Reddit
- GitHub Issues
- GitHub Discussions
- itch.io
- Godot Forum
- RPG Maker community

Collect:

- bugs
- complaints
- feature requests
- workflow issues
- limitations
- UI complaints
- export problems
- animation problems
- random outfit issues
- license issues

Group similar discussions together.

Rank by:

- frequency
- severity
- community demand

Output:

Top 100 pain points.

For each pain point include:

- summary

- representative quotes

- where it was discussed

- existing solutions

- whether LPC Toolkit could solve it

Finally rank:

High ROI features
Medium ROI features
Low ROI features
```

---

# Research 03：Competitive Analysis

> ⭐⭐⭐⭐⭐

---

```text
I am building LPC Toolkit.

Research every existing tool related to LPC.

Include:

Universal LPC Generator

RapidLPC

LPC Studio

Godot plugins

Unity plugins

RPG Maker plugins

Desktop applications

CLI tools

Web generators

Compare:

Architecture

Features

UX

Performance

Export

License

Offline

Customization

Plugin support

Maintenance

Community

Popularity

Technology stack

Business model

Release activity

For each competitor:

Strengths

Weaknesses

Community perception

Missing features

Finally create:

Feature matrix

SWOT

Blue Ocean opportunities

Recommended positioning for LPC Toolkit
```

---

# Research 04：Developer Workflow

這份我超推薦。

很多產品都沒研究。

---

```text
Research how indie developers actually use LPC.

Focus on:

Godot

Unity

RPG Maker

GameMaker

Pixel artists

Solo developers

Find complete workflows.

Example:

Idea

↓

Character Generator

↓

Edit

↓

Animation

↓

Game Engine

↓

Git

↓

Release

Find:

Current workflows

Pain points

Manual steps

Repeated work

Export issues

Version control issues

Asset management issues

License tracking

Finally recommend:

How LPC Toolkit could simplify each workflow.
```

---

# Research 05：Release Strategy

這份就是：

我要怎麼發布。

---

```text
Research successful open source releases.

Focus on:

GitHub

OpenGameArt

itch.io

Reddit

Bluesky

Twitter

Indie game communities

Research:

Successful launches

Failed launches

Best timing

Best content

Best demos

Best screenshots

Best GIFs

Build in Public strategies

What developers like

What developers dislike

Finally produce:

Release roadmap

Launch checklist

Community engagement plan

Content calendar

Recommendations specifically for LPC Toolkit.
```

---

# Research 06：Commercial Strategy

這份先不要急。

等產品成熟。

---

```text
Research business models for open source developer tools.

Focus on:

Aseprite

Godot

Pixelorama

RapidLPC

Open source generators

Asset stores

Plugin marketplaces

Desktop software

Compare:

Open source

Paid

Dual license

Marketplace

Cloud

Subscription

Sponsor

Patreon

Premium edition

Evaluate which model would best fit LPC Toolkit.

Recommend:

Short term

Medium term

Long term business strategy.
```

---

# Research 07：Future Roadmap

這份最後。

等全部完成。

---

```text
Using all previous research,

Design a 2-year roadmap for LPC Toolkit.

Include:

Community priorities

Technical priorities

Open source priorities

Plugin ecosystem

AI integration

Desktop application

CLI

Marketplace

SDK

Commercial opportunities

Rank every feature by:

Community value

Implementation effort

Long-term strategic value

Generate:

Quarterly roadmap

Milestones

Risk analysis

Success metrics
```

---

# 我建議再增加一個「隱藏版」研究（我認為價值最高）

這份我甚至會排在 **Research 02 前面**。

## Research 00：**「Why would someone switch to LPC Toolkit?」**

這不是研究 LPC。

而是研究：

> **為什麼一個已經在用 Universal LPC Generator 的人，會願意改用你的工具？**

Prompt：

```text
I am creating a new open source project called LPC Toolkit.

Research this question:

Why would existing users leave the original Universal LPC Generator and switch to LPC Toolkit?

Analyze:

- switching costs
- habits
- missing features
- emotional attachment
- compatibility
- migration difficulty
- ecosystem lock-in

Identify:

Top 20 reasons people WOULD switch.

Top 20 reasons people WOULD NOT switch.

For each reason:

- supporting evidence
- community discussions
- possible mitigation

Finally propose:

A unique value proposition for LPC Toolkit.

Do NOT simply compare features.

Focus on user behavior and product positioning.
```

---

## 如果是我，我會按照下面的順序執行

1. **Research 00**：Why switch?（產品定位）
    
2. **Research 01**：Ecosystem（了解生態）
    
3. **Research 02**：Pain Points（找需求）
    
4. **Research 03**：Competitor（找差異化）
    
5. **Research 04**：Workflow（找真正的工作流程）
    
6. **Research 05**：Release Strategy（規劃發布）
    
7. **Research 06**：Commercial（評估商業模式）
    
8. **Research 07**：Roadmap（整合所有研究）
    

這樣完成後，你得到的不只是幾份研究報告，而是一整套有資料支持的產品策略，之後無論是 GitHub 發布、OpenGameArt、itch.io、Devlog，甚至未來是否推出付費版，都會有清楚的依據。

## Notes

## Possible Follow-up
