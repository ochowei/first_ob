---
created: 2026-06-01 18:51
kind: project
project: game-asset-2026-2
tags:
in-progress: false
archived: true
priority: medium
reviewed: false
reviewed_at:
---

# game-asset-2026-2

## 📌 Context & Goals / 專案脈絡與目標

- **Core Objective:** 參考人家的 pixel art icon 的做法
- **~~Background:** 記錄背景脈絡、目前的系統狀態、或者觸發此需求的前置事件。

---


#### [[2026-05-09]]
- 完成下一階段準備
- 接下來是 i18n, theme change, 然後才是新的 icon
#### [[2026-05-08]]
- 實作了 spear
- 接下來想要先加上 i18n, theme change
- 然後市場調查跟擬定行銷計劃
```markdown

# 開新 session 前的 prep

## 1. 視覺驗證 spear(最重要,~10 min)

我整輪沒 browser 工具,所有 task 都靠 node smoke test 跟 mask count 驗證。**spec §11 列了 9 個 risk fallback,實作沒踩到任何一個自動測得出來**,但你眼睛掃過才知道。打開兩個頁面看:

- `index.html` → type=spear,size=32,連跑 ~10 個 random seed,size 切 16 再跑一輪
- `regression.html` → 看 16-seed spear grid。特別檢查:
  - **obsidian + WOOD shaft 對比**(risk #1)— obsidian metal 是 L=30 接近 outline,跟 wood 主色 #a87c4e 對比夠不夠
  - **trident 32 三 prong 之間斷縫**(risk #2)— 4-鄰居 outline 在 1 cell gap 處有沒有漏判
  - **shaft binding 看起來像「裂縫」還是「綁帶」**(risk #3)— 若像裂縫,WOOD.shadow 從 `#6a4020` 拉淺到 `#7a5028`
  - **trident 16 三 prong 是否糊成一條粗線**(risk #5)
  - **hooked 16 col 11 1 px hook 是否可讀**(risk #6)

有問題就 follow-up commit。沒問題就放心開新 session。

## 2. 加 `.gitignore` for `.claude/`

整 session 都看到 `Untracked: .claude/`,這是 Claude Code / superpowers 的 cache,不該追進 git。1 行 commit:

```bash
echo ".claude/" >> .gitignore
git add .gitignore && git commit -m "chore: ignore .claude/ (Claude Code session cache)"
```
```
```


# 新 session 第一個 prompt(可直接複製)

```
Icon Machine 專案,memory 已記錄完整 context(spear 已 ship 在 main,potion + sword + spear 三種 item type)。

這個 session 要做 i18n(國際化)。

開工前請先讀:
- memory(project_icon_machine.md / user_pixel_art_preferences.md / feedback_resolution_dependent_design.md)
- 看一眼 index.html 的 UI label 區段(目前都是 zh-Hant 寫死,例如「藥水 (potion)」「劍 (sword)」「長矛 (spear)」「下載 PNG」「重抽種子」等)
- 看一眼 main.js 看有沒有 user-facing string(seed placeholder、error message 之類)
- 看一眼 regression.html(這是內部工具,brainstorm 時討論要不要也 i18n)

然後按 superpowers 標準流程:brainstorm → write-plan → execute-plan(subagent-driven)。

Brainstorm 重點討論:
- 支援哪些語言(zh-Hant 一定有、en 一定有、ja/ko/zh-Hans 要嗎?)
- 怎麼切換(URL param ?lang=en / localStorage 記憶 / UI dropdown / 三個都做)
- 翻譯範圍:
  - UI label(button、placeholder、aria-label)— 一定要
  - item type 中文名稱(「藥水」「劍」「長矛」)— 要嗎?有些 RPG 圖示工具會故意保留中文當 flavor
  - metal/magical family 名稱(「steel/鋼」「fire/火焰」)— 翻不翻?regression 的 spec dump 要看到原文還是翻譯?
- 切換機制:動態(JS 即時換)還是頁面 reload?動態複雜但 UX 好
- string 表放哪:新增 `i18n.js`(內含 `STRINGS = { 'zh-Hant': {...}, 'en': {...} }` + `t(key)` 函式)?還是分檔(i18n/zh-Hant.js + i18n/en.js)?vanilla JS 無 build 環境下怎麼避免「忘記某語言漏 key」
- regression.html 是內部視覺迴歸工具,要不要也 i18n(我傾向不用,但你可以提)

不要重新發明 item-type 架構 — 那是 canvas 渲染層的事。i18n 是 UI 層,大概是「string table + 一個 t(key) 函式 + 在 DOM ready 時套上 + dropdown 觸發 reload(或動態 update)」這個 scope。

我有 superpowers,所以照標準流程走,不要急著寫 code。
```


```
Icon Machine 專案,memory 已記錄完整 context(spear 已 ship,i18n 已做完)。

這個 session 要做 dark/light theme。

開工前請先讀:
- memory(project_icon_machine.md 等)
- 看一眼 index.html 跟 regression.html 的 <style> 區段
- 看一眼前一輪 i18n 是怎麼加 settings infrastructure 的(theme 切換可能可以 reuse 同一套 localStorage / URL param / dropdown 機制)

然後按 superpowers 標準流程:brainstorm → write-plan → execute-plan(subagent-driven)。

Brainstorm 重點討論:
- 預設 theme(light / dark / 跟 OS `prefers-color-scheme` 走)
- 切換機制(獨立 toggle button / 跟 i18n 共用同一個 settings dropdown / URL param)
- theme 變數定義方式:
  - CSS custom properties(`--bg / --fg / --accent` + `body[data-theme]` 屬性)— 推薦,動態切換不需 reload
  - 兩套完整 stylesheet 切換 — 簡單但動態切換閃爍
- 範圍:
  - body bg / 文字色 / button / table border / h2 顏色(目前橘 #c46a00)— 一定要
  - **canvas 背景色**要不要跟著變?如果變,要保證 dark 背景上仍可讀:
    - obsidian metal 的 bladeMain 是 L=30 已經很暗,在黑底會 wash out
    - outline `HSL(h, 50, 12)` 在亮底是黑、在暗底會跟背景融合
    - 可能 fallback:dark theme 用 dark grey(`#2a2a32`)而非純黑,給 outline 留 contrast
  - 預覽放大區的 background(目前像 paper)— 跟 canvas bg 同步還是獨立?
- regression.html 也要 themed 嗎?(內部工具,可選擇不做)
- icon 本身不變色(palette 是 item-driven 的,跟 page theme 解耦)— 確認所有 family 在兩 theme 上都可讀

不要動 palette.js / potion.js / sword.js / spear.js 的渲染邏輯 — theme 是 page CSS 層的事,跟 canvas 內容互相獨立。

我有 superpowers,所以照標準流程走,不要急著寫 code。
```

```
Icon Machine 專案,memory 已記錄完整 context(potion + sword + spear 已 ship,i18n + theme 已做完)。

這個 session 要做新 item type。我在想 dagger / axe / shield 之中選一個 — brainstorm 開頭請先問我目標物品。

開工前請先讀:
- memory(project_icon_machine.md / user_pixel_art_preferences.md / feedback_resolution_dependent_design.md)
- **必讀**:`docs/superpowers/2026-05-08-drawspear-implementation-notes.md` — spear 的 SPEAR_ 命名規則、hooked V1→V2 A/B 比較流程、spec drift 處理 idiom。新 item 套同一套規則。
- **必讀**:`docs/superpowers/2026-05-07-drawsword-implementation-notes.md` — sword 的 v0/v1/v2/v3/v4 五版迭代故事,curved 在 32×32 的 resolution-dependent 教訓
- 看一眼 palette.js(WOOD_PALETTE / LEATHER_PALETTE / METAL_FAMILIES 已備齊,sampleSpearPalette wrapper 模式)
- 看一眼最相近現存武器的 .js:
  - dagger → 最像 sword(blade-based 武器)
  - axe → 較獨特(head 比例特殊,可能短 shaft)
  - shield → 跟其他都不同(沒有「武器主軸」概念,boss + body + rim 三段)

然後按 superpowers 標準流程:brainstorm → write-plan → execute-plan(subagent-driven)。

Brainstorm 重點討論(順序):
1. **目標物品定哪一個**(dagger / axe / shield / 其他)— 這題回答完才有後面
2. **部位分解**(每個物品都不同):
   - dagger:同 sword 4-part(blade / guard / grip / pommel)還是更精簡 3-part?
   - axe:head + haft + butt 3-part,head 是矩形不是 leaf
   - shield:boss(中心金屬凸)+ body(主面)+ rim(邊框)3-part
3. **Archetype 怎麼設**:
   - dagger:short-blade / curved kris / parrying main-gauche?
   - axe:single-head / double-head / pickaxe?
   - shield:round / kite / heater(歐洲三角)/ buckler 小圓?
4. **Palette**:reuse METAL / WOOD / LEATHER 即可?還是需要:
   - shield 可能加 wooden-shield-plank 或 painted-shield 主色?
   - dagger grip 可能 reuse LEATHER 直接 ok
5. **Mask enum 要新增什麼**(parts 對應的 enum value;盡量少新增,reuse 'head' / 'shaft' / 'butt' 等通用名)
6. **32×32 vs 16×16 解析度權衡**(spear 教訓:14 行限制下細節要 collapse 哪些)
7. **整體方向**:
   - dagger 大概垂直
   - axe 大概垂直 + 短 shaft 比例
   - shield 大概是「畫一個圓 / 三角」而非「直立武器」— 整個 layout 思路不同
8. **第三個 metal-using item 出現**(若選 dagger / axe):是時候做 spec §12 defer 兩輪的 `sampleMetalPalette` refactor — sword + spear + dagger 共用一個 sampler,各自做欄位 rename。Brainstorm 階段就決定要不要做。

不要重新發明架構 — 直接套 sample→render 兩階段、共用 palette / pixel-utils。新 file-internal const 一律加 item-type 前綴(per spear 教訓:寧可前綴過頭也不要 silent override),新 shape function 一律加 item-type 中綴避撞 sword.js / spear.js 既有同名 function。

我有 superpowers,所以照標準流程走,不要急著寫 code。
```

#### [[2026-05-07]]
- 決定重新開始 game-asset-2026-2, 參考 https://bmaczero.itch.io/icon-machine
- 先設計一個產品，再做市場調查，跟擬定行銷計劃
下一個 prompt
```
這個專案是 Icon Machine,memory 裡有完整 context,先讀 memory 再開始。

Potion 跟 Sword 都做完上 git 了,我想接著做 <<drawSpear>>。

開工前請先讀:
- docs/superpowers/2026-05-07-drawsword-implementation-notes.md
  (必讀。記錄 sword 五版迭代、踩過的命名 collision 坑、以及
  「32 解析度不能直接抄 reference layout」這個教訓)
- docs/superpowers/specs/2026-05-07-drawsword-design.md
  (sword 的 spec→render 兩階段架構 reference)
- 看一眼 palette.js / pixel-utils.js / sword.js
  (palette.js 已有 METAL_FAMILIES + LEATHER_PALETTE 可共用;
  sword.js 是最新的 item type,pattern 最參考價值)

然後按 superpowers 標準流程:brainstorm → write-plan → execute-plan
(subagent-driven)。

Brainstorm 時直接沿用 potion / sword 的架構 pattern
(sampleXxxSpec + renderXxxSpec32/16 + drawXxx),不要重新發明。

重點討論的是:
- 矛的部位分解(head / shaft / butt 三段?還是四段含 cross-piece?)
  跟劍很不一樣 — shaft 是主體 (~長 24 列?)、head 是上端短突起、
  比例完全反過來
- Archetype 怎麼設(直矛 / 三叉 / 鉤矛 / 帶 cross-piece 的 partisan?)
- Palette:metal 部分(矛頭)套既有 METAL_FAMILIES;shaft 木質
  考慮新色族還是 reuse LEATHER_PALETTE / CORK_PALETTE?
- Mask enum 要新增什麼(spearhead / shaft / butt / 可選 cross-piece)
- 32 與 16 的細節取捨 — 矛比例細長,16 高度 14 列要塞長 shaft 會
  跟 sword 完全不同
- 整體方向:**直立**還是**沿對角線**?(從 sword 學到 32 解析度
  不能直接抄高解析度 reference 的「中段彎」設計)

新 file-internal const 一律加 `SPEAR_` prefix
(避免跟 potion.js / sword.js 同名 const 撞名 → SyntaxError,
 sword 踩過這個坑)。

我有 superpowers,所以照標準流程走,不要急著寫 code。
```


