# AAA Operate Maintain Guide Leverage Matrix

## Summary
本文件整理：
- source：`/Users/imac/Documents/Code/AI-Lotto/Lamaco/Lamaco_show_DN/docs/operate_maintain_guide.md`
- target：`aaa-docs/bootstrap/operate_maintain_guide.md`

目的不是整份搬移 Lamaco guide，而是收斂出：
- `直接建議吸收`
- `縮小後吸收`

判準固定如下：
- 只吸收對 AAA top guide 有長期治理價值的 law / guard rail
- 不搬 Lamaco 專案專屬 artifact path、page shape、registry shape
- 不讓 AAA top guide 膨脹成 Lamaco 專屬執行手冊

## Directly Recommended

### 1. Machine-Parseable Truth Priority
**建議**  
直接吸收為 AAA top guide 的 `Strict Discipline` 條目。

**Lamaco 核心價值**  
- guide MUST + gate parser 高於人類敘述
- 截圖 / proof / checklist / narrative 不得取代 machine-checkable 結構

**為何適合 AAA**  
- AAA 已有 machine-checkable workflow 與 evidence 語言
- 但目前缺少「當 parser 與文字敘述衝突時誰優先」的硬法條

**建議收斂語句**
- `若 guide MUST、schema/gate parser、與人類可讀敘述不一致，以 guide MUST + machine-checkable parser 為最高真相。`
- `截圖、proof、checklist、completion narrative 不得單獨取代 machine-checkable completion evidence。`

**吸收層級**  
AAA top guide 直接增補。

---

### 2. Generated Artifact Shape Verification
**建議**  
直接吸收為 AAA top guide 的 generated artifact preflight law。

**Lamaco 核心價值**  
- 讀 generated JSON / registry artifact 前，先檢查 top-level keys 與 schema/type
- 不得先猜欄位名再做診斷

**為何適合 AAA**  
- AAA 大量依賴：
  - `version_index` / `workflow_index`
  - registry artifacts
  - evidence bundles
  - package runtime payloads
- 若不先驗 shape，後面很容易產生無效診斷

**建議收斂語句**
- `讀取 generated artifact 前，必須先確認 top-level keys 與對應 schema/type；不得直接假設欄位結構。`
- `使用未定義欄位名做出的 ad hoc 診斷，不得作為 current truth 或 failure claim 依據。`

**吸收層級**  
AAA top guide 直接增補。

---

### 3. Step2 Scarcity Governance
**建議**  
直接吸收為 AAA top guide 的 Step2 稀缺治理法。

**Lamaco 核心價值**  
- Step2 是稀缺治理配額，不是每版自動擁有
- 預設優先 bridge-only、bundled execution、carrier reuse

**為何適合 AAA**  
- AAA 版本數量已高，若每版都開新 workflow，後續 CI / workflow 會快速膨脹
- 這條能幫 AAA 保住：
  - Step2 eligibility discipline
  - bundled execution discipline
  - workflow minimization

**建議優先吸收子條目**
- `Step2 Eligibility Policy`
- `Bundled Execution Policy`
- `Budget-Aware Versioning Policy`
- `Step2 Carrier Reuse Policy`

**建議收斂語句**
- `擬進 Step2 的版本必須先回答：為何不能 bridge-only、為何不能重用既有 execution carrier、為何不能被 bundled execution 吸收。`
- `Step2 run_ref 合法不等於每版都可新增專屬 workflow。`

**吸收層級**  
AAA top guide 直接增補，但以 AAA 用語重寫，不照搬 Lamaco artifact 細節。

---

### 4. Step4 Checklist Tiering
**建議**  
直接吸收為 AAA top guide 的 Step4 checklist 治理分級。

**Lamaco 核心價值**  
將 Step4 item 分成：
- `ALWAYS_ON_MUST`
- `CONDITIONAL_MUST`
- `REVIEW_SAMPLED`

**為何適合 AAA**  
- AAA 剛調整過 Step4 MCP 頁面數，代表 Step4 item 的訊號強度確實需要治理
- 這條可防止 checklist 膨脹與低訊號強制項長期殘留

**建議收斂語句**
- `Step4 checklist item 必須分級；非不可替代的 closeout 真相檢查，不得預設進 ALWAYS_ON_MUST。`

**吸收層級**  
AAA top guide 直接增補。

---

### 5. Guide Patch Threshold
**建議**  
直接吸收為 AAA top guide 的修法閾值。

