# Film Success Analysis
## Summary
* The project brings in data from [The Movie Database API](https://developers.themoviedb.org/3/getting-started/introduction), cleans the data, and analyzes the factors that make films successful
* The following conclusions can be drawn from the analysis:
    * On average, profitable films have higher ratings than unprofitable films
    * On average, profitable films have higher budgets than unprofitable films
    * Film budget is positively correlated with level of critical acclaim
#### How to Reproduce the Analysis
1. Enter [The Movie Database API](https://developers.themoviedb.org/3/getting-started/introduction) key into the "api_keys.py" file
2. Run the "data_cleanup.ipynb" file to pull data from the API, clean the data, and export the cleaned data into a new CSV file
3. Run the "analysis.ipynb" to reproduce the analysis
#### Files
* The "api_keys.py" file is a Python file that contains the API key used in the analysis. The current API key must be replaced in order for the analysis to run
* The "data_cleanup.ipynb" file is a Jupyter Notebook file that pulls in data from the API, cleans the data, and exports the data into a new CSV file
* The "Analysis.ipynb" file is a Jupyter Notebook file that analyzes the data
* All PNG files in the "Figures" folder are images of the graphs that the "Analysis.ipynb" file generates
* All CSV files in the "Output" folder are the datasets that the "data_cleanup.ipynb" file generates
## Data Extraction and Cleaning
* A list of film IDs found on [Kaggle](https://www.kaggle.com/tmdb/tmdb-movie-metadata) is used to pull fresh data from [The Movie Database API](https://developers.themoviedb.org/3/getting-started/introduction)
* Data is cleaned in the following ways:
      * Date columns are converted to datetime format
      * The dataset contains a few rows with N/A'd metrics. These rows only make up a small percentage of the data so all rows with N/As are removed
      * Movies shorter than one hour and longer than four hours generally represent films that are too different than those in the rest of the dataset. Therefore, films shorter than one hour and longer than four hours are removed
      * Films with budgets less than $100,000 are either very old or are not films that many people commonly see and are thus too different from films in the rest of the dataset. Therefore, films with budgets less than $100,000 are removed
      * All films that have 0 reviews are removed from the analysis
      * Films released before the internet age generally have much fewer reviews than films released during the internet age. To prevent there from being inherent bias against older films, only movies released after 2005 are included in this analysis

