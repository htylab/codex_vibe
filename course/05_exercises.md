# 練習關卡

## Level 1：Domain 狀態機 + 測試（20-25 分鐘）
**目標**
- 完成床位狀態機（允許/禁止轉移）
- 測試覆蓋所有狀態轉移

**提示**
- 狀態與轉移規則請以 SPEC 為準
- 用 table-driven 測試可降低重工

**常見錯誤**
- 忘記覆蓋「禁止轉移」的測試
- 轉移規則與 SPEC 不一致

**驗證方式**
- `dotnet test`

---

## Level 2：API + 權限 + audit log + API 測試（20-25 分鐘）
**目標**
- POST /api/beds/{bedId}/status
- VIEWER -> 403
- 非法轉移 -> 400（error 含 from/to）
- 合法轉移 -> 200 + 狀態更新 + audit log 增加

**提示**
- header 預設 VIEWER
- X-User-Id 用於 audit
- 測試要涵蓋 403 / 400 / 200

**常見錯誤**
- 忘記把 from/to 寫進錯誤訊息
- audit log 沒有正確帶入 userId 或 reason

**驗證方式**
- `dotnet test`

---

## Level 3：Next.js /beds UI + audit 顯示 + 狀態更新（20-25 分鐘）
**目標**
- /beds 顯示 ward 下拉（5A/5B/ICU）
- 卡片 grid 顯示床位狀態
- 點卡片顯示最近 10 筆 audit
- NURSE 角色才能更新狀態（含 reason）

**提示**
- UI 更新成功後要 refresh audit
- status 更新要帶 header X-User-Role

**常見錯誤**
- UI 沒有顯示 audit
- 更新狀態後沒有重新載入清單

**驗證方式**
- `npm install`
- `npm run dev`
