# 講師逐字講稿（口語化，可直接照念）

> 主題：Vibe Coding 導入：Visual Studio Community + Terminal + Codex CLI（ASP.NET Core 為主，前端 Next.js）
> 對象：30 位資深工程師（熟 ASP.NET Core，未接觸 vibe coding / agentic coding）
> 時長：建議 3.5~4 小時（含工作坊）

## 0:00-0:10 開場與目標對齊
**重點**
- 今天要做的事：把「vibe coding」變成可落地的團隊工作流
- 不只是「讓 AI 寫程式」，而是「工程化導入」：流程、分工、治理
- 以 Bed Board（住院病床看板）作完整 demo

**示範操作**
- 打開投影片第 1 頁與 Bed Board 需求簡述
- 顯示 demo repo 結構（course/、demo/）

**問學員的問題**
- 目前團隊最痛的地方是：需求變更、測試不足、還是 review 壓力？

**可能追問與回答**
- Q：AI 會不會取代我們？
  - A：不會。它是放大器，重點是把工程規範落地，讓人做判斷、AI 做加速。

## 0:10-0:25 什麼是 Vibe Coding / Agentic Coding
**重點**
- 定義：用 AI agent 以「規格 + 任務 + 驗證」驅動開發
- 不是 prompt 亂寫，是「像在帶一個新人」：有規格、有驗收
- 關鍵：SPEC、AGENTS.md、Review Checklist、DoD

**示範操作**
- 打開 SPEC.md 範例（demo/SPEC.md）
- 打開 AGENTS.md 範例（demo/AGENTS.md）

**問學員的問題**
- 你們的團隊現在有沒有「對齊規格」與「驗收方式」的統一格式？

**可能追問與回答**
- Q：這不就是把需求文檔寫詳細嗎？
  - A：對，但加上「可被 agent 執行」的結構化欄位，例如驗證指令與 DoD。

## 0:25-0:40 角色與分工：Driver / Navigator / Reviewer
**重點**
- Driver 操作 IDE/Terminal
- Navigator 引導拆解任務，控管範圍
- Reviewer 對照 DoD、風險、安全紅線

**示範操作**
- 在投影片中秀 3 角色卡
- 強調 20 分鐘輪換節奏

**問學員的問題**
- 如果你是 Reviewer，你最想抓的是什麼？

**可能追問與回答**
- Q：Reviewer 會不會變成卡住進度？
  - A：不會，因為 Reviewer 只要對照 checklist，快速過濾風險。

## 0:40-1:05 規格到任務：SPEC、AGENTS.md、DoD
**重點**
- SPEC：功能需求、流程、API、狀態機、測試最低要求
- AGENTS.md：分層規則、命名、紅線
- DoD：可以「驗收」的條件

**示範操作**
- 展示 SPEC.md 的 Bed Board 狀態機與 API 規格
- 展示 review checklist 範本

**問學員的問題**
- 你們目前 DoD 有沒有包含「測試、文件、回滾」？

**可能追問與回答**
- Q：SPEC 寫太多很慢？
  - A：只寫「可以驗收的」部分，避免模糊需求造成返工。

## 1:05-1:30 Vibe Coding 工作流（VS + Terminal + Codex CLI）
**重點**
- Visual Studio 做方案管理、除錯
- Terminal 做指令、測試、Git
- Codex CLI 做任務驅動與文件生成

**示範操作**
- 開 VS Community：打開 demo/HospitalApi
- Terminal：`dotnet test` / `dotnet run`
- 示範「需求 -> 任務拆解 -> 產生 PR 變更」的流程

**問學員的問題**
- 你們團隊現在最常在哪個環節卡住？

**可能追問與回答**
- Q：為什麼不能只在 IDE 裡做？
  - A：Terminal 對 CI/CD 與測試更一致，方便複製到 pipeline。

## 1:30-2:00 Bed Board Demo（概觀）
**重點**
- Domain 狀態機 -> API -> UI
- 每一步都要有測試與驗證
- 審核重點：授權、audit log、狀態轉移

**示範操作**
- 開啟 `/demo/README.md` 看 roadmap
- 展示 API 路由與 Swagger

**問學員的問題**
- 哪一層最容易出問題？Domain / API / UI？

**可能追問與回答**
- Q：audit log 為什麼重要？
  - A：醫療場景要可追溯，避免責任不清。

## 2:00-2:10 休息

## 2:10-3:20 工作坊分組實作（10 組 × 3 人）
**重點**
- 每 20 分鐘輪換角色
- 每關卡都有清楚的 DoD 與驗證指令

**示範操作**
- 展示 workshop guide
- 示範如何用 checklist 進行 review

**問學員的問題**
- 你們覺得哪個角色最難？

**可能追問與回答**
- Q：AI 產生的程式碼要不要全改？
  - A：不必，先對齊需求與測試，確保可驗收。

## 3:20-3:40 成果回顧與教訓
**重點**
- 分享每組遇到的阻礙
- 針對風險控管與回滾策略做討論

**示範操作**
- 收集問題與踩雷點

**問學員的問題**
- 如果要導入兩週試點，你覺得最先改哪一塊流程？

**可能追問與回答**
- Q：治理會不會太重？
  - A：一開始就用「兩週試點」，以 KPI 驗證收益與成本。

## 3:40-4:00 結語與行動方案
**重點**
- 提供兩週導入 playbook
- 建議 KPI 與 PR 模板

**示範操作**
- 打開 rollout playbook

**問學員的問題**
- 你們回去後第一件事要做什麼？

**可能追問與回答**
- Q：管理層要看什麼？
  - A：Lead time、缺陷率、review 回合數、測試覆蓋率。
