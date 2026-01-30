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

## 6. `aaa init interactive`（互動式 Policy Wizard）
> 互動式建立治理 Policy，**不**等同於專案初始化。

### 6.1 啟動
- `aaa init interactive`

### 6.2 互動流程（提示）
- Policy Name（預設 `my-repo-policy`）
- Version（預設 `1.0.0`）
- Add a rule?（可多次新增規則）
  - Rule ID（例：`readme_exists`）
  - Description
  - Check Type（`file_exists` / `content_contains` / `json_match`）
  - File Path / Pattern / Key Path / Expected Value（依 check 類型）
  - Severity（`blocking` / `high` / `medium` / `low`）

### 6.3 輸出
- YAML 檔：`<policy_name>.yaml`（需要 `pyyaml`）
- Python 檢查腳本：`check_<policy_name>.py`（可選擇是否編譯）

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
