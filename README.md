# Make Effective Data Visualization Project

June 2017, by Jude Moon

## Summary
The objective of this project is to create an effective visualization of Titanic dataset, which contains samples (891 out of total 2,224 people including passengers and crew on board) of demographics and passenger information such as passenger class, sex, age, survived (0: dead and 1: survived), etc. 
The key story I would like to convey is that females and higher socio-economic status (1st and 2nd classes) more likely survived from the Titanic disaster than males and lower socio-economic status (3rd class). The groups of 1st and 2nd class females had a survival rate greater than 92%. This was far greater than the average survival rate of the sample, which was 38%. 
Considering that females were 35% and females with 1st and 2nd classes were only 24% of total sample size, the evidence that such minor group showed greater survival infers that the people put on lifeboats was not randomly taken but selectively. This supports that features of being female and higher classes were top priorities to be put on lifeboats.

## I Need Feedback
- What do you notice in the visualization?
- What questions do you have about the data?
- What relationships do you notice?
- What do you think is the main takeaway from this visualization?
- Is there something you don’t understand in the graphic?

### Technical Questions
- How can I add charts from two different versions of d3? For now, they are separated into two different html files.

## Design

### What factors do I have?
I have 2 categorical explanatory variables and 1 categorical response variable. One explanatory variable is sex which is Boolean (female and male), the other is socio-economic status with 3 levels, including 1st, 2nd, and 3rd classes. And the response variable is Boolean (survived or dead). This can be shown as the numbers of people survived vs. dead by groups. However, the group sizes of female and male are not proportional, so as for socio-economic classes. Simply showing counts can mislead the findings. For example, 70 of 2nd class female survived and 72 of 3rd class female survived. They were similar in counts. But 70 survived out of 76 of 2nd class female vs. 72 survived out of 144 of 3rd class female, that is 92% survived v. 50% survived, respectively, are very different. Thus, the survival proportion (max is 1) or percentage (max is 100%) can be a good representing statistics in this case. For example, 74% survival of female group means 74% of female survived, while 26% of female died within the sample size of 314. Lastly, I have an additional factor that can affect the interpretation in the dataset, which is the size of each group, that is, the count of people in each group.  Although using absolute counts of people survived is not appropriate to compare between groups, it can add information like how many people died, something like the 26% represents 3 people or 30 people.

### What visualization choices do I have?
## Choice1.
I think a bar chart can be simple and easy to visualize the difference in the survival percentage between different groups. Since there is an interesting interaction between two explanatory variables on survival, I think putting them together in one chart would be better than separating them into two charts. Y axis can be survival percentage from 0 to 100%. X axis can be class variable with ascending order from left to right. Color coding can be by sex. If I go with white or off-white background, female can be blue as highlighting point, and male can be grey. Or I can go with general gender colors such as red for female and blue for male. Both color choice can be color-blind friendly, but I can also add a texture on female bars. And the legend for color coding is necessary. I can add an interaction showing the y-axis values and actual count of people when users move cursors on the bars.

## Choice2.
Another option can be Parallel Sets Plot.  In this case, I will have 3 categorical variables, so 3 horizontal bars represent variables. Each horizontal bar is divided by levels of the variable. For example, survived bar is separated by Yes and No. And the lengths of bar segment represent the proportions of the group sizes; the length of Yes-bar segment will be 38% of total bar length, while that of No-bar segment will be 62% of total bar length. The top horizontal bar can be survival variable, the second bar can be sex variable, and the bottom bar can be socio-economic class variable. Vertical bars connecting horizontal bars represent hierarchical grouping and the thicknesses of vertical bars represent the proportions of the group sizes. Color can be encoded by survival: Yes for blue and No for red or grey. I don’t think the legend of color coding is necessary in this case because when user look at the plot from top to bottom, they can see all Survived-Yes started as blue and all Survived-No started as red. One thing that can draw attention from top to bottom is animation. I can make the vertical bars appear from top to bottom or I can even display blue vertical bars first and display red later. At the end of the animation, I can add an interaction showing the percentage and actual count of people when users move cursors on the bars.

## Choice3.
Lastly, I think circle chart + pie chart can be another option. I will have 6 circle representing each group (Sex * Class). X-axis can be sex variable and y-axis can be class variable. For example, the left 3 circles are female and the right 3 circles are male groups. The top 2 circles are 1st class, middle 2 circles are 2nd class, the bottom 2 circles are 3rd class groups. The size of the circle represents the size of each group. Each circle is pie chart for each group, showing proportion of survival. I can encode color first by dead and then by sex. All the dead pie is black. Female survived is pink and male survived is sky blue. I don’t think that I will need a legend for color but the labels of the variable titles and levels will be necessary. I don’t think the animation is necessary but I can add an interaction by mouse cursor, showing  the percentage and actual count of people.

### What choice is reviewers' favorite?
The most favorite choice by reviewers was the bar chart. It is a classical chart so reviewers are familar with the chart components and layout and well-trained with how to read the chart. On the contrary, the least favorite was the parallel sets plot. It is not straight forward to highlight the key story. Although it has a great level of interaction and flexibility on the plot, the reviewers think that it is less focus on the key story.   


## Feedback
### Reviewer1
Nice stuff going one, this looks neat.
I struggled to understand the parallel plot. It took me some good time (several minutes) to understand the plot, yet I still do not get it much. 

Whereas for the bar chart, I was able to understand the story right away; discrepancy in class and gender in the deaths/survival rates of the titanic tragedy. It didn't take me much time to draw useful information from that one, and If I am to write an article, I would not need much time understanding the data from that figure. 

The pie chart does a similar job, but for me, it was the bar chart being much more effective. What I like more about the pie is that the tool tip gives a better data summary in the pie chart, better than the bar plot. 

I see that you are using D3JS. We were looking into that library for visualization in the computational course I was taking last spring. Good choice.
Have you played yet with JQuery? Also consider R and ShinyR.

### Reviewer2
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

### Reviewr3
I believe choice #1, the bar chart, is the best. It is easy to read and understand. You may want to add labels for the x-axis meaning 1st class, 2nd class, and 3rd class to improve it.

***
## Files
- index1.html: html, css, and js to create 3 charts using d3.v3, dimple.v2.0.0, and d3.parsets - initial version
- index2.html: html, css, and js to update the third chart with d3.v4 and dimple.v2.3.0
- titanic_bar.csv: data summary file for 1st chart in index1.html
- titanic_parsets.csv: data file for 2nd chart in index1.html 
- titanic_pie.csv: data summary file for 3rd chart in index1.html and index2.html
- titanic_data.csv: original data file from [Udacity Project Details](https://classroom.udacity.com/nanodegrees/nd002/parts/0021345403/modules/317671873575461/lessons/3176718735239847/concepts/54201485780923)

