# AAA Lite / Core / Full Inheritance Package Definition Skeleton

> 目的：定義 AAA 對 remote client 提供的可繼承 package 分級骨架。  
> 適用對象：AAA 核心團隊、方案設計者、客戶導入顧問、AI agents。  
> 文件性質：inheritance-package-layer skeleton，不是 version line、roadmap 或 import tier。  
> 生效前提：本文件可在 `v2.1.19` 之後進入正式化；`v2.1.20 ~ v2.1.22` 是否完成，不影響本 skeleton 的成立。

---

## 1. Positioning

### 1.1 定義

`AAA Lite / Core / Full` 是 **AAA 提供給 remote client 的 inheritance packages 分級**。

它回答的問題是：

- AAA 提供哪一層可繼承能力包
- remote client 要承接哪些治理責任
- AAA inheritance package 應帶哪些 repo / workflow / governance / runtime 組件
- remote client 會落在哪一種導入深度

它**不回答**：

- AAA 下一版做什麼
- `v2.1.xx` roadmap 如何排序
- 哪個版本先進 Step2 / Step3 / Step4

### 1.2 與版本線的關係

- `v2.1.1 ~ v2.1.19`：建立 AAA 的 core absorption line
- `v2.1.20 ~ v2.1.22`：conditional expansion
- `Lite / Core / Full`：在核心能力面穩定後，用已完成能力面做切片的 inheritance package layer

固定原則：

- version line = build AAA
- inheritance package layer = package AAA for remote client inheritance

---

## 2. Classification Axis

### 2.1 正式主軸

`Lite / Core / Full` **按導入深度分級**。

能力範圍只作為各級結果說明，不作第一分類軸。

### 2.2 級別語義

- `Lite` = bootstrap-ready
- `Core` = governance-ready
- `Full` = operating-base-ready

### 2.3 Cumulative Rule

inheritance package 預設為 cumulative：

- `Core = Lite + governance/runtime base additions`
- `Full = Core + operating-base additions`

### 2.4 Packaging Rule

inheritance package 以 **enablement bundle 為主、deliverable bundle 為輔**。

也就是說，AAA 的主要價值不是丟給客戶一批模板，而是讓客戶團隊能承接：

- governance discipline
- AI collaboration boundary
- reusable asset flow
- long-term project base

---

## 3. Offering Definitions

### 3.1 AAA Lite

**定位**  
`Bootstrap Package`

**適用客戶**

- 新專案剛起步
- 團隊治理能力尚弱
- 先求可啟動、可協作、可交付
- 不要求完整 runtime / governance 閉環

**remote client 繼承後得到什麼**

- 可啟動的新專案骨架
- 最小協作秩序
- AI 可受控進場
- 最小文件 / 模板 / workflow baseline

**建議最小 repo 組合**

- `.github`
- `aaa-tpl-service` 或對應 vertical template repo
- `aaa-actions`
- `aaa-tools`
- `aaa-tpl-docs` 的裁切導入素材

**包含能力**

- repo bootstrap
- AI context loading baseline
- `AI_COMMAND_CENTER` / `PROJECT_PLAYBOOK` baseline
- PR / issue / CODEOWNERS / branch protection baseline
- contract-first / mock-first 的最小導入說明
- candidate asset area

**不包含**

- 完整 `operate_maintain_workflow_v2`
- 完整 eval governance
- delegation / extension runtime adoption
- session persistence / recovery / normalized result 的完整 runtime plane
- remote / external resource / operator product surface

**remote client 承接前提**

- 願意遵守最小 PR discipline
- 願意接受 template + playbook 的基本約束
- 至少能維持基本 CI

**一句話定位**

讓 remote client 不要從零開始造輪子，但不要求立刻成為高度治理化團隊。

---

### 3.2 AAA Core

**定位**  
`Governance Runtime Base Package`

**適用客戶**

- 不只想快速啟動，還要可持續開發
- 已有基本工程節奏
- 願意導入 contract-first / mock-first / QA / evidence discipline
- 希望 AI 協作不只是輔助，而是可治理

**remote client 繼承後得到什麼**

- 共享治理底盤
- 一致的 repo / contract / schema / mock / QA / evidence 邏輯
- 可複用資產流
- 可持續演進的 project base

**建議最小 repo 組合**

- `.github`
- `aaa-tpl-docs`
- `aaa-actions`
- `aaa-evals`
- `aaa-tools`
- `aaa-prompts`
- 至少一個 service repo
- 至少一個 frontend 或 consumer-facing template repo

**包含能力**

