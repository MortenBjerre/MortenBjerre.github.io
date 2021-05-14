# Analyzing Standardized Testing Scores of Schools in San Francisco

In our research of San Francisco (SF) school performances, we are getting our data from [CAASPP](https://caaspp-elpac.cde.ca.gov/caaspp/ResearchFileList?ps=true&lstTestYear=2019&lstTestType=B&lstCounty=00&lstDistrict=00000&lstSchool=0000000), which is the standardized testing program for the state of California.

The explainer notebook can be found [here](https://colab.research.google.com/drive/1nTUUG7OzbG3ZU3RtGFZ67-_bXx0zW2Cw?usp=sharing).

NOTE: If mousing over/hovering doesn't work, try a different browser or incognito mode. 


# Introduction

Our goal is to explore the SF school data and to see if the patterns in the school performances are in connection with some specific socio-economic factors. To make sure we have an unbiased, universal metric of school performances, we turn to the CAASPP, the standardized testing program for California. The variable we are examining there is the Mean Scale Score (MSS). As the CAASPP is relatively new, there is only data from 2015-2019, with no data from 2020 due to the pandemic. 

## What does Mean Scale Score mean?

The Scale Score is the score a student achieved on the exam. Contrary to a raw score, the Scale Score takes into account differences in difficulty of the exam from year to year, as well as giving a higher score for answering more difficult, discriminating questions correctly, as explained [here](https://www.caaspp.org/rsc/pdfs/CAASPP.post-test_guide.2018-19.pdf) from the Department of Education for the State of California.

## Standards

The CAASPP has a standard, which all students should be meeting. There are four categories in relation to this standard, from highest to lowest: 
- Standard exceeded
- Standard met
- Standard nearly met
- Standard not met 

## Short about the data

The CAASPP dataset of school scores consist of 510,665 rows and 42 columns. After filtering to just the schools of SF we are left with  3236 rows. There are 125 different schools in the data set.

In addition to the above data set, we have the following data set:
- A map of school location found [here](https://data.sfgov.org/Economy-and-Community/Map-of-Schools/qb37-w9se).
- A map of zip codes to bin the data, which is found [here](https://data.sfgov.org/Geographic-Locations-and-Boundaries/Bay-Area-ZIP-Codes/u5j3-svi6).
- SF is not only divided into zip codes but also *tracts*. This is a more finegrained division of SF, which we find from [here](https://data.sfgov.org/Geographic-Locations-and-Boundaries/Census-2010-Tracts-for-San-Francisco/rarb-5ahf) and [here](https://data.sfgov.org/Geographic-Locations-and-Boundaries/Census-2000-Tracts-for-San-Francisco-no-water-/xx87-44s6). We use the newest tract data, which fits with other data sets, but we use the old for the shape of a three tracts as their shape goes into the water. 
- Crime data from 2013 to 2018 found [here](https://data.sfgov.org/Public-Safety/Police-Department-Incident-Reports-Historical-2003/tmnf-yvry) and from 2018 up until present found [here](https://data.sfgov.org/Public-Safety/Police-Department-Incident-Reports-2018-to-Present/wg3w-h783).
- Income data of SF. The income data is found [here](https://datausa.io/profile/geo/san-francisco-ca#economy) and is measured as the median household income for each tract.
- Ethnicity demographics by track, which was found [here](https://data.census.gov/cedsci/table?t=-00%20-%20All%20available%20races%3ARace%20and%20Ethnicity&g=0400000US06.140000_0500000US06075.140000&tid=DECENNIALSF22010.PCT42).

## School locations

Look at the map below, and see what schools are included in this data analysis. 

<div class="responsive-wrap">
<!-- this is the embed code provided by Google -->
  <iframe src="/images/schools.html" frameborder="0" width="100%" height="700" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>
<!-- Google embed ends -->
</div>

# Initial overview

First, we will take a look at how the MSS looks like for all of San Francisco in general. 

![image](/images/summary.png)

There is a general upwards trend of the MSS over time for San Francisco. When looking at the standards, we can see that this is mostly due to a general reduction in students in the "met" and "not met" standards, and a general increase in students in the top 2 categories. However, the percentage of students who have not met the standard, i.e. the lowest category, increased only until 2017, after which it went back up to its 2015 levels. 

Below you will find a choropleth of the Mean Scale Scores for each zip code from 2015-2019. 

Mouse over the zip codes to see the Mean Scale Score and the zip code. 

<div class="responsive-wrap">
<!-- this is the embed code provided by Google -->
  <iframe src="/images/MSS_all_years.html" frameborder="0" width="100%" height="700" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>
<!-- Google embed ends -->
</div>

It is easy to see a general east/west and north/west divide. It seems clear that the west side of SF performs better than east side. 

Additionally, when looking at the average scores of the individual schools, we get the following. Click on the dots to see the MSS and school name. The size of a school's dot is relative to its MSS. Color has also been added to show the MSS, where yellow and red are low and high scores, respectively. 

<div class="responsive-wrap">
<!-- this is the embed code provided by Google -->
  <iframe src="/images/dot_all.html" frameborder="0" width="100%" height="700" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>
<!-- Google embed ends -->
</div>

Here, the divide is again rather strong, as the south-eastern half of the city has very few schools better than any in the north-western half. For all the following time sliding choropleths, the date only represents the full year and not a specific date. Therefore, the month and day can be ignored.


# Looking at Scores by zip code over the years

Next, we look at the scores by the zip code over the years in the choropleth, to see if there are any large changes from year to year. 

## Mean Scale Score

First, we look at the Mean Scale Score. Mouse over to see the zip codes. 

<div class="responsive-wrap">
<!-- this is the embed code provided by Google -->
  <iframe src="/images/TimeSliderMSS.html" frameborder="0" width="100%" height="700" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>
<!-- Google embed ends -->
</div>

It seems that some of the zip codes have improvements from 2015 to 2019, whereas some zip codes remain the same. 

## Standards

Next, we will examine the percent of students at the different standard levels. 

### Standard exceeded

Time sliding choropleth showing percentage of students exceeding the standards. Mouse over to see the zip codes. 

<div class="responsive-wrap">
<!-- this is the embed code provided by Google -->
  <iframe src="/images/TimeSlider_per_exceeded.html" frameborder="0" width="100%" height="700" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>
<!-- Google embed ends -->
</div>

Here, the divide is much more stark than the Mean Scale Score would indicate. As of 2019, while most of the western/northern zip codes have more than 33% of students exceeding the standards, the eastern/southern zip codes have typically under 17%, a more than two-fold difference. 

### Standard met

Time sliding choropleth showing percentage of students meeting the standards. Mouse over to see the zip codes. 

<div class="responsive-wrap">
<!-- this is the embed code provided by Google -->
  <iframe src="/images/TimeSlider_per_met.html" frameborder="0" width="100%" height="700" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>
<!-- Google embed ends -->
</div>

While the divide is still visible, it is not nearly as strong as it is with the Standard exceeded students. 

### Standard nearly met

Time sliding choropleth showing percentage of students nearly meeting the standards. Mouse over to see the zip codes. 

<div class="responsive-wrap">
<!-- this is the embed code provided by Google -->
  <iframe src="/images/TimeSlider_per_nearly.html" frameborder="0" width="100%" height="700" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>
<!-- Google embed ends -->
</div>

Here again, while the divide is visible, it is not extreme. 

### Standard not met

Time sliding choropleth showing percentage of students not meeting the standards. Mouse over to see the zip codes. 

<div class="responsive-wrap">
<!-- this is the embed code provided by Google -->
  <iframe src="/images/TimeSlider_per_not.html" frameborder="0" width="100%" height="700" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>
<!-- Google embed ends -->
</div>

This one is interesting, as there is only one school performing extremely poorly in this metric, Life Learning Academy Charter on Treasure Island. Upon further research, it seems this school is especially for the disadvantaged and those who have had difficulty in school, which explains the abysmal performance on the CAASPP. 

### Standard met and above
Time sliding choropleth showing percentage of students meeting or exceeding the standards. Remember that this is a combination of exceed and met. Mouse over to see the zip codes. 

<div class="responsive-wrap">
<!-- this is the embed code provided by Google -->
  <iframe src="/images/TimeSlider_per_met_above.html" frameborder="0" width="100%" height="700" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>
<!-- Google embed ends -->
</div>

Again, the divide is extreme, likely mostly from the standard exceeded group. 


# Making connections

Now that we have had a look at the performances of the schools, we can examine the geographical data on socio-economic factors to see if there are any correlations. Mouse over to see the zip codes. 

## Income

Time sliding choropleth showing income of different 'tracts' (an area of land used by the US Census) from 2015-2019. Mouse over to see the tract codes. 

<div class="responsive-wrap">
<!-- this is the embed code provided by Google -->
  <iframe src="/images/IncomeSlider.html" frameborder="0" width="100%" height="700" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>
<!-- Google embed ends -->
</div>

Here, we see that the divide is not quite what we might expect based on the school data, of higher income areas being in the same areas as the higher performing zip codes. While there are higher income areas in the northern parts of the city, matching the higher performing schools in that area, there are also some very high income areas in the east, where some of the lowest performing zip codes were. 

However, over time, we see that the western block becomes richer over time, perhaps indicating richer people moving to these zip codes to be closer to these better schools. 

Additionally, in general, the income increases drastically in the city, likely due to gentrification pushing out poorer people. 

## Ethnicity

Choropleth showing the majority ethnicity of each tract of land. The data is based on the census of 2010. Mouse over to see the tract name and the majority ethnicity. 

<div class="responsive-wrap">
<!-- this is the embed code provided by Google -->
  <iframe src="/images/Ethnicity.html" frameborder="0" width="100%" height="700" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>
<!-- Google embed ends -->
</div>

Interestingly, there is a block of Asians in the high performing zip codes of the west, but also a block of Asians in the lower performing zip codes in the south. This can maybe be explained by one group of Asians moving to a more expensive area of the city (by income) for the schools, while another group moves to a cheaper area as it is all they can afford. This however, indicates that there isn't any strong connection in whether Asians are the majority ethnicity of an area and the school. 

There is also an "enclave" of asians in the north-east, around the area of China town, which makes sense. 

The dock area in the south-east, which has the worst schools, also has majority black population, which is also a low-income area. It could be that, because that area has a lower income, that the schools aren't able to afford as good teachers and resources, or that the city under-prioritizes this "black" district. 

There are very small, disconnected areas with majority Hispanic, and therefore not much can be gleaned from that. It may be that Hispanic populations mostly live in areas that are majority made up of other races. 

Lastly, the white population seems to live both in the high and low income areas of the city, as well as both the areas with better and worse schools. There is no connection to school performance here, at least from the data we have. 


# Conclusion

While there is a general connection between income of an area and the performance of schools in the area, there is a somewhat weaker connection between school performance and race. There is, however, a real divide between the north-west and the south-east of the city, which is only more marked when looking at the top and bottom students. Crime seems to have no impact on the scores of the schools, though this is likely due to a flawed data set, or that we need to examine a specific subset of crimes. 
