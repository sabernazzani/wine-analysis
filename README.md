# Wine Price-Quality Analysis

Problem statement: As a consequence of the highly complex nature of wine as a product, the relationship between wine quality (+ value perception) and price has been a long debate and topic of research.


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
This function condenses reviews in a score ranging from -1 to 1 and simplify the price:quality analysis under study. 

### Second function: `bucketing`
This function aggregates data in a quantile-based statistical approach and creates 20 price buckets of equal sizes 

### Third function `spatial_means(df, column)`
This function calculates the average wine sentiment score per country and the price average per country. Next I plotted an interactive choropleth map with the `px.choropleth` function. 

## Results
-  **Rosé wines:** there seems to be a linear regression in the price quality relationship but very inconsistent, with high and low peaks meaning high volatility. We might not have enough information in the dataset or a representative sample size because we can’t seem to notice a pattern or a relationship. It is worth mentioning that rose was the least reviewed type of wine in the dataset.
-  **White wines:** there seems to be a fairly straight linear regression and positive correlation meaning that price and quality go up at a fairly similar pace. In other words the pricier the white wine, to some extent the better the quality.
-  **Red wines:** There is no correlation evident for red wines. There seems to be a sweet spot around $20 then a decay and another sweet spot at $40 where quality is considered high by the sentiment score at those similar price points.

## Conclusions
Price and quality do not seem to have a strong relationship according to the results of my analysis. 

## Potential explanation
Expensive wines are usually expensive for three reasons:
- High quality raw materials (grape, time, barrel, and terroir) that derive a greater value which is typically associated with a higher quality (e.g. aging wine in a high quality oak barrel is more expensive and exposes the wine to oxygen that renders the wine smoother because the tannins become less intense vs a wine aged in a steel barrel). These subtleties are the ones Sommeliers like the reviewers are able to distinguish with their palate. And yet, they reflect the quality of the wine only to the extent that you agree with liking the product, which is where subjectivity comes into play. 
- Other. ther expenses not directly linked to production costs like transportation, packaging, marketing, sales, administrative costs, import taxes5​ ​ etc. If the wine isn’t sold directly to a consumer, then distributors, wholesalers and retailers add a markup price to the bottle.
- "Perceived value" some wines are expensive because they can be. Blindfolded experiments6 show that people do not always prefer the most expensive wine and previous research like the one conducted in 2008 by Plassmann7 prove that an increase in the perceived price of a wine increased taste expectations and increased activity in the orbitofrontal cortex, hence influencing decision making processes.
