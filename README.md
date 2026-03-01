IMDb Sentiment Analysis:
Bayesian Approach
This project applies Bayes’ Theorem to 50,000 IMDb movie reviews to quantify how specific keywords shift our confidence in a review’s sentiment.

The Logic.

We treated sentiment analysis as a process of updating beliefs based on evidence:
 The Prior: P(Positive). We started with a neutral 0.50 probability, as the dataset is perfectly balanced.
 The Likelihood: P(Keyword|Positive). We calculated how often a word appears specifically in positive reviews.
 The Marginal: P(Keyword). We used the Law of Total Probability to find the total frequency of a word across the entire dataset.
 The Posterior: P(Positive|Keyword). This is the final result that "updates" our initial 50% guess based on the keyword found.
 
 Key Findings.
 
 Our analysis showed that negative keywords often provide a stronger mathematical "shove" than positive ones. For example, while a word like "excellent" increases the probability of a positive review to roughly 77%, a negative word like "waste" is much more influential—it crashes the probability of a positive sentiment down to nearly 8%. This proves that certain "high-signal" words carry significantly more predictive power than others.
 Technical Implementation
 Modular Design: Created a reusable function to handle keywords without repeating code (DRY principle).
 Regex Precision: Used Regular Expression boundaries (\b) to prevent the "substring trap," ensuring the model didn't confuse "waste" with "wasteful."
 Total Probability: Applied the Law of Total Probability to the marginal denominator to ensure all results were statistically normalized.
 
 How to Run

 Place IMDB Dataset.csv in the project folder.
 Open the Jupyter Notebook.
 Execute all cells to generate the probability tables and analysis.
