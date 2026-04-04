# Operate & Maintain Guide v2.0.1
> AAA 版本開發與維運權威流程（AI/Agent 專用，無歧義可執行）。

## 文件中繼資料
- document_version: `v2.0.1`
- effective_date: `2026-03-01`
- replaces: `aaa-docs/bootstrap/operate_maintain_guide.md`（舊版）
- authority_level: `workflow-law`

## 0. 權威與優先序（MUST）
1. 本文件是 AAA 版本開發工作流唯一權威來源。
2. 任何自建 `task.md`、memo、agent checklist 不得覆寫本文件規則。
3. 優先序固定：`operate_maintain_guide.md > task.md > 臨時備忘`。
4. 違反本文件任一 blocking 規則，流程狀態必須標記為 `NOT READY` 或 `FAIL`。

## 1. 核心目標
1. 讓 AAA 本體與繼承專案可共用同一套版本治理流程。
2. 讓流程具 machine-checkable 特性，避免主觀判斷與語意漂移。
3. 以可執行證據鏈（remote run_ref + evidence paths）取代敘述式完成宣告。

## 2. Canonical Data Sources（MUST）
下列兩份 index 檔是版本/工作流程頁面的原始資料來源（raw data SSOT）：
- `aaa-tpl-docs/ops/index/version_index.md`
- `aaa-tpl-docs/ops/index/workflow_index.md`

規則：
1. 新版本開發時，Step1 必須先更新對應 index。
2. Step2~Step4 的完成狀態與 evidence 必須回寫對應 index 行。
3. `ops-registry` / `ops-version` 類頁面資料不得繞過上述 index 另建平行來源。

## 3. Release Type
- `NORMAL_RELEASE`：需完成 Step1 + Step2 + Step3 + Step4。
- `BRIDGE_RELEASE`：只做治理補洞，可停在 Step1；Step4 狀態僅可 `COMPLETED_STEP1` 或 `BRIDGE_ONLY`。

## 3.1 Step2 Scarcity Governance（MUST）
1. Step2 是稀缺治理配額，不是每個新版本的預設權利。
2. 擬進 Step2 的版本，plan / audit 必須先回答：
   - 為何不能 bridge-only
   - 為何不能被既有 execution package 吸收
   - 為何不能重用既有 execution carrier
3. 下列類型預設不應建立獨立 Step2，除非 audit 明示不能 bridge-only 且不能被 bundled execution 吸收：
   - wording / vocabulary baseline
   - positioning / framing baseline
   - appendix / guide / narrative clarification baseline
   - historical / metadata / registry interpretation baseline
4. Step2 run_ref 合法，不等於可自動新增 version-specific workflow；預設必須優先重用既有 carrier 或 bundled execution。

## 3.2 Bridge Visibility Package（Reduced-Form MUST）
1. `BRIDGE_RELEASE` 若要求 consumer-visible surface，plan / audit 必須顯式定義 `bridge visibility package`。
2. `bridge visibility package` 只能處理 version-side visible surface，不得自動擴張到 workflow-side active registry。
3. bridge visibility proof 只可作為 local / page-visible evidence，不得冒充 Step2 remote executable evidence。

## 4. Strict Discipline（全部為 MUST）
1. Step1/Step2 邊界隔離：Step1 只允許治理資產，不得碰 runtime domain code。
2. No-Glob Policy：deliverables/evidence 路徑不得使用 `*`、`**`。
3. Step2 run_ref remote-only：僅允許 `gh-actions:<repo>@<workflow_file>#<run_id>`。
4. Completion Claim Guard：若缺 remote evidence，不得使用 `COMPLETED/PASS/已落地` 語意。
5. Full-File Consistency：修改多視圖文件（如 index + registry）必須全檔一致。
6. Guide Parity Gate（v2.0.1+）：`aaa-docs/bootstrap/operate_maintain_guide.md` 與 `aaa-tpl-docs/operate_maintain_guide.md` 的 canonical sections 必須通過 CI parity gate；不一致一律 FAIL。
7. Machine-Parseable Truth Priority：若 guide MUST、schema/gate parser、與人類可讀敘述不一致，以 guide MUST + machine-checkable parser 為最高真相。
8. Generated Artifact Shape Verification：讀取 generated artifact 前，必須先確認 top-level keys 與對應 schema/type；不得直接假設欄位結構或猜測欄位名。
9. Guide Patch Threshold：只有 truth precedence、closeout sequence、shared validator/contract law、或 guide-level promotion law 類問題，才可直接升格為 top guide patch；其餘 recurring issue 預設優先進 register / checklist / validator / schema。

