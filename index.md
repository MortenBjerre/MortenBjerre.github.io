# Project B
This is the webpage showing the most important and interesting points in our analysis of the Netflix universe. The explainer notebook can be found ...

We will take a deep dive into the world of Netflix and try to investigate why it sometimes seems 

## Motivation

We've chosen a Kaggle dataset called ['Netflix Movies and TV Shows'](https://www.kaggle.com/shivamb/netflix-shows). It's a dataset containing the tv shows and movies available on Netflix as of 2019 and is obtained from [Flixable](https://flixable.com/).

Instead of looking at the entire movie industry, we chose to look only at Netflix’s ecosystem. We believe this is more interesting, as it represents a single company’s choices rather than an entire industry. This means the network might be more connected, as Netflix actively chooses who becomes part of the network - whereas in the movie industry network, the industry doesn’t choose who makes movies and thus becomes part of the network. 

Overall, we want to get a better overview of the movie industry from a private company’s point of view. Secondly, we propose the Netflix Paradox, which says that “How does Netflix have everything, but nothing at the same time”. A problem many people can acknowledge, as it appears Netflix has every type of show, but there’s never anything you want to watch. Thirdly, as maybe the least important, but also the funniest, is trying to find out if the meme that Adam Sandler is everywhere is true (As he is a well known actor that has starred in MANY movies). 

## Basic statistics
**Preprocessing the data**

The preprocessing of the data mainly revolves around correcting the format of the columns as some values are string while they should in fact be lists of strings. This change is made so that we can easily work with the data. The NaN values in the data set are changed to empty strings.

For every show, a corresponding cast is listed. This is presented as one long string; this string must be split into a list with each of the mentioned actors as a separate element. This is also true in directors, listed_in and country.

Titles of movies and tv shows are not unique, however, each of them have a unique show_id. This is used to differentiate between two shows that have the same name. This also means, that when we talking about shows, we're talking about both movies *and* TV Shows. Shows is used as an umbrella term.

**The statistics**

The dataset we have chosen to work with consists of 6234 rows of movies each containing 12 attributes.




