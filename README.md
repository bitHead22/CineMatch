# 🎬 CineMatch - Movie Recommendation System

![CineMatch App](https://github.com/bitHead22/CineMatch/raw/main/screenshots/app-demo.png)

## Overview

**CineMatch** is an intelligent movie recommendation system built with **Streamlit** and **FastAPI**. It provides personalized movie suggestions using multiple recommendation algorithms including TF-IDF similarity, genre-based filtering, and TMDB API integration.

## Features

✨ **Core Features:**
- 🔍 **Smart Search** - Type keywords to find movies with autocomplete suggestions
- 🎭 **Movie Details** - View comprehensive movie information including overview, genres, release date, and backdrop
- 🤖 **AI Recommendations** - Get personalized recommendations using:
  - TF-IDF similarity matching
  - Genre-based filtering
  - Trending & popular movies
- 🏠 **Home Feed** - Browse trending, popular, top-rated, now playing, and upcoming movies
- 📱 **Responsive UI** - Clean, modern Streamlit interface with customizable grid layout
- 🎨 **TMDB Integration** - Access to 500,000+ movies with high-quality posters and metadata

## Tech Stack

**Frontend:**
- Streamlit 1.36.0
- Modern responsive CSS styling

**Backend:**
- FastAPI 0.111.0
- Uvicorn 0.30.1
- Python 3.11+

**Data & ML:**
- Pandas 2.3.1
- NumPy 2.3.2
- Scikit-learn 1.7.1
- SciPy 1.16.1

**APIs:**
- TMDB (The Movie Database) API

## Installation

### Prerequisites
- Python 3.11+
- pip

### Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/bitHead22/CineMatch.git
   cd CineMatch
   ```

2. **Create a virtual environment (optional but recommended):**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Set up environment variables:**
   Create a `.env` file in the project root:
   ```
   TMDB_API_KEY=your_tmdb_api_key_here
   API_BASE=http://127.0.0.1:8000
   ```

   Get your TMDB API key from: https://www.themoviedb.org/settings/api

## Usage

### Start the Backend Server

```bash
python main.py
# or
uvicorn main:app --reload
```

The API will be available at `http://127.0.0.1:8000`

### Start the Streamlit App

In a new terminal:

```bash
streamlit run app.py
```

The app will open at `http://localhost:8501`

## Project Structure

```
CineMatch/
├── app.py                    # Streamlit frontend application
├── main.py                   # FastAPI backend server
├── movies_metadata.csv       # Movie dataset
├── movies.ipynb             # Jupyter notebook for exploration
├── requirements.txt         # Python dependencies
├── runtime.txt             # Python version specification
├── .gitignore              # Git ignore file
├── df.pkl                  # Preprocessed dataframe
├── indices.pkl             # TF-IDF indices
├── tfidf.pkl               # TF-IDF vectorizer
└── README.md               # This file
```

## API Endpoints

The backend provides the following endpoints:

### Search & Discovery
- `GET /tmdb/search` - Search movies by keyword
- `GET /home` - Get home feed (trending, popular, etc.)
- `GET /movie/id/{tmdb_id}` - Get movie details

### Recommendations
- `GET /movie/search` - Search with recommendations bundle
- `GET /recommend/genre` - Genre-based recommendations
- `GET /recommend/tfidf` - TF-IDF similarity recommendations

## How It Works

1. **Search** - User enters a movie keyword
2. **Suggestions** - API provides autocomplete suggestions with release years
3. **Results** - Matching movies displayed in grid format
4. **Details** - Click "Open" to view full movie details
5. **Recommendations** - AI generates personalized recommendations:
   - **Similar Movies (TF-IDF)** - Based on plot, cast, and metadata similarity
   - **More Like This (Genre)** - Based on matching genres

## Features in Detail

### Smart Search
- Real-time keyword matching
- Minimum 2 characters to trigger search
- Autocomplete with release years
- Word-matching based filtering

### Movie Details
- High-quality TMDB poster and backdrop images
- Complete metadata (genres, release date, overview)
- Two recommendation algorithms running in parallel
- Graceful fallback if TF-IDF data unavailable

### Home Feed
- Multiple categories: Trending, Popular, Top Rated, Now Playing, Upcoming
- Customizable grid columns (4-8)
- Infinite scrolling with caching
- Real-time category switching

## Performance

- **Caching**: 30-second cache on autocomplete and API calls
- **Lazy Loading**: Images load on demand
- **Grid Optimization**: Efficient column layout system
- **Error Handling**: Graceful fallbacks for API failures

## Contributing

Contributions are welcome! Feel free to:
- Report bugs
- Suggest features
- Submit pull requests

## License

This project is open source and available under the MIT License.

## Contact

- **GitHub**: [bitHead22](https://github.com/bitHead22)
- **Email**: ayushmantiwari033@gmail.com

---

**Enjoy discovering your next favorite movie! 🍿**
