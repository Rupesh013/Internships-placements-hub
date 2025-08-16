1. Project Overview / Objective
Objective:
The aim of this project is to analyze and visualize data from the IMDB Movie dataset. I want to discover the top-rated movies overall and in the Comedy genre, using Python and data science tools in Google Colab.

2. Dataset Description
Dataset Used:
The project uses IMDB-Movie-Data.csv, which contains information on many movies.
Key columns include:

Title: Name of the movie

Genre: Type of movie (Comedy, Action, etc.)

Rating: IMDB score

Year, Director, Cast, etc.

3. Code Cells
(Show your code for each part – below is an example for loading data and analysis)

python
import pandas as pd
data = pd.read_csv('/content/IMDB-Movie-Data.csv')
4. Analysis & Results
A. Top 10 Rated Comedy Movies

python
comedy_movies = data[data['Genre'].str.contains('Comedy', na=False)]
top_10_comedy = comedy_movies.sort_values(by='Rating', ascending=False).head(10)
print(top_10_comedy[['Title', 'Rating', 'Genre']])
(Printed table appears here)

B. Top 5 Rated Movies Overall

python
top_5_movies = data.sort_values(by='Rating', ascending=False).head(5)
print(top_5_movies[['Title', 'Rating', 'Genre']])
(Printed table appears here)

5. Visualization (Optional)
python
import matplotlib.pyplot as plt
plt.figure(figsize=(10, 6))
plt.barh(top_10_comedy['Title'], top_10_comedy['Rating'], color='skyblue')
plt.xlabel('Rating')
plt.title('Top 10 Rated Comedy Movies')
plt.gca().invert_yaxis()
plt.show()
(Chart appears here)

6. Explanations & Insights
Filtering by genre shows which movies excel in a certain style (like Comedy).

Sorting by ratings lets us easily see what the audience appreciates most.

Visualization makes it quicker to compare movie ratings.

7. Challenges Faced & What I Learned (Optional but good to include)
I faced errors with missing libraries and file paths, but learned to troubleshoot using error messages.

Learned how to filter data based on text in columns and create charts in Python.

Gained practical experience in working with real-world datasets.
