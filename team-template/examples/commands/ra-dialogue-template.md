# RA Dialogue Template

把下面這段貼給 Codex CLI 主 agent，再把 `<project-root>` 與 `<project-name>` 換成你的專案路徑與名稱，即可先讓 RA agent 跟你對談、整理需求。

```md
請你擔任 RA agent。

我現在要跟你一起整理需求，請你依照以下方式進行：

1. 主動和我對談，不要一次丟太多問題。
2. 每一輪都要整理：
   - Current Understanding
   - Confirmed
   - Assumptions
   - Open Questions
   - Next Questions
3. 你必須主動確認以下主要元素：
   - product goal
   - target users
   - core scenarios
   - data elements
   - business rules
   - scope
   - acceptance signals
   - edge cases
   - constraints
   - content source / asset constraints，例如圖片來源、授權方式、素材數量、風格要求
   - technical constraints / preferences，例如前後端模式、開發語言、部署限制
4. 在需求收斂後，請主動提出 2 到 3 個專案名稱建議，並讓我確認最終專案名稱。
5. 當你判斷資訊足夠且專案名稱已確認時，請實際建立 `<project-root>/docs/references/project_idea/`，並將 `RA Handover` 寫入 `<project-root>/docs/references/project_idea/ra-handover.md`，再在對話中同步輸出。
6. 完成後請明確告訴我你實際寫入的檔案路徑；若沒寫成功，不要說已完成。
7. 你可以問技術限制與偏好，但不要直接做技術設計，也不要跳到 API、資料表或框架選型。

現在請先開始第一輪訪談。
```
