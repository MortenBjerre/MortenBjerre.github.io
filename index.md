# Analyzing Standardized Testing Scores of Schools in San Francisco test 1

In our research of San Francisco (SF) school performances, we are getting our data from [CAASPP](https://caaspp-elpac.cde.ca.gov/caaspp/ResearchFileList?ps=true&lstTestYear=2019&lstTestType=B&lstCounty=00&lstDistrict=00000&lstSchool=0000000), which is the standardized testing program for the state of California.

The explainer notebook can be found [here](https://colab.research.google.com/drive/1nTUUG7OzbG3ZU3RtGFZ67-_bXx0zW2Cw?usp=sharing)


# Introduction

Our goal is to find any patterns in the school performances in San Francisco, and to see if there are any connections in these patterns with socio-economic factors. To make sure we have an unbiased, universal metric of school performances, we turn to the CAASPP, the standardized testing program for California. The variable we are examining there is the Mean Scale Score (MSS). 

## What does Mean Scale Score mean?

The Scale Score is the score a student achieved on the exam. Contrary to a raw score, the Scale Score takes into account differences in difficulty of the exam from year to year, as well as giving a higher score for answering more difficult, discriminating questions correctly, as explained [here](https://www.caaspp.org/rsc/pdfs/CAASPP.post-test_guide.2018-19.pdf) from the Department of Education for the State of California.

## Standards

The CAASPP has a standard, which all students should be meeting. There are five categories in relation to this standard, from highest to lowest: 
- Standard exceeded
- Standard met
- Standard nearly met
- Standard not met 

## School locations

Look at the map below, and see what schools are included in this data analysis. 

<div class="responsive-wrap">
<!-- this is the embed code provided by Google -->
  <iframe src="/images/schools.html" frameborder="0" width="100%" height="700" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>
<!-- Google embed ends -->
</div>

# Initial overview

First, we will take a look at how the MSS looks like for all of San Francisco in general. 

[INSERT LINE PLOT HERE]




There is a general upwards trend of the MSS over time for San Francisco. When looking at the standards, we can see that this is mostly due to a general reduction in students in the "met" and "not met" standards, and a general increase in students in the top 2 categories. However, the percentage of students who have not met the standard, i.e. the lowest category, went only until 2017, after which it went back up to its 2015 levels. 

Additionally, a choropleth of the Mean Scale Scores of each zip code is shown below. Each dot represents a school, which can be clicked on to find the specific school. 

Mouse over the zip codes to see the Mean Scale Score and the zip code. 

<div class="responsive-wrap">
<!-- this is the embed code provided by Google -->
  <iframe src="/images/MSS_all_years.html" frameborder="0" width="100%" height="700" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>
<!-- Google embed ends -->
</div>
It is easy to see a general east/west and north/west divide. 


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

Choropleth showing the majority ethnicity of each tract of land. Mouse over to see the tract name and the majority ethnicity. 

<div class="responsive-wrap">
<!-- this is the embed code provided by Google -->
  <iframe src="/images/Ethnicity.html" frameborder="0" width="100%" height="700" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>
<!-- Google embed ends -->
</div>

Interestingly, there is a block of Asians in the high performing zip codes of the west, but also a block of Asians in the lower performing zip codes in the south. This can maybe be explained by one group of Asians moving to a more expensive area of the city (by income) for the schools, while another group moves to a cheaper area as it is all they can afford. 

There is also an "enclave" of asians in the north-east, around the area of China town, which makes sense. 

The dock area in the south-east, which has the worst schools, also has majority black population, which is also a low-income area. It could be that, because that area has a lower income, that the schools aren't able to afford as good teachers and resources, or that the city under-prioritizes this "black" district. 

There are very small, disconnected areas with majority Hispanic, and therefore not much can be gleaned from that. It may be that Hispanic populations mostly live in areas that are majority made up of other races. 

Lastly, the white population seems to live both in the high and low income areas of the city, as well as both the areas with better and worse schools. 
