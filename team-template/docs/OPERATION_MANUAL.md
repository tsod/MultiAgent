# 操作手冊

這份手冊說明如何使用 `$pm-team` 操作 RA / CRA / PM / SA / SD / PG 團隊。

建議日常使用 `$pm-team` 短提示詞，讓 skill 自動判斷該走 RA、CRA、PM 或 PG 流程。只有在沒有 `$pm-team` skill 的環境，或你想完全控制完整提示詞內容時，才改用 `examples/commands/*.md` 的手動模板。

## 核心觀念

`$pm-team` 會依照你的意圖自動路由：

- 新專案需求模糊：走 RA discovery。
- 新專案需求已清楚：走 PM planning。
- 既有專案增修需求模糊：走 CRA discovery。
- 既有專案 CR 已清楚：走 PM change planning。
- 規格或實作計畫已完成：走 PG implementation。

所以你不一定要在提示詞中指定 agent。像下面這句是有效的：

```text
請使用 $pm-team 幫我釐清新專案需求：<想法>
```

它會被判定為新專案需求探索，並自動使用 RA 流程。

實務上，建議在正式開始專案時使用更穩定的寫法，明確要求 RA / CRA、輸出檔案與狀態檔。

## 標準目錄

### 新專案

- 專案根目錄：`<project-root>`
- 需求輸入：`<project-root>/docs/references/project_idea/requirements.md`
- RA handover：`<project-root>/docs/references/project_idea/ra-handover.md`
- 專案規格輸出：`<project-root>/docs/specs/`
- 專案計畫輸出：`<project-root>/docs/plans/`
- 狀態檔：`<project-root>/docs/status/pm-team-status.md`

新專案輸出通常包含：

- `docs/specs/system-spec.md`
- `docs/specs/ui-proposal.md`
- `docs/specs/api-spec.md`
- `docs/specs/domain-model.md`
- `docs/plans/implementation-plan.md`
- `docs/specs/open-questions.md`

### 既有專案增修

- 變更需求：`<project-root>/docs/change-requests/CR-###/change-request.md`
- 變更輸出：`<project-root>/docs/change-requests/CR-###/`
- 狀態檔：`<project-root>/docs/change-requests/CR-###/pm-team-status.md`

增修資料夾通常包含：

- `change-request.md`
- `impact-analysis.md`
- `implementation-plan.md`
- `pm-team-status.md`

## 建議工作順序

新專案：

```text
RA discovery -> PM planning -> PG implementation
```

既有專案增修：

```text
CRA discovery -> PM change planning -> PG implementation
```

如果需求文件已經很完整，可以跳過 RA / CRA。若只是初步想法、口語描述、bug 印象或 UI 感覺不對，先讓 RA / CRA 整理，後續 PM 與 PG 會更穩定。

## 新專案需求模糊

使用 RA 逐步訪談，不要先跳到技術設計。

短版：

```text
請使用 $pm-team 幫我釐清新專案需求：<想法>
```

穩定版：

```text
請使用 $pm-team 幫我做新專案需求探索。

我的初步想法是：
<想法>

請先由 RA 逐步訪談我，確認 product goal、target users、core scenarios、data elements、business rules、scope、acceptance signals、edge cases、constraints、素材限制與技術偏好。不要直接進入技術設計。

需求收斂後，請提出 2 到 3 個專案名稱建議讓我確認。專案名稱確認後，請建立 `<project-root>/docs/references/project_idea/ra-handover.md`，並更新 `<project-root>/docs/status/pm-team-status.md`。
```

完成後查看：

```text
<project-root>/docs/references/project_idea/ra-handover.md
<project-root>/docs/status/pm-team-status.md
```

## 新專案需求已清楚

如果你已經有 `requirements.md`，直接讓 PM 統整 SA / SD 做規劃。

```text
請使用 $pm-team 啟動新專案 PM planning。

專案名稱：<project-name>
專案根目錄：<project-root>
需求文件：<project-root>/docs/references/project_idea/requirements.md

請讀取 requirements.md；如果有 ra-handover.md 也一起讀取。請由 PM 統整 SA 與 SD 的分析，產出 `docs/specs/system-spec.md`、`docs/specs/ui-proposal.md`、`docs/specs/api-spec.md`、`docs/specs/domain-model.md`、`docs/plans/implementation-plan.md`、`docs/specs/open-questions.md`，並更新 `docs/status/pm-team-status.md`。

若資訊不足，請把未決事項寫入 `docs/specs/open-questions.md`，不要直接停止。
```

完成後查看：

```text
<project-root>/docs/
```

## 新專案一路做到規劃

如果你希望從模糊想法開始，需求收斂後直接進 PM planning，可以一次說清楚。

```text
請使用 $pm-team 從新專案 discovery 開始，必要時一路進到 PM planning。

我的初步想法是：
<描述你的產品、目標使用者、核心場景>

請先由 RA 訪談整理需求，確認專案名稱後寫入 `docs/references/project_idea/ra-handover.md`。若需求已足夠，接著由 PM 整合 SA / SD 分析，產出完整專案規格與 `docs/plans/implementation-plan.md`。請全程維護 `docs/status/pm-team-status.md`。
```

## 既有專案增修需求模糊

使用 CRA 先整理變更需求。這適合 bug、功能調整、UI 調整、重構、文件補充等既有專案變更。

