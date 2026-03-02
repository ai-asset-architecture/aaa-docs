# Ops Version Detail

## Route
- `/ops-version/<version>?lang=zh-TW`

## Canonical Source
- `aaa-tpl-docs/ops/index/version_index.md`

## Response Contract
- `docs/contracts/ops_version_detail_response.v0.1.schema.json`

## Notes
1. 版本詳情由 versions index 單筆展開，不另建平行 version truth。
2. 若查無版本，回應 `item = null` 並保留來源與更新時間欄位。
3. 回應必含 `steps.step1~steps.step4`，前端可直接渲染每步 `present/artifacts/artifact_count`。
4. `availability` 欄位為 `可用性驗證` 的 key-value 展開（如 `run_ref`, `evidence`, `criteria`, `note`）。
