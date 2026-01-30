# CLI Connection Guide
> 遠端 AI 使用 CLI 的最小可行操作說明。

## 1. 安裝
- `git clone https://github.com/ai-asset-architecture/aaa-tools.git`
- `pip install -e aaa-tools`

## 1.1 執行位置
- CLI 指令需在「目標 repo 根目錄」執行。

## 2. 初始化（DoD）
- `aaa init`
- `aaa init repo-checks --suite governance`

## 3. 基礎檢查（建議）
- `aaa check`
- `aaa audit`

## 4. LLM 格式輸出
- `aaa check --format llm`
- `aaa audit --format llm`

## 5. 繼承既有專案（範例）
- `git clone <TARGET_REPO_URL>`
- `cd <TARGET_REPO_DIR>`
- `aaa init repo-checks --suite governance`

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
