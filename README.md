# Movie Recommendation System

A content-based movie recommendation system built with Python that suggests similar movies based on user input using TF-IDF vectorization and cosine similarity.

## Overview

This project implements a movie recommendation engine that analyzes movie attributes (genres, keywords, tagline, cast, and director) to find and recommend similar movies. When a user enters their favorite movie, the system finds the closest match and returns a list of similar movies ranked by similarity score.

## Features

- **Content-Based Filtering**: Recommends movies based on movie content/attributes rather than user ratings
- **Fuzzy Matching**: Uses difflib to find the closest match even if the user doesn't type the exact movie title
- **TF-IDF Vectorization**: Converts text data into numerical feature vectors
- **Cosine Similarity**: Measures similarity between movies based on their feature vectors
- **Top 30 Recommendations**: Returns up to 30 similar movies sorted by relevance

## Project Structure

```
Movie-Recommendation-System/
│
├── movies.csv                    # Dataset containing movie information
├── Movie_Recommendation.ipynb    # Jupyter notebook with the recommendation system
├── requirements.txt              # Python dependencies
├── README.md                     # Project documentation
└── .gitignore                    # Git ignore file
```

## Dataset

The system uses a movie dataset (`movies.csv`) containing the following key features:

| Feature | Description |
|---------|-------------|
| `title` | Movie title |
| `genres` | Movie genres (Action, Comedy, Drama, etc.) |
| `keywords` | Keywords associated with the movie |
| `tagline` | Movie tagline |
| `cast` | Main cast members |
| `director` | Movie director |
| `overview` | Brief plot summary |
| `budget` | Production budget |
| `revenue` | Box office revenue |
| `vote_average` | Average user rating |
| `release_date` | Release date |

## Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/Movie-Recommendation-System.git
   cd Movie-Recommendation-System
   ```

2. **Create a virtual environment (recommended)**
   ```bash
   python -m venv venv
   
   # On Windows
   venv\Scripts\activate
   
   # On macOS/Linux
   source venv/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

## Usage

1. **Launch Jupyter Notebook**
   ```bash
   jupyter notebook
   ```

2. **Open the notebook**
   - Navigate to `Movie_Recommendation.ipynb`

3. **Run all cells**
   - Execute the cells sequentially
   - When prompted, enter your favorite movie name
   - The system will display 30 similar movie recommendations

### Example

```
Enter your favourite movie name: Iron Man

Movies suggested for you:

1. Iron Man
2. Iron Man 2
3. Iron Man 3
4. Avengers: Age of Ultron
5. The Avengers
6. Captain America: Civil War
7. Ant-Man
8. Thor
9. Thor: The Dark World
10. Captain America: The Winter Soldier
...
```

## How It Works

### Algorithm Flow

1. **Data Loading**: Load the movie dataset from CSV file
2. **Feature Selection**: Select relevant features (genres, keywords, tagline, cast, director)
3. **Data Preprocessing**: Handle missing values by replacing them with empty strings
4. **Feature Combination**: Concatenate all selected features into a single text field
5. **Vectorization**: Convert combined text to TF-IDF feature vectors
6. **Similarity Calculation**: Compute cosine similarity matrix between all movies
7. **User Input**: Accept movie name from user
8. **Fuzzy Matching**: Find the closest matching movie title in the dataset
9. **Recommendation**: Sort movies by similarity score and display top recommendations

### Key Concepts

**TF-IDF (Term Frequency-Inverse Document Frequency)**
- Converts text into numerical vectors
- Weights terms by their importance in a document relative to the entire corpus
- Common words get lower weights, distinctive words get higher weights

**Cosine Similarity**
- Measures the cosine of the angle between two vectors
- Values range from 0 (completely different) to 1 (identical)
- Used to find movies with similar feature vectors

## Dependencies

| Package | Version | Purpose |
|---------|---------|---------|
| numpy | >=1.21.0 | Numerical computations |
| pandas | >=1.3.0 | Data manipulation and analysis |
| scikit-learn | >=1.0.0 | TF-IDF vectorization and cosine similarity |
| jupyter | >=1.0.0 | Interactive notebook environment |
| notebook | >=6.4.0 | Jupyter notebook interface |

## Future Improvements

- [ ] Add a web interface using Flask or Streamlit
- [ ] Implement hybrid recommendation (combine content-based and collaborative filtering)
- [ ] Add movie posters and additional metadata to recommendations
- [ ] Include user rating system
- [ ] Deploy as a web application
- [ ] Add more sophisticated NLP techniques (word embeddings, etc.)

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is open source and available under the [MIT License](LICENSE).

## Acknowledgments

- Dataset source: TMDB Movie Dataset
- Inspired by various content-based recommendation system implementations