## 5. 4-Step Lifecycle

### Step 1: Contract Baseline（契約基線）
**目標**：先鎖規格、邊界與驗收，再進入實作。

允許範圍（Step1）：
- `internal/development/plans/**`
- `internal/development/audits/**`
- `internal/development/reviews/**`
- `internal/development/contracts/**`
- `scripts/gates/**`
- `.github/workflows/**`（僅草案）

禁止範圍（Step1）：
- `src/**`
- `PRD/**`
- runtime/build config（如 `package.json`, `tsconfig*`, `next.config*`）

必備交付：
1. Plan：`internal/development/plans/YYYY-MM-DD-<version>-<name>-plan.md`
2. Audit：`internal/development/audits/YYYY-MM-DD-<version>-<name>-audit.md`
3. Diff Paths：`internal/development/reviews/YYYY-MM-DD-<version>-<name>-diff-paths.md`
4. Schema：至少 1 份 `*.schema.json`
5. Examples：至少 1 份 pass + 1 份 fail

Index 更新（Step1 Blocking）：
1. 必須追加/更新 `aaa-tpl-docs/ops/index/version_index.md` 對應版本列。
2. 若涉及 workflow，必須追加/更新 `aaa-tpl-docs/ops/index/workflow_index.md` 對應列。
3. 排序必須維持：日期 DESC；同日期下版本或 ID DESC。
4. Step1 允許 placeholder `run_ref=N/A (step2-pending)`，但不得宣稱 Step2 PASS。

#### Step 1 Exit Checklist（Machine-Scannable）
```yaml
ExitChecklistStep: 1
ExitChecklistVersion: v2.0.1
ExitChecklistOwner: <ai-or-human-role>
ExitChecklistVerdict: PASS|FAIL|N/A
```
- [ ] Plan 已建立（No-Glob 路徑）
- [ ] Audit 已建立（含 1+2+1 coverage）
- [ ] Diff-Paths 已建立（含 allowlist/denylist/verdict）
- [ ] Schema + Pass/Fail examples 已建立
- [ ] Step1 邊界合規（無 `src/**` / `PRD/**`）
- [ ] `version_index.md` 已新增或更新對應版本列
- [ ] `workflow_index.md` 已新增或更新對應 workflow 列（若涉及）
- [ ] index 排序正確（日期/版本規則）
- [ ] Triple-Summary 已填寫

### Step 2: Implementation & Executable Evidence（實作與可執行證據）
**目標**：依 Step1 契約完成實作，並提供可重放證據。

硬規則：
1. run_ref 必須 remote-only：`gh-actions:<repo>@<workflow_file>#<run_id>`。
2. 禁止 `local:*`, `file:*`, `shell:*`, `gh://` 作為 Step2 新證據。
3. 任何 completion claim 必須附 remote run_ref + evidence_path。
4. 若新增/重大修改 workflow，至少 1 次 remote smoke run。

必備證據欄位：
- `run_ref`
- `computed_at_taipei`
- `inputs_digest`
- `source_paths`（No-Glob）
- `evidence_path`（No-Glob）

