# 李宏毅 ML 2025 / 2026 — 课件与作业

本仓库放课程课件（PDF/PPT）、作业说明（`hwN.pdf`）和官方 notebook。

**开工前先读第 0–2 节。** 它回答一个问题：这份作业交到哪、我能不能交、交不了怎么算分。

> 事实来源：课程页的 Platform 列 + 每个 `hwN.pdf` 的 `Submission & Grading` 页。
> 两者冲突时**以 PDF 为准**（课程页总表会滞后，见第 7 节）。

---

## 0. 一句话结论（截至 2026-11-15）

- **2026 Spring 十个作业：5 个 JudgeBoi（1/2/4/5/7）+ 5 个 NTU COOL（3/6/8/9/10），没有一个用 Kaggle 评分。**
  仓库里 `kaggle.com/code/...` 的链接全部是**官方 sample code**，不是比赛、不是评分页。
- 旁听生（GitHub 没绑 NTU 邮箱、不在选课名单）**交不了 JudgeBoi，也交不了 NTU COOL** —— 2026 这十份一份都提交不了。
- 全仓库唯一的 Kaggle 评分页是 **2026 Bonus Competition**：不是作业，是「教学视频系统」赛，5/15 已截止。
- 想「交上去有排行榜分数」，只能走 **2021 那套 Kaggle 比赛**（第 4 节），Late Submission 一直开着。

## 1. 先判断平台：看 PDF 的 Submission 页

| 平台 | PDF 里的关键词 | 提交物 | 旁听能交 |
|---|---|---|---|
| **JudgeBoi** | `submit ... to JudgeBoi` | `.txt` / `.json` | ❌ 需 NTU 邮箱绑 GitHub + role 为 `Student` |
| **NTU COOL** | `submit ... to NTU Cool` | 测验 / 代码 | ❌ 需选课账号 |
| **Gradescope**（2025 用） | `gradescope.com/courses/...` | 测验 | ❌ 需课程码 |
| **Kaggle** | `kaggle.com/competitions/...` | `submission.csv` 等 | ✅ 有 Kaggle 号就行 |

判定流程（给 agent）：

```
读 hwN.pdf 的 "Submission & Deadline" 页
├─ 出现 JudgeBoi   → 能登录且 role=Student？ 否 → 自评模式（第 6 节）
├─ 出现 NTU Cool   → 自评模式
├─ 出现 Gradescope → 自评模式（2025 的 HW3/7/8）
└─ 出现 kaggle.com/competitions → 正常提交（≤5 次/天）
```

## 2. 2026 Spring 十个作业（以 PDF 为准）

| # | 主题 | 平台 | 提交物 | 指标 / 官方 public 线 | 截止（UTC+8） |
|---|---|---|---|---|---|
| 1 | LLM Malicious Instruction Defense | JudgeBoi | 防御 prompt `.txt` | 14 条攻击各 1%（safety 0.5% + utility 0.5%），总分上限 10 | 03/26 |
| 2 | AI Agent as an AI Engineer | JudgeBoi + NTU COOL | `pred.json` + 代码（4 分） | Accuracy：Simple 0.00 / Medium 0.65 / Strong 0.87 | 04/02 |
| 3 | LLM Fast Inference | NTU COOL | 纯测验，不交代码 | — | 04/09 |
| 4 | Training Transformer | JudgeBoi + NTU COOL | 80 行 `.txt` + `.ipynb` | FID 与 PDR **同时**达标：86/0.1、80/0.5、73/0.85 | 04/16 |
| 5 | Finetuning without Forgetting | JudgeBoi + NTU COOL | `<学号>.txt` + 代码 | GSM8K accuracy / AILuminate safety：0.212/0.558、0.379/0.631、0.455/0.813 | 04/30 |
| 6 | Model Editing | NTU COOL | 代码 + 测验 | efficacy / paraphrase / neighborhood / portability 四项 | 05/14 |
| 7 | Model Merging | JudgeBoi + NTU COOL | `submission.json` + `.ipynb` | JP-Math QA accuracy：Simple ≥50%、Strong ≥75%；另有 8 题 paper reading | 05/28 |
| 8 | Test-Time Scaling | NTU COOL | 纯测验 | — | 06/04 |
| 9 | Flow Matching | NTU COOL | 纯测验 19 题 | 16 题 paper reading ×0.5 + 3 题 coding（0.5/0.5/1.0） | 06/11 |
| 10 | Spoken Language Model | NTU COOL | 12 道选择题 | — | 06/18 |
| Bonus | Teaching Monster | **Kaggle** | 教学视频生成系统（接 API） | — | 05/15 |

