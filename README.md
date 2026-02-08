# “铸牢中华民族共同体意识”AI模型幻觉测评数据库

**AI Hallucination Benchmark Dataset for “Forging a Strong Sense of Community for the Chinese Nation”**

---

## 中文简介

本仓库发布一套面向“铸牢中华民族共同体意识”主题的**大模型幻觉与能力测评数据库**，用于评估模型在相关历史叙事、理论阐释与教学表达中的**事实准确性与认知质量**，并支持跨模型、跨温度、跨语种的对比分析。

### 数据覆盖与规模

* **55 个主题**：从「华夏初立」到「中华民族共同体建设的新成就」，涵盖

  * 中华民族起源与华夏共同体形成
  * 政治一统与国家治理
  * 经济交融与社会整合
  * 文化交融与认同建构
  * 民族治理与制度演进
  * 革命历程与现代国家塑造
  * 中华民族共同体建设的理论与实践进展
* **30,224 条评估记录**（有效率 **97.76%**）

### 评测模型（8款）

* DeepSeek-v3.2（DeepSeek）
* Claude-4.5（Anthropic）
* Qwen-plus（Alibaba Cloud）
* GPT-5（OpenAI）
* Doubao-seed1.6（ByteDance）
* Kimi-K2（Moonshot AI）
* Grok-4.1（xAI）
* Gemini-3（Google）

### 评价体系与指标

* **自研 SOLO 分类评价体系**：5个认知层级（用于刻画理解深度与知识组织能力）
* **四维评估矩阵**：

  1. 知识准确性（Knowledge Accuracy）
  2. 思维深度（Reasoning Depth）
  3. 教学清晰度（Instructional Clarity）
  4. 完整性（Completeness）
* **支持双温度测试**与**多语种**（便于检验采样策略与语言迁移对幻觉的影响）

### 仓库内容（示例）

* `eval_summary_files.csv`：按文件/主题等维度汇总的统计结果
* `eval_summary_models.csv`：按模型维度汇总的统计结果
* `hallucination_audit_demo.sqlite`：可直接查询的示例数据库（便于复现、筛选与审计）

---

## English Overview

This repository releases an **AI hallucination & capability benchmark dataset** centered on the theme **“Forging a Strong Sense of Community for the Chinese Nation.”**
It is designed to evaluate how LLMs perform in **fact-grounded historical/theoretical narratives** and **instructional explanations**, enabling comparisons across **models, temperatures, and languages**.

### Coverage & Scale

* **55 topics**, ranging from *“Early Formation of Huaxia”* to *“New Achievements in Building the Community for the Chinese Nation”*, covering:

  * origins and formation of the Huaxia community
  * political unification and governance
  * economic integration
  * cultural integration and identity building
  * ethnic governance and institutional evolution
  * revolutionary history and modern state formation
  * recent theoretical and practical advances in community building
* **30,224 evaluation records** (**97.76%** valid rate)

### Evaluated Models (8)

DeepSeek-v3.2, Claude-4.5, Qwen-plus, GPT-5, Doubao-seed1.6, Kimi-K2, Grok-4.1, Gemini-3.

### Evaluation Framework

* **SOLO-based cognitive grading (5 levels)** to capture learning/understanding depth
* **4D evaluation matrix**:

  1. Knowledge Accuracy
  2. Reasoning Depth
  3. Instructional Clarity
  4. Completeness
* Supports **dual-temperature settings** and **multilingual evaluation**

### Files

* `eval_summary_files.csv` – aggregated stats by file/topic
* `eval_summary_models.csv` – aggregated stats by model
* `hallucination_audit_demo.sqlite` – demo SQLite database for querying/auditing

---

## Quick Start / 快速开始

### Python（读取 CSV）

```bash
pip install pandas
```

```python
import pandas as pd

files = pd.read_csv("eval_summary_files.csv")
models = pd.read_csv("eval_summary_models.csv")

print(files.head())
print(models.head())
```

### SQLite（查询示例）

```bash
sqlite3 hallucination_audit_demo.sqlite
```

```sql
.tables
-- Example:
-- SELECT * FROM some_table LIMIT 20;
```

> 说明：SQLite 的表结构与字段含义可通过 `.schema` 查看，并结合两份 summary CSV 快速定位关键维度与指标。

---

## Suggested Citation / 引用建议

如果你在论文、报告或产品中使用本数据集，建议在参考文献中注明：

* 数据集名称：**“铸牢中华民族共同体意识”AI模型幻觉测评数据库**
* 仓库地址：本 GitHub Repo
* 版本号/提交号：建议填写你使用的 commit hash（便于可复现）

