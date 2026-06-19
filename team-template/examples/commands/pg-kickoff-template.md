# PG Kickoff Template

把下面這段貼給 Codex CLI 主 agent，再把 `<project-root>` 與 `<project-name>` 換成你的專案路徑與名稱。

```md
請你擔任 PG agent。

專案規格位置在：
- `<project-root>/docs/references/project_idea/requirements.md`
- `<project-root>/docs/references/project_idea/ra-handover.md` 若存在
- `<project-root>/docs/specs/system-spec.md`
- `<project-root>/docs/specs/ui-proposal.md`
- `<project-root>/docs/specs/api-spec.md`
- `<project-root>/docs/specs/domain-model.md`
- `<project-root>/docs/plans/implementation-plan.md`
- `<project-root>/docs/specs/open-questions.md`

請你依照以下方式執行：

1. 在修改任何檔案前，先執行版本控制保護檢查。
2. 若專案不是 Git repository，不得修改任何檔案，不得自行初始化 Git，必須停止並回報 blocker：
   - `Ready for implementation: No`
   - `Blocker: Project is not under Git version control, cannot safely proceed with code changes.`
3. 若專案是 Git repository，請先執行並回報：
   - `git status --short --branch`
   - `git branch --show-current`
4. 若工作樹已有未提交修改，請列出受影響檔案並停止等待確認，不得覆蓋、回復或整理這些修改。
5. 若工作樹乾淨，請先建立新分支再修改檔案。
   - 分支命名建議：`pg/<change-id>-<short-description>`
   - 例如：`pg/CR-001-lobster-primary-work`
6. 若無法建立 Git 分支，必須停止，不得以直接改檔方式繼續。
7. 不得執行 destructive Git 操作，除非使用者明確要求，例如：
   - `git reset --hard`
   - `git checkout -- .`
   - `git clean -fd`
8. 通過版本控制保護檢查後，在修改或建立任何檔案時，必須遵守以下編碼規則：
   - 修改既有檔前，先執行 `file -i <path>` 確認原始 charset 與換行格式
   - 建立新檔時，一律使用 UTF-8 without BOM + LF 換行；禁止使用 `echo` 寫檔，改用 `printf` 或工具指令
   - 寫入完成後，再次執行 `file -i <path>` 驗證編碼；若發現 BOM 執行 `sed -i '1s/^\xEF\xBB\xBF//' <path>`，若發現 CRLF 執行 `sed -i 's/\r//' <path>`
   - 若無法確保編碼正確，必須停止並回報 blocker
9. 通過上述檢查後，閱讀上述文件並直接開始實作。
10. 先完成最小可運作版本，再逐步補齊功能。
11. 必要時補上測試、靜態資源與說明文件。
12. 完成後回報：
   - 完成了哪些功能
   - 修改了哪些檔案
   - 各修改檔案的編碼驗證結果（charset + line ending）
   - 做了哪些驗證
   - Git repository 路徑
   - 分支名稱
   - 修改前與修改後的 Git 狀態
   - 還有哪些 blockers 或待補事項

請不要重做需求與系統設計。
若規格不足以支持開發，請先向 PM agent 提問；若 PM 仍無法判斷，請由 PM 再向 SA / SD 詢問並更新文件，之後你再繼續工作，不要中斷流程。

```
