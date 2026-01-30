# MCP Connection Guide
> 遠端 AI 使用 MCP 的最小可行連線說明。

## 1. 安裝與啟動
- 前置依賴（MCP SDK）：`pip install mcp`
- 安裝（Repo 模式）：`pip install -e aaa-tools`
- 啟動（Python）：`python -m aaa.mcp_server`

## 2. MCP Tool 清單（現況）
- `aaa_check`：執行治理檢查，回傳語義化診斷結果。
- `aaa_audit`：產出治理稽核報告（LLM 可讀格式）。

## 3. MCP 回傳格式（LLM）
> MCP 回傳為 JSON，核心欄位為 `report`（LLM 格式字串），並包含 init 提示欄位。

```json
{
  "report": "<LLM-formatted report>",
  "post_init_required": ["aaa init repo-checks --suite governance"],
  "post_init_purpose": "post-init governance validation"
}
```

**MCP 真實輸出範例（節錄）**
```json
{
  "report": "# AAA CHECK Technical Report\nStatus: **SUCCESS**\n\n## Summary\nCommand completed successfully.",
  "post_init_required": ["aaa init repo-checks --suite governance"],
  "post_init_purpose": "post-init governance validation"
}
```

## 4. Tool 參數 / 範例
- 參數（共用）
  - `path`（可選，預設 "."）：目標 Repo 路徑。
- 範例
  - `aaa_check(path=".")`
  - `aaa_audit(path=".")`

## 5. 初始化限制
- MCP 目前不含 `init`；初始化請走 CLI。

## 6. 建議使用順序
1. 先用 CLI 完成初始化與 repo-checks。
2. 再用 MCP 執行 `aaa_check` / `aaa_audit` 作為驗證與監控。
