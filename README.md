# 🌐 **Dataset Construction Based on AI Regulations (EU · China · Japan · South Korea)**

> **Goal:**
> Build a *unified, comparable dataset* derived from the major AI governance frameworks of **the European Union, China, Japan, and South Korea**.
>
> Each dataset entry pairs a **legally actionable provision** with a **neutral prompt** and a set of **positive** and **negative examples**, illustrating **compliance** and **non-compliance**.
>
> This enables **cross-jurisdictional research**, **AI model evaluation**, and **comparative analysis** of AI regulatory principles.

---

## 🇨🇳 **1. China**

**Source:**
《生成式人工智能服务管理暂行办法》
📄 **File:** `China/生成式人工智能服务管理暂行办法.txt`
🔗 [Original text (Ministry of Justice)](https://www.moj.gov.cn/pub/sfbgw/flfggz/flfggzbmgz/202401/t20240109_493171.html)

**Filtering Criterion:**
Only include provisions that allow the construction of:

* one **neutral prompt**,
* and both **positive (compliant)** and **negative (non-compliant)** output examples.

**Dataset File:**
📘 `Chinese_dataset.json`
Each record contains:

* 🧩 The legal provision text
* 💬 A **neutral prompt**
* ⚖️ A pair of **positive / negative** examples

---

## 🇪🇺 **2. European Union**

**Source:**
European Union **AI Act**
📄 **File:** `European Union/Selected_articles_id.json`
🔗 [Original text (EUR-Lex)](https://eur-lex.europa.eu/eli/reg/2024/1689/oj/eng)

**Filtering & Processing Pipeline:**

1. **Article selection** → Based on suitability for dual-scenario generation (compliance vs. violation)
2. **Splitting** → Articles decomposed into smaller provisions (`Selected_articles_split.json`)
3. **Evaluation** → Actionable ones retained (`Selected_articles_split_evaluated_yes.json`)

**Dataset File:**
📘 `Euro_dataset.json`
Each record includes:

* 🧩 The legal provision text
* 💬 A **neutral prompt**
* ⚖️ **Positive / negative** examples illustrating compliance and violation

---

## 🇯🇵 **3. Japan**

**Source:**
**Act on the Promotion of Research and Development and Utilization of AI-Related Technology**
(令和五年法律第五十三号)
📄 **File:** `Japan/Jp_articles`
🔗 [Original text (e-Gov Japan)](https://laws.e-gov.go.jp/law/507AC0000000053)

**Filtering Criterion:**
Each provision must be applicable to:

* one **neutral prompt**,
* with clearly distinguishable **positive (supporting)** and **negative (conflicting)** examples.

**Dataset File:**
📘 `Jp_AI_Promotion_Act_Dataset`
Each record contains:

* 🧩 The legal provision text
* 💬 **Prompt** (neutral)
* ⚖️ **pe / ne** examples (positive & negative)

---

## 🇰🇷 **4. South Korea**

**Source:**
**Artificial Intelligence Basic Act (인공지능 기본법)**
📄 **File:** `South Korea/Kr_articles`
🔗 [Original text (Law.go.kr)](https://www.law.go.kr/법령/인공지능%20발전과%20신뢰%20기반%20조성%20등에%20관한%20기본법/%2820676,20250121%29)

**Filtering Criterion:**
Include only provisions that:

* define **behavioral or procedural obligations**,
* can be mapped to a **neutral prompt**,
* and be illustrated with **positive (compliant)** and **negative (non-compliant)** examples.
  Exclude purely *declarative* or *definitional* articles.

**Dataset File:**
📘 `South_Korea_AI_Basic_Act.json`
Each record includes:

* 🧩 Legal provision text
* 💬 **Prompt** (neutral)
* ⚖️ **pe / ne** examples (positive & negative)

---

## 📁 **Project Structure Overview**

```
AI_Regulation_Dataset/
│
├── China/
│   ├── 生成式人工智能服务管理暂行办法.txt
│   └── Chinese_dataset.json
│
├── European Union/
│   ├── Selected_articles_id.json
│   ├── Selected_articles_split.json
│   ├── Selected_articles_split_evaluated_yes.json
│   └── Euro_dataset.json
│
├── Japan/
│   ├── Jp_articles
│   └── Jp_AI_Promotion_Act_Dataset
│
└── South Korea/
    ├── Kr_articles
    └── South_Korea_AI_Basic_Act.json
```

