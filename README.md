#  An Analysis of Kickstarter Campaigns
—
## Project Overview
This project is an analysis of fundraising campaigns launched on Kickstarter with the purpose of identifying trends in order to inform the strategy for Louise’s fundraising efforts for her play, Fever.

## Analysis and Challenges
The dataset consists of 4114 online fundraising campaign results from the platform Kickstarter. 

By segmenting campaigns categorically, manipulating the unix timestamp data in order to analyze success by temporal measures, and eliminating potential outliers, I have identifed a few key recommendations for Louise’s fundraiser.

### Analysis of Outcomes Based on Launch Date
![Theater_Outcomes_vs_Launch](https://user-images.githubusercontent.com/82285562/115973477-de2a9f00-a51a-11eb-9b8c-4a3d69c373b5.png)
_Figure 1_

In analyzing the success of campaigns based on their launch date, two trends appeared.
1. Campaigns launched in the summer months, May through July, have a greater success rate than those launched at any other time of year. This trend is especially pronounced for campaigns in the Theater category.
2. Campaigns launched in December have the lowest success rate.

### Analysis of Outcomes Based on Goals
![Outcomes_vs_Goals](https://user-images.githubusercontent.com/82285562/115973484-e5ea4380-a51a-11eb-9954-26c27e18dd9c.png)
_Figure 2_

In order to determine how fundraising goals on Kickstarter affect campaign success, I segmented the data by goal amount, then drilled down to just those fundraisers in the “plays” subcategory (_Figure 2_). I found that almost half of those campaigns (49.7%) were within the goal range of $1,000-$4,999. This means that the data in question is skewed toward the lower end of the goal scale, which ranged from *Less than $1,000* to *Greater than $50,000*. I then plotted a box-and-whisker chart to visualize the distribution of fundraising goal by outcome (_Figure 3_).
![Goal Frequency Distribution](https://user-images.githubusercontent.com/82285562/115973497-05816c00-a51b-11eb-9ec1-f193c7f7fa1c.png)
_Figure 3_

This visualization confirmed that the failed group in particular included outliers with very high goals. Thus, using the 1.5 IQR rule, I was able to set a quantitative boundary and produce _Figure 4_, illustrating that for play fundraisers, the $15,000-$19,999 goal range is the inflection point at which success rates drop below 50%.
![Outcomes vs goal 2](https://user-images.githubusercontent.com/82285562/115973487-eda9e800-a51a-11eb-87c1-9b992ee04da0.png)
_Figure 4_

### Challenges and Difficulties Encountered
The first challenge I encountered with the dataset was a set of fields labeled **deadline** and **launched_at**, which appeared to reflect campaign start and end dates but required manupulation. Using a [Unix Timestamp Converter] (https://www.epochconverter.com/), I confirmed that the data was indeed Unix values, then converted it to a date format using `DATE()` function in Excel.

Additionally, I found the fundraising categories as they were initially exported from Kickstarter to be too broad for my analysis. To address this, I parsed the catigorical data and whittled it down using the text-to-column feature. I subdivided broad, “parent” categories and smaller subcategories, which allowed me to drill down and identify trends among the campaigns most relevant to our research objectives.

## Results
In conclusion, my recommendations are as follows: 
- Louise shoud launch her fundraising campaign in May, if possible. 
- She should avoid a launch in the winter months, particularly December.
- Louise should also consider that lower fundraising goals are associated with greater success rates — This is true for plays in particular, so she should not increase her goal amount beyond the budgeted $12,000.

There are certainly limitations of this analysis. In particular, it would be helpful to analyze the results of campaigns across fundraising platforms other than Kickstarted (e.g. GoFundMe, IndieGogo). 
Additionally, the Kickstarter data did not include campaigns launched after 2017. A lot has changed with regard to digital fundraising in the last 5 years, so I strongly suggest a review of more recent trends.