#### Step 2 Exit Checklist（Machine-Scannable）
```yaml
ExitChecklistStep: 2
ExitChecklistVersion: v2.0.1
ExitChecklistOwner: <ai-or-human-role>
ExitChecklistVerdict: PASS|FAIL|N/A
```
- [ ] Step1 全項 PASS
- [ ] 實作變更符合 Step1 契約範圍
- [ ] run-evidence 文件已建立並含必要欄位
- [ ] run_ref 為 remote-only 合規格式
- [ ] workflow smoke run 已完成（若適用）
- [ ] `version_index.md` 對應列已更新 Step2 狀態與 run_ref/evidence
- [ ] `workflow_index.md` 對應列已更新 latest_run/evidence（若適用）

### Step 3: Asset Preservation（資產保存）
**目標**：把 Step1/Step2 產生的可重用成果轉成 AAA 資產，形成可回放、可匯入、可審計的資產鏈。

AAA Valuable Assets（MUST）：
1. Templates：
   - 例：`internal/development/templates/**`、可被繼承專案直接套用的 SOP/規格模板。
2. Prompts：
   - 例：`prompts/**`、agent/system prompt bundles、審核提示詞。
3. Contracts：
   - 例：`internal/development/contracts/**/*.schema.json`、reason-codes、pass/fail fixtures。
4. Workflows/Gates：
   - 例：`.github/workflows/*.yml`、`scripts/gates/**`。
5. Evals/Test Assets：
   - 例：`evals/**`、測試資料、驗證案例與 replay inputs。
6. Runbooks/Operational Guides：
   - 例：`internal/development/runbooks/**`、`internal/development/reviews/*-checklist.md`。
7. UI/Observability Assets（若有）：
   - 例：dashboard spec、MCP screenshots、ops/version page mapping docs。

來源規則（MUST）：
1. Step1 產物：以「治理可重用」為主（templates/contracts/gates/workflow specs）。
2. Step2 產物：以「可執行證據可重用」為主（run evidence/evals/replay assets）。
3. Step3 必須明確標示每項資產來自 Step1 或 Step2，不得混寫為不明來源。

最小保存交付（MUST）：
1. `internal/development/evidence/<version>/<asset>/result.json`
2. `internal/development/evidence/<version>/<asset>/index.json`
3. `internal/development/evidence/<version>/<asset>/run-evidence.md`
4. `internal/development/evidence/<version>/<asset>/asset-manifest.v0.1.json`
   - 至少欄位：`asset_id`, `asset_type`, `source_step`, `source_paths`, `reuse_target`, `owner`, `digest`

Value Gate（MUST）：
1. 若本版本沒有任何可沉澱 AAA 資產，必須在 Step3 checklist 填寫 `No-Asset Justification`（不可留空）。
2. 若有資產，`asset-manifest.v0.1.json` 至少 1 筆 `reuse_target` 必須是 `AAA core` 或 `AAA inherited projects`。
3. 每筆資產都要有對應 digest（如 `inputs_digest`, `policy_digest`, `dataset_digest`, `asset_digest`）。

#### Step 3 Exit Checklist（Machine-Scannable）
```yaml
ExitChecklistStep: 3
ExitChecklistVersion: v2.0.1
ExitChecklistOwner: <ai-or-human-role>
ExitChecklistVerdict: PASS|FAIL|N/A
```
- [ ] Valuable Assets 已分類（Templates/Prompts/Contracts/Workflows/Evals/Runbooks/UI）
- [ ] 每項資產已標註 `source_step`（Step1 或 Step2）
- [ ] `asset-manifest.v0.1.json` 已建立（或有 No-Asset Justification）
- [ ] 證據檔已保存（`result.json`, `index.json`, `run-evidence.md`）
- [ ] digest 欄位已填寫（含 asset_digest 類欄位）
- [ ] 里程碑摘要文件已建立

### Step 4: Completion & Delivery（結案與交付）
**目標**：鎖定版本、同步索引、完成可審計閉環。

