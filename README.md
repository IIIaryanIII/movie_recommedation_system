# 🎬 Movie Recommendation System (NLP + FastAPI)

A full-stack movie recommendation system built using **Natural Language Processing (NLP)** and **TF-IDF**, capable of suggesting similar movies based on content. The system integrates with the **TMDB API** to fetch real-time movie details and posters, and provides an interactive UI using Streamlit.

---

## 📌 Features

* 🔍 Search any movie and get similar recommendations
* 🧠 Content-based filtering using TF-IDF
* ⚡ FastAPI backend for high-performance APIs
* 🎨 Interactive UI using Streamlit
* 🎥 Real-time movie data (posters, ratings, genres) via TMDB API
* 📊 Supports ~45,000 movies dataset

---

## 🛠️ Tech Stack

* **Python**
* **FastAPI**
* **Streamlit**
* **Pandas, NumPy**
* **Scikit-learn (TF-IDF Vectorizer)**
* **NLTK / NLP preprocessing**
* **TMDB API**
* **Pickle (for model persistence)**

---

## ⚙️ How It Works

1. **Dataset Processing**

   * Collected ~45,000 movies dataset from Kaggle
   * Cleaned and preprocessed text data
   * Applied NLP techniques:

     * Tokenization
     * Lowercasing
     * Removing punctuation

2. **Feature Engineering**

   * Combined important features (overview, genres, keywords, etc.)
   * Converted text data into numerical vectors using **TF-IDF**

3. **Similarity Calculation**

   * Computed similarity scores using cosine similarity
   * Stored TF-IDF matrix for fast retrieval

4. **Backend (FastAPI)**

   * Handles recommendation logic
   * Integrates with TMDB API for:

     * Posters
     * Movie details
     * Genre-based recommendations

5. **Frontend (Streamlit)**

   * User-friendly interface
   * Displays recommendations with posters and ratings

---

## 📂 Project Structure

```
project/
│── app.py                # FastAPI backend
│── streamlit_app.py      # Streamlit UI
│── df.pkl                # Processed dataset
│── tfidf.pkl             # TF-IDF vectorizer
│── tfidf_matrix.pkl      # TF-IDF matrix
│── indices.pkl           # Title-index mapping
│── requirements.txt
│── README.md
```

---

## 🚀 API Endpoints

* `GET /health` → Check API status
* `GET /home` → Get trending/popular movies
* `GET /tmdb/search?query=` → Search movies
* `GET /movie/id/{id}` → Get movie details
* `GET /recommend/tfidf?title=` → TF-IDF recommendations
* `GET /movie/search?query=` → Full recommendation bundle

---

## 🔑 Setup Instructions

### 1️⃣ Clone Repository

```bash
git clone https://github.com/your-username/movie-recommender.git
cd movie-recommender
```

### 2️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

### 3️⃣ Add TMDB API Key

Create a `.env` file:

```
TMDB_API_KEY=your_api_key_here
```

### 4️⃣ Run Backend

```bash
uvicorn app:app --reload
```

### 5️⃣ Run Frontend

```bash
streamlit run streamlit_app.py
```

