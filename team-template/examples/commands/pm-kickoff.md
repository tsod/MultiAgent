# PM Kickoff Command

把下面這段貼給 Codex CLI 主 agent，即可用 PM 主導方式啟動團隊流程。

```md
請你擔任 PM agent。

需求文件在：
`/mnt/d/AIProject/Workspaces/leave-request-system/docs/references/project_idea/requirements.md`

請你依照以下方式執行：

1. 先閱讀需求文件。
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
5. 將結果寫入以下文件：
   - `/mnt/d/AIProject/Workspaces/leave-request-system/docs/specs/system-spec.md`
   - `/mnt/d/AIProject/Workspaces/leave-request-system/docs/specs/ui-proposal.md`
   - `/mnt/d/AIProject/Workspaces/leave-request-system/docs/specs/api-spec.md`
   - `/mnt/d/AIProject/Workspaces/leave-request-system/docs/specs/domain-model.md`
   - `/mnt/d/AIProject/Workspaces/leave-request-system/docs/plans/implementation-plan.md`
   - `/mnt/d/AIProject/Workspaces/leave-request-system/docs/specs/open-questions.md`
   - `/mnt/d/AIProject/Workspaces/leave-request-system/docs/status/pm-team-status.md`

請不要把工作回丟給我，也不要要求我分別和 SA / SD 對話。
若資訊不足，請先由 PM 與 SA / SD 討論，再把未決事項整理到 `/mnt/d/AIProject/Workspaces/leave-request-system/docs/specs/open-questions.md`。
```
