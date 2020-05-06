# Trending-YouTube-Video-Analysis
## by Yueh-Han Chen
## Dataset Overview
YouTube (the world-famous video sharing website) maintains a list of the top trending videos on the platform. According to Variety magazine, “To determine the year’s top-trending videos, YouTube uses a combination of factors including measuring users interactions (number of views, shares, comments and likes). Note that they’re not the most-viewed videos overall for the calendar year”. Top performers on the YouTube trending list are music videos (such as the famously virile “Gangam Style”), celebrity and/or reality TV performances, and the random dude-with-a-camera viral videos that YouTube is well-known for. Dataset from https://www.kaggle.com/datasnaek/youtube-new.

## Research Question:
1. Which region got most views?
2. What are the average time for potential videos to get to trending in each region?
3. What are the top 3 channels in each region measured by views and comments?
4. What top 3 categories were the most popular in each regions by views?
5. Throughout 2006 to 2018, which month was published most videos by channels?

### Assessment report of original dataset:

**general issues:**

**Quality issues**

- The data type of category_id should be object instead of int
- Many duplicated rows including exactly same rows and same video but was recorded in dataset in different time
- The data type of trending_date and publish_time should be datetime instead of object

**Tidiness issues**

- not useful coulumns: 'thumbnail_link','tags', 'description'
- The data includes a category_id field, which varies between regions. The categories for a specific video in the associated JSON.
- Each region’s data is in a separate file. They should be joined together and created a 'region' column to specify what is the region each data from


# Limitation and Conclusion:

> Limitation 1 : Youtube videos has **long tail effect**, which means some videos was not be popular at first, but might be popular in years so that the rank of each popular videos listed above might changed now. For example, the video "The Poop In My Pants | Rick and Morty | Adult Swim" had only near 2 millions views in this dataset, but it has 7 millions views now in 2020.

> Limitation 2 : There are some most important metrics of youtube like **Watch Time, unique views, and share counts**, but we don't have each of those information in the dataset so that based on the information given by the dataset to make decision about video creation will be some degree wrong.

> Limitation 3 : Average time for potential videos to get to trending in each region is based on 95% of the data because the 5% of the data is extremely high, therefore if someone use this analysis to predict the time of their videos to get to trending, it would be 5% degree wrong.

> Limitation 4 : The dataset missed the data from July to October, so the final analysis is only based on January to June, November and December.

#### Research Question 1: Which region got most views?

- Great Britain's average views is near 1.3m, which is almost 3 times as much as USA's views. And it would be interesting that if we divide the views by each population of region. For numbers of views per person, Great Britain was still the first place, which was at least 5 times higher than the rest of the regions is this dataset.

#### Research Question 2: What are the average time for potential videos to get to trending in each region?

- Average time for potential videos to get to trending in USA and Great Britain is around 22-25 hours, which is nearly two times as much as the average time in Japan and Russia.
       
#### Research Question 3: What are the top 3 channels in each region measured by views and comments?

- In these 6 regions, Great Britain's top 3 channel got most views and comments, which are LuisFonsiVEVO, BeckyGVEVO, and DrakeVEVO. All of them are singers' channels, and LuisFonsiVEVO's number calculated by 80% weight of views and 20% weights of comment counts was almost 4 times as many as DrakeVEVO.

#### Research Question 4: What top 3 categories were the most popular in each regions by views

- Music is the popular category that is in top 3 category in each region. In Great Britain, music got average 2750 k views, which is over 2 times as many a the rest of two in the top 3. Besides, gaming is a special category that got the highest average views in India and USA, and which is even not in top 3 list in the rest regions in the dataset.

#### Research Question 5: Throughout 2006 to 2018, which month was published most videos by channels?

- Around 6 regions, people tended to published less video in June, and pubished most in January or December.
