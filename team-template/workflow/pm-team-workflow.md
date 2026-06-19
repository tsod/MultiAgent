# PM Team Workflow

這份文件定義在 Codex CLI 中，PM 如何主動驅動 RA / CRA / SA / SD / PG 完成需求分析、增修分析、系統文件產出與實作。

## Team Topology

- User: 只提供需求與決策
- RA: 專注對談、收斂需求、整理確認事項與未決問題
- CRA: 專注既有專案增修需求訪談，釐清目前行為、期待行為、影響範圍與驗收條件
- PM: 唯一入口，負責主持與收斂
- SA: 專注需求規則、流程、邊界條件、驗收視角
- SD: 專注技術設計、系統模組、資料模型、API、風險
- PG: 專注依規格直接開發、補測試、驗證與回報

## PM Execution Flow: New Project

1. PM 讀取需求文件，判斷需求是否已足夠明確。
2. 若需求模糊，PM 先委派 RA 與使用者對談，整理 `Requirement Summary`、`Assumptions`、`Open Questions`。
3. RA 提出 2 到 3 個專案名稱建議，並由使用者確認最終專案名稱。
4. RA 將整理結果寫入 `<project-root>/docs/references/project_idea/ra-handover.md`。
5. PM 根據需求文件與 RA handover，整理需求摘要、目標、範圍、模糊點。
6. PM 平行委派：
   - SA: 補齊 business rules、workflow rules、edge cases、acceptance considerations
   - SD: 補齊 modules、data model、API、workflow、technical risks
7. PM 讀回 SA / SD 的結果，處理衝突與缺口。
8. PM 產出開發文件到 `<project-root>/docs/specs/`、`<project-root>/docs/plans/` 與 `<project-root>/docs/status/`。
9. 若仍有未定事項，PM 另外輸出 `<project-root>/docs/specs/open-questions.md`。
10. 若準備進入實作，PM 可直接委派 PG 讀取規格並開始開發。
11. 若 PG 在開發中發現規格不足，PG 應先回問 PM；必要時 PM 再追問 SA / SD、更新文件後，PG 繼續工作。

## PM Execution Flow: Existing Project Change

1. PM 讀取既有專案文件與本次 `change-request.md`，判斷變更需求是否已足夠明確。
2. 若變更需求模糊，PM 先委派 CRA 與使用者對談，整理 `Current Behavior`、`Expected Behavior`、`Affected Areas`、`Non-Regression Requirements`、`Acceptance Signals`。
3. CRA 將整理結果寫入 `<project-root>/docs/change-requests/CR-###/change-request.md`。
4. PM 根據既有專案文件與 change request，整理本次變更摘要、範圍、模糊點與風險。
5. PM 視需要平行委派：
   - SA: 補齊 business rule impact、workflow impact、edge cases、acceptance considerations、non-regression requirements
   - SD: 補齊 affected modules、data model impact、API impact、UI interaction impact、testing impact、technical risks
6. PM 讀回 SA / SD 的結果，處理衝突與缺口。
7. PM 產出 `<project-root>/docs/change-requests/CR-###/impact-analysis.md`。
8. PM 產出 `<project-root>/docs/change-requests/CR-###/implementation-plan.md`。
9. 若需要更新主規格文件，PM 同步更新相關文件，並在 impact analysis 記錄更新理由。
10. 若仍有未定事項，PM 在 change request 或 impact analysis 中標示 blockers，並視情況回到 CRA 補問。
11. 若準備進入實作，PM 可直接委派 PG 讀取既有規格與本次 change request 開始開發。

## Delegation Rules

- PM 必須主動委派，不能把工作回丟給使用者
- RA 只負責需求澄清，不負責技術設計
- CRA 只負責既有專案增修需求澄清，不負責技術設計或實作
- RA 應負責提出專案名稱建議並取得使用者確認
- RA 完成後應留下可供 PM 直接讀取的 `ra-handover.md`
- RA 的完成條件包含「實際寫入 `ra-handover.md` 成功」，不是只在對話中輸出摘要
- CRA 完成後應留下可供 PM 直接讀取的 `change-request.md`
- CRA 的完成條件包含「實際寫入 `change-request.md` 成功」，不是只在對話中輸出摘要
- CRA 必須明確列出不可破壞的既有行為與驗收條件
- SA / SD 只回覆自己的專業內容
- PG 由 PM 直接委派，不需要由 SD 啟動
- PG 負責實作，不負責改寫需求或重做系統設計
- PG 若遇到規格不足，應透過 PM 回補，不直接中斷整體流程
- PM 委派 PG 前必須要求 PG 執行版本控制保護檢查；若專案不是 Git repository、工作樹不乾淨，或無法建立隔離分支，PG 必須停止並回報 blocker，不得直接改檔
- 若 SA / SD 意見衝突，PM 必須在最終文件明確寫出取捨理由
- 預設最多兩輪交互，避免無限討論

## Deliverables

### New Project

- `<project-root>/docs/specs/system-spec.md`
- `<project-root>/docs/specs/ui-proposal.md`
- `<project-root>/docs/specs/api-spec.md`
- `<project-root>/docs/specs/domain-model.md`
- `<project-root>/docs/plans/implementation-plan.md`
- `<project-root>/docs/specs/open-questions.md`
- `<project-root>/docs/status/pm-team-status.md`

### Existing Project Change

- `<project-root>/docs/change-requests/CR-###/change-request.md`
- `<project-root>/docs/change-requests/CR-###/impact-analysis.md`
- `<project-root>/docs/change-requests/CR-###/implementation-plan.md`
- `<project-root>/docs/change-requests/CR-###/pm-team-status.md`

## Output Standard

- 文件要能被工程 agent 直接拿來實作
- 文件要盡量結構化
- 若資訊不足，用 `TBD` 或 `Open Questions` 表示，不可硬編
- RA 的輸出要能讓 PM 直接接手，不可只留下聊天紀錄
- CRA 的輸出要能讓 PM 直接接手，不可只留下聊天紀錄
