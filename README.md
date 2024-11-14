Item-Based Collaborative Filtering Recommendation System
This recommendation system is built using item-based collaborative filtering, a popular method used in recommendation systems to suggest items similar to those a user has shown interest in. Instead of recommending items based on similar users, it recommends items based on similarities between items themselves.

How It Works
Item-Based Collaborative Filtering:

Collaborative filtering is a method of making automatic predictions about the interests of a user by collecting preferences from multiple users.
In item-based collaborative filtering, items are compared to each other based on user interactions. For example, if many users who liked Item A also liked Item B, these two items are considered similar.
Similarity Calculation with Pearson Correlation Coefficient (PCC):

This system calculates the similarity between items using the Pearson Correlation Coefficient (PCC), a measure of the linear correlation between two variables.
PCC helps identify items that have been interacted with similarly by users. If two items have a high PCC score, they are likely to be recommended together.
Formula for PCC:

PCC
𝑖
,
𝑗
=
∑
(
𝑅
𝑢
,
𝑖
−
𝑅
𝑖
‾
)
(
𝑅
𝑢
,
𝑗
−
𝑅
𝑗
‾
)
∑
(
𝑅
𝑢
,
𝑖
−
𝑅
𝑖
‾
)
2
⋅
∑
(
𝑅
𝑢
,
𝑗
−
𝑅
𝑗
‾
)
2
PCC 
i,j
​
 = 
∑(R 
u,i
​
 − 
R 
i
​
 
​
 ) 
2
 
​
 ⋅ 
∑(R 
u,j
​
 − 
R 
j
​
 
​
 ) 
2
 
​
 
∑(R 
u,i
​
 − 
R 
i
​
 
​
 )(R 
u,j
​
 − 
R 
j
​
 
​
 )
​
 
Where:
𝑅
𝑢
,
𝑖
R 
u,i
​
  and 
𝑅
𝑢
,
𝑗
R 
u,j
​
  are the interaction values (e.g., ratings) of user 
𝑢
u for items 
𝑖
i and 
𝑗
j.
𝑅
𝑖
‾
R 
i
​
 
​
  and 
𝑅
𝑗
‾
R 
j
​
 
​
  are the average interaction values for items 
𝑖
i and 
𝑗
j.
Features and Components
Recommender Class
The Recommender class performs the following functions:

Loading Data: Reads the items, users, and events datasets.
Training the Model: Computes similarity between items using PCC based on the user-item interaction data.
Analyzing Sessions: Processes user sessions to compute metrics like bounce rate and average session length.
Making Recommendations: Recommends items by finding those similar to items in a user’s current session.
Evaluation
The model is evaluated by checking if the target item for each session appears in the top 5 recommended items, calculating the hit rate as an evaluation metric.


