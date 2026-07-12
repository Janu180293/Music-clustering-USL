# 🎵 Music Clustering Using Unsupervised Machine Learning

## 📌 Project Overview

With millions of songs available on music streaming platforms, manually categorizing tracks into genres or moods is both time-consuming and impractical. This project applies **Unsupervised Machine Learning** techniques to automatically group similar songs based on their audio characteristics.

The project explores two clustering algorithms:

- **K-Means Clustering** (Final Selected Model)
- **DBSCAN Clustering** (Comparison Model)

The songs are grouped using audio features such as danceability, energy, tempo, acousticness, and more, without using any predefined labels.

---

## 🎯 Objectives

- Perform Exploratory Data Analysis (EDA) on the music dataset.
- Preprocess and scale the audio features.
- Apply K-Means clustering to group similar songs.
- Determine the optimal number of clusters using the Elbow Method and Silhouette Score.
- Apply DBSCAN for density-based clustering and outlier detection.
- Evaluate clustering performance using multiple evaluation metrics.
- Visualize clusters using PCA.
- Interpret and profile each cluster based on feature averages.

---

## 📂 Dataset

**Dataset:** Amazon Music Dataset

**Total Songs:** 95,837

### Selected Audio Features

- Danceability
- Energy
- Loudness
- Speechiness
- Acousticness
- Instrumentalness
- Liveness
- Valence
- Tempo
- Duration (ms)

These features describe the rhythm, mood, instrumentation, and overall characteristics of each song.

---

## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

---

## 📊 Project Workflow

```
Dataset
   │
   ▼
Data Exploration (EDA)
   │
   ▼
Data Preprocessing
   │
   ▼
Feature Scaling (StandardScaler)
   │
   ▼
K-Means Clustering
   │
   ▼
DBSCAN Clustering
   │
   ▼
Cluster Evaluation
   │
   ▼
PCA Visualization
   │
   ▼
Cluster Interpretation
   │
   ▼
Export Final Dataset
```

---

# 🔍 Exploratory Data Analysis

The following analyses were performed:

- Dataset overview
- Missing value analysis
- Duplicate value checking
- Summary statistics
- Feature distribution
- Correlation analysis
- Outlier detection

---

# ⚙️ Data Preprocessing

The preprocessing steps included:

- Selecting relevant audio features
- Removing unnecessary columns
- Handling missing values (if any)
- Standardizing features using **StandardScaler**

Feature scaling ensures that all audio features contribute equally during distance calculations in clustering algorithms.

---

# 🤖 K-Means Clustering

K-Means clustering was selected as the primary clustering algorithm.

### Steps Performed

- Standardized the dataset
- Applied the Elbow Method
- Evaluated different values of K using Silhouette Score
- Selected the optimal number of clusters
- Assigned cluster labels to each song

### Optimal Number of Clusters

**K = 3**

<img width="548" height="359" alt="image" src="https://github.com/user-attachments/assets/ac1fd613-0117-4254-aa68-0ee8a93bb7f7" />


### Silhouette Scores

| K | Score |
|---|--------|
|2|0.2045|
|3|0.2413|
|4|0.2312|
|5|0.1904|
|6|0.1600|
|7|0.1916|
|8|0.1699|
|9|0.1695|
|10|0.1778|

Based on the evaluation, **K = 3** was selected as it provided the best balance between compactness and separation.

---

# 📈 Cluster Evaluation

The clustering model was evaluated using:

- Silhouette Score
- Davies-Bouldin Index
- Inertia

These metrics help measure cluster compactness and separation.

---

# 🎵 Cluster Interpretation

## Cluster 0 – Spoken & Live Tracks

Characteristics:

- High Speechiness
- High Liveness
- Moderate Danceability
- Short Duration

Examples:

- Spoken-word recordings
- Podcasts
- Live recordings
- Comedy tracks

---

## Cluster 1 – Chill Acoustic Songs

Characteristics:

- High Acousticness
- High Instrumentalness
- Low Energy

Examples:

- Acoustic music
- Instrumental tracks
- Folk music
- Relaxing songs

---

## Cluster 2 – Energetic Party Tracks

Characteristics:

- High Energy
- High Tempo
- High Danceability
- High Valence

Examples:

- Pop
- Dance
- EDM
- Workout playlists

---

# 🌐 PCA Visualization

Principal Component Analysis (PCA) was used to reduce the 10-dimensional feature space into two principal components.

PCA helps visualize how the clusters are distributed in a two-dimensional space while preserving as much variance as possible.

<img width="523" height="371" alt="image" src="https://github.com/user-attachments/assets/bd3ab633-9c57-4665-91cb-693b89f3b44f" />


---

# 🌟 DBSCAN Clustering

DBSCAN was implemented as an alternative clustering algorithm.

### Parameters

- eps = 1.0
- min_samples = 10

### Results

- One dominant cluster
- Multiple very small clusters
- 13,081 songs identified as noise (≈13.65%)

### Observation

Although DBSCAN successfully detected outliers, it produced one very large cluster and several tiny clusters, making the results less balanced and difficult to interpret.

Therefore, **K-Means was selected as the final clustering algorithm**.

---

# 📊 K-Means vs DBSCAN

| Feature | K-Means | DBSCAN |
|---------|----------|----------|
| Number of Clusters | Fixed | Automatic |
| Need to specify K | ✅ Yes | ❌ No |
| Detects Outliers | ❌ No | ✅ Yes |
| Cluster Shape | Spherical | Arbitrary |
| Interpretation | Easy | Moderate |
| Selected for Project | ✅ Yes | Comparison Only |

---

# 📷 Visualizations

The project includes the following visualizations:

- Elbow Method
- Silhouette Score
- PCA Scatter Plot
- Cluster Profile Bar Chart
- Heatmap
- Distribution Plots
- Boxplots

---

# 📁 Project Structure

```
Music-clustering-USL/
│
├── data/
│   └── single_genre_artists.csv
│
├── notebooks/
    └── Amazon_EDA.ipynb
│   └── Amazon_Clustering.ipynb
│
├── output/
│   ├── Songs_Clustered.csv
│   ├── cluster_summary.csv
│
├── README.md
└── requirements.txt
```

---

# 🚀 How to Run the Project

### Clone the Repository

```bash
git clone https://github.com/Janu180293/Music-Clustering-Project.git
```

### Navigate to the Project Folder

```bash
cd Music-Clustering-Project
```

### Install Required Libraries

```bash
pip install -r requirements.txt
```

### Run the Notebook

Open Jupyter Notebook and execute:

```
Music_Clustering.ipynb
```

---

# 📌 Results

- Successfully clustered **95,837 songs** into **3 meaningful groups**.
- Compared K-Means and DBSCAN clustering techniques.
- Identified spoken, acoustic, and energetic music categories.
- Demonstrated how unsupervised learning can organize music collections without predefined labels.

---

# 🔮 Future Enhancements

- Implement Hierarchical Clustering.
- Explore Gaussian Mixture Models (GMM).
- Integrate a music recommendation system.
- Build a Streamlit web application for interactive clustering.
- Deploy the project on Streamlit Community Cloud or Hugging Face Spaces.

---

# 👨‍💻 Author

Janani M

Machine Learning Project

---

# ⭐ If you found this project useful, don't forget to Star ⭐ the repository!
