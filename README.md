# Building Recommendation Systems using Python

I am already close to finishing this project, and will be updating this README page on a daily basis till I can explain the whole code and the logic.

This is a follow-along practice, using this tutorial: [Beginner Tutorial: Recommender Systems in Python](https://www.datacamp.com/tutorial/recommender-systems-python)

I will use this knowledge I gain and try to create a project made form scratch on my own.

# Theory

## 2 types of filtering

- Content filtering: Location, age, gender
- Collaborative filtering: Previous behavior, similar users

Used to predict rating or preference that a user would give to an item.

## 3 types of recommendation systems

- **Simple recommenders**: Generalized recommendations, based on popularity and/or genre. Eg. Top 100
- **Content-based recommenders**: Similar items based on a particular item. Uses item metadata, such as genre, director, description, etc. Eg. YouTube recommendations.
- **Collaborative filtering engines**: Based on past ratings and preferences of **other users.**
## Dataset

- Lot of movies in one of the csv files of the dataset.
- Multiple features.
- 6 csv files.

Find the dataset [**here](https://www.kaggle.com/rounakbanik/the-movies-dataset/data).**

---

## Simple Recommenders

The following are the steps involved:

- Decide on the metric or score to rate movies on.
- Calculate the score for every movie.
- Sort the movies based on the score and output the top results.

**Most Basic metric to decide top 250: RATINGS. Why NOT to use this?**

- Doesn't take into consideration the movie popularity. Hence, a movie rated 9 by 10 people would be ranked higher than the movie rated 8.5 by 1000 people.
- This could also mean though, that the movie just came out.

To tackle this, we need to come up with a weighted rating that considers the average rating and the number of votes it accumulated.

### Weighted Rating (WR)
$$
WR = \frac{v}{v+m}R + \frac{m}{v+m}C
$$
