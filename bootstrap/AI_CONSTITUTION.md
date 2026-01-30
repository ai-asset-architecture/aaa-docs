# AI Context Configuration
> 本文件為 AI Agent（Codex/Antigravity）在 AAA 工作區的核心行為準則（AI Constitution）。

## 1. Mandatory Knowledge Loading (Pre-flight)
**每個 session 只讀一次**；僅在規則變更時再讀。

在執行任何計畫或編碼前，**必須**讀取：
- `bootstrap/WORKSPACE_ARCHITECTURE.md` (基礎架構)
- `../aaa-tpl-docs/AI_COMMAND_CENTER.md`
- `../aaa-tpl-docs/PROJECT_PLAYBOOK.md` (專案憲法)

## 2. Features/Milestone Development Lifecycle Workflow (vx.y)
任何版本 (vx.y) 的開發必須遵循以下四個步驟（4-Step Lifecycle）(ps: this workflow is used on AAA develpment, also welcome remote user AI to leverage)。

> **⚠️ 嚴格執行紀律 (Strict Discipline)**：
> 1.  **禁止有損壓縮 (No Lossy Compression)**：在建立 `task.md` 時，嚴禁將下方列出的任何交付項目「合併」或「簡化」。每一項要求（如「摘要文件」與「詳細報告」）都必須轉換為獨立的 Checkbox。
> 2.  **分段批准 (Step-by-Step Approval)**：每完成一個步驟 (Step 1 / 2 / 3 / 4)，**必須暫停 (STOP)**，向指揮官回報該步驟的總結，並等待獲得明確批准後，才可進入下一個步驟。
> 3.  **全域一致性檢查 (Full-File Consistency)**：當更新具有多重視圖（如 Summary List + Detail Table）的文件（例如 Roadmap）時，**必須**執行全文掃描，確保所有相關區塊皆同步更新。遺漏任何一處皆視為嚴重失誤。


### Step 1: Initialization (啟動與追蹤)
1) **Required Output Files** (Naming + Location)
   - **Implementation Plans**: `../aaa-tpl-docs/internal/development/plans/YYYY-MM-DD-<feature>-plan.md`
   - **Validation Audits**: `../aaa-tpl-docs/internal/development/audits/YYYY-MM-DD-<name>.md`
   - **Naming Rule**: Filenames must match the patterns above (strict).

2) **Debt Check (Stop the Line)**
   - Before starting new features, ensure Core Component coverage > 90%.
   - If < 80%, **STOP** and repay debt first.

3) **一致性要求 (Consistency Policy)**
   - **Audit Coverage (1+2+1)**: **每份 Audit 必須涵蓋** 1 個 Happy Path + 2 類 Edge Cases + 1 類 Negative Case（方向覆蓋，不代表最少數量）。
   - **Format (Audit Files)**: **必須** 依 `../aaa-tpl-docs/internal/development/audits/` 目錄內**既有檔案格式**撰寫（標題、Task/Objective/Status、Executive Summary/證據段落等），不得自創簡化格式。

4) **Format (Plan) Template**
   - **必須** 使用以下 `<template id="plan">`：
     ```markdown
     <template id="plan">
     # Implementation Plan: {Milestone} {Title}

     ## Goal Description
     {Brief description of what and why}

     ## User Review Required
     > [!IMPORTANT]
     > {Critical decisions, standards, or breaking changes}

     ## Proposed Changes
     ### [{repo-name}]
     #### [NEW/MODIFY] {path/to/file}
     - {Description of change}

     ## Triple-Summary Protocol ({Milestone})
     ### 1. Strategic Plan (戰略計畫摘要)
     ### 2. Schema Evolution (結構演進摘要)
     ### 3. Component Architecture (組件架構摘要)

     ## Verification Plan
     ### Automated Tests
     ### Manual Verification
     </template>
     ```
   - **通訊**: 計畫必須包含 **Triple-Summary Protocol**（concise, architectural focus）。

5) **Format (Audit) Template**
   - **必須** 使用以下 `<template id="validation-audit">`：
     ```markdown
     <template id="validation-audit">
     # Validation Audit: {Milestone} {Title}

     ## Metadata
     *   **Milestone**: {vX.Y}
     *   **Release Name**: {Name}
     *   **Status**: {PENDING|COMPLETED}
     *   **Date**: {YYYY-MM-DD}
     *   **Auditor**: {Name/Role}

     ## 1. Executive Summary
     {What is being validated and why}

     ## 2. Audit Evidence (Baseline)
     ### A. Governance Checks (Current State)
     *   **Local Checks**: {PASS/PENDING}
     *   **Debt Check**: {PASS/PENDING} (include counts if available)

     ### B. New Feature Verification (Final)
     | Feature | Success Criteria | Status |
     | :--- | :--- | :--- |
     | {Feature} | {Criteria} | {PASS/PENDING/FAIL} |

     ## 3. Test Coverage (1+2+1 Directional)
     **Requirement**: Cover 1 Happy Path + 2 Edge Case categories + 1 Negative category (directional coverage, not minimum count).
     - [ ] **Happy Path (1)**: {case}
     - [ ] **Edge Case (2)**: {category + cases}
     - [ ] **Edge Case (2)**: {category + cases}
     - [ ] **Negative Case (1)**: {category + cases}

     ## 4. Test Case Inventory (Full List)
     | ID | Scenario | Type (Happy/Edge/Negative) | Status | Evidence |
     | :--- | :--- | :--- | :--- | :--- |
     | T-001 | {description} | {type} | {PASS/PENDING/FAIL} | {path or log ref} |

     ## 5. Next Steps
     1. {step}
     2. {step}
     3. {step}
     </template>
     ```

