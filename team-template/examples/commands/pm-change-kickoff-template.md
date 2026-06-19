# PM Change Kickoff Template

把下面這段貼給 Codex CLI 主 agent，再把 `<project-root>`、`<project-name>` 與 `<CR-###>` 換成你的專案路徑、名稱與變更編號。

```md
請你擔任 PM agent，處理既有專案的增修需求。

既有專案文件在：
- `<project-root>/docs/specs/system-spec.md`
- `<project-root>/docs/specs/ui-proposal.md`
- `<project-root>/docs/specs/api-spec.md`
- `<project-root>/docs/specs/domain-model.md`
- `<project-root>/docs/plans/implementation-plan.md`
- `<project-root>/docs/specs/open-questions.md`

本次變更需求在：
`<project-root>/docs/change-requests/<CR-###>/change-request.md`

請你依照以下方式執行：

1. 先閱讀既有專案文件與本次 `change-request.md`。
2. 判斷本次變更需求是否足夠明確。
3. 若需求仍不清楚，請明確列出需要 CRA 回補的問題，不要直接硬做假設。
4. 若需求足夠，主動委派 SA agent 分析：
   - business rule impact
   - workflow impact
   - edge cases
   - acceptance considerations
   - non-regression requirements
5. 主動委派 SD agent 分析：
   - affected modules
   - data model impact
   - API impact
   - UI interaction impact
   - testing impact
   - technical risks
6. 收斂 SA 與 SD 的討論結果。
7. 將影響分析寫入：
   `<project-root>/docs/change-requests/<CR-###>/impact-analysis.md`
8. 將本次實作計畫寫入：
   `<project-root>/docs/change-requests/<CR-###>/implementation-plan.md`
9. 將本次 CR 狀態寫入：
   `<project-root>/docs/change-requests/<CR-###>/pm-team-status.md`
10. 若需要更新主規格文件，請同步更新相關文件，並在 `impact-analysis.md` 明確列出更新理由與檔案。
11. 若可以進入實作，請明確標示 `Ready for PG: Yes`；若不行，請標示 `Ready for PG: No` 並列出 blockers。

請不要把工作回丟給我，也不要要求我分別和 SA / SD 對話。
若資訊不足，請把缺口整理成可交給 CRA 補問的問題。
```
