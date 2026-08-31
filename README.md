# AI × 在宅醫療與居家照護 (Hospital at Home & Home Care) 智慧落地藍圖

> **從「零碎訊號」到「臨床可行動閉環」** —— 聚焦失能長者、慢性病患及術後返家者的日常照護與訪視減負。

[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-Live%20Demo-brightgreen?logo=github)](https://howardliao.github.io/HAH/)
[![PowerPoint Deck](https://img.shields.io/badge/PowerPoint-16%3A9%20Presentation-orange?logo=microsoftpowerpoint)](AI_Hospital_at_Home_HaH_智慧在宅醫療藍圖_Howard_Liao.pptx)
[![FHIR Standard](https://img.shields.io/badge/Standard-HL7%20FHIR%20R4-blue)](https://hl7.org/fhir/)
[![Governance](https://img.shields.io/badge/Governance-ISO%2027001%20%7C%20ISO%2042001-purple)](https://www.iso.org)

---

## 📌 執行摘要 (Executive Summary)

AI 在在宅醫療（Hospital at Home, HaH）與居家照護（Home Care）最有價值的角色，**不是取代醫師或護理師**，而是把居家端零碎、低頻、難以判讀的生理與環境資訊，轉化為「**可預警、可分流、可協作、可追蹤**」的標準臨床照護流程。

### 核心目標
1. **讓病人更安全留在家中**：及早捕捉微小病情惡化徵兆，避免非計畫性急診與再住院。
2. **降低急診待床與醫療負擔**：精準分流高風險個案，優化整體健保資源分配。
3. **大幅減輕照護團隊行政壓力**：導入生成式 AI 與語音環境智慧，自動化長照評估與病歷初稿，釋放醫護量能回歸臨床關懷。

---

## 🏡 居家照護 (Home Care) 專屬四大核心場景與標竿案例

| 領域 | 技術與演算法 | 代表產品 / 案例 | 核心功能與臨床價值 | 文獻與查閱方向 |
|---|---|---|---|---|
| **1. 傷口照護與壓瘡預防** | 電腦視覺 (Computer Vision) | **Tissue Analytics** (Net Health), **Swift Skin and Wound**, 成大/奇美醫療體系 | 手機拍攝壓瘡/糖尿病足，AI 自動校正光源、量測長寬面積與邊界、辨識組織分期 (壞死/肉芽組織比例)，追蹤癒合進度。 | *Journal of Wound Care* 智慧手機傷口辨識效能臨床驗證 |
| **2. 非接觸安全監控與跌倒偵測** | 毫米波雷達 (mmWave) / WiFi 擾動微都卜勒 | **Vayyar Care**, **Origin Wireless**, **工研院 (ITRI)** 智慧居家照護雷達 | 無需配戴手環或安裝攝影機（高隱私保護），透過無線都卜勒反射辨識床邊起身、如廁滯留、步態不穩及突發跌倒，即時告警。 | 工研院智慧感測照護白皮書、IEEE 微都卜勒雷達演算法論文 |
| **3. 日常連續生理數據監測與惡化預警** | 時序預測 (Time-Series ML + RPM) | **Current Health** (Best Buy Health), **Biofourmis** | 整合 HRV、血氧、呼吸與活動量，運用 ML 計算早期惡化指標，在心衰竭復發、COPD 急性發作前 **24~48 小時** 發出預警。 | *JMIR mHealth and uHealth* 居家心衰竭與 COPD 預測臨床實證 |
| **4. 訪視減負與照護計畫生成** | 語音環境智慧 (Ambient Clinical Intelligence / LLM) | **Abridge**, **Nuance DAX Copilot**, 本土居家護理資訊系統 (NIS) Whisper/LLM | 訪視對話即時轉為長照評估表（**ADLs、巴氏量表描述**）或結構化 SOAP 紀錄，解決護理師每天 2~3 小時文書繕打痛點。 | 長照資訊系統商 (HIS/NIS) 與 GenAI 照護計畫落地案例 |

---

## 🏛️ AI 應用全景（四層技術與臨床架構）

```
┌────────────────────────────────────────────────────────────────────────┐
│ 4. 協作層 (Collaboration)                                              │
│    AI Copilot、訪視語音轉 SOAP、ADLs/巴氏量表、交班摘要、多語衛教單張  │
├────────────────────────────────────────────────────────────────────────┤
│ 3. 決策層 (Decision / CDS)                                             │
│    Clinical Decision Support、分流與優先級排序 (電訪/視訊/到府/轉急診) │
├────────────────────────────────────────────────────────────────────────┤
│ 2. 判讀層 (Interpretation)                                             │
│    多維時間序列異常偵測、個人基線偏離分析、體液滯留預警、傷口 CV 影像辨識 │
├────────────────────────────────────────────────────────────────────────┤
│ 1. 感知層 (Perception)                                                 │
│    IoT 資料品質檢核、去雜訊 (血壓/血氧/心率/血糖/體重/智慧床墊/mmWave雷達)│
└────────────────────────────────────────────────────────────────────────┘
  ▲  跨層資料互通基石：HL7 FHIR (Fast Healthcare Interoperability Resources)
```

---

## 🚀 三階段落地推動藍圖

| 階段 | 週期 | 核心任務與里程碑 |
|---|:---:|---|
| **Phase 1: 90 天 MVP** | 0~3 月 | 聚焦單一族群（心衰竭/壓傷），建立量測、警示、處置 SLA SOP 與個案 Dashboard，導入 AI 摘要初稿。 |
| **Phase 2: 系統擴展** | 3~9 月 | 採用 HL7 FHIR 串接 EMR/HIS、處方與檢驗，擴展多病種個人化預警與 Multimodal 多模態 AI，建置 24/7 告警中心。 |
| **Phase 3: 制度常態化** | 9~18 月 | 建立區域「醫院—診所—居護—長照—藥局」共照網，部署分角色 Agent，對接健保與商業保險支付機制。 |

---

## 🛡️ 資安與 AI 治理架構 (ISO 27001 / ISO 42001 / NIST AI RMF)

1. **資料最小化 (Data Minimization)**：防跌優先採毫米波雷達/姿態骨架，預設不上傳原始畫面。
2. **明確同意與可撤回**：告知用途、期限與存取對象，支援隨時撤回授權。
3. **端到端零信任 (ZTA)**：雙向憑證、AES-256 加密、MDM 遠端納管與 API 審計。
4. **供應鏈風險 (SBOM)**：供應商提供物料清單、弱點修補 SLA 與 DPA 協議。
5. **人類最終決策 (Human-in-the-loop)**：處方、診斷與轉診均由合格醫師審核簽章。
6. **模型可監測性**：持續監控族群偏差與模型漂移 (Drift)。
7. **全鏈路可稽核 (Auditability)**：完整保留原始訊號、提示詞、模型版本與覆核軌跡。
8. **緊急失效 SOP (Fail-Safe)**：斷網或服務中斷時無縫回退至電話與紙本 SOP。

---

## 📂 專案檔案清單

- `index.html`：雙模態互動網頁（包含 15 頁全螢幕簡報投影模式 + 居家照護四大場景 + 臨床分流模擬器 + ROI 試算器）。
- `AI_Hospital_at_Home_HaH_智慧在宅醫療藍圖_Howard_Liao.pptx`：指定來源 16:9 專業商業版 PowerPoint 簡報檔案。
- `README.md`：專案核心架構與策略落地說明文件。

---

## 📚 參考文獻與政策來源

1. 行政院 (2025/2026). 《在宅醫療科技願景與行動》. 行政院科技政策推動辦公室.
2. CIO Taiwan (2025/2026). 2026 年智慧醫療趨勢：從生成式 AI 到制度化治理的關鍵拐點. *CIO Taiwan*.
3. 黃冠凱 (2026). 從醫院到客廳：AI如何重塑在宅照護新模式. *AnkeCare 安可人生*.
4. 黃冠凱 (2025). 在宅醫療的智慧轉向以科技賦能社區照護. *AnkeCare 安可人生*.
5. 成大醫院/奇美醫院 (2024/2026). 無牆化遠距醫療照護：智慧安寧與傷口影像分析. (在宅善終率 83%)
6. 高雄醫學大學附設中和紀念醫院 (2025). 不用再跑醫院！高醫用「一支手機」重寫醫療模式在宅照護正式進入 AI 時代. *醫策會 HST*.
7. 臺北醫學大學 AI 中心 (2026). 從 MEDICA 到 CES: 在宅醫療、穿戴式數據與物理 AI.
8. *Journal of Wound Care* & *JMIR mHealth and uHealth*: 智慧手機傷口辨識 (Tissue Analytics/Swift) 與居家心衰竭/COPD 機器學習預測臨床實證.
9. 工研院 (ITRI) 智慧感測照護白皮書 & IEEE 論文: 毫米波 (mmWave) 微都卜勒雷達室內防跌與步態分析技術.
10. 數位時代 / 臺灣AZ (2025). 從減負到在宅：北台灣醫界領袖共論 AI 醫療落地藍圖三大趨勢.

---
*Developed for Hospital at Home (HaH) & Home Care AI Strategic Governance & Implementation by Howard Liao Ph.D.*
