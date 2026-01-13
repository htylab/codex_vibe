# Demo 專案開發規範（Bed Board）

## 分層與邊界
- Domain 層：狀態機與規則，不可依賴 API 或 UI
- Application/API 層：只調用 Domain，不可直接操作 UI
- UI 層：僅透過 API 互動

## 命名與結構
- C# 檔案使用 PascalCase
- 測試檔案以 `*Tests.cs` 結尾
- Next.js 元件以 PascalCase

## DoD（Definition of Done）
- 規格符合 SPEC.md
- 測試通過（dotnet test / npm test 若有）
- 無敏感資料或真實個資
- 變更範圍最小化

## 安全紅線
- 不可移除授權檢查
- 不可寫入真實個資
- 不可跳過 audit log
