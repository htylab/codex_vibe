# 投影片逐頁大綱

## 1. 開場：為什麼是 Vibe Coding？
- 今天要解決的痛點
- 不是「讓 AI 寫程式」，而是「工程化導入」
- 目標：流程、分工、治理
- Demo：Bed Board
- 講者備註：先建立共識與價值

## 2. 定義與核心概念
- Vibe Coding / Agentic Coding 定義
- 規格驅動（SPEC）
- 行為約束（AGENTS.md）
- 可驗收的 DoD
- 講者備註：強調「可驗收」

## 3. 風險與責任
- 安全與合規責任仍在團隊
- 錯誤輸出可被放大
- 需要治理：review checklist
- 講者備註：先談風險，再談速度

## 4. 角色分工
- Driver：操作、合併、提交
- Navigator：拆解、控管範圍
- Reviewer：對照 DoD、抓風險
- 20 分鐘輪換
- 講者備註：像 Pair/Mob programming

## 5. 工作流全景
- Visual Studio：方案、偵錯、依賴
- Terminal：測試、Git、CI 接軌
- Codex CLI：任務生成與文件
- 講者備註：三件事協作

## 6. SPEC 範本重點
- 需求清單
- 狀態機與流程
- API 與錯誤碼
- 測試最低要求
- 講者備註：示範 Bed Board SPEC

## 7. AGENTS.md 範本重點
- 分層規則
- 命名規範
- 安全紅線
- DoD 最低標準
- 講者備註：Agent 的「工作守則」

## 8. Review Checklist
- 規格符合度
- 測試覆蓋
- 授權/審計
- 風險點
- 講者備註：review 應該可快速完成

## 9. Bed Board 架構
- Domain 狀態機
- API + Audit log
- Next.js /beds UI
- 講者備註：三層分開驗收

## 10. Demo Flow（高層）
- 需求 -> 任務拆解
- 產生變更
- 執行驗證
- 講者備註：示範 VS + Terminal

## 11. Demo：Domain 狀態機
- 允許/禁止轉移
- 單元測試
- 講者備註：風險在規則錯誤

## 12. Demo：API + Audit
- 權限（VIEWER/NURSE）
- 400/403 規則
- audit log
- 講者備註：追溯與責任

## 13. Demo：Next.js UI
- Ward 下拉
- 床位卡片
- Audit 顯示
- 狀態更新
- 講者備註：UI 仍需守規格

## 14. 工作坊規則
- 10 組 × 3 人
- 20 分鐘輪換
- 每段驗收
- 講者備註：角色輪換避免偏差

## 15. Level 1 任務
- Domain 狀態機 + 測試
- DoD：轉移規則全覆蓋
- 講者備註：先守規則

## 16. Level 2 任務
- API + 權限 + Audit
- DoD：403/400/200 測試
- 講者備註：對照規格

## 17. Level 3 任務
- Next.js /beds UI
- DoD：可視化 + 更新
- 講者備註：UI 驗證

## 18. 兩週試點策略
- 範圍選擇
- KPI
- 回滾策略
- 講者備註：小步試點

## 19. PR 模板與治理
- AI 參與範圍
- 驗證指令
- 風險點
- 回滾方式
- 講者備註：留下稽核線索

## 20. 收尾
- 立即行動
- Q&A
- 講者備註：鼓勵嘗試
