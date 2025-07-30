# 🎬 Movie Recommender System

A content-based movie recommendation system built with Streamlit that suggests movies based on similarity scores using machine learning algorithms.

## 🌟 Features

- **Content-Based Filtering**: Recommends movies based on movie features and similarity
- **Interactive Web Interface**: Built with Streamlit for easy user interaction
- **Movie Posters**: Fetches and displays movie posters from The Movie Database (TMDB) API
- **Top 5 Recommendations**: Provides 5 similar movie suggestions for any selected movie
- **Large Movie Database**: Includes a comprehensive dataset of movies with their features

## 🚀 Demo

The application allows users to:
1. Select a movie from the dropdown menu
2. Click "Recommend" to get 5 similar movie suggestions
3. View movie titles along with their posters

## 🛠️ Technology Stack

- **Python 3.x**
- **Streamlit** - Web application framework
- **Pandas** - Data manipulation and analysis
- **NumPy** - Numerical computing
- **Scikit-learn** - Machine learning algorithms (for similarity computation)
- **Requests** - HTTP library for API calls
- **Pickle** - For saving and loading pre-trained models

## 📋 Prerequisites

- Python 3.7 or higher
- TMDB API key (for fetching movie posters)

## 🔧 Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd movies-recomender-system
   ```

2. **Create a virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Run the application**
   ```bash
   streamlit run app.py
   ```

5. **Open your browser**
   - The app will automatically open at `http://localhost:8501`
   - If not, navigate to the URL shown in the terminal

## 📁 Project Structure

```
movies-recomender-system/
├── app.py                 # Main Streamlit application
├── movie_dict.pkl         # Pickled movie dataset (2.1MB)
├── similarity.pkl         # Pre-computed similarity matrix (176MB)
├── requirements.txt       # Python dependencies
├── .gitignore            # Git ignore file
├── venv/                 # Virtual environment (ignored)
└── README.md             # Project documentation
```

## 🎯 How It Works

1. **Data Processing**: The system uses a pre-processed movie dataset stored in `movie_dict.pkl`
2. **Similarity Computation**: A pre-computed similarity matrix (`similarity.pkl`) contains cosine similarity scores between all movies
3. **Recommendation Algorithm**: 
   - When a user selects a movie, the system finds its index in the dataset
   - Retrieves similarity scores for that movie with all other movies
   - Sorts movies by similarity score in descending order
   - Returns the top 5 most similar movies (excluding the selected movie itself)
4. **Poster Fetching**: Uses TMDB API to fetch and display movie posters

## 🔑 API Configuration

The application uses The Movie Database (TMDB) API for fetching movie posters. The API key is currently hardcoded in the application. For production use, consider:

- Using environment variables to store the API key
- Implementing proper error handling for API failures
- Adding rate limiting to respect API quotas

## 🚀 Deployment Options

### Local Development
```bash
streamlit run app.py
```

### Cloud Deployment
- **Streamlit Cloud**: Direct deployment from GitHub
- **Heroku**: With appropriate buildpacks
- **Docker**: Containerized deployment
- **AWS/GCP/Azure**: Cloud platform deployment

**Note**: The `similarity.pkl` file (176MB) may exceed size limits on some free hosting platforms.

## 📊 Dataset Information

- **Movies Dataset**: Contains movie information including titles, genres, and other features
- **Similarity Matrix**: Pre-computed using content-based features (likely genres, keywords, cast, etc.)
- **Total Movies**: The exact number depends on the dataset used during preprocessing

## 🔮 Future Enhancements

- [ ] Add collaborative filtering for hybrid recommendations
- [ ] Implement user rating system
- [ ] Add movie search functionality
- [ ] Include more detailed movie information (cast, director, plot)
- [ ] Optimize similarity matrix storage for better performance
- [ ] Add user authentication and personalized recommendations
- [ ] Implement caching for better API performance
- [ ] Add movie trailers integration
- [ ] Create mobile-responsive design

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

## 📞 Contact

For questions, suggestions, or issues, please open an issue on GitHub or contact the project maintainer.

## 🙏 Acknowledgments

- The Movie Database (TMDB) for providing the movie poster API
- Streamlit team for the amazing web framework
- The open-source community for various Python libraries used in this project

---

**Note**: Make sure to replace the TMDB API key with your own before deploying to production, and consider implementing proper environment variable management for security.
