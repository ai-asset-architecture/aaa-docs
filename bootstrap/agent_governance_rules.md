# Agent Governance Rules (Full)
> 完整 Hard-Lock 規則與行為限制。此文件為內規全文，入口僅保留最小版。

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
