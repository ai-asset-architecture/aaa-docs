# Remote AI Quickstart (Local Init)
> 最短路徑：讓遠端 AI 在本機完成 AAA 初始化與治理驗證。

## 1. 選擇本機路徑
- 建議建立獨立工作資料夾（例：`~/AAA_WORKSPACE/projects/`）。

## 1.1 前置條件
- 已安裝 `git`、`python3`、`pip`

## 2. 讀取入口文件
- `bootstrap/ai_bootstrap.md`
- `bootstrap/workspace_architecture.md`

## 3. 建立互動環境
- MCP：`bootstrap/mcp_connection_guide.md`
- CLI：`bootstrap/cli_connection_guide.md`

## 4. 初始化流程（CLI）
1. 建立工作區：
   - `mkdir -p ~/AAA_WORKSPACE/projects`
   - `cd ~/AAA_WORKSPACE/projects`
2. 取得工具：
   - `git clone https://github.com/ai-asset-architecture/aaa-tools.git`
   - `pip install -e aaa-tools`
3. 初始化新專案：
   - `aaa init`
4. 治理驗證（必做）：
   - `aaa init repo-checks --suite governance`

> MCP 目前不含 init；初始化請走 CLI。

## 5. 初始化後（可選）
- MCP 可用於：`aaa_check` / `aaa_audit`
- CLI 可用於：`aaa check --format llm` / `aaa audit --format llm`

## 5.1 繼承既有專案（GitHub AAA）
1. 取得既有 repo：
   - `git clone <TARGET_REPO_URL>`
   - `cd <TARGET_REPO_DIR>`
2. 套用治理驗證：
   - `aaa init repo-checks --suite governance`
3. 健康檢查：
   - `aaa check --format llm`
   - `aaa audit --format llm`

## 6. Init DoD
- 請依 `bootstrap/init_dod_checklist.md` 確認完成。

## 7. 操作 / 維護
- 參考 `bootstrap/operate_maintain_guide.md`
