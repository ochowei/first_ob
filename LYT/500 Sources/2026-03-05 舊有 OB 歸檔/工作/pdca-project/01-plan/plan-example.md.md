---
record_time: 2025-08-21 17:09
source: 舊有 OB
---

# 📝 Plan & Roadmap

本檔案整合 **Goals（長期目標）**、**Roadmap（中期目標/里程碑）** 與 **TODOs（短期任務）**。  
- **Goals**：專案的長期願景與成果指標  
- **Roadmap**：中期目標或里程碑，對應到 Goals  
- **TODOs**：短期任務，掛載到 Roadmap

---

## 🎯 Goals（長期目標）

| ID    | Title                     | Success Metrics    | Due        | Status        | Notes                 |     |
| ----- | ------------------------- | ------------------ | ---------- | ------------- | --------------------- | --- |
| G-001 | 跨平台分享插件：Facebook → Notion | MVP 上線 & 100 位活躍用戶 | 2025-10-31 | ⏳ In-Progress | 核心價值是降低分享摩擦，專注穩定性與易用性 |     |

---

## 🗺️ Roadmap（中期目標 / 里程碑）

| ID           | Title                  | Due        | Status       | Related Goals | Depends On    | Deliverables                 | Risk  | Notes                          |
|--------------|------------------------|------------|--------------|---------------|---------------|------------------------------|-------|-------------------------------|
| M-2025-08-01 | 完成 MVP（Chrome/Firefox 基本流程） | 2025-08-31 | ⏳ In-Progress | G-001         | -             | 安裝流程、基本分享到 Notion   | ⚠️ 中  | Firefox API 相容性需驗證 |
| M-2025-09-01 | 內部封測 & Edge 測試   | 2025-09-20 | 📅 Planned    | G-001         | M-2025-08-01  | Edge 偵錯、封測回饋          | ⚠️ 中  | -                             |
| M-2025-10-01 | 上架流程與最終優化     | 2025-10-15 | 📅 Planned    | G-001         | M-2025-09-01  | 商店素材、錯誤追蹤           | 🟢 低  | -                             |

---

## ✅ TODOs（短期任務）

### Milestone: M-2025-08-01

| ID           | Title                           | Status       | Priority | Estimate | Due        | Links | Notes                                 |
|--------------|---------------------------------|--------------|----------|----------|------------|-------|---------------------------------------|
| T-2025-08-001 | 完成 Notion OAuth 流程與 Token 儲存 | ✅ Done      | 🔥 High  | 4h       | 2025-08-20 | -     | -                                     |
| T-2025-08-002 | Firefox API 相容性：訊息傳遞與權限 | 🔄 Doing     | 🔥 High  | 1d       | 2025-08-23 | -     | 需抽象封裝 browser.* API 差異         |
| T-2025-08-003 | 分享面板 UX 草圖與文案           | ⏳ Todo      | ⭐ Medium | 4h       | 2025-08-24 | -     | -                                     |

### Milestone: M-2025-09-01

| ID           | Title                    | Status    | Priority | Estimate | Due        | Links | Notes |
|--------------|--------------------------|-----------|----------|----------|------------|-------|-------|
| T-2025-08-004 | Edge 初步打包與 sideload 測試 | ⏳ Todo  | ⭐ Medium | 4h       | 2025-09-05 | -     | -     |

---

## 🔗 用法建議
- 在 **Commit/PR/日誌** 中引用：`refs: M-2025-08-01, T-2025-08-002`  
- 每週檢討時更新：Roadmap 的 `Status / Risk` 與 TODO 的 `Status`  
- 若目標需調整：修改 Goals/Roadmap，並在 `.pdca-project/04_Act/adjustments_YYYY-MM.md` 紀錄原因  
