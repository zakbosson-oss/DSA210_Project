# DSA 210 Project Proposal: Quantifying and Clustering Team Playstyles in European Soccer

**Course:** DSA 210 Introduction to Data Science  
**Term:** 2025-2026 Fall

---

## 1. Project Proposal

According to many sources, football is the most watched and followed sport on the globe. According to GWI (GlobalWebIndex), 49% of global consumers watch or follow football making it the most followed sport by a clear margain. A lot of football fans spend time watching, reading, listening or talking about football. A question that often arises is how do people watch so much football in a limited time. After all, around 50 mathces are played every week among Europe's top 5 leagues. This number goes up when European matches and tournaments are accounted for. Even though highlights and analysis' of football is mutch more widespread and accesible than it used to be, it is far beyond the capabilities of a human to watch and analyze every single football match. It is a time constrained problem. In response to this problem, statistics such as xG (Expexted Goals), xA (Expected Assits) and xS (Expected Saves) have been formulated. These statistics are mathematically correct by all means, however fall shart in painting the whole picture of events in football. With the rapid growth of AI, a model that could analyze every single match and draw conclusions does not seem beyond the realms of possibility. Until that breakthrough occurs the best solution on our hands will remain statistics.
The objective of this project is to numerically quantify and categorize the "playstyles" of professional soccer teams. Rather than using simple metrics like wins or goals, this project will analyze *how* teams play. For example, does a team use a slow, possession-based build-up, or a fast, direct, counter-attacking style?

To achieve this, I will use two distinct public datasets as required by the project guidelines. I will start with a base dataset of team-level statistics and then **enrich** it by engineering novel features from granular, play-by-play event data.

Finally, I will apply unsupervised machine learning (PCA and K-Means clustering) to group teams from Europe's "Big 5" leagues based on these engineered playstyle features, identifying distinct tactical archetypes.

## 2. Motivation

This project is designed to fulfill several key learning objectives:
* **Apply Data Science Methodologies:** It addresses a practical, real-world problem in sports analytics, moving beyond simple performance metrics to understand tactical behavior.
* **Develop Skills in Data Collection & Preparation:** The project requires collecting and integrating two different types of datasets, including parsing complex, nested JSON event data.
* **Implement Appropriate Techniques:** The "enrichment" step requires significant **feature engineering**. The analysis will use dimensionality reduction (PCA) and clustering (K-Means), which are key machine learning techniques.
* **Create Effective Visualizations:** The final clusters will be presented visually to communicate the different tactical groups clearly.

## 3. Data Source and Collection Plan

This project will use two sets of publicly available data.

### Data Set 1: Base Team Statistics

* **Data to be Used:** A foundational dataset of aggregated team statistics for the "Big 5" European Leagues (England, Spain, Germany, Italy, France).
* **Data Points:** This will include standard metrics like `Squad`, `Matches Played`, `Possession %`, `Goals`, `Assists`, `Tackles`, `Shots on Target`, etc.
* **Collection Plan:** I will download this data as a `.csv` file from a public Kaggle repository, such as the "Football Players Stats (2024-2025)" or "Football Data | Top 5 European Leagues" dataset.

### Data Set 2: Event Data (for Enrichment)

* **Data to be Used:** Granular, coordinate-based event data from the **StatsBomb open data** repository. This data is necessary to create the novel playstyle features.
* **Data Points:** This data is in JSON format and includes (x, y) coordinates for every `Pass` (start and end location), `Shot` (location), and `Pressure` event in a match.
* **Collection Plan:** I will use the **`statsbombpy`** Python library. This library allows me to programmatically query and download the free competition and match event data directly into my `pandas` DataFrame, satisfying the reproducibility requirement.

## 4. Analysis Plan & Timeline

This plan is structured to meet the deadlines specified in the project guidelines. All code will be written in Python.

### Phase 1: Data Collection & EDA

* **Action:** Collect data from both sources as described above.
* **Action:** Parse the complex StatsBomb JSON data and aggregate it to the team level.
* **Action (Enrichment):** Engineer new playstyle features (indices) from the event data. Examples include:
    * `Average Pass Length`
    * `Passes per Defensive Action (PPDA)` (a proxy for pressing intensity)
    * `Attacking Third Pass %` (as a fraction of all passes)
    * `Average Shot Distance`
    * `Build-up Speed` (e.g., meters advanced per second of possession)
* **Action:** Merge these new features with the base Kaggle dataset.
* **Action:** Conduct Exploratory Data Analysis (EDA) and hypothesis tests on the new features.
    * *Hypothesis Example:* "Test if teams with a higher `PPDA` (less pressing) have a statistically lower `Possession %`."

### Phase 2: Apply ML Methods

* **Action:** Apply **Principal Component Analysis (PCA)** to the engineered playstyle features. This will reduce dimensionality and identify the main components that explain the variance in playstyle.
* **Action:** Apply the **K-Means Clustering** algorithm to the resulting principal components to group teams into distinct clusters.
* **Action:** Analyze the resulting clusters to define them (e.g., "Cluster 1: High Press, Direct Attack", "Cluster 2: Patient Build-up, Low Press").

### Phase 3: Final Submission

* **Action:** Prepare a final presentation of findings. This will be in the form of a final report in this repository, a video, or a webpage.
* **Action:** Create final visualizations (e.g., a 2D scatter plot of the clusters) to communicate the findings.
* **Action:** Ensure all Python code is well-documented with comments.
* **Action:** Finalize and submit the GitHub repository, including a `requirements.txt` file and this `README.md` with instructions to reproduce the analysis.
