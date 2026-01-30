# Remote AI Quickstart (Local Init)
> 最短路徑：讓遠端 AI 在本機完成 AAA 初始化與治理驗證。

## 1. 選擇本機路徑
- 建議建立獨立工作資料夾（例：`~/AAA_WORKSPACE_REMOTE`）。

## 2. 讀取入口文件
- `bootstrap/ai_bootstrap.md`
- `bootstrap/workspace_architecture.md`

## 3. 建立互動環境
- MCP：`bootstrap/mcp_connection_guide.md`
- CLI：`bootstrap/cli_connection_guide.md`

## 4. 初始化流程（CLI）
1. 安裝：`pip install -e aaa-tools`
2. 初始化：`aaa init`
3. 治理驗證：`aaa init repo-checks --suite governance`

> MCP 目前不含 init；初始化請走 CLI。

## 5. 初始化後（可選）
- MCP 可用於：`aaa_check` / `aaa_audit`
- CLI 可用於：`aaa check --format llm` / `aaa audit --format llm`

## 6. Init DoD
- 請依 `bootstrap/init_dod_checklist.md` 確認完成。

## 7. 操作 / 維護
- 參考 `bootstrap/operate_maintain_guide.md`
