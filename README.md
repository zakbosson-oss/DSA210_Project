# DSA 210 Project  
## Competition & Niche Analysis for a YouTube Channel

---

## Background and Motivation

Industrial Engineering focuses on analyzing, improving, and optimizing systems. While these
methods are often associated with large-scale corporate or industrial environments, the same
principles can also be applied to smaller, digital systems.

In this project, YouTube content creation is treated as an operational pipeline. The specific
context is a YouTube channel operating in the *Short Documentary* niche, with a focus on
*World War II* content. A significant portion of the production process—such as script writing,
title generation, descriptions, tags, and voiceovers—is automated using AI-based tools. The
remaining steps, including visual assembly and publishing, form a repeatable workflow analogous
to a production line.

From an operational perspective, the objective of this system is to maximize revenue, which is
primarily driven by video views and audience engagement. However, optimizing such a system
without understanding the factors that influence video performance is inherently difficult.
This project aims to reduce this uncertainty by analyzing competing channels within the same
niche and identifying video-level characteristics associated with both high and low performance.

---

## Project Objective

The primary objective of this project is to analyze video-level metadata from YouTube channels
within the same niche in order to understand:

- Which video characteristics are associated with higher performance
- Whether low-performing videos are random outcomes or exhibit systematic patterns
- How content and timing decisions can be informed by data-driven insights

---

## Data Sources

The primary data source for this project is the YouTube Data API v3. A predefined list of
YouTube channels operating within the same content niche was used as the basis for data
collection.

For each channel, all publicly available uploaded videos were retrieved. The following
metadata was collected for each video:

- Video identifier and channel identifier
- Upload timestamp
- Video duration
- View count
- Like count
- Comment count
- Video title and description

The final dataset contains one observation per video and forms the basis for all subsequent
analysis.

---

## Data Processing

Data processing and analysis were conducted using Python. Raw video metadata was cleaned
and transformed to ensure consistency and analytical usability.

Key preprocessing steps include:
- Standardizing timestamp formats and resolving timezone inconsistencies
- Converting numeric fields (views, likes, comments) to appropriate data types
- Removing invalid observations
- Engineering derived features relevant to analysis

The following features were engineered:
- Video duration (minutes)
- Engagement rate (likes + comments divided by views)
- Video age (days since upload)
- Upload hour
- Upload day of week

All preprocessing steps are fully reproducible and documented in the accompanying Jupyter
notebook.

---

## Research Questions

Rather than focusing on a single factor, this project investigates multiple dimensions of video
performance to better understand why some videos succeed while others underperform.

The analysis is guided by the following research questions:

1. How does video duration relate to total views and engagement rates?
2. Does upload timing (hour of day) influence average video performance?
3. Are there systematic performance differences across channels within the same niche?
4. Are low-performing videos random outcomes, or do they share common structural characteristics?
5. How do engagement metrics differ between low-performing and typical-performing videos?

These questions are explored through exploratory data analysis and simple quantitative methods,
with the goal of identifying actionable insights that can inform content strategy within a
structured production pipeline.

---

## Methodology

The analysis follows a structured workflow:

1. Data collection  
   Video metadata was collected programmatically using the YouTube Data API.

2. Data cleaning and feature engineering  
   Raw data was cleaned and transformed to derive meaningful analytical variables.

3. Exploratory data analysis  
   Visualizations were used to examine distributions, relationships, and variability across
   videos and channels.

4. Quantitative analysis  
   Correlation analysis was used to support patterns observed during exploratory analysis.

5. Focused sub-analysis  
   Low-performing videos were analyzed as a distinct subgroup to determine whether poor
   performance is associated with identifiable characteristics rather than random variation.

---

## Key Findings

- View counts are highly skewed, with a small number of videos accounting for a large share of
  total views.
- Video duration exhibits a weak relationship with total views, while very long videos tend
  to show lower engagement rates.
- Upload timing is associated with differences in average views, suggesting temporal effects
  in audience behavior.
- Performance differs substantially across channels, indicating strong channel-level effects.
- Low-performing videos are not purely random; they often differ systematically in engagement,
  timing, or channel context.

---

## Scope and Limitations

This study relies exclusively on publicly available YouTube metadata. Internal platform metrics
such as watch time, click-through rate, recommendation impressions, and audience demographics
are not accessible and therefore not included.

View counts are cumulative and naturally increase over time, which limits causal interpretation.
The analysis identifies associations rather than causal relationships.

While additional features such as thumbnail content, transcript sentiment, or time-series view
trajectories could provide deeper insight, the current scope prioritizes robust and reproducible
metadata that can be collected consistently across channels.

---

## Repository Structure

