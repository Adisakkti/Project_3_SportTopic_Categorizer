# SportTopic Categorizer

## Project Name : SportTopic Categorizer 
**Description :** The filter that will help categorize posts about football and basketball that have come in abundance in webpage

| Feature       | Dataset                               | Description                             |
|:----------------:|:-------------------------------------:|:--------------------------------------:|
| **subreddit**    | Basketball.csv, Football.csv | The category of the post |
| **title** | Basketball.csv, Football.csv | Title of the post |
| **selftext**  | Basketball.csv, Football.csv | The content of that post       |

**Exploratory Data Analysis And Cleaning Data**
1. Collecting data  
    - Basketball.csv ( 7441 rows , 114 columns ) 
    - Football.csv = ( 7431 rows , 114 columns ) 
2. Merging the data from "basketball.csv" and "football.csv" into one dataframe and Drop duplicate , Drop Null values
3. Use  regular expression character that is not an alphabetical letter (lowercase or uppercase) or a whitespace character replace with  withespace
4. Remove words  “football” , “basketball” from all of text
5. Lemmatizer
6. Change Subreddit to Topic_encoded 
    - 0 : Basketball 
    - 1 : Football

**Cleaned data after drop null values , drop duplicate**
![alt text](Pictures/distribution.png)




**Objective:**
1. Build a robust text classification model capable of accurately predicting the topic of a post as either basketball or football.
2. Identify key features and characteristics within the text data that contribute to accurate classification.
3. Evaluate the model's performance on a comprehensive test set to ensure generalization.

## Problem Statement
In an online community platform, users often engage in discussions across a wide range of topics. However, with an increasing volume of content, it becomes challenging for users to navigate and find posts that align with their specific interests. To address this issue, we aim to develop a text classification model that can accurately categorize posts into one of two categories: "Basketball" and "Football". 

**Questions:**  
1. How can we effectively differentiate between posts related to basketball and football?
2. What features of the text data are most influential in making accurate classifications?
3. How can we ensure the model performs reliably on new, unseen posts?



**Solution**
The proposed solution involves implementing a pipeline that combines text preprocessing techniques, including tokenization, lemmatization, and stop word removal, with a machine learning classifier. The selected classifier, `Logistic regression`, `Naive Bayes`, `Random Forest`, is trained on a labeled dataset containing posts from both the "Basketball" and "Football" subreddits. The trained model is then capable of predicting the topic of new, unseen posts with a high degree of accuracy.



**Conclusions:**

The developed text classification model demonstrates strong performance in accurately categorizing posts into the "Basketball" and "Football" topics. Key features such as `selftext` , `title` were found to significantly influence classification outcomes. The model showcases `Naive Bayes` with `Countvectorizer` performance is highest Accuracy.

The best hyperparameters for this model are 
   - cvec__max_df : 0.9 
   - cvec__max_features : 3000 
   - cvec__min_df: 2 
   - cvec__ngram_range : (1, 2)
   - nb__alpha': 1
   - nb__fit_prior : True



**Recommendations:**
1. Use features 'Selftext' and 'Title' with the Naive Bayes model and CountVectorizer to achieve the highest F1-score for categorizing posts into the football and basketball categories. 
2. Continuously monitor and update the model with new data to maintain its accuracy and relevance.
3. Explore the possibility of incorporating additional features or contextual information to further enhance classification accuracy.
4. Consider integrating user feedback mechanisms to iteratively improve the model based on community preferences.


**Impact:**

1. **Enhanced User Experience:** The implementation of the text classification model will streamline content discovery for users, allowing them to quickly find and engage with posts that align with their specific interests.
2. **Improved Community Engagement:** By accurately categorizing posts, users are more likely to participate in discussions, leading to increased interaction and a more vibrant community.
3. **Time and Resource Efficiency:** Automating the categorization process reduces the need for manual sorting and tagging of posts, saving both time and human resources.
4. **Data-Driven Insights:** The model can provide valuable insights into user preferences and popular topics, which can inform content curation and community management strategies.
