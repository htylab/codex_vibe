# 工作坊指南（分組流程）

## 分組與角色
- 10 組 × 3 人
- 角色：Driver / Navigator / Reviewer
- 每 20 分鐘輪換（時間到強制換）

## 節奏總覽（建議 70~80 分鐘）
1. Level 1（20-25 分鐘）
2. Level 2（20-25 分鐘）
3. Level 3（20-25 分鐘）
4. 結果回顧（10 分鐘）

---

## Level 1：Domain 狀態機 + 測試
**任務**
- 建立床位狀態機（允許/禁止轉移）
- 覆蓋所有狀態轉移測試

**完成定義（DoD）**
- 所有允許轉移皆通過
- 所有禁止轉移皆回傳 false 或拋出明確錯誤
- `dotnet test` 全綠

**驗證指令**
- `dotnet test`

**提交方式**
- Git commit：`完成 Level 1 狀態機與測試`

---

## Level 2：API + 權限 + Audit
**任務**
- 建立 POST /api/beds/{bedId}/status
- VIEWER 呼叫 -> 403
- 非法轉移 -> 400（error 含 from/to）
- 每次更新寫入 audit log

**完成定義（DoD）**
- API 測試符合規格
- Audit log 內容完整
- `dotnet test` 全綠

**驗證指令**
- `dotnet test`
- `dotnet run --project demo/HospitalApi`

**提交方式**
- Git commit：`完成 Level 2 API 與 audit`

---

## Level 3：Next.js /beds UI
**任務**
- /beds 顯示 ward 下拉（5A/5B/ICU）
- 以卡片 grid 顯示床位
- 點卡片顯示最近 10 筆 audit
- NURSE 才能更新狀態（含 reason）

**完成定義（DoD）**
- UI 可操作
- 狀態更新成功寫入 audit

**驗證指令**
- `npm install`
- `npm run dev`

**提交方式**
- Git commit：`完成 Level 3 /beds UI`

---

## 角色指引（每輪 20 分鐘）
- Driver：負責操作 VS/Terminal
- Navigator：對照 SPEC/AGENTS，拆解任務
- Reviewer：依 checklist 驗收，抓風險
