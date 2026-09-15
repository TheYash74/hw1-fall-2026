# MovieLens 32M (mini-32m)

The MovieLens platform is a movie recommendation service, capturing user ratings for movie recommendations using a 5-star rating system.

This dataset is prepared for MSE 121 at the University of Waterloo as an example dataset for learning to work with data at the command line and in Python. The data is designed and modified specifically for MSE 121 homework practice and should not be used for academic or industry research outside the context of this course.


## Files

| file              | rows   |
|-------------------|--------|
| `movies.csv`    | 23144   |
| `ratings.csv`       | 340237 |


### `movies.csv`

A CSV file (comma-separated values, one header row, and potential quotes for the `title` field). Movie titles may contain commas in their name, so the file cannot be split on commas with any tool. The first few rows are provided.

```
movieId,title,genres
1,Toy Story (1995),Adventure|Animation|Children|Comedy|Fantasy
2,Jumanji (1995),Adventure|Children|Fantasy
3,Grumpier Old Men (1995),Comedy|Romance
```

Each row represents a movie's details. Rows are sorted in numerical order by `movieId`.

| column | meaning |
|---|---|
| `movieId`| A unique identifier for each movie. |
| `title` | The name of the movie. |
| `genres` | A pipe-separated list of tags that describe the movie. Possible values include: Action, Adventure, Animation, Children's, Comedy, Crime, Documentary, Drama, Fantasy, Film-Noir, Horror, Musical, Mystery, Romance, Sci-Fi, Thriller, War, Western, (no genres listed). |


### `ratings.csv`

A plain CSV file (comma-separated values, one header row, and no quoting). No field contains a comma, so the file can be split on commas with any tool. The first few rows are provided.

```
userId,movieId,rating,timestamp
326,50,3.5,1587531385
326,2959,4.0,1587531389
326,202439,4.0,1587531414
```

Each row represents a user's rating for a movie. Rows are sorted in numerical order by `userId` then `movieId`.

| column | meaning |
|---|---|
| `userId` | A unique identifier for each user. |
| `movieId` | The ID of the movie. The name of this movie can be found in the `movies.csv` file. |
| `ratings` | The user's rating for the movie. |
| `timestamp` | The date and time that the rating was made. Timestamps represent seconds since midnight Coordinated Universal Time (UTC) of January 1, 1970. |


## Things to know before you compute anything

**Row uniqueness.** Users can make multiple movie ratings. Each row in `ratings.csv` is only unique on the `userID` and `movieId` combination.

**Rating scale.** Ratings are made on a 5-star scale, with half-star increments (0.5 stars - 5.0 stars).


## Source

University of Minnesota open data, *MovieLens 32M*, published by GroupLens Research:

<https://grouplens.org/datasets/movielens/32m/>

Licensed under the [University of Minnesota](https://grouplens.org/).


### Usage License

Neither the University of Minnesota nor any of the researchers involved can guarantee the correctness of the data, its suitability for any particular purpose, or the validity of results based on the use of the data set. The data set may be used for any research purposes under the following conditions:

- The user may not state or imply any endorsement from the University of Minnesota or the GroupLens Research Group.
- The user must acknowledge the use of the data set in publications resulting from the use of the data set (see below for citation information).
- The user may redistribute the data set, including transformations, so long as it is distributed under these same license conditions.
- The user may not use this information for any commercial or revenue-bearing purposes without first obtaining permission from a faculty member of the GroupLens Research Project at the University of Minnesota.
- The executable software scripts are provided "as is" without warranty of any kind, either expressed or implied, including, but not limited to, the implied warranties of merchantability and fitness for a particular purpose. The entire risk as to the quality and performance of them is with you. Should the program prove defective, you assume the cost of all necessary servicing, repair or correction.

In no event shall the University of Minnesota, its affiliates or employees be liable to you for any damages arising out of the use or inability to use these programs (including but not limited to loss of data or data being rendered inaccurate).


## How these files differ from the source

GroupLens Research published the MovieLens 32M in May 2024. What changed:

- **Data subset.** To reduce the total number of rows to process, a subset of regular users with fairly recent movie ratings was extracted.
- **Data filter.** The dataset was filtered for pedagogical reasons, removing particular movies and ratings.