必備文件：
1. `internal/development/milestones/YYYYMMDD_vX.Y_<name>.md`
2. `internal/development/milestones/completion-reports/vX.Y_completion_report_YYYYMMDD.md`

必做同步：
1. `version_index.md`：狀態更新為最終狀態（NORMAL: `COMPLETED` / BRIDGE: `COMPLETED_STEP1`）
2. `workflow_index.md`：對應 workflow 狀態/模式/latest_run 同步
3. 若宣稱 completed，必須可對應 Step2 remote evidence

Global MCP Validation（Step4 MUST）：
1. versions page（`/ops-registry?tab=versions`）
2. workflows page（`/ops-registry?tab=workflows`）
3. version detail（`/ops-version/<version>`）

UI Validation Evidence Policy（Reduced-Form MUST）：
1. Step4 若產出 UI validation evidence，必須明示：
   - `primary_tool`
   - `fallback_tool`
   - `exception_reason`（若使用 fallback）
2. UI validation tool naming 只作 evidence metadata，不自動升格為 workflow-law 主權判斷。

Step4 Checklist Tiering（MUST）：
1. Step4 checklist item 必須分級為：
   - `ALWAYS_ON_MUST`
   - `CONDITIONAL_MUST`
   - `REVIEW_SAMPLED`
2. 新增 Step4 item 預設不得直接進 `ALWAYS_ON_MUST`，除非 audit 能證明其對 closeout 真實性具有不可替代價值。

Single Review Artifact Rule（MUST）：
1. 每次 4-step closeout 完成後，只允許一份 post-closeout review artifact。
2. 該 artifact 必須同時承載 lesson learned、follow-up decision、與必要 appendix。
3. 不得再拆出 decision note / wording draft / mutation patch draft / completion note 的中間文件鏈充當 current preferred process。

Recurring Issue Register Discipline（Reduced-Form MUST）：
1. recurring issue 不得只留在 review note；若屬重複性 failure / drift / checklist degradation，必須進入正式 register。
2. register mutation 至少必須包含：
   - `entry_id`
   - `pattern_summary`
   - `affected_area`
   - `recommended_promotion_target`
   - `status`
3. `ABSORBED` 不得只表示「已知悉」；至少必須已有 1 個正式 guard 落地於 guide / schema / validator / checklist 之一。

Post-Closeout Interpretation Boundary（Reduced-Form MUST）：
1. post-closeout interpretation artifact 只能限制外推邊界，不得自動授權新 runtime family、new version line、或新治理主權層。
2. interpretation artifact 可作為 review / planning 邊界參考，但不得單獨取代正式 plan / audit / schema / validator 規則。

#### Step 4 Exit Checklist（Machine-Scannable）
```yaml
ExitChecklistStep: 4
ExitChecklistVersion: v2.0.1
ExitChecklistOwner: <ai-or-human-role>
ExitChecklistVerdict: PASS|FAIL|N/A
```
- [ ] completion report 已建立
- [ ] milestone 摘要已建立
- [ ] index 同步完成（version/workflow）
- [ ] Step4 MCP 3頁驗證證據存在
- [ ] completion claim 與 remote evidence 一致

## 6. Import Model（給繼承專案）
能力名稱：`operate_maintain_workflow_v2`

規則：
1. 繼承專案可選擇是否匯入。
2. 未匯入時，不必提供 ops-registry/ops-version 能力。
3. 匯入後，必須遵守本文件 Step1~4 所有 MUST 規則。

## 7. 狀態列舉（Canonical Enums）
- `PLANNED`
- `UNVERIFIED`
- `COMPLETED_STEP1`
- `BRIDGE_ONLY`
- `COMPLETED`

## 8. 違規處置
1. 缺 Step1 index 追加：`Step1 FAIL`。
2. Step2 使用 non-remote run_ref：`Hard FAIL`。
3. completion claim 無 evidence：`Hard FAIL`。
4. index/頁面資料不一致：`Process Non-Compliance`，必須先修復再繼續。
