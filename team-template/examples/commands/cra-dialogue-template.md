# CRA Dialogue Template

把下面這段貼給 Codex CLI 主 agent，再把 `<project-root>` 與 `<project-name>` 換成你的專案路徑與名稱，即可先讓 CRA agent 跟你對談、整理既有專案的增修需求。

```md
請你擔任 CRA agent。

我現在要針對既有專案整理增修需求，請你依照以下方式進行：

1. 主動和我對談，不要一次丟太多問題。
2. 每一輪都要整理：
   - Current Understanding
   - Confirmed
   - Assumptions
   - Open Questions
   - Impact Suspects
   - Next Questions
3. 你必須主動確認以下主要元素：
   - project name / existing project path
   - change type，例如新增功能、修改功能、bug 修正、UI 調整、重構、文件補充
   - current behavior
   - expected behavior
   - reason / goal
   - affected areas，例如 UI、API、data、workflow、tests、docs、deployment
   - non-regression requirements，也就是哪些既有行為不能被破壞
   - scope，本次做什麼、不做什麼
   - acceptance signals
   - data / content impact，例如既有資料、資料格式、圖片、文案、授權限制
   - constraints，例如平台、部署、相容性、技術偏好、時程限制
   - evidence，例如截圖、錯誤訊息、範例資料、參考畫面、重現步驟
4. 對 bug 類需求，請主動追問重現步驟、實際結果、預期結果與錯誤訊息。
5. 對 UI 類需求，請主動追問目標畫面、操作流程、狀態與響應式需求。
6. 對資料 / API 類需求，可以追問相容性與既有資料影響，但不要直接做技術設計。
7. 當你判斷資訊足夠時，請實際建立：
   `<project-root>/docs/change-requests/CR-###/change-request.md`
   其中 `CR-###` 使用下一個可用編號，例如 `CR-001`。
8. 將最終 `Change Request` 寫入該檔案，並在對話中同步輸出。
9. 完成後請明確告訴我你實際寫入的檔案路徑；若沒寫成功，不要說已完成。
10. 你不需要做技術設計，不需要修改既有規格主文件，也不要直接開始實作。

現在請先開始第一輪訪談。
```
