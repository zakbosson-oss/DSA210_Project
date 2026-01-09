# DSA 210 Project  
## Competition & Niche Analysis for a YouTube Channel

---

## Project Motivation and Background

My name is Erim, and I am a senior Industrial Engineering student. Throughout my education, the
core focus of Industrial Engineering has been the analysis, improvement, and optimization of
systems and operations. These methods are often associated with large-scale corporate or
industrial environments; however, I believe that the underlying principles are equally
applicable to smaller, non-traditional systems.

Recently, I started a YouTube channel in the *Short Documentary* niche, with a specific focus
on *WW2 short documentaries*. The content production process for this channel is heavily
supported by AI-based tools. Scripts, titles, descriptions, tags, image search prompts, hook
comments, and voiceovers are all generated using AI. My role in the pipeline is primarily to
curate images, assemble voiceovers, add visual elements, and publish the final videos.

From a high-level perspective, this workflow resembles a simplified production line. Content
is generated, assembled, and released at a regular cadence with the objective of maximizing
revenue through views and audience engagement. However, attempting to optimize views and RPM
without understanding the factors that influence video performance is analogous to optimizing
a system without knowing its constraints or decision variables.

The motivation of this project is to analyze video performance within the WW2 short
documentary niche by examining data from similar channels. By applying statistical analysis
and machine learning methods, the goal is to identify which factors systematically affect
video performance and which commonly assumed strategies have limited impact. In doing so, the
project demonstrates how Industrial Engineering methodologies can be applied to creative
digital systems and individual-scale projects, rather than exclusively to traditional
industrial settings.

---

## Data Sources

The dataset was constructed using publicly available information obtained through the
YouTube Data API v3. The collected data includes:

- Video metadata (title, description, duration)
- Engagement metrics (views, likes, comments)
- Upload timestamps
- Channel identifiers for normalization

To enable fair comparison across channels of different sizes, channel-level aggregation was
used to compute channel-normalized performance measures. The final dataset consists of **6,484
videos** from multiple channels operating within the same content niche.

---

## Methodology Overview

The analysis follows a structured, multi-stage approach consistent with the topics covered in
DSA 210.

### 1. Exploratory Data Analysis (EDA)
- Distributional analysis of views and engagement
- Investigation of video duration, upload timing, and textual metadata
- Construction of channel-normalized performance metrics

### 2. Hypothesis Testing
Statistical hypothesis tests were conducted to formally evaluate relationships observed during
exploration. Due to skewed distributions and outliers, non-parametric methods were used,
including:
- Spearman correlation
- Kruskal–Wallis tests
- Mann–Whitney U tests

These tests were applied to examine duration effects, upload timing, metadata length, and
engagement differences between low-performing and typical videos.

### 3. Machine Learning
Machine learning methods were used to explore latent structure and predictive patterns in the
data:
- **Principal Component Analysis (PCA)** for dimensionality reduction
- **K-Means clustering** for unsupervised grouping
- **Logistic regression** for supervised classification of low-performing videos

All models were designed with interpretability in mind rather than maximum predictive
performance.

---

## Key Findings

- Video performance is **not random**, but it is also **not driven by a single dominant
  factor**.
- Apparent effects of upload timing and video duration weaken substantially once channel
  baseline behavior is controlled for.
- Channel-normalized performance reveals that low-performing videos tend to underperform
  relative to their own channel’s historical baseline rather than simply belonging to smaller
  channels.
- Engagement rate emerges as the most consistent and informative indicator of
  underperformance.
- PCA and clustering analyses show substantial overlap between low-performing and typical
  videos, indicating that performance exists along a continuum rather than in clearly
  separable categories.
- Supervised learning results demonstrate that low-performing videos can be identified with
  high accuracy using a small set of interpretable features, with engagement-related and
  channel-relative variables dominating feature importance.

---

## Practical Implications

From a practical standpoint, the results suggest that creators should focus less on identifying
universally optimal upload schedules or metadata lengths and more on improving early audience
engagement and maintaining alignment with their channel’s established performance baseline.
Surface-level optimizations may provide marginal gains, but they are unlikely to compensate
for weak audience response or content–audience mismatch.

---

## Limitations and Future Work

This study relies exclusively on publicly available metadata and engagement metrics. Important
factors such as thumbnail design, narrative quality, visual pacing, and viewer retention are
not directly observed. Additionally, performance is measured using snapshot metrics rather
than full time-series growth trajectories.

Future work could incorporate image analysis of thumbnails, natural language processing of
video transcripts, and time-series modeling of view growth. Extending the analysis to
additional content niches would also help assess the generalizability of the findings.

---

## AI Usage Disclosure

This project was developed with the assistance of AI-based tools. Large language models were
used to support code structuring, debugging, and the drafting and refinement of explanatory
text. All analytical decisions, interpretations, and conclusions were reviewed and validated
by the author. AI tools were used strictly as a productivity aid and not as a substitute for
conceptual understanding or independent reasoning.

---

## Course Information

This project was completed as part of **DSA 210** and follows the course guidelines on
exploratory data analysis, hypothesis testing, and machine learning applications.
