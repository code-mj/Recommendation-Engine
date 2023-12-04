# Recommendation-Engine

### Dataset:
MovieLens: https://grouplens.org/datasets/movielens/latest/
![image](https://github.com/code-mj/Recommendation-Engine/assets/25456564/f15b068e-2f48-45ae-adb9-f50afd12606f)

FER2013 dataset: https://www.kaggle.com/datasets/msambare/fer2013
![Uploading image.png…]()


### Module1: Movie Recommendation Engine using ALS

**Motivation:**  
This project focuses on leveraging the ALS collaborative recommendation engine through Spark MLlib to provide user-based movie recommendations. The goal is to implement a scalable matrix factorization technique for generating accurate movie suggestions.

**Step 1: Data Exploration**  
- Loaded four datasets: movies, ratings, links, and tags.
- Conducted exploratory data analysis to gather fundamental information, including user count, movie count, user-wise and movie-wise rating distribution, and genre distribution across movies.

**Step 2: Model Building and Tuning**  
- Preprocessed the data.
- Constructed an ALS model using rating data to predict movie ratings.
- Tuned model parameters (maxIter, rank, regParam) through grid search and 5-fold cross-validation to minimize RMSE on the validation set, obtaining the best-performing model.

**Step 3: Model Evaluation**  
- Utilized the best model to predict ratings on the test set.
- Calculated RMSE to assess the model's predictive performance.

**Step 4: Recommendations and Similar Movies**  
- Recommended 5 movies for users with IDs 575 and 232 based on the predictions of the best model.
- Identified 5 movies most similar to movies with IDs 471 and 454 using an approximate nearest neighbor search algorithm on movie feature vectors.

**Conclusion:**  
- The RMSE of the best ALS model on the test data is 0.93, demonstrating the model's ability to predict movie ratings effectively.
- ALS facilitates movie recommendations based on user preferences and finds similar movies, proving its effectiveness in recommendation systems.
- Future improvements could involve integrating additional dataset information like movie genres and tags, incorporating both explicit and implicit feedback, experimenting with various techniques such as KNN, Deep Learning, ensemble methods, etc., to enhance model performance.

### Module2: Real-time Emotion-Based Movie Recommendation

**Motivation:**

The motivation behind this project is to create a real-time movie recommendation system that leverages emotion recognition to suggest top-rated movies aligned with the user's current emotional state. By training emotion recognition model on "fer2013" dataset and using movies - rating datasets, the aim is to provide personalized movie recommendations tailored to the user's detected emotion.

**Steps:**

1. **Data Loading:**
   - Loaded the movies and ratings datasets.
  
2. **Emotion Recognition Model Setup:**
   - Loaded a pre-trained emotion recognition model from the saved JSON and weights files which is generated from Mansi Face_Emotion_Recognition.ipynb file.
     
3. **Simulated Emotion Detection:**
   - Created a simulation for real-time emotion recognition from a camera feed by randomly selecting an emotion from a predefined list. This step simulates the detection of user emotion.

4. **Recommendation Function:**
   - Defined a function to recommend top-rated movies based on the recognized emotion.
   - Mapped emotions to movie genres to filter relevant movies from the dataset.
   - This step involves joining the filtered movie data with ratings to calculate average movie ratings. Sorting these movies by their average ratings in descending order enables the system to recommend top-rated movies aligned with the user's detected emotion.

5. **Movie Recommendation Based on Recognized Emotion:**
   - Utilized the recognized emotion to recommend top-rated movies specific to that emotion.
   - Displayed the recommended top-rated movies to the user.

**Conclusion:**

 - The emotional recognition model is trained with accuracy 0.76 using CNN and as per our case, the recognized emotion is "sad" and for that emotion, the top rated movies are:
    - George Carlin: You Are All Diseased
    - Dr. Goldfoot and the Bikini Machine
    - I'm the One That I Want
 - The project successfully implemented a real-time movie recommendation system based on the user's detected emotion. By combining emotion recognition with movie rating data, the system provided personalized movie recommendations aligned with the user's current emotional state.
 - The implementation allowed for dynamic movie suggestions, enhancing user engagement and satisfaction.
 - Further enhancements could involve deploying this recommendation system in a live environment with an actual emotion recognition interface to provide real-time recommendations to users.
