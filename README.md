# A study on how recommender systems can improve the candidate matching process

The goal of this project is to determine the best Collaborative Filtering algorithm and best Content-based Filtering System (CBF) for macthing jobseekers with vacant positions on our own artifically created job data set. We conclude that KNNBasic (user-based) is the best predictor, closely follwed by KNNBaseline (user-based). However, in terms of noise robustness, KNNBasic turns out to perform second worst out of our ten algorithms (excluding the NormalPredictor algorithm which is a used a as a baseline comparison). NMF on the other hand turned out to be the most robust algorithm.

## Synthetic data
A synthetic dataset is created by means of Faker. In total, we discern between eight job titles, sixteen industry options, five languages, four education level variants, and lastly, four categories for the years of experience, giving rise to thirty-seven features. The result is three different tables: (1) Jobseekers, (2) Vacancies and (3) Matches.

Each of the files can be found in the data.zip. Note the following explanation of the files therein:
* Jobseeker Data: jobseekers
* Vacancies Data: vacancies
* Vacancies with an additional description column for the CBF: vacancies_description
* Matches Data: matches
* Matches with 10% noise: matches_ln10
* Matches with 20% noise: matches_ln20
* Matches with 30% noise: matches_ln30
* Matches with 40% noise: matches_ln40

## Collaborative Filtering
We set aside a training and test set. After that, we train each of our eleven algorithm with the best parameters obtained from the gridsearch on our previously set aside training data. Afterwards, we evaluate the performance in terms of MAE. 

## Content-Based Filtering
We employ two methods: user profiling and a top-vacancy approach. The user profile approach, in which an average for all features by a user is averaged, does not provide convincing results in terms of the job titles recommended. Our findings suggest that the content approach performs better in terms of Kendall ranking compared to the user profiling. However, these results are not statistically significant.
