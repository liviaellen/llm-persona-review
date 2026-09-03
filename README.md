# llm-persona-review

Data supplement for **"The Effects of Personas on LLM Generative Output and LLM-as-a-Judge Evaluation: A Literature Review."**

This repository holds the coded extraction table for the 70 papers included in the review.

## Data

`data/persona_llm_review.csv` — one row per included paper (70 rows, 18 columns).

| Column | Description |
| --- | --- |
| `article_id` | Internal identifier (A01, A02, …) |
| `Year` | Publication year |
| `Type` | Contribution type (evaluation, novel method/framework, LLM-as-a-judge, review) |
| `Keywords**` | Author-supplied keywords |
| `Title` | Paper title |
| `Authors` | Full author list |
| `First Author` | First author surname |
| `Retrieved` | Whether the full text was retrieved |
| `Analysis Theme` | Study design: quantitative, qualitative, or mixed |
| `LLMs Used` | Models evaluated |
| `Sample Size of Personas/Profiles` | Number of personas or profiles used |
| `Human Participants?` | Whether human participants/annotators were involved, with details |
| `Statistical Methods Used` | Statistical tests and metrics reported |
| `Effect of Personas on LLM Output` | Coded direction of effect: Positive, Negative, or Mixed |
| `Summary of Results` | Extracted findings |
| `Prompt Architecture/Methodology` | Prompt structure and method described in the paper |
| `Research Questions` | The paper's own research questions |
| `Review Research Question` | Which review research question the paper addresses |

## Corpus at a glance

**Publication year**

| Year | Papers |
| --- | --- |
| 2023 | 2 |
| 2024 | 23 |
| 2025 | 35 |
| 2026 | 10 |

**Coded effect of personas on LLM output**

| Effect | Papers |
| --- | --- |
| Positive | 27 |
| Negative | 22 |
| Mixed | 21 |

**Study design**

| Theme | Papers |
| --- | --- |
| Quantitative | 49 |
| Mixed | 18 |
| Qualitative | 3 |

## Notes

- The CSV is preserved exactly as exported, so a few headers carry trailing spaces or footnote markers (`Keywords**`, `" Statistical Methods Used"`, `"Review Research Question      "`). Strip whitespace when loading if you plan to reference columns by name.
- Several free-text cells contain embedded newlines and commas; read with a proper CSV parser rather than splitting on commas.

```python
import pandas as pd

df = pd.read_csv("data/persona_llm_review.csv")
df.columns = df.columns.str.strip().str.rstrip("*")
```
