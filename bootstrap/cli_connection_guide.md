# CLI Connection Guide
> 遠端 AI 使用 CLI 的最小可行操作說明。

## 1. 安裝
- `pip install -e aaa-tools`

## 2. 初始化（DoD）
- `aaa init`
- `aaa init repo-checks --suite governance`

## 3. 基礎檢查（建議）
- `aaa check`
- `aaa audit`

## 4. LLM 格式輸出
- `aaa check --format llm`
- `aaa audit --format llm`

**CLI 真實輸出範例（節錄）**
```text
# AAA CHECK Technical Report
Status: **SUCCESS**

## Summary
Command completed successfully.
```

```text
# AAA AUDIT Technical Report
Status: **SUCCESS**

## Summary
Command completed successfully.
```
