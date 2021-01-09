---
date: 2020-04-17
excerpt: "Exploring popularity of the Star Wars franchise by analyzing survey responses. Data cleaning, exploration and visualization using Python."
header: ~
tags:
  - star-wars
  - exploration
title: "Revelations from a Star Wars Survey"
---

*Quick links - [Dataset](https://www.kaggle.com/samaxtech/star-wars-survey-data), [Analysis](https://github.com/sinhasaumya/projects/blob/main/star-wars-survey-data-exploration.ipynb)*  

Supposedly one of United States’ favourite movie series, the Star Wars franchise is one known to all across the globe. An author interested in understanding the franchise’s popularity in the US ran a poll on SurveyMonkey to quiz respondents on their most and least favourite movies and characters in the series among other things.  

The [dataset](https://www.kaggle.com/samaxtech/star-wars-survey-data) is downloaded from Kaggle and explored using Python to find -
1. how respondents rated Star Wars movies
2. the veracity of some plausible hypotheses
3. the presence or lack of relationship between respondents’ demographics and their attitude to Star Wars characters  

Analysis of the dataset is available [here](https://github.com/sinhasaumya/projects/blob/main/star-wars-survey-data-exploration.ipynb).

Key findings from data exploration are summarised below.

**1. How have respondents rated Star Wars movies?**  
As respondents have varied preferences of episodes, how 1185 of them rank films is understood by seeing the most and least popular opinions. An opinion is the combination of an episode and rank. There are 935 respondents who have watched at least one film and their responses are considered. However, a respondent who has watched only two out of six films is not as strong a judge of ranking the films as someone who has watched all six films. Therefore, assigning an equal weight to the opinions of people who have watched an unequal number of films is not a good approach. In the approach adopted, based on the number of films each of the 935 respondents has watched, his/her opinion is assigned a weight as per the table below..

Films watched | Weight
------------- | -------------
6             | 6/6
5             | 5/6
4             | 4/6
3             | 3/6
2             | 2/6
1             | 1/6
0             | 0

It shows that most people, with an aggregated weight of 252.5, agree that episode 2 be ranked 5. Next, a fairly large population of respondents has positioned episode 5 at rank 1 with an aggregated weight of 225.83. Few people with an aggregated weight of 26.83 seem to agree to position episode 5 at rank 6 and even fewer people with an aggregated weight of 24.5 place episode 2 at rank 1.

**2. What is the result of the evaluation of the following hypothesis?**  
**2.1 All fans of Star Wars are also fans of Star Trek.**  
It is seen that while the largest sub-section of people, 370, are fans of Star Wars and also fans of Star Trek, there is a significant population of 220 (175 + 45) that is a fan of only one of the two. With more relevance to the hypothesis, there are 175 respondents who claim to be fans of Star Wars but not of Star Trek. In addition to this, 7 Star Wars fans have not indicated whether or not they are fans of Star Trek. Hence, it is concluded that not all Star Wars fans are Star Trek fans, and the hypothesis is incorrect. It is also noted that 237 people are fans of neither of the two. 

**2.2 Men and women have watched nearly equal number of Star Wars films.**  
It is found that people have watched 0-6 films and the interest lies in confirming if men and women indeed watch nearly the same number of movies. The number of men and women who have watched the same number of movies is unequal in all cases (number of movies watched from 0 to 6), while also having variable difference across the number of films watched. The difference between men and women who have watched a certain number of films is in fact very high in the edge cases, wherein 78 women more than men have not watched any Star Wars film and 94 men more than women have watched all six films. There are more women than men who have watched between one and four, both inclusive, films. There is a slightly greater number of men than women who have watched five movies. It is concluded that more men than women tend to watch at least one Star Wars film and are also more likely than women to finish watching all six movies. There are fewer men than women who watch less than five Star Wars films. 

**2.3 There are more older viewers of Star Wars than younger viewers.**  
It is first noted that across all age buckets, there are more viewers than non-viewers. Second, the number of viewers of any Star Wars films is found to be the greatest in the youngest age bracket of 18-29 years, and is followed by 45-60, 30-44 and >60. Interestingly, lesser people aged 30-44 are viewers than those who are younger at 18-29 and older at 45-60 years of age. Therefore, the hypothesis that there are more older viewers than youngers viewer of Star Wars stands false. However, there are also several viewers who have not reported their age bracket and have not been considered to analyze the hypothesis. 

**3. Is there a relationship between respondents’ demographics and their attitude to Star Wars characters?**  
A mosaic plot representing the people’s views by demographic is created for each combination of 14 characters and 5 demographics. A mosaic plot graphically displays cell frequencies of a contingency table, wherein area of boxes of the plot are proportional to cell frequencies of the contingency table. For the sake of brevity, the result is interpreted below for popular characters Darth Vader, Anakin Skywalker and Jar Jar Binks. 

Widths of different views indicate more people view the character favorably than unfavorably. More males than females view Darth Vader ‘very favorably’ and ‘somewhat favorably’, and more females than males tend to view the character ‘very unfavorably’ and ‘somewhat unfavorably’. Nearly equal number of males and females view Darth Vader neutrally or are unfamiliar with the character. 
A lot more people in the age buckets of 45-60 and >60 tend to view Anakin Skywalker ‘very favorably’ than the younger lot of 18-29 and 30-44. A larger chunk of the younger group of 18-29 and 30-44 in fact views the character ‘very unfavorably’ or ‘somewhat unfavorably’. A significant population of all age groups views the character ‘somewhat favorably’ or ‘neutrally’. More respondents in lowest and highest household incomes groups of $0-$24,999 and $150,000 view the character unfavourably (very and somewhat combined) than favorably (very and somewhat combined). While a visibly large population of respondents in the group $50,000-$99,999 views Jar Jar Binks very unfavourably, the remaining population of this group is divisive in its views of this character. The other household groups are also quite divisive in their view of this character. 