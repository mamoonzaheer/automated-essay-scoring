# Automated Essay Scoring System

This project implements an automated essay scoring system using machine learning techniques. The system analyzes essays and provides numerical scores based on the content and quality of the writing.

## Features

- Essay scoring using machine learning
- Text preprocessing with NLP techniques
- RESTful API endpoint for scoring essays
- CORS support for cross-origin requests

## Project Structure

- `app.py`: Main Flask application with the scoring API
- `automated_essay_scoring.ipynb`: Jupyter notebook containing the model training code
- `train.csv`: Training dataset for the model
- `tfidf_vectorizer.joblib`: Saved TF-IDF vectorizer
- `rf_model.joblib`: Saved Random Forest model

Note: The trained model file rf.joblib is not included in this repository because of size limits on GitHub.

## Setup and Installation

1. Clone the repository
2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Download the required NLTK data:
   ```python
   import nltk
   nltk.download('punkt')
   nltk.download('stopwords')
   nltk.download('wordnet')
   ```
4. Download the spaCy model:
   ```bash
   python -m spacy download en_core_web_sm
   ```

## Usage

1. Start the Flask server:
   ```bash
   python app.py
   ```

2. The API will be available at `http://localhost:5000`

3. To score an essay, send a POST request to `/predict` with the following JSON format:
   ```json
   {
       "essay": "Your essay text here"
   }
   ```

4. The API will return a JSON response with the predicted score:
   ```json
   {
       "prediction": 4
   }
   ```

## Model Details

The system uses:
- TF-IDF vectorization for text feature extraction
- Random Forest classifier for scoring
- NLTK and spaCy for text preprocessing
- Flask for the web API

## License

This project is open source and available under the MIT License. 