```text
請使用 $pm-team 幫我整理既有專案的變更需求。

專案名稱：<project-name>
目前想改的是：
<描述 bug、功能調整、UI 調整、重構或文件變更>

請由 CRA 逐步訪談我，釐清 current behavior、expected behavior、影響範圍、不可破壞的既有行為、驗收條件與限制。需求收斂後，請建立下一個 CR 編號，寫入 `<project-root>/docs/change-requests/CR-###/change-request.md`，並更新該 CR 的 `pm-team-status.md`。
```

完成後查看：

```text
<project-root>/docs/change-requests/CR-###/change-request.md
<project-root>/docs/change-requests/CR-###/pm-team-status.md
```

## 既有專案 CR 已清楚

如果 `change-request.md` 已經存在，讓 PM 做影響分析與實作計畫。

```text
請使用 $pm-team 分析既有專案變更。

專案名稱：<project-name>
CR 編號：<CR-###>
專案根目錄：<project-root>
變更需求文件：<project-root>/docs/change-requests/<CR-###>/change-request.md

請讀取既有專案文件與 change-request.md，由 PM 統整 SA / SD 分析，產出 `impact-analysis.md` 與 `implementation-plan.md`。若可以實作，請標示 Ready for PG: Yes；若不行，請列出 blockers。請更新該 CR 的 `pm-team-status.md`。
```

完成後查看：

```text
<project-root>/docs/change-requests/<CR-###>/impact-analysis.md
<project-root>/docs/change-requests/<CR-###>/implementation-plan.md
```

## 開始實作

### 新專案實作

```text
請使用 $pm-team 進入 PG implementation。

專案名稱：<project-name>
專案根目錄：<project-root>
請讀取 `<project-root>/docs/status/pm-team-status.md`、`<project-root>/docs/specs/system-spec.md`、`<project-root>/docs/specs/ui-proposal.md`、`<project-root>/docs/specs/api-spec.md`、`<project-root>/docs/specs/domain-model.md`、`<project-root>/docs/plans/implementation-plan.md`，依照 `implementation-plan.md` 開始實作。

請完成必要測試，回報修改檔案與驗證結果，並更新 `docs/status/pm-team-status.md`。
```

### 既有專案 CR 實作

```text
請使用 $pm-team 讓 PG 實作既有專案變更。

專案名稱：<project-name>
CR 編號：<CR-###>

請讀取 `<project-root>/docs/change-requests/<CR-###>/pm-team-status.md`、`change-request.md`、`impact-analysis.md`、`implementation-plan.md`，以及相關既有專案文件。請依照 CR `implementation-plan.md` 實作、測試，回報修改檔案與驗證結果，並更新該 CR 的 `pm-team-status.md`。
```

## 恢復進度

新專案恢復：

```text
請使用 $pm-team 恢復專案進度。

專案名稱：<project-name>

請先讀取 `<project-root>/docs/status/pm-team-status.md`，判斷目前階段、已完成事項、目前輸出檔案與下一步，然後繼續執行 Next Action。
```

既有專案 CR 恢復：

```text
請使用 $pm-team 恢復變更需求進度。

專案名稱：<project-name>
CR 編號：<CR-###>

請先讀取 `<project-root>/docs/change-requests/<CR-###>/pm-team-status.md`，判斷目前階段與 Next Action，然後繼續處理。
```

## 手動模板備援

沒有 `$pm-team` skill，或你想手動控制完整提示詞時，可以使用舊式模板：

- [ra-dialogue-template.md](/mnt/d/AIProject/MultiAgent/team-template/examples/commands/ra-dialogue-template.md)
- [pm-kickoff-template.md](/mnt/d/AIProject/MultiAgent/team-template/examples/commands/pm-kickoff-template.md)
- [cra-dialogue-template.md](/mnt/d/AIProject/MultiAgent/team-template/examples/commands/cra-dialogue-template.md)
- [pm-change-kickoff-template.md](/mnt/d/AIProject/MultiAgent/team-template/examples/commands/pm-change-kickoff-template.md)

手動模板流程：

1. 打開對應模板。
2. 替換 `<project-root>`、`<project-name>` 與 `<CR-###>`。
3. 把整段提示詞貼給 Codex CLI 主 agent。
4. 到 `<project-root>/docs/` 或 `<project-root>/docs/change-requests/<CR-###>/` 查看結果。

## 你不用做的事

- 不用分別和 SA / SD 對話。
- 不用手動貼完整模板，除非你選擇使用備援流程。
- 不用在需求模糊時自己整理完整規格，RA / CRA 會先幫你問清楚。
- 不用每次從聊天紀錄找進度，`pm-team-status.md` 會記錄目前階段與下一步。
- 不用在資訊不足時硬做決策，未決事項會寫入 `open-questions.md` 或 blockers。

## 一句話版本

新專案需求模糊：

```text
請使用 $pm-team 幫我釐清新專案需求：<想法>
```

新專案需求已清楚：

```text
請使用 $pm-team 啟動 <project-name> 的 PM planning。
```

既有專案增修需求模糊：

```text
請使用 $pm-team 幫我整理 <project-name> 的變更需求：<想改什麼>
```

既有專案 CR 已清楚：

```text
請使用 $pm-team 分析 <project-name> 的 <CR-###>。
```