**Lamaco 核心價值**  
不是每個 recurring issue 都改 top guide，只有高權威法條才值得升格。

**為何適合 AAA**  
- AAA guide 已在擴長
- 若沒有 threshold，後續所有 recurring issue 都會想往 top guide 塞

**建議收斂語句**
- `只有 truth precedence、closeout sequence、shared validator/contract law、或 guide-level promotion law 類問題，才可直接升格為 top guide patch。`
- `其餘 recurring issue 預設優先進 register / checklist / validator / schema。`

**吸收層級**  
AAA top guide 直接增補。

---

### 6. Single Review Artifact Rule
**建議**  
直接吸收為 AAA 的 post-closeout review hygiene。

**Lamaco 核心價值**  
每次 closeout 後只保留一份 post-closeout review artifact，避免 review note 鏈條膨脹。

**為何適合 AAA**  
- AAA 已有 review / audit / completion / interpretation 類文件
- 若沒有這條，後續 calibration / follow-up 很容易拆成多段中介文件

**建議收斂語句**
- `每次 4-step closeout 後，只允許一份 post-closeout review artifact 承載 lesson learned、follow-up decision、與必要 appendix。`

**吸收層級**  
AAA top guide 或 closeout review sub-spec 直接增補。

## Absorb In Reduced Form

### 1. UI Validation Tool Policy
**建議**  
縮小後吸收，不直接搬工具名治理。

**Lamaco 可借點**
- default tool / fallback tool / exception reason 的三段式治理

**AAA 不宜直接搬的部分**
- 不應直接把 `Playwright` / `MCP Chrome DevTools` 的 Lamaco-specific 優先序原封不動塞進 AAA top guide

**AAA 建議縮寫方向**
- `UI validation evidence 必須有 primary tool、fallback tool、與 exception reason 的明示欄位。`

---

### 2. Bridge Visibility Package
**建議**  
縮小後吸收為 bridge-only visible consumer surface law。

**Lamaco 可借點**
- bridge-only 版本若要 page-visible，需要額外 visibility package
- version-side visibility 與 workflow-side visibility 必須分開

**AAA 不宜直接搬的部分**
- 不應直接搬 Lamaco 的：
  - `version_index.ai.v0.1.jsonl`
  - `public/ops/registry/...`
  - 專案專屬 dashboard artifact path

**AAA 建議縮寫方向**
- `bridge-only 版本若要求 consumer-visible surface，plan/audit 必須顯式定義 bridge visibility package，且不得自動擴張到 workflow-side active registry。`

---

### 3. Calibration Register Authority
**建議**  
縮小後吸收為 recurring issue register discipline。

**Lamaco 可借點**
- recurring failure 不應只留在 review note
- register entry 應有固定欄位與 promotion target

**AAA 不宜直接搬的部分**
- 不宜一次整包引入 Lamaco 的完整 calibration framework 與所有條文

**AAA 建議縮寫方向**
- 先只吸收：
  - recurring issue 要進 register
  - register mutation 要有固定欄位
  - `ABSORBED` 不得只代表「大家知道了」

---

### 4. Post-Closeout Interpretation Gate
**建議**  
縮小後吸收為 interpretation boundary law。

**Lamaco 可借點**
- interpretation authority 可以存在
- interpretation note 不得自動授權新版本擴張

**AAA 不宜直接搬的部分**
- 不宜照抄 Lamaco 的具體 judgment 檔、version family、或 boundary wording

**AAA 建議縮寫方向**
- `post-closeout interpretation artifact 只能限制外推邊界，不得自動授權新 runtime family 或新 version line。`

## Recommended Adoption Order
若 AAA 只先補最有 ROI 的項目，建議順序固定如下：
1. `Machine-Parseable Truth Priority`
2. `Generated Artifact Shape Verification`
3. `Step2 Scarcity Governance`
4. `Step4 Checklist Tiering`
5. `Guide Patch Threshold`
6. `Single Review Artifact Rule`

## Non-Goals
本 leverage matrix 明確不做：
- 不直接改寫 AAA top guide
- 不把 Lamaco guide 整份搬進 AAA
- 不引入 Lamaco 專案專屬 registry/build/runtime 路徑
- 不在本文件中宣告哪些條文已批准入版

## Next Use
這份 matrix 的用途是：
- 作為後續 `operate_maintain_guide.md` 修法的吸收清單
- 幫 reviewer 區分：
  - `直接建議吸收`
  - `縮小後吸收`
- 避免後續再次回頭全量 deep dive Lamaco guide
