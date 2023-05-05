# Building a Basic Job-Recommender-System

The goal of this project is to develop a basic Collaborative (CF) and Content-based Filtering System (CBF) for job vacancies using the given synthetic data, and in a second step, to determine the best performing model.

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
We use a benchmarking approach to choose a set of algorithms to tune the hyperparameters. The Surprise Library will be used for this. We determine that KNNBasic performs the best for the clean as well as noisy data levels. Moreover, our expectation is confirmed that the noiser, the higher the MAE is generally.

## Content-Based Filtering
The user profile approach, in which an average for all features by a user is averaged, is tried first. The results are not convincing in terms of job titles recommended. The content approach performs better. For this, we used the well-known TF-IDF approach and add a minimum similarity requirement as well as filtering out already matched vacancies in the recommendation. In the future, we would also like to add a feature that attaches weights to the job title to increase the relevance of recommendations.
