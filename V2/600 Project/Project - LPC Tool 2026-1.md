---
created: 2026-06-01 18:55
kind: project
project: LPC Tool 2026-1
tags:
in-progress: true
archived: false
priority: medium
reviewed: false
reviewed_at:
source: https://github.com/ochowei/lpc-toolkit-2026-1
---

# LPC Tool 2026-1

## 📌 Context & Goals / 專案脈絡與目標

- **Core Objective:** 說明此項子任務/模組開發在 [LPC Tool 2026-1] 中的核心目的與預期成效。
- **Background:** 記錄背景脈絡、目前的系統狀態、或者觸發此需求的前置事件。

---

### 產品




LPC 效能優化方案
https://gemini.google.com/share/e645d073c79d

LPC 可靠性 Solution
https://gemini.google.com/share/7d7ca7fcba44

---
#### Reference

- [title:: LPC 原版應用]
  [url:: [link](https://liberatedpixelcup.github.io/Universal-LPC-Spritesheet-Character-Generator/)]
  [category:: reference]
  [tags:: tool]
  [comment:: 用來比對舊版]
  [create:: [[2026-05-30]]]

- [title:: LPC原版文件]
  [url:: [link](https://lpc.opengameart.org/static/LPC-Style-Guide/build/index.html#)]
  [category:: reference]
  [tags:: article]
  [comment::  美術創作規則]
  [create:: [[2026-05-30]]]

- [title:: opengameart 遊戲資產 hub]
  [url:: [link](https://opengameart.org/content/liberated-pixel-cup-0)]
  [category:: reference]
  [tags:: tool]
  [comment:: LPC 社群]
  [create:: [[2026-05-30]]]

- [title:: RapicLPC]
  [url:: [link](https://opengameart.org/content/liberated-pixel-cup-0)]
  [category:: reference]
  [tags:: tool]
  [comment:: 競品分析]
  [create:: [[2026-05-30]]]


#### Roadmap
- 社群分析，相關作品歷史分析
- 產品規劃
	- ChatGPT 專案(風險評估與產品定位)
		https://chatgpt.com/g/g-p-6a19990cecd881919dfe92ef4b223a13-lpc-jiao-se-chan-sheng-xiao-gong-ju/project 
- 開發
	- 確保舊功能都有正確的被包涵在 toolkit 裡面

### Log

[[2026-06-02]]

> 使用 agy 先把比對的範圍裁切到 spritesheet 左上角的第一張圖 , 然後使用最原始的 layers, `#sex=male&body=Body_Color_light&head=Human_Male_light&expression=Neutral_light`,
> 找出一些問題並修復, 所以 e2e parity 測試變成 5+1(指定)+1(minimal) = 7 個, 此時在 local 端用本地 server 開啟 toolkit 跟 upstream 來測試都沒有問題。不過在 vercel preview 的版本跟 upstream 用 random 比對, 還是會出現動畫 render 不完全的問題。

> 為 packages/core, packages/web 都加了 comment, 然後讓 codex 找出 toolkit 跟 upstream 不一致的地方, 並且寫在 github issue 上面。雖然只加了 comment, 但是 parity check 多了一個 fail, 所以只有成功 6 個。手動在 toolkit 跟 upstream 上面查看，反而覺得很正常，所以成功失敗可能不是一定的，就看圖層有沒有抓到。



[[2026-06-01]]

> 原本 codex 是在 fix-random-upstream-parity-mismatches 工作的，但是因為額度用完了，先保留 branch, 並把臨時的工作檔案 commit 到 fix-random-upstream-parity-mismatches-temp，從 origin/main 開始用 antigravity 試試看

> [[Exploration - Antigravity 2.0 上安裝並套用 Superpowers]]
> 透過 gemini 的舊 plugin 先裝好，另外有一個 chatgpt 的討論 [superpower on antigravity](https://chatgpt.com/share/6a1d9a29-0c2c-83a5-b80f-3c7fc39e8281)

> 從 main 開始切一個新的 worktree
---
2026-05-29

Bug

https://lpc-toolkit-2026-1-web.vercel.app/#sex=male&body=Body_Color&head=Human_Female&eyes=Cyclops_Eyes&eyebrows=Thin_Eyebrows&nose=Large_nose&ears=Big_ears&ears_inner=Side_Wolf_Ears_Skintone&beard=Medium_Beard&expression=Happy_Alt&expression_crying=Tears&bandana=Bordered_Bandana&bandana_overlay=Skull_Bandana_Overlay&updo=High_Bun&hairextr=Right_Long_Straight&hairtie_rune=Hair_Tie_Rune&facial_mask=Plain_Mask&facial_right=Right_Monocle&facial_right_trim=Right_Monocle_Frame_Color&visor=Narrow_slit_visor&arms=Armour&clothes=Shortsleeve&overalls=Overalls&armour=Legion&chainmail=Chainmail&bracers=Bracers&bauldron=Bauldron&hat=Hood&jacket=Frock_coat&jacket_collar=Frock_collar&jacket_trim=Frock_coat_lapel&vest=Vest&hat_buckle=Wizard_Hat_Buckle&hat_overlay=Bicorne_Athwart_Skull&shoes_toe=Plated_Toe&cape_trim=Cape_Trim&quiver=Quiver&charm=Pearl_Gem&bandages=Bandages&cargo=Wood&gloves=Gloves&necklace=Simple_Necklace&sash=Obi&weapon_magic_crystal=Crystal&shield_paint=Revised_Heater_Shield_Paint&wings=Bat_Wings&wings_dots=Monarch_Wings_Dots&wings_edge=Monarch_Wings_Edge&fins=Fin&furry_ears=Cat_Ears&furry_ears_skin=Cat_Ears_Skintone&tail=Wolf_Tail

跟 

https://liberatedpixelcup.github.io/Universal-LPC-Spritesheet-Character-Generator/#sex=male&body=Body_Color_light&head=Human_Female_light&eyes=Cyclops_Eyes_cyclops&eyebrows=Thin_Eyebrows_orange&nose=Large_nose_light&ears=Big_ears_light&ears_inner=Side_Wolf_Ears_Skintone_light&beard=Medium_Beard_orange&expression=Happy_Alt_light&expression_crying=Tears_blue&bandana=Bordered_Bandana_brown&bandana_overlay=Skull_Bandana_Overlay_brown&updo=High_Bun_orange&hairextr=Right_Long_Straight_orange&hairtie_rune=Hair_Tie_Rune_brown&facial_mask=Plain_Mask_dark&facial_right=Right_Monocle_steel&facial_right_trim=Right_Monocle_Frame_Color_black&visor=Narrow_slit_visor_ceramic&arms=Armour_ceramic&clothes=Shortsleeve_brown&overalls=Overalls_leather&armour=Legion_ceramic&chainmail=Chainmail_ceramic&bracers=Bracers_ceramic&bauldron=Bauldron_brown&hat=Hood_brown&jacket=Frock_coat_black&jacket_collar=Frock_collar_bronze&jacket_trim=Frock_coat_lapel_bronze&vest=Vest_gray%20striped&hat_buckle=Wizard_Hat_Buckle_steel&hat_overlay=Bicorne_Athwart_Skull_black&shoes_toe=Plated_Toe_steel&cape_trim=Cape_Trim_black&quiver=Quiver_quiver&charm=Pearl_Gem_blue&bandages=Bandages_white&cargo=Wood_3_logs&gloves=Gloves_ceramic&necklace=Simple_Necklace_steel&sash=Obi_black&weapon_magic_crystal=Crystal_blue&shield_paint=Revised_Heater_Shield_Paint_aegean&wings=Bat_Wings_blonde&wings_dots=Monarch_Wings_Dots_amber&wings_edge=Monarch_Wings_Edge_amber&fins=Fin_light&furry_ears=Cat_Ears_blonde&furry_ears_skin=Cat_Ears_Skintone_light&tail=Wolf_Tail_blonde

的 hash 部分一樣，但是 render 出來的圖差很多

Survey LPC 小工具發佈的風險 ^51ce81

Survey LPC 角色設計的規格

---