- `Lite` 全部內容
- 完整 consume / feedback pipeline
- reusable actions / evals / tools / prompts
- contract / schema / dictionary / design discipline
- mock-first / QA parallelization
- candidate -> hardening -> upstream -> adoption 資產回流模型
- `operate_maintain_workflow_v2` 核心版
- AI governance baseline
- versioned governance / evidence / review discipline

**不包含**

- distributed / remote runtime
- heavy external resource integration
- polished operator product surface

**remote client 承接前提**

- 有基本 CI discipline
- 接受 contract-first / mock-first
- 願意維持 review / code owner / QA / evidence 流程
- 願意把專案看成長期資產，而非一次性交付

**一句話定位**

讓 remote client 不只是開專案，而是開始建立可治理、可複用、可複利的工程底盤。

---

### 3.3 AAA Full

**定位**  
`Operating Base Package`

**適用客戶**

- 將 AAA 視為長期 operating base
- 願意把多 repo、多 AI、多資產、多 workflow 全部納入共同底盤
- 不是只買交付，而是買一個可長期運作的 project operating system

**remote client 繼承後得到什麼**

- 完整工程治理底盤
- 長期可持續演進的 runtime / asset / workflow / evidence base
- 可逐步承接後續 conditional expansion 的能力接口

**建議最小 repo 組合**

- `.github`
- `aaa-tpl-docs`
- `aaa-actions`
- `aaa-evals`
- `aaa-tools`
- `aaa-prompts`
- `aaa-tpl-service`
- `aaa-tpl-frontend`
- 視情況加上 operator/detail surface repo

**包含能力**

- `Core` 全部內容
- 更完整的 `operate_maintain_workflow_v2`
- 進階 evidence / closeout / asset promotion discipline
- 更強的 AI role orchestration
- 更完整的 shared runtime / project-base posture
- 為 `v2.1.20+` conditional expansion 預留 integration boundary

**不預設包含**

- `v2.1.20 ~ v2.1.22` 全部自動開啟
- full SaaS collaboration suite
- consumer-grade polished product surfaces

**remote client 承接前提**

- 有穩定工程管理能力
- 有 CI / review / QA / release discipline
- 願意接受 AAA 作為 ground base，而不是只拿模板
- 願意投入長期資產回流與治理維護

**一句話定位**

讓 remote client 把 AAA 不是當 starter kit，而是當專案與團隊的長期操作底盤。

---

## 4. Workflow Inclusion Rule

每級是否包含 `operate_maintain_workflow_v2`，不得用模糊文字帶過，必須顯式標示：

- `Lite`：縮減版 workflow baseline
- `Core`：`operate_maintain_workflow_v2` 核心版
- `Full`：`operate_maintain_workflow_v2` 完整版

此規則用來確保：

- `Lite` 不會過重
- `Core` 具備正式治理能力
- `Full` 保有 operating-base 差異化

---

## 5. Client Prerequisites

inheritance package 定義不得只寫 AAA 提供什麼，也必須寫 remote client 需承接什麼。

至少要明寫以下前提：

- 是否要求 CI discipline
- 是否要求 contract-first
- 是否要求 mock-first
- 是否要求 AI governance
- 是否要求 code review / QA / branch protection
- 是否要求 asset feedback loop

若 remote client 不具備承接能力，inheritance package 必須允許降級，而不是硬塞較高級別方案。

---

## 6. Non-Goals / Exclusion Boundary

本 skeleton 明確不做：

- 不把 `Lite / Core / Full` 變成 `v2.1.xx` roadmap 版本
- 不把 inheritance package 分級寫成 import capability law
- 不預先承諾 `Full` 一定包含 `v2.1.20 ~ v2.1.22`
- 不把 `Full` 直接等同 managed service
- 不把 remote client inheritance package 與內部 engineering maturity 混寫

若後續要定義：

- managed adoption
- managed operation
- operator service package

應另立 commercial / service model 文件，不與本 skeleton 混用。

---

## 7. Formalization Checklist

下一版正式 inheritance package 文件，至少應能直接回答：

1. `Lite / Core / Full` 的定位差異是什麼？
2. 每級的最小 repo 組合是什麼？
3. 每級是否包含完整 `operate_maintain_workflow_v2`？
4. 每級要求客戶承接哪些治理責任？
5. inheritance package layer 是否已與 version line 明確分離？
6. `Core` 是否可在 `v2.1.19` 完成後直接切出，而不依賴 `v2.1.20 ~ v2.1.22`？

---

## 8. Assumptions

- inheritance package layer 可在 **至少 `v2.1.19` 之後** 正式規劃，不必等待 `v2.1.22`
- `v2.1.20 ~ v2.1.22` 仍屬 conditional expansion line
- `Lite / Core / Full` 預設面向客戶導入方案，而非內部成熟度標籤
- `Full` 目前仍是 capability package，不預設等同 managed adoption / managed operation
