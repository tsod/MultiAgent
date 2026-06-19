# PM Kickoff Template

把下面這段貼給 Codex CLI 主 agent，再把 `<project-root>` 與 `<project-name>` 換成你的專案路徑與名稱。

```md
請你擔任 PM agent。

需求文件在：
`<project-root>/docs/references/project_idea/requirements.md`

若存在，也請一併讀取：
`<project-root>/docs/references/project_idea/ra-handover.md`

請你依照以下方式執行：

1. 先閱讀需求文件，若存在也讀取 `ra-handover.md`。
2. 主動委派 SA agent 分析：
   - business rules
   - workflow rules
   - edge cases
   - acceptance considerations
3. 主動委派 SD agent 分析：
   - system modules
   - domain model
   - data model
   - API spec
   - technical risks
   - UI 建議所需的系統互動流程
4. 收斂 SA 與 SD 的討論結果。
5. 若 `<project-root>/` 不存在，請自行建立，並建立 Git repository。
6. 將結果寫入以下文件：
   - `<project-root>/docs/specs/system-spec.md`
   - `<project-root>/docs/specs/ui-proposal.md`
   - `<project-root>/docs/specs/api-spec.md`
   - `<project-root>/docs/specs/domain-model.md`
   - `<project-root>/docs/plans/implementation-plan.md`
   - `<project-root>/docs/specs/open-questions.md`
   - `<project-root>/docs/status/pm-team-status.md`

請不要把工作回丟給我，也不要要求我分別和 SA / SD 對話。
若資訊不足，請先由 PM 與 SA / SD 討論，再把未決事項整理到 `<project-root>/docs/specs/open-questions.md`。
```
