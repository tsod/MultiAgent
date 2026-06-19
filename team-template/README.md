# PM-Led Team Template

這個資料夾是 PM-led agent team 的流程範本，不是實際專案工作區。

實際專案實作應寫回該專案的 `project_root`。若沒有其他明確專案路徑，可用 `/mnt/d/AIProject/Workspaces/<project-name>/` 作為預設 `project_root`。專案需求與 RA handover 等重要參考文件請放在該專案的 `docs/references/project_idea/`。歷史輸出與搬遷前備份資料請放在 `/mnt/d/AIProject/Archives/`。

## 目錄內容

- `prompts/`: RA / CRA / PM / SA / SD / PG 角色定義。
- `workflow/`: PM 如何驅動 RA / CRA / SA / SD / PG 的流程文件。
- `templates/`: 系統規格、API、domain model、implementation plan 等輸出模板。
- `examples/commands/`: 可複製使用的 kickoff 與 dialogue 指令範本。
- `docs/`: 操作手冊、快速開始、專案結構標準與歷史 project implement 說明。

## 使用原則

- `team-template` 只放流程、prompt、template、文件與範例。
- 不在 `team-template` 內放正式專案原始碼。
- 不在 `team-template` 內放正式專案 git repo。
- 專案產出一律寫回 `project_root`，不要寫回 `team-template`。
- `Workspaces/<project-name>/` 只是預設 `project_root`，不是唯一合法位置。
- 若需要保留專案需求或 RA handover，放到該專案的 `docs/references/project_idea/`。
- 系統規格文件放在該專案的 `docs/specs/`。
- 主實作計畫放在該專案的 `docs/plans/`。
- 專案主狀態檔放在該專案的 `docs/status/`。
- 變更需求文件放在該專案的 `docs/change-requests/CR-###/`。
- 若只是搬遷前備份或不再作為專案依據的歷史輸出，放到 `Archives/`。

## 常用範本

- 新專案 PM kickoff: `examples/commands/pm-kickoff-template.md`
- 既有專案變更訪談: `examples/commands/cra-dialogue-template.md`
- 既有專案變更分析: `examples/commands/pm-change-kickoff-template.md`
- PG 開發啟動: `examples/commands/pg-kickoff-template.md`

## 角色摘要

- RA: 新專案需求訪談。
- CRA: 既有專案增修需求訪談。
- PM: 對使用者負責的主要入口，整合 RA / CRA / SA / SD / PG。
- SA: 系統與架構分析。
- SD: 設計與資料模型分析。
- PG: 規格完成後的開發角色。

## 搬遷備註

原本的 `example-team/project_idea` 專案參考文件已移入各自專案：

```text
<project-root>/docs/references/project_idea
```

原本的 `example-team/project_implement` 實際專案已搬到：

```text
/mnt/d/AIProject/Workspaces
```
