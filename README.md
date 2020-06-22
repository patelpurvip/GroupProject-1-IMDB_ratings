# Critic Scores vs. Viewer Ratings on the Internet Movie Database(IMDb)

This repository houses my personal contributiones to part of a larger data group project related to IMDb. The original project (including commit history) and the full final product is housed in the following repository: https://github.com/cckuqui/IMDB-movie-data

The project used Pandas & Matplotlib libraries to analyze movie ratings data to determine weather, in general, critics or average viewers are harsher critics of movies listed on IMDb.


## Definitions 
In order to be able to compare the two measures, it is important to understand how each measure is created and the scale on which it is measured.

WEIGHTED AVERAGE VOTE: IMDb registered users can cast a vote (from 1 to 10) on every released title in the database. Individual votes are then aggregated and summarized as a single IMDb rating. Users can update their votes as often as they’d like, but any new vote on the same title will overwrite the previous one, so it is one vote per title per user.

METACRITIC SCORE: A Metascore is a weighted average where IMDB assigns more importance, or weight, to some critics and publications than others, based on their quality and overall stature. A movie gets a Metascore when IMDB has collected at least four critics' reviews for that movie. Metascores range from 0-100, with higher scores indicating better overall reviews. IMDB also normalizes the resulting scores (akin to "grading on a curve" in college), which prevents scores from clumping together.


## Data Cleaning
Only 74,196 of the total movies listed in IMDB (at the time) had been reviewed by viewers, and only 70,286 had been reviewed by critics. Therefore, the first step is to eliminate the movies that did not have reviews by BOTH viewers and critics.

Additionally, and more importantly, only 12,722 movies had been given a metascore - meaning they were reviewed by at least 4 critics and assigned a score rating the qulaity of the movie. Without a metascore, a movie had no measure listed related to how critics rated the quality the movie.

Thus, the dataset Had to be limited to only the movies with an assigned metascore that had also been reviwed by viewers. After data cleaning, the resulting data set had 12,662 entries, which were used for the final analysis. 


## General Conclusions
Overall, there was a positive correlation between higher viewer scores and critic metascores.

There were far greater numbers of overall user reviews submitted per movie than critic reviews, but more consitstency (i.e. less variance and narrower standard deviation) in the number of critic reviews for any given movie recived vs. the number of user reviews each movie recieved. In terms of ratings of movie quality, it should be noted that there are may more outliers present in the viwer review data than the critic metascores, but this in part probably reflects the fact that the metscores have been set to a normal curve as part of IMDB's metscore methodology.

As far as a direct comparison of how well users rated a movie vs. critics, we have to keep in mind that, aside from critic metescores having already been normalized, the viewer ratings are scales from 1-10 while the metascores are scaled 1-100, so they may not be directly comparable without additional statistial analysis. However:
* if we compare the average criitc metascore relative to its range (1-100) to the average voter score relative to its range (1-10), viwers do seem to rate movies overall slight more favorably than critics.

* a closer look at the average ratings and metascores for viewers' and critics' 100 favorite and least favorites movies (as well as the top 5 and bottom 5 titles for each group) confirm that viewers and critics often values different characteristics in their "favorite" movies.  


## Reviews by Movie Decade
On average, both viwers and critics rated movies from the 1960s and earlier higher than movies made in the 1970s and after. However, the vast majority of the movies in IMDB were made in the 1970s and afterwards. It could be that the better the quality of movies made before 1070, the more likely it is to be listed and reviewed on IMDB. More recent movies might be more likely to be listed on IMDB regardless of quality, thus bring the average scores for reviews of recent movies down.

Additional obersvations:
* An interesting point is the difference in "average year of release" for the viewers' favorite movies (1990), and critics' favorite movies (1973), indicating that critics favor older films more than IMDB users.

* Both IMDB users and critics had similar "average year of release" for bad movies (used as a proxy measure for "worst decade") -- the 2010s for both groups (2007 vs. 2004).


## Gender & Nationality Comparisons
In general, females viewers rated movies slightly more favorably than male viewers. This trend was consistent across all age ranges when the data are divide by age. Older viewers (both male and female) consistently gave less favorable ratings than viewers younger than them.

Average ratings from US viewers also tended to be slightly higher than ratings from viewers in other countries.


