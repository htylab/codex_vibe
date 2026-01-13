# 學員講義（可列印）

## 1. 什麼是 Vibe Coding
- **定義**：以「規格 + 任務 + 驗證」為核心，透過 AI agent 輔助開發的工程流程。
- **重點**：不是 prompt 魔法，而是「工程治理 + 可驗收」。
- **預期效益**：縮短 lead time、降低重工、提升測試覆蓋。

## 2. 標準工作流（VS + Terminal + Codex CLI）
1. **讀 SPEC**：對齊需求、狀態、API 與測試要求
2. **拆任務**：切成小步可驗收的變更
3. **產生變更**：Codex CLI 輔助產生初稿
4. **驗證**：用 Terminal 跑測試、lint、API 測試
5. **Review**：依 checklist 驗收、修正

## 3. SPEC 模板（可複製）
```md
# SPEC - <功能名稱>

## 背景與目標
- 目標：
- 不在範圍：

## 功能需求
- [ ] 

## 狀態機 / 流程
- 狀態：
- 允許轉移：

## API
- GET /...
- POST /...
  - headers
  - 例外處理

## 測試最低要求
- 單元測試：
- 整合測試：

## 驗證指令
- dotnet test
- ...
```

## 4. AGENTS.md 模板（可複製）
```md
# Agent 工作規範

## 分層與邊界
- Domain 不可依賴 API/UI
- API 只調用 Application/Domain
- UI 僅透過 API

## 命名與結構
- 檔案/資料夾命名規則

## DoD
- 測試通過
- 無敏感資料
- 變更最小化

## 安全紅線
- 不可存取真實個資
- 不可移除既有安全機制
```

## 5. Review Checklist（摘要）
- 規格符合度
- 測試覆蓋
- API 錯誤碼
- 授權與審計
- 風險點與回滾

## 6. 兩週導入策略（摘要）
- **第 1 週**：選小範圍功能、訂 SPEC 與 DoD
- **第 2 週**：評估 KPI（lead time、review 回合、缺陷率）

## 7. Bed Board 範例
- 狀態：EMPTY、CLEANING、OCCUPIED、TRANSFER_PENDING
- API：GET /api/beds?ward=5A
- POST /api/beds/{bedId}/status
  - X-User-Role (VIEWER/NURSE)
  - X-User-Id (for audit)

## 8. 練習題（概述）
- Level 1：Domain 狀態機 + 測試
- Level 2：API + 權限 + audit log + API 測試
- Level 3：Next.js /beds UI + audit 顯示 + 狀態更新
