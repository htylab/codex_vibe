# Bed Board 功能規格

## 背景與目標
- 建立住院病床看板（Bed Board）
- 提供狀態管理與審計追蹤

## 狀態定義
- EMPTY
- CLEANING
- OCCUPIED
- TRANSFER_PENDING

## 允許轉移
- EMPTY -> OCCUPIED
- OCCUPIED -> TRANSFER_PENDING
- TRANSFER_PENDING -> CLEANING
- OCCUPIED -> CLEANING
- CLEANING -> EMPTY

## API
### GET /api/beds?ward=5A
- 回傳指定 ward 的床位清單

### POST /api/beds/{bedId}/status
- Header：
  - X-User-Role (VIEWER/NURSE)，預設 VIEWER
  - X-User-Id（for audit）
- 行為：
  - VIEWER 呼叫 -> 403
  - 非法轉移 -> 400，error 訊息包含 from/to
  - 合法轉移 -> 200
- 成功更新必寫 audit log

### GET /api/beds/{bedId}/audit?limit=50
- 回傳該床位最近 audit

## 前端 /beds
- Ward 下拉（5A/5B/ICU）
- 卡片 grid 顯示床位
- 點卡片顯示最近 10 筆 audit
- NURSE 才能更新狀態（含 reason）

## 測試最低要求
### Domain 狀態機測試
- 覆蓋所有允許/禁止轉移

### API 整合測試
- VIEWER POST status -> 403
- 非法轉移 -> 400（含 from/to）
- 合法轉移 -> 200 + bed 狀態更新 + audit log 增加

## 資料限制
- 不得包含任何真實個資或敏感資訊
