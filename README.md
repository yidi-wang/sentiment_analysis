# Sentiment Analysis Using Deep Learning


## Install

This project requires **Python 2.7** and the following Python libraries installed:

- [NLTK](http://www.nltk.org/)
- [re](https://docs.python.org/2/library/re.html)
- [scikit-learn](http://scikit-learn.org/stable/)
- [keras](https://keras.io/)
- [matplotlib](http://matplotlib.org/)
- [seaborn](https://seaborn.pydata.org/)
- [pyodbc](https://mkleehammer.github.io/pyodbc/)
- [tweepy](http://tweepy.readthedocs.io/en/v3.5.0/)
- [pickle](https://docs.python.org/2/library/pickle.html)
- [IMDbPY](https://imdbpy.sourceforge.io/)

You will also need to have software installed to run and execute a [Jupyter Notebook](http://ipython.org/notebook.html).

If you do not have Python installed yet, it is highly recommended that you install the [Anaconda](http://continuum.io/downloads) distribution of Python, which already has the above packages and more included. Make sure that you select the Python 2.7 installer and not the Python 3.x installer.


## Code

`create_database` folder contains the SQL scripts that create the tables for storing relevant information of each tweet in Microsoft SQL Server.  You need to create the tables first, then follow this [documentation](https://github.com/mkleehammer/pyodbc/wiki) to connect Python to SQL Server. 

`pylib` folder provides some convenient functions to write results to SQL Server.

`sentiment_analysis.ipynb` lets you train different models on labeled movie reviews to classify sentiment.

`twitter_streaming.ipynb` provides sample code for streaming 100 tweets with the hashtag "#DaddysHome2".

`tweets_analysis.ipynb` allows you to load the pre-trained classifier to analyze the sentiment of tweets about movies, convert the results in the range of [0, 10], and compare the number to the IMDB rating. 


## Run

**To train a sentiment classifier:**

In a terminal or command window, navigate to the top-level project directory `sentiment_analysis/` (that contains this README), and run one of the following commands:

```bash
ipython notebook sentiment_analysis.ipynb
```  
or
```bash
jupyter notebook sentiment_analysis.ipynb
```

**To analyze tweets:**

Modify the `config.py` file to add your Twitter API credentials, and run one of the following commands to stream tweets:

```bash
ipython notebook twitter_streaming.ipynb
```  
or
```bash
jupyter notebook twitter_streaming.ipynb
```

After receiving enough tweets, run one of the following commands:

```bash
ipython notebook tweets_analysis.ipynb
```  
or
```bash
jupyter notebook tweets_analysis.ipynb
```


## Data

The “Large Movie Review Dataset” contains 25,000 highly polar movie reviews for training, and another 25,000 reviews for testing. In both training and testing data sets, there are 50% positive reviews and 50% negative reviews. More information can be found on the [Stanford AI Lab](http://ai.stanford.edu/~amaas/data/sentiment/).
