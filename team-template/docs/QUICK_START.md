# Quick Start

## 新專案你要做的事

1. 建立需求檔：

`<project-root>/docs/references/project_idea/requirements.md`

2. 打開：

[pm-kickoff-template.md](/mnt/d/AIProject/MultiAgent/team-template/examples/commands/pm-kickoff-template.md)

如果需求還很模糊，先打開：

[ra-dialogue-template.md](/mnt/d/AIProject/MultiAgent/team-template/examples/commands/ra-dialogue-template.md)

3. 把裡面的 `<project-name>` 換成你的專案名稱。

4. 把整段指令貼給 Codex CLI 主 agent。

## 既有專案增修你要做的事

1. 如果增修需求還很模糊，先打開：

[cra-dialogue-template.md](/mnt/d/AIProject/MultiAgent/team-template/examples/commands/cra-dialogue-template.md)

2. 讓 CRA 對談並寫出：

`<project-root>/docs/change-requests/CR-###/change-request.md`

3. 再打開：

[pm-change-kickoff-template.md](/mnt/d/AIProject/MultiAgent/team-template/examples/commands/pm-change-kickoff-template.md)

4. 把裡面的 `<project-name>` 與 `<CR-###>` 換成你的專案名稱與變更編號。

5. 把整段指令貼給 Codex CLI 主 agent。

## Codex 會幫你做的事

- PM 讀需求
- 若需求模糊，可先由 RA 對談整理
- 若既有專案增修需求模糊，可先由 CRA 對談整理
- RA 會提出專案名稱建議並讓你確認
- RA 會把整理結果寫到 `<project-root>/docs/references/project_idea/ra-handover.md`
- RA 只有在檔案真的寫出來後，才算完成 handover
- CRA 會把增修需求寫到 `<project-root>/docs/change-requests/CR-###/change-request.md`
- PM 可依 change request 產出 `impact-analysis.md` 與 `implementation-plan.md`
- PM 委派 SA / SD
- PM 會把系統規格寫到 `<project-root>/docs/specs/`，把主實作計畫寫到 `<project-root>/docs/plans/`，把狀態檔寫到 `<project-root>/docs/status/`
- PM 輸出文件
- 若要開始實作，可再由 PM 直接委派 PG 開始開發
- 若 PG 發現規格缺口，先由 PM 回補，再讓 PG 繼續

## 你去哪裡看結果

新專案：

`<project-root>/docs/`

既有專案增修：

`<project-root>/docs/change-requests/CR-###/`

## 例子

- 需求：`/mnt/d/AIProject/Workspaces/leave-request-system/docs/references/project_idea/requirements.md`
- 輸出：`/mnt/d/AIProject/Workspaces/leave-request-system/docs/`

## 一句話

新專案需求很模糊時，先讓 RA 跟你對談；既有專案增修需求很模糊時，先讓 CRA 跟你對談；需求夠清楚後，再叫 PM 開工。
