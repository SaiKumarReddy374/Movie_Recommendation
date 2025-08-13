# 🎬 TMDB Movie Recommendation System

A **Content-Based Movie Recommender** built using the TMDB Movie Metadata dataset from Kaggle.  
The system suggests similar movies based on **plot summaries, genres, keywords, cast, and crew information**.

---

## 📌 Features
- **Content-Based Filtering** using NLP on movie metadata.
- Combines multiple features (`overview`, `genres`, `keywords`, `cast`, `crew`) into a unified **tag**.
- **Text Vectorization** using Bag-of-Words (CountVectorizer).
- Measures similarity using **Cosine Similarity** for fast recommendations.
- Returns **Top N similar movies** for any given title.
- Ready for integration with **Streamlit** or other front-end tools.

---

## 📂 Dataset
Dataset: [TMDB 5000 Movie Metadata](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata)  
Contains:
- `movie_id`, `title`, `overview`
- `genres`, `keywords`, `cast`, `crew`
- Other metadata

---

## 🛠 Tech Stack
- **Python**  
- **Pandas, NumPy** — Data processing  
- **Scikit-learn** — CountVectorizer, Cosine Similarity  
- **NLTK** — Text preprocessing, stemming  
- **Jupyter Notebook** — Development environment  

---

## ⚙️ How It Works
1. **Data Cleaning & Preprocessing**
   - Parse JSON-like columns (`genres`, `keywords`, `cast`, `crew`).
   - Remove spaces in names (`"Sam Worthington"` → `"SamWorthington"`).
   - Combine metadata into a single `tags` column.

2. **Text Vectorization**
   - Convert tags into vectors using **CountVectorizer** (Bag-of-Words).
   - Limit vocabulary size and remove stopwords.

3. **Similarity Calculation**
   - Use **Cosine Similarity** to measure closeness between movies.

4. **Recommendation Function**
   ```python
   recommend('Avatar')
   # Output:
   # 1. Aliens
   # 2. Silent Running
   # 3. Mission to Mars
   # 4. Moonraker
   # 5. Alien³
