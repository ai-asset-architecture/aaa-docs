# AI Bootstrap (Single Entry Point)
> 遠端 AI 的單一入口文件，僅保留「必須知道」的最小內容。

## 🚦 Hard-Lock (Minimal)
> 必須遵循的四條最小規則（完整條款見 `bootstrap/agent_governance_rules.md`）。

1. **Preflight**: 每個 session 只讀一次規則文件；規則變更才重讀。
2. **Mandatory Load**: 依 Preflight 規則讀取必讀文件。
3. **Evidence Mode**: 結論必須標註來源。
4. **Fail-Closed**: 缺少必要規格即停止並輸出缺口清單。

## 1. Remote AI Bootstrap (Minimal)
> 只保留「必須知道」的最小內容，其餘細節請依指引文件執行。

### 1.1 選擇本機路徑
- 建議建立獨立工作資料夾（例：`~/AAA_WORKSPACE_REMOTE`）。

### 1.2 讀取入口文件
- `bootstrap/ai_bootstrap.md`
- `bootstrap/workspace_architecture.md`

### 1.3 建立互動環境
- MCP：`bootstrap/mcp_connection_guide.md`
- CLI：`bootstrap/cli_connection_guide.md`

### 1.4 初始化與接管
- 初始化請走 CLI：`bootstrap/remote_ai_quickstart.md`
- MCP 目前只支援 `check/audit`（無 init）。

### 1.5 Init DoD Checklist
- `bootstrap/init_dod_checklist.md`

### 1.6 操作 / 維護指南
- `bootstrap/operate_maintain_guide.md`

## 2. Mandatory Knowledge Loading (Pre-flight)
**每個 session 只讀一次**；僅在規則變更時再讀。

在執行任何計畫或編碼前，**必須**讀取：
- `bootstrap/workspace_architecture.md` (基礎架構)
- `../aaa-tpl-docs/AI_COMMAND_CENTER.md`
- `../aaa-tpl-docs/PROJECT_PLAYBOOK.md` (專案憲法)

## 3. Guides Index (bootstrap/)
- `bootstrap/remote_ai_quickstart.md`
- `bootstrap/mcp_connection_guide.md`
- `bootstrap/cli_connection_guide.md`
- `bootstrap/init_dod_checklist.md`
- `bootstrap/operate_maintain_guide.md`
- `bootstrap/agent_governance_rules.md`

---
*Last updated: 2026-01-30 (Bootstrap Re-org)*
