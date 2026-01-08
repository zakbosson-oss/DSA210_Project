# DSA 210 Project  
## Competition & Niche Analysis for a YouTube Channel

### Author
Erim  
Senior Industrial Engineering Student

---

## Project Overview

This project applies data analytics, statistical hypothesis testing, and machine learning
techniques to analyze video performance dynamics within the *WW2 short documentary* niche on
YouTube. The motivation of the study is to demonstrate that Industrial Engineering concepts
and data-driven methods can be effectively applied beyond traditional corporate systems,
including creative digital content pipelines.

By treating YouTube content production as a system influenced by multiple interacting
variables, the project aims to identify which factors systematically contribute to video
underperformance and which commonly assumed strategies (such as upload timing) have limited
impact once channel size and baseline behavior are accounted for.

---

## Data Sources

The dataset was constructed using publicly available information obtained through:

- **YouTube Data API v3**  
  - Video metadata (title, description, duration)
  - Engagement metrics (views, likes, comments)
  - Upload timestamps
- Channel-level aggregation for normalization purposes

The final dataset contains **6,484 videos** across multiple channels in the same content
niche.

---

## Methodology

The analysis follows a structured, multi-stage approach:

### 1. Exploratory Data Analysis (EDA)
- Distributional analysis of views and engagement
- Investigation of upload timing, duration, and metadata length
- Channel-normalized performance measures

### 2. Hypothesis Testing
Non-parametric statistical tests were used to evaluate relationships between:
- Video duration and engagement
- Upload hour/day and performance
- Metadata length and views
- Engagement differences between low-performing and typical videos

Tests included Spearman correlation, Kruskal–Wallis, and Mann–Whitney U tests.

### 3. Machine Learning
Machine learning methods were applied to explore latent structure and predictive patterns:
- **Principal Component Analysis (PCA)** for dimensionality reduction
- **K-Means clustering** for unsupervised grouping of videos
- **Logistic regression** for supervised classification of low-performing videos

Feature importance analysis was used to interpret model behavior.

---

## Key Findings

- Video performance is **multifactorial** and cannot be explained by a single dominant
  variable.
- Apparent effects of upload timing and duration largely diminish once channel baseline
  performance is controlled for.
- Engagement rate and channel-relative performance are the most informative predictors of
  underperformance.
- Low-performing and typical videos do not form clearly separable clusters, indicating that
  performance exists along a continuum rather than in distinct categories.

---

## Practical Implications

The results suggest that creators should prioritize:
- Improving early engagement signals
- Maintaining consistency with channel-level audience expectations
- Evaluating performance relative to their own historical baseline rather than global
  benchmarks

Optimization of upload schedules or metadata length alone is unlikely to compensate for weak
audience response.

---

## Limitations and Future Work

- Thumbnail design, visual quality, and narrative structure were not directly analyzed.
- Performance was measured using static snapshots rather than full time-series growth.
- Binary classification of underperformance simplifies a continuous outcome.

Future work may incorporate computer vision, natural language processing of transcripts,
time-series modeling, and cross-niche comparisons.

---

## AI Usage Disclosure

This project was developed with the assistance of AI-based tools. Large language models were
used to support:
- Code structuring and debugging
- Drafting and refining explanatory text
- Improving clarity and organization of analysis sections

All analytical decisions, interpretations, and conclusions were reviewed, validated, and
curated by the author. AI tools were used as a productivity aid and not as a substitute for
conceptual understanding or independent reasoning.

---

## Course Information

This project was completed as part of **DSA 210** and adheres to the course guidelines on data
analysis, hypothesis testing, and machine learning applications.
