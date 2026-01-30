# AI Context Configuration
> 本文件為 AI Agent（Codex/Antigravity）在 AAA 工作區的核心行為準則（AI Constitution）。

## 🚦 MANDATORY: 4-Step Hard-Lock Protocol (v2.0.1+)
> 為絕不再次違反治理紀律，Agent 在處理任何治理/規格輸出時 **必須** 執行以下機械化流程：

1. **Preflight**: **每個 session 只讀一次**此檔案（`.ai-context.md`）確認當下規則；**僅在規則變更時再讀**。
2. **Mandatory Load**: 依 Preflight 規則讀取 `AI_COMMAND_CENTER.md` + `PROJECT_PLAYBOOK.md`（每個 session 一次；或規則變更時再讀）。
3. **Evidence Mode**: 所有的結論與輸出 **必須** 標註原文引用（Cite Source Lines），禁止任何模糊引用。
4. **Fail-Closed**: 若缺少必要的模板、規格或 Roadmap 內容，**禁止硬寫**。Agent 必須立即暫停並輸出「缺口清單 (Gap List)」。

> [!IMPORTANT]
> **Workflow Primacy Rule (Antigravity Mode)**:
> While operating in this workspace, the AI (Antigravity) MUST **IGNORE** its default system-generated `implementation_plan.md` and `task.md` artifacts when preparing for features or functions.
> 1.  You are **REQUIRED** to use the human-defined workflow in this document (Section 2: 3-Step Milestone Lifecycle).
> 2.  All plans, tasks, and audits MUST be written to the `aaa-tpl-docs` directory as specified, NOT the default `.gemini/brain` directory.
> 3.  Adherence to this rule is the highest-priority constraint. Any deviation triggers a Step 4 (Fail-Closed) event.

## 1. Single Entry: Remote AI Bootstrap (Minimal)
> 本段只保留「必須知道」的最小內容，其餘細節請依指引文件執行。

### 1.1 選擇本機路徑
- 建議建立獨立工作資料夾（例：`~/AAA_WORKSPACE_REMOTE`）。

### 1.2 讀取入口文件
- `bootstrap/AI_CONSTITUTION.md`
- `bootstrap/WORKSPACE_ARCHITECTURE.md`

### 1.3 建立互動環境
- MCP：`bootstrap/mcp-connection-guide.md`
- CLI：`bootstrap/cli-connection-guide.md`

### 1.4 初始化與接管
- 初始化請走 CLI：`bootstrap/remote-ai-quickstart.md`
- MCP 目前只支援 `check/audit`（無 init）。

### 1.5 Init DoD Checklist
- `bootstrap/init-dod-checklist.md`

### 1.6 操作 / 維護指南
- `bootstrap/operate-maintain-guide.md`

## 2. Mandatory Knowledge Loading (Pre-flight)
**每個 session 只讀一次**；僅在規則變更時再讀。

在執行任何計畫或編碼前，**必須**讀取：
- `bootstrap/WORKSPACE_ARCHITECTURE.md` (基礎架構)
- `../aaa-tpl-docs/AI_COMMAND_CENTER.md`
- `../aaa-tpl-docs/PROJECT_PLAYBOOK.md` (專案憲法)

## 3. Guides Index (bootstrap/)
- `bootstrap/remote-ai-quickstart.md`
- `bootstrap/mcp-connection-guide.md`
- `bootstrap/cli-connection-guide.md`
- `bootstrap/init-dod-checklist.md`
- `bootstrap/operate-maintain-guide.md`

---
*Last updated: 2026-01-30 (Bootstrap Re-org)*
