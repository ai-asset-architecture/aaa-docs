# Ops Registry: Versions

## Route
- `/ops-registry?tab=versions&lang=zh-TW`

## Canonical Source
- `aaa-tpl-docs/ops/index/version_index.md`

## Response Contract
- `docs/contracts/ops_registry_versions_response.v0.1.schema.json`

## Row Contract
- `docs/contracts/ops_version_index_row.v0.1.schema.json`

## Notes
1. 此頁為 index 原始資料的讀取視圖，不可私自引入平行來源。
2. 新版本在 Step1 即必須追加 `version_index.md` 對應行。
3. Step2 完成後需回填 remote `run_ref` 與 evidence。
