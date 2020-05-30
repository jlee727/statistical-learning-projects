# Representation of Women in Film: Project Overview

> The [Bechdel test](https://en.wikipedia.org/wiki/Bechdel_test), also known as the Bechdel–Wallace test, is a measure of the representation of women in fiction. It asks whether a work features at least two women who talk to each other about something other than a man. The requirement that the two women must be named is sometimes added.

- Created a report that explores statistical models for predicting the bechdel test score of movies based on pre-production data
- Collected data from three separate data sources (bechdel test score, movie meta data, movie genre data) 
- Feature engineered predictor variables (female director, female writer, female ratio of crew, genre)
- Optimized regression and classification models (K-nearest-neighbors, stochastic gradient boosted, multinomial/logistic regression)


***


## Code used

**R version 3.6.1**

**Python version 3.8.0**


## Data

- [Bechdel Test](https://bechdeltest.com/api/v1/doc)

- [MovieLens Dataset](https://www.kaggle.com/rounakbanik/the-movies-dataset)

- [Movie Genere](https://developers.themoviedb.org/3/genres/get-movie-list)


The first dataset contains the Bechdel test scores for over 8000 movies ranging from the early 1900s to 2019, thus providing us with a varied sample. The second dataset contains widespread information about movies thus allowing us to try a variety of modeling approaches. The two datasets are merged based on their IMDB IDs.

The specific task at hand here is classifying the multiclass variable `bechdel` and its binary counterpart `bechdel_bin`. Important predictors such as `female_ratio`, `female_director` as well as the various genre dummy variables are calculated from the `cast_crew` data set. Other predictors include budget and year of release.
 
We specifically focus on pre-release information to improve the overall applicability of this model. Some exploratory data analysis can be found in the appendix.


## Model Building

In order to predict the Bechdel test score, a variety of binary and multiclassification techniques were used in addition to regression methods. Multiclassification tasks tried to predict a score between 0 - 3 whereas binary classification tasks simply predicted 0 (fail) or 1 (pass). 

The modeling strategies considered were:

- KNN Classification (multi / binary)
- KNN Regression 
- Stochastic Gradient Boosted (multi / binary classification) 
- Multinomial Regression (multiclass)
- Logistic Regression (binary class)

