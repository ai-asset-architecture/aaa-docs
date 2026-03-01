# Ops Version Detail

## Route
- `/ops-version/<version>?lang=zh-TW`

## Canonical Source
- `aaa-tpl-docs/version_index.md`

## Response Contract
- `docs/contracts/ops_version_detail_response.v0.1.schema.json`

## Notes
1. 版本詳情由 versions index 單筆展開，不另建平行 version truth。
2. 若查無版本，回應 `item = null` 並保留來源與更新時間欄位。
