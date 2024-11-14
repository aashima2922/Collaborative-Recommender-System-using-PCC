**Item-Based Collaborative Filtering Recommendation System**

This project implements an item-based collaborative filtering recommendation system. The code uses a similarity measure between items (Pearson Correlation Coefficient) to recommend items similar to those a user has previously interacted with. It’s ideal for scenarios like recommending products, movies, or other items based on a user’s past actions.

Overview of How It Works
Loading Data: The system reads data from three CSV files:

items.csv: Contains details of items (e.g., item ID and category).
users.csv: Contains user details, including their country.
events.csv: Records user interactions with items, including timestamps.
Calculating Similarity:

The system builds a user-item interaction matrix to capture how often each user interacts with each item.
Pearson Correlation Coefficient (PCC) is then used to calculate similarity scores between items. Items with higher similarity scores are more likely to be recommended together.
Session Analysis:

Events are grouped into sessions based on an 8-hour gap between actions.
Duplicate item visits within a session are removed, and sessions with only one event are excluded.
The analysis includes computing statistics like the total number of sessions, average events per session, and popular categories.
Generating Recommendations:

For each session, the system looks at items the user has interacted with and identifies similar items based on the PCC similarity matrix.
It then recommends the top items that are most similar to those in the current session.
Evaluation:

The system is evaluated by checking if recommended items match a target item for each session, allowing a calculation of the "hit rate" for recommendation accuracy.

How to Run the Code
Place items.csv, users.csv, and events.csv in the same directory as the code file.

Run the code:
python recommender.py


The output includes:

Session statistics (like bounce rate and popular categories).
Recommendations for each session.
Evaluation results showing how often the recommended items matched the target item.
Key Components
Loading and Preprocessing Data: Initializes data from CSV files and prepares it for analysis.
Calculating Item Similarity: Builds a similarity matrix using PCC between items.
Session Analysis: Groups events into sessions, computes session statistics, and filters sessions based on criteria.
Recommendation Generation: Identifies top similar items to those in the current session and outputs recommendations.
Evaluation: Measures recommendation accuracy using a hit rate metric.
