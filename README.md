<div align="center">

# Spotify Audio Features Mining

**What can the sound of a song tell us about it?**
Clustering, popularity regression, genre classification and association rules on 114K Spotify tracks.

<p align="center">
  <i></i><br>
  <a href="https://skillicons.dev">
    <img src="https://skillicons.dev/icons?i=python,sklearn,git" />
  </a>
</p>

</div>

---

## Overview

Final project for the **Data Mining** course (UANL, FCFM, Group 032). We apply the full data mining process (cleaning, exploration, modeling and evaluation) to the *Spotify Tracks Dataset* to answer four questions:

| # | Problem | Technique |
|---|---------|-----------|
| 1 | Which songs sound alike? | **K-Means + PCA** (and a content-based recommender) |
| 2 | Can we predict a song's popularity (0–100)? | **Random Forest**, **Gradient Boosting** |
| 3 | Can we recognize a song's genre from its audio? | **Random Forest**, **SVM** |
| 4 | Which audio traits go along with high popularity? | **Apriori** association rules |

## Dataset

- **114,000 tracks · 114 genres · 21 columns**
- Metadata (artist, album, track, genre, popularity, duration, explicit) and **audio features**: `danceability`, `energy`, `loudness`, `speechiness`, `acousticness`, `instrumentalness`, `liveness`, `valence`, `tempo`, `key`, `mode`, `time_signature`.
- After cleaning: **113,836 records** and **89,578 distinct songs** (a song can appear under several genres).

Source: *Spotify Tracks Dataset* (Pandya, Hugging Face), collected through the Spotify Web API.

## Key results

| Analysis | Result |
|----------|--------|
| **Segmentation** | 5 interpretable segments (danceable & happy, intense & dark, soft & acoustic, instrumental & ambient, spoken). Silhouette 0.179; 2 PCA components explain 47.9% of the variance |
| **Popularity** | R² = **0.091** with audio + metadata; **0.285** when genre is added. Error drops from 18.8 (baseline) to 13.95 points |
| **Genre (112 classes)** | **26.9%** accuracy (0.9% by chance), 45.0% top-3 |
| **Genre (10 classes)** | Random Forest **57.2%** · SVM 53.3% |
| **Association rules** | 281 rules → high popularity (max lift **1.39**), 226 rules → low popularity (max lift **1.91**) |

## How to run

```bash
git clone https://github.com/nataliettv/spotify-audio-features-mining.git
cd spotify-audio-features-mining
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
jupyter notebook proyecto_final_spotify.ipynb
```

The notebook reads `dataset.csv` from the same folder, so run it from the repository root.

## Repository structure

```
├── dataset.csv                    # Spotify Tracks Dataset
├── proyecto_final_spotify.ipynb   # Full analysis (in Spanish)
└── *.pdf                          # Project report and slides
```

## 🛠️ Tools

Python · Jupyter Notebook · pandas · NumPy · scikit-learn · Matplotlib · seaborn.
Apriori is implemented from scratch in the notebook, and `HistGradientBoostingRegressor` (scikit-learn) is used as the gradient boosting model.

## Team

- Luis Rolando Aguilar Ortiz
- Yael Abiezer García Guerra
- Perla Natalie González Treviño
- Axel Ivan Verastegui Patiño
- Jaime Cesar Zermeño Pereyra

*Facultad de Ciencias Físico Matemáticas, Universidad Autónoma de Nuevo León.*

## References

- Pandya, M. *Spotify Tracks Dataset*. Hugging Face.
- Pedregosa, F. et al. (2011). Scikit-learn: Machine learning in Python. *JMLR, 12*, 2825–2830.
- Agrawal, R., & Srikant, R. (1994). Fast algorithms for mining association rules. *VLDB*.

---