- HW10 的 PDF 只在课程页上，仓库里没有（仓库收的是 HW1–9）。
- 2026 全部截止日期都已过（今天 11/15），这一点比 JudgeBoi 更硬：**有号也交不了**。
- **HW4 与 2025 HW4 是同一份作业**（2026 PDF 首行写着 `Slide Credit: ML2025 spring HW4`）：sample code 的 code cell 逐字一致，2026 只多一个 `drive.mount`；数据集同为 `lca0503/ml2025-hw4-pokemon`，模型同为 GPT-2 小配置（`n_embd=64 / n_layer=2 / n_head=2 / n_positions=400`）。唯一实质差别是**分数线**——2025 simple ≤84.50 / medium ≤81.00 / strong ≤73.00，2026 simple ≤86.00 / medium ≤80.00 / strong ≤73.00。判分一律用**当年那份 PDF** 的表，别拿 2025 的线当 2026 的。

## 3. JudgeBoi / NTU COOL 规则速查

**JudgeBoi**（[ml.ee.ntu.edu.tw](https://ml.ee.ntu.edu.tw)）

- 登录 = GitHub，**必须绑 NTU 邮箱**，且系统把你识别为 `Student`；Guest **没有配额**（= 交不了）。
- 每天 5 次，23:59（UTC+8）重置；每个作业最多选 **2 份**提交作为最终成绩（不选则取 public 最高）。
- 只收对应后缀（HW1 `.txt`、HW2 `.json`、HW4 `.txt`、HW5 `.txt`、HW7 `.json`），< 1MB。
- 每周日 00:00–03:00 维护；截止日临近会很卡，卡住不补次数。
- 禁止手改预测文件；违规该次 0 分且学期总分 ×0.9。

**NTU COOL**

- 测验基本不限次数：HW3/HW8/HW9 取最高，HW6 取**最新一次**（以各 PDF 为准）。
- 代码提交只看最后一次，截止后不补。

## 4. 2021 Spring：唯一还能交的 Kaggle 序列

15 个作业里 **只有 8 个**开了 Kaggle，其余 7 个（HW5/6/9/10/12/14/15）当年就没开，别去 Kaggle 搜：

| HW | 主题 | 比赛 | 指标 |
|---|---|---|---|
| 1 | Regression | [ml2021spring-hw1](https://www.kaggle.com/competitions/ml2021spring-hw1) | RMSE |
| 2 | Classification | [ml2021spring-hw2](https://www.kaggle.com/competitions/ml2021spring-hw2) | Accuracy |
| 3 | CNN | [ml2021spring-hw3](https://www.kaggle.com/competitions/ml2021spring-hw3) | Accuracy |
| 4 | Self-Attention | [ml2021spring-hw4](https://www.kaggle.com/competitions/ml2021spring-hw4) | Accuracy |
| 7 | BERT | [ml2021-spring-hw7](https://www.kaggle.com/competitions/ml2021-spring-hw7) | Accuracy |
| 8 | Anomaly Detection | [ml2021spring-hw8](https://www.kaggle.com/competitions/ml2021spring-hw8) | AUC |
| 11 | Adaptation | [ml2021spring-hw11](https://www.kaggle.com/competitions/ml2021spring-hw11) | Accuracy |
| 13 | Compression | [ml2021spring-hw13](https://www.kaggle.com/competitions/ml2021spring-hw13) | Accuracy |

- 比赛已过期，但 **Late Submission 开着**：2026-11-14/15 实测还能交 hw1/hw2（0.88478 / 0.75869）。
- 第一次提交前要先 Join（接受比赛规则）；每天 5 次。
- 这套的仓库是 [`jodi345/ML2021-Spring`](https://github.com/jodi345/ML2021-Spring)，流程见那边的 `AGENT.md`。

## 5. 2025 Spring 对照（同仓库，别和 2026 搞混）

| HW | 主题 | 平台 |
|---|---|---|
| 1 | AI Agent1 — RAG | JudgeBoi |
| 2 | AI Agent2 | **Kaggle**（`kaggle.com/t/486f...`） |
| 3 | Understand Transformer | Gradescope |
| 4 | Training Transformer | JudgeBoi（**与 2026 HW4 同一份作业**） |
| 5 | Fine tune is powerful | JudgeBoi |
| 6 | Fine-tuning leads to Forgetting | JudgeBoi |
| 7 | RLHF | Gradescope |
| 8 | Model Editing | Gradescope |
| 9 | Model Merging | JudgeBoi |
| 10 | Diffusion | JudgeBoi |
| Bonus | — | **Kaggle**（`ml-2025-bonus-competition`） |

## 6. 交不了的时候：自评协议

旁听生不许提交，但作业照做，**用 PDF 里公布的线自己判分**：

1. **不要伪造排行榜分数**。没交就是没交，写清楚。
2. 按 PDF 的 metric 在本地 / Kaggle kernel 算，和 public baseline 表逐项对比（例：HW4 要 FID 与 PDR 同时达标才算过 simple）。
3. 结果写进 `SOLUTION.md`，成绩表标 `self-evaluated (not submitted — auditor)`，并附 1–2 个互补指标（RMSE 之外给 R²/MAE，accuracy 之外给 F1/混淆矩阵）。
4. 能自评的上限就是「有没有过 simple/medium/strong」，拿不到排行榜排名 —— 这要提前说清，别假装有 LB 分数。
5. **有指标算不了的作业要提前认**：HW4 的 FID 可以自己用 Inception-v3 算，但 PDR 用的是**助教训练的 classifier**，没公开 → 自评只能给 FID，PDR 那栏写「不可测」并注明，别拿自己训的 discriminator 冒充官方 PDR。HW1 的 private 攻击 prompt、HW5 的 private baseline 同理。

## 7. 已知出入 / 坑

- `policy.pdf` 的总表把 作業一/九/十 标了 JudgeBoi，但 `hw1/hw9/hw10.pdf` 写的是 **JudgeBoi-only / NTU COOL-only** → 以 PDF 为准。
- 2026 的 Kaggle 链接全部在 **Code 列**（hw1/hw2/hw4/hw5/hw7 的官方 sample code），不是比赛。
- 2025 HW2 的 Kaggle 是私有邀请链接（`/t/486f3f5988bd4240b6476b08ab579d0a`），不在公开比赛列表里。
- **Training Transformer（Pokémon 20×20）这道题没有任何 Kaggle 比赛。** 在 Kaggle 搜 `pokemon` / `transformer` / `hw4` / `ml2025-hw4` 都搜不到它；搜到的 `ml2021spring-hw4`、`ml2023springhw4` 是 2021/2023 的 Self-Attention（说话人分类），不是这道题。它的分只走 JudgeBoi。
- 课程 policy 原话：「實際修課和旁聽的差別只有 **助教不批改旁聽生作業** 而已」—— 旁听不是被禁止，卡的是 JudgeBoi 的 `Student` 身份和 NTU COOL 的选课名单。有台大邮箱的话，值得绑一次 GitHub 看 role 会不会变成 Student。
