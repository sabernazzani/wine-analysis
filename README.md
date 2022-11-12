# Wine Price-Quality Analysis

Problem statement: As a consequence of the highly complex nature of wine as a product, the relationship between wine quality (+ value perception) and price has been a long debate and topic of research for years.


## Feature Engineer

### Color-coding Wine
Observations:
1. White: Most wines cost around 25 USD (median), 50% of wines are priced between 18 USD and 40 USD (second and third quartiles).
2. Red: Most wines cost around 30 USD (median), 50% of wines are priced between 20 USD and 50 USD (second and third quartiles).
3. Rose: Most wines cost around 18 USD (median), 50% of wines are priced between 10 USD and 22 USD.

### Coding Countries
`country_iso` was added to dataset to code countries by their respective ISO code

### Import `NLTK` and Download Associated Lexicon
The function `NLTK` is not a pre-installed python package thus it required an installation. I used the command `!pip install NLTK`. `NLTK`’s feature of interest is the `SentimentIntensityAnalyzer` command and more specifically the `polarity_scores` method. In order to use this it needs an additional download of the `vader_lexicon`

## Sentiment Analysis
### First function: `get_sentiment_score`
The goal of this function is to condence every review in a score ranging from -1 to 1 and simplify the price:quality analysis under study. 

### Second function: `bucketing`
