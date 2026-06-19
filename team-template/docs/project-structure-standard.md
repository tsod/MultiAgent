# Project Structure Standard

這份文件定義 PM team 產出在專案內的標準放置規則。

## 核心原則

- `MultiAgent` 只放 agent 規範、workflow、prompt、template 與範例。
- 專案產出一律寫回該專案自己的 `project_root`。
- `/mnt/d/AIProject/Workspaces/<project-name>/` 只是預設 `project_root`，不是唯一合法位置。
- 不把規格文件、狀態檔或 change request 寫回 `MultiAgent`。

## 標準目錄

```text
<project-root>/
├─ docs/
│  ├─ references/
│  │  └─ project_idea/
│  │     ├─ requirements.md
│  │     └─ ra-handover.md
│  ├─ specs/
│  │  ├─ system-spec.md
│  │  ├─ ui-proposal.md
│  │  ├─ api-spec.md
│  │  ├─ domain-model.md
│  │  └─ open-questions.md
│  ├─ plans/
│  │  └─ implementation-plan.md
│  ├─ status/
│  │  └─ pm-team-status.md
│  └─ change-requests/
│     └─ CR-###/
│        ├─ change-request.md
│        ├─ impact-analysis.md
│        ├─ implementation-plan.md
│        ├─ pm-team-status.md
│        └─ attachments/
├─ src/
├─ tests/
└─ ...
```

## Artifact Mapping

- `requirements.md`:
  - 路徑：`<project-root>/docs/references/project_idea/requirements.md`
  - 用途：原始需求輸入
- `ra-handover.md`:
  - 路徑：`<project-root>/docs/references/project_idea/ra-handover.md`
  - Owner：RA
- `system-spec.md`:
  - 路徑：`<project-root>/docs/specs/system-spec.md`
  - Owner：PM
- `ui-proposal.md`:
  - 路徑：`<project-root>/docs/specs/ui-proposal.md`
  - Owner：PM
- `api-spec.md`:
  - 路徑：`<project-root>/docs/specs/api-spec.md`
  - Owner：PM
- `domain-model.md`:
  - 路徑：`<project-root>/docs/specs/domain-model.md`
  - Owner：PM
- `open-questions.md`:
  - 路徑：`<project-root>/docs/specs/open-questions.md`
  - Owner：PM
- `implementation-plan.md`:
  - 路徑：`<project-root>/docs/plans/implementation-plan.md`
  - Owner：PM
- `pm-team-status.md`:
  - 路徑：`<project-root>/docs/status/pm-team-status.md`
  - Owner：PM

## Change Request Mapping

- `change-request.md`:
  - 路徑：`<project-root>/docs/change-requests/CR-###/change-request.md`
  - Owner：CRA
- `impact-analysis.md`:
  - 路徑：`<project-root>/docs/change-requests/CR-###/impact-analysis.md`
  - Owner：PM
- `implementation-plan.md`:
  - 路徑：`<project-root>/docs/change-requests/CR-###/implementation-plan.md`
  - Owner：PM
- `pm-team-status.md`:
  - 路徑：`<project-root>/docs/change-requests/CR-###/pm-team-status.md`
  - Owner：PM
- `attachments/`:
  - 路徑：`<project-root>/docs/change-requests/CR-###/attachments/`
  - 用途：截圖、流程圖、參考圖、範例資料

## Path Resolution Guidance

- 若使用者明確指定專案路徑，直接使用該路徑作為 `project_root`。
- 若目前工作目錄已是專案目錄，直接使用目前專案目錄作為 `project_root`。
- 若能從既有專案結構推導出專案根目錄，使用推導出的 `project_root`。
- 只有在無法推導時，才使用 `/mnt/d/AIProject/Workspaces/<project-name>/` 作為預設 `project_root`。
