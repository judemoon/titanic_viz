# Make Effective Data Visualization Project

June-July 2017, by Jude Moon

## Summary
The objective of this project is to create an effective visualization of Titanic dataset, which contains samples (891 out of total 2,224 people including passengers and crew on board) of demographics and passenger information such as passenger class, sex, age, survived (0: dead and 1: survived), etc. 
The key story I would like to convey is that females and higher socio-economic status (1st and 2nd classes) more likely survived from the Titanic disaster than males and lower socio-economic status (3rd class). The groups of 1st and 2nd class females had a survival rate greater than 92%. This was far greater than the average survival rate of the sample, which was 38%. 
Considering that females were 35% and females with 1st and 2nd classes were only 24% of total sample size, the evidence that such minor group showed greater survival infers that the people put on lifeboats was not randomly taken but selectively. This supports that features of being female and higher classes were top priorities to be put on lifeboats.

## Design Part1. before coding and getting feedback

### What factors do I have?
I have 2 categorical explanatory variables and 1 categorical response variable. One explanatory variable is sex which is Boolean (female and male), the other is socio-economic status with 3 levels, including 1st, 2nd, and 3rd classes. And the response variable is Boolean (survived or dead). This can be shown as the numbers of people survived vs. dead by groups. However, the group sizes of female and male are not proportional, so as for socio-economic classes. Simply showing counts can mislead the findings. For example, 70 of 2nd class female survived and 72 of 3rd class female survived. They were similar in counts. But 70 survived out of 76 of 2nd class female vs. 72 survived out of 144 of 3rd class female, that is 92% survived v. 50% survived, respectively, are very different. Thus, the survival proportion (max is 1) or percentage (max is 100%) can be a good representing statistics in this case. For example, 74% survival of female group means 74% of female survived, while 26% of female died within the sample size of 314. Lastly, I have an additional factor that can affect the interpretation in the dataset, which is the size of each group, that is, the count of people in each group.  Although using absolute counts of people survived is not appropriate to compare between groups, it can add information like how many people died, something like the 26% represents 3 people or 30 people.

### What visualization choices do I have?
## Choice1.
I think a bar chart can be simple and easy to visualize the difference in the survival percentage between different groups. Since there is an interesting interaction between two explanatory variables on survival rate, I think putting them together in one chart would be better than separating them into two charts. Y axis can be survival percentage from 0 to 100%. X axis can be class variable with ascending order from left to right. Color coding can be by sex. If I go with white or off-white background, female can be blue as highlighting point, and male can be grey. Or I can go with general gender colors such as red for female and blue for male. Both color choice can be color-blind friendly, but I can also add a texture on female bars. And the legend for color coding is necessary. I can add an interaction showing the y-axis values and actual count of people when users hover on the bars.

