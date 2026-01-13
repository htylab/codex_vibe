# 部門導入 Playbook（兩週試點）

## 目標
- 建立可驗收的 Vibe Coding 流程
- 以 KPI 驗證效益與風險

## 兩週試點路線

### 第 1 週：建立基礎與小範圍試點
- 選定單一模組或功能
- 撰寫 SPEC、AGENTS.md、Review Checklist
- 設定 DoD 與驗證指令

### 第 2 週：擴大與評估
- 擴展到相鄰功能或 API
- 追蹤 KPI 與 review 回合
- 整理風險與回滾策略

## PR 模板（含 AI 參與範圍）
```md
# PR Summary
- 變更概要：
- AI 參與範圍：
- 風險點：
- 回滾方式：

## 驗證指令
- dotnet test
- ...

## 備註
- SPEC 連結：
```

## KPI 建議
- Lead time
- Review 回合數
- 缺陷率
- 測試覆蓋率