### Step 2: Implementation (執行與驗證)
- **前置條件**: **只有在 Step 1 計畫獲得批准後**才能開始寫/改任何程式碼或文件。
- **執行內容**: 所有實作、bug 修復、不確定議題澄清、測試與最終驗證都屬於 Step 2。
- **證據要求**: 每一項實作結果都必須在對應 Audit 中留下可追溯證據。

### Step 3: Asset Preservation (資產保存)
- **Goal**: 確保每次迭代都累積可復用的價值 (Reusable Value)。
- **Mandatory Value Check (價值檢查)**:
  - 結案前 **必須** 盤點產出的 Evals, Templates, Policy Packs, Tools。
  - **Zero-Asset Trap**: 如果清單為空，**禁止結案**，除非提供明確的 Reasoning (Justification)。
- **Action**: **必須**將其註冊至對應的資產目錄 (Catalog) 或 `ai-asset-architecture-registry/registry_index.json`。
- **Nightly Promotion Criteria**:
  - Promote tests that cover **Critical User Flows** or **Core Logic** (>20% impact).
  - Do **NOT** promote trivial UI tests or flaky tests.
- **產出**: 在結案報告 template 中填寫 `Asset Preservation` 章節。

### Step 4: Completion Documentation (結案存檔)
- **要求**: 當版本項目的完成度達到 100% 時，**必須**產出兩份正式文件：
  - **摘要文件**: `../aaa-tpl-docs/milestones/YYYYMMDD_vX.Y_<name>.md`
  - **詳細報告**: `../aaa-tpl-docs/internal/development/milestones/completion-reports/aaa_vX.Y_completion_report_YYYYMMDD.md`
- **一致性要求 (Consistency Policy)**:
  - **Naming**: 檔案命名必須嚴格參考目標資料夾內既有文件的命名慣例。
  - **Format (Completion Reports)**: **必須** 依 `../aaa-tpl-docs/internal/development/milestones/completion-reports/` 目錄內**既有檔案格式**撰寫，確保與既有結構一致。
  - **Format (Template)**: **必須** 使用以下 `<template id="completion-report">`：
    ```markdown
    <template id="completion-report">
    # Milestone Completion Report: {Milestone} {Title}

    ## Metadata
    *   **Milestone**: {vX.Y}
    *   **Release Name**: {Name}
    *   **Status**: COMPLETED
    *   **Date**: {YYYY-MM-DD}
    *   **Hash**: {Commit Hash}

    ## 1. Executive Summary
    {High-level achievement summary}

    ## 2. Deliverables Status
    ### A. {Component Area}
    | Component | Function | Status | Coverage |
    | :--- | :--- | :--- | :--- |
    | `{path}` | {desc} | ✅ Done | {N}% |

    ## 3. Verification Evidence
    *   **Snapshot Tests**: ...
    *   **Unit Tests**: ...
    *   **Manual Verification**: ...

    ## 4. Asset Preservation (Nightly Candidates)
    1.  `{test_path}` ({reason})

    ## 5. Next Steps
    *   **{Next Version}**: ...
    *   **Backlog**: ...
    </template>
    ```

## 3. MCP 連線指南（Remote AI Entry）
> 本段為「遠端 AI」的第一入口指引，提供最低可用的 MCP 連線資訊。

### 3.1 建議入口（MCP）
- **前置依賴（MCP SDK）**：`pip install mcp`
- **安裝（Repo 模式）**：`pip install -e aaa-tools`
- **啟動（Python）**：`python -m aaa.mcp_server`
- **用途**：AI 透過 MCP 進行治理互動與資產查詢。

### 3.1.1 MCP Tool 清單（現況）
- `aaa_check`：執行治理檢查，回傳語義化診斷結果。
- `aaa_audit`：產出治理稽核報告（LLM 可讀格式）。

### 3.1.2 MCP Tool 使用參數 / 範例
- **參數**（共用）
  - `path`（可選，預設 `"."`）：目標 Repo 路徑。
- **範例**
  - `aaa_check(path=".")`
  - `aaa_audit(path=".")`

### 3.2 MCP 客戶端讀取（必要）
- **必讀資源**（使用 MCP `read_resource`）：  
  - `bootstrap/AI_CONSTITUTION.md`  
  - `bootstrap/WORKSPACE_ARCHITECTURE.md`  
  - `index.json`  

### 3.3 退路（CLI Fallback）
- 若 MCP 不可用：使用 CLI `aaa init` 進行初始化，再補跑 `aaa init repo-checks --suite governance`。

## 4. CLI 連線指南（Remote AI Entry）
> 本段為「遠端 AI」的 CLI 最小可用流程，確保無 MCP 也能完成初始化與治理驗證。

### 4.1 安裝（Repo 模式）
- `pip install -e aaa-tools`

### 4.2 最小指令流程（DoD）
- `aaa init`
- `aaa init repo-checks --suite governance`

### 4.3 基礎檢查（建議）
- `aaa check`
- `aaa audit`

## 5. Agent Behavior Profile

### Mode: ARCHITECT (Planning Phase)
- **Primary Goal**: Cross-repo consistency & long-term stability.
- **Mandatory Action**: Draft implementation plans to `internal/development/plans/` first.
- **Constraint**: No implementation until plan approval.

### Mode: BUILDER (Implementation Phase)
- **Primary Goal**: Solid implementation & automated verification.
- **Mandatory Action**: Record proof-of-work/audit evidence to `internal/development/audits/`.
- **Constraint**: Follow 1+2+1 Test Coverage Rule.

## 6. Single Source of Truth (SSOT)
- **Registry**: `ai-asset-architecture-registry/registry_index.json`
- **Assets**: All metadata must be indexed in `internal/index.json`.

---
*Last updated: 2026-01-29 13:25 (Split Release)*
