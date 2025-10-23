# Movie-Recommendation-ModelOverview
This project is a Movie Recommendation System built using Streamlit that suggests similar movies to users based on their preferences. Alongside recommendations, it also fetches movie posters in real time using the TMDB (The Movie Database) API. The system is powered by machine learning algorithms, data preprocessing techniques, and interactive front-end visualization provided by Streamlit.

The goal of this project is to provide users an engaging, intelligent interface where they can search for a movie and instantly view five similar films complete with posters and metadata. It combines data science, software engineering, and API integration into a functional, visually pleasing web app for movie lovers.

Table of Contents
Features

Dataset Description

System Architecture

Tools and Libraries

Data Preprocessing Workflow

Machine Learning Model

Streamlit Front-End Design

TMDB API Integration

How to Run the Project

File Structure

Screenshots

Future Enhancements

Acknowledgments

Features
Interactive Streamlit web application for easy user interaction.

Content-based filtering model using similarity metrics to recommend movies.

Displays movie posters and names, fetched dynamically using TMDB API.

Efficient data preprocessing pipeline to handle 5000+ movie records.

Responsive, visually appealing Streamlit interface for seamless usage.

Clean and modular Python code ensuring scalability and readability.

Supports quick real-time recommendations with minimal latency.

Dataset Description
The dataset used in this project was sourced from Kaggle’s Movie Dataset repository. It contains around 5000 movies with features such as:

Title

Overview

Genres

Cast and Crew

Keywords

Popularity

Vote Average

Release Date

After data cleaning, these features were refined to focus on attributes most relevant to similarity detection, especially title, genre, cast, crew, and plot overview.

System Architecture
1. Data Collection
Data was downloaded from Kaggle in CSV format, consisting of approximately 5000 unique movie entries.

2. Data Cleaning and Preprocessing
Preprocessing was performed on Jupyter Notebook to ensure accuracy and efficiency. Techniques used include:

Handling missing values and duplicates.

Combining multiple related columns into a unified feature.

Tokenization and stopword removal for textual data.

Vectorization and transformation using CountVectorizer from Scikit-learn.

3. Model Development
A content-based recommendation model was built using cosine similarity. It identifies relationships between movies based on content-related metadata.

4. Backend Integration
Code was refined and finalized in PyCharm, where all machine learning logic, API requests, and Streamlit scripts were implemented.

5. Frontend Deployment
The Streamlit app interface was created for users to input their favorite movies and receive instant recommendations with poster displays.

Tools and Libraries
Core Tools

Python (v3.9+)

Streamlit

Jupyter Notebook

PyCharm IDE

Python Libraries

pandas – data manipulation and cleaning

numpy – numerical computation

scikit-learn – vectorization, cosine similarity calculation

requests – for accessing TMDB API and fetching poster images

pickle – to save and load preprocessed models and similarity matrices

streamlit – for building the web interface

External Resource

TMDB API – provides movie posters and essential metadata

Data Preprocessing Workflow
The preprocessing steps performed in Jupyter Notebook are as follows:

Data Loading: Imported datasets using pandas.read_csv().

Merging Datasets: Combined multiple CSV files (movies, credits, etc.) based on the title or movie ID for cohesive data representation.

Feature Selection: Key features chosen include title, overview, genres, cast, crew, and keywords.

Text Normalization:

Removed unnecessary symbols and punctuation.

Converted text to lowercase for uniformity.

Tokenization & Lemmatization: Structured the text for better processing by the vectorizer.

Feature Engineering: Combined text features into a unified column “tags” for all essential data.

Vectorization: Converted text data into numerical form using Scikit-learn’s CountVectorizer.

Similarity Matrix Creation: Computed pairwise cosine similarity between movies to measure closeness based on content features.

The cleaned data was then serialized into .pkl files (pickle format) for faster loading by the Streamlit app.

Machine Learning Model
Content-Based Filtering
The project uses content-based filtering — a technique that compares the similarity between item features rather than collaborative user behavior.

Cosine Similarity
Given two movie vectors 
A
A and 
B
B, cosine similarity is computed as:

similarity
(
A
,
B
)
=
A
⋅
B
∥
A
∥
×
∥
B
∥
similarity(A,B)= 
∥A∥×∥B∥
A⋅B
 
Movies with the highest similarity scores to a selected movie are recommended as output.

Model Caching
To speed up recommendation generation, the computed cosine similarity matrix is cached in a pickle object, enabling near-instant responses.

Streamlit Front-End Design
The Streamlit app provides a clean, user-friendly layout comprising:

A dropdown or search box for selecting any movie.

A “Recommend” button that triggers the algorithm.

Dynamic display of posters with titles arranged horizontally.

The app utilizes minimalistic design principles with a focus on clarity and interactivity. The recommendations and visuals are presented simultaneously for immediate engagement.

TMDB API Integration
To visually enrich recommendations, poster images are fetched from The Movie Database (TMDB).
Using the requests library, an API call retrieves the movie’s unique ID and poster path. Poster URLs are then constructed as follows:

Poster URL
=
"
h
t
t
p
s
:
/
/
i
m
a
g
e
.
t
m
d
b
.
o
r
g
/
t
/
p
/
w
500
/
"
+
poster_path
Poster URL="https://image.tmdb.org/t/p/w500/"+poster_path
This integration enhances the user experience by combining functional recommendations with appealing visuals.

Ensure you generate an API key by signing up at TMDB and storing it securely. Your app should reference this key in the code (preferably using environment variables or configuration files for privacy).

How to Run the Project
Step 1: Clone the Repository
text
git clone https://github.com/your-username/movie-recommender-streamlit.git
cd movie-recommender-streamlit
Step 2: Install Required Libraries
text
pip install -r requirements.txt
Step 3: Add Your TMDB API Key
Insert your TMDB API key inside the Python script or as an environment variable.

Step 4: Run the Streamlit App
text
streamlit run app.py
Step 5: Use the App
Select a movie from the dropdown.

Click the Recommend button.

View top 5 recommended movies with posters.

File Structure
text
movie-recommender-streamlit/
│
├── app.py                    # Main Streamlit app  
├── movie_list.pkl            # Pickled list of movies  
├── similarity.pkl            # Pickled similarity matrix  
├── notebooks/
│   └── data_preprocessing.ipynb  
├── datasets/
│   └── movies.csv, credits.csv
├── requirements.txt  
├── README.md  
└── images/                   # Optional screenshots or visuals
Screenshots (Suggested)
Include images like:

Main homepage of the app

Recommendation result view

Dataset preprocessing snapshot

Screenshots enhance documentation quality and make the project presentation-ready for GitHub or portfolio use.

Future Enhancements
Integrate hybrid recommendation combining content and collaborative filtering.

Add IMDb/Rotten Tomatoes ratings and streaming availability status.

Implement search-based auto-complete for movie input.

Include movie trailers or additional metadata from APIs.

Deploy the app on Heroku, Streamlit Cloud, or AWS for public access.

Acknowledgments
Thanks to Kaggle for the dataset.

Appreciation to TMDB API for providing movie metadata and posters.

Special credit to scikit-learn and Streamlit for their efficient open-source tools enabling this project’s development.