**Update**: I added the second y axis with scatters to show the size of group instead of using hover box. 
[See my blocks.org](http://bl.ocks.org/judemoon/raw/c48b65e8570eacd9c6ed7d6a1c5aab93/)

## Choice2.
Another option can be Parallel Sets Plot.  In this case, I will have 3 categorical variables, so 3 horizontal bars represent variables. Each horizontal bar is divided by levels of the variable. For example, survived bar is separated by Yes and No. And the lengths of bar segment represent the proportions of the group sizes; the length of Yes-bar segment will be 38% of total bar length, while that of No-bar segment will be 62% of total bar length. The top horizontal bar can be survival variable, the second bar can be sex variable, and the bottom bar can be socio-economic class variable. Vertical bars connecting horizontal bars represent hierarchical grouping and the thicknesses of vertical bars represent the proportions of the group sizes. Color can be encoded by survival: Yes for blue and No for red or grey. I don’t think the legend of color coding is necessary in this case because when user look at the plot from top to bottom, they can see all Survived-Yes started as blue and all Survived-No started as red. One thing that can draw attention from top to bottom is animation. I can make the vertical bars appear from top to bottom or I can even display blue vertical bars first and display red later. At the end of the animation, I can add an interaction showing the percentage and actual count of people when users move cursors on the bars.
[See my blocks.org](http://bl.ocks.org/judemoon/4b56a8cc98345a47a0cfd67fa525a34b)


## Choice3.
Lastly, I think circle chart + pie chart can be another option. I will have 6 circle representing each group (Sex * Class). X-axis can be sex variable and y-axis can be class variable. For example, the left 3 circles are female and the right 3 circles are male groups. The top 2 circles are 1st class, middle 2 circles are 2nd class, the bottom 2 circles are 3rd class groups. The size of the circle represents the size of each group. Each circle is pie chart for each group, showing proportion of survival. I can encode color first by dead and then by sex. All the dead pie is black. Female survived is pink and male survived is sky blue. I don’t think that I will need a legend for color but the labels of the variable titles and levels will be necessary. I don’t think the animation is necessary but I can add an interaction by mouse cursor, showing  the percentage and actual count of people.

**Update**: I couldn't implement bubble and pie matrix together by using version 2.0.0. of dimple, so I had to use newer version of d3 and dimple to make this matrix.
[See my blocks.org](http://bl.ocks.org/judemoon/4f7954689ce31ea34254cb5f4e0a6c58)


## Feedback
#### Reviewer1
Nice stuff going one, this looks neat.
I struggled to understand the parallel plot. It took me some good time (several minutes) to understand the plot, yet I still do not get it much. 

Whereas for the bar chart, I was able to understand the story right away; discrepancy in class and gender in the deaths/survival rates of the titanic tragedy. It didn't take me much time to draw useful information from that one, and If I am to write an article, I would not need much time understanding the data from that figure. 

The pie chart does a similar job, but for me, it was the bar chart being much more effective. What I like more about the pie is that the tool tip gives a better data summary in the pie chart, better than the bar plot. 

I see that you are using D3JS. We were looking into that library for visualization in the computational course I was taking last spring. Good choice.
Have you played yet with JQuery? Also consider R and ShinyR.

#### Reviewer2
Choice #1
•	What do you notice in the visualization? - It is clean and easy to follow. 
•	What questions do you have about the data? - None
•	What relationships do you notice? - The survived vs. dead is clearly displayed as the classes lower. 
•	What do you think is the main takeaway from this visualization? A classic graph that is easy to understand.
•	Is there something you don’t understand in the graphic? - It's very clear. 

Choice #2
•	What do you notice in the visualization? - The information in the graph seems clouded. 
•	What questions do you have about the data? - How can I better understand the information in the graph. 
•	What relationships do you notice? - I don't. 
•	What do you think is the main takeaway from this visualization? - What am I looking at. 
•	Is there something you don’t understand in the graphic? - Unfortunately, I do not understand the information in the graph other than it's supposed to compare the survival rate by sex and class. 

Choice #3
•	What do you notice in the visualization? - It is clean and easy to follow.
•	What questions do you have about the data? - None
•	What relationships do you notice? - The survived vs. dead is clearly displayed as the classes lower. 
•	What do you think is the main takeaway from this visualization? - It wouldn't have been favorable to be a male in 3rd class.
•	Is there something you don’t understand in the graphic? - It's very clear. 

#### Reviewer3
I believe choice #1, the bar chart, is the best. It is easy to read and understand. You may want to add labels for the x-axis meaning 1st class, 2nd class, and 3rd class to improve it.

#### Reviewer4
I think the Bar Chart is the easiest to understand, but I wonder if the scatter plot can be shown in a different way. Perhaps that information is better suited on the tooltip, or animated outside the chart area.The parralel sets plot is interesting and could be improved by labelling or a legend on the colors. (ie. instead of yes/no, state survived/not survived). Otherwise it's really creative.

#### Reviewer5
I like the different types of visuals that you created. Out of the three, I think the bar chart represent the data better. It seems like you were trying to plot a black dot as the total for each sex for each bar and that was a little confusing to me. You could consider updating the plot with the totals only?

#### Udacity Reviewer by the first project submission
Great work with the overall design of the visualization. You have successfully represented sample size of each demographic with a pie chart that uses area of the pie to encode number of passengers rather than radius (which is a common pitfall). The colors for the sex and survival features are both intuitive and offer easy interpretation :clap:

The only required change here should be some way to interpret the group size from looking at the plot (ie a legend). Alternatively you could format the y-axis of the second chart to be smaller and show a few tick marks. Essentially, there needs to be some way to interpret the size of the pie charts on the visualization. You may be able to get away with just the tooltip, but in that case the y-axis with Group Size should be removed. I would make that the title for chart 2 instead of the y-axis. Try and see if you can create a legend for the pie chart size first, and then go from there.


## Design Part2. after coding and getting feedback

### What choice is the reviewers' favorite?
The most favorite choice by reviewers was the bar chart. It is a classical chart so reviewers are familiar with the chart components and layout and well-trained with how to read the chart. On the contrary, the least favorite was the parallel sets plot. It is not straight forward to highlight the key story. Although it has a great level of interaction and flexibility on the plot, the reviewers think that it is less focus on the key story.   

### How did I make improvements?
#### Revise1
The drawback of using the bar chart only is that it does not include count summary, while the pie matrix does. Thus, I combined the two charts. I still think that bar chart is the most effective to highlight the findings, and so I placed the bar chart on the top while pie matrix is presented as a supplementary chart. One of reviewers recommended to add "class" into the labels, but I didn't implement it because that will increase redundancy in the chart.

#### Revise2
The comments from the Udacity Reviewer, Reviewer4 & 5 said that separating the pie chart (or scatter plot from the previous version) from the bar chart will make the points clearer. And I agree with that. I created the second bar chart below the first bar chart. I have chosen the bar chart instead of pie matrix because the bar shows the difference in values more accurately than pie chart. I encoded colors by “Survived”: green for survived and black for dead. 
The first bar chart focuses on relative survival rate within each group, meaning that the sample number of each group was relativized to 100% for the y axis. The second chart focuses on absolute survival count, emphasizing the difference in group size. The tricky thing on the second chart was that I can encode colors either by survived or sex. I decided to encode colors by survived and updated the x-axis title to describe that a pair of "Female" and "Male" bars are shown in each class. The second chart alone may not be very descriptive because there is no clear encoding of "Female" and "Male" and viewers can be confused by this. However, I think that viewers see the first chart and can learn the order of bars, and then they can understand the second chart without trouble. Plus, the tooltip can guide the right label for each bar.


***
## Files
- index1.html: html, css, and js to create 3 charts using d3.v3, dimple.v2.0.0, and d3.parsets - initial version
- index2.html: html, css, and js to update the third chart with d3.v4 and dimple.v2.3.0
- index3.html: html, css, and js of project draft for the first submission 
- index_final.html: html, css, and js to create the final chart
- titanic_bar.csv: data summary file for 1st chart in index1.html, index3.html, and index_final.html
- titanic_parsets.csv: data file for 2nd chart in index1.html 
- titanic_pie.csv: data summary file for 3rd chart in index1.html, index2.html, and index_final.html
- titanic_data.csv: original data file from [Udacity Project Details](https://classroom.udacity.com/nanodegrees/nd002/parts/0021345403/modules/317671873575461/lessons/3176718735239847/concepts/54201485780923)

