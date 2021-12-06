For marker of this file, please read from the readme preview which shows the files in the repo, and not by clicking into the file, due to formatting differences (https://github.com/ChristianSarran/d25). HTML formatting became to cumbersome

# CSCD25: Course Project


Reddit had an estimated 303.4 million (https://www.redditinc.com/blog/reddits-2020-year-in-review/) new posts in 2020. It is a social media platform with growing popularity and with that comes better need for structure and organization of the platform. Some Subreddits including r/AskScience use a manual flair method where a mod will assign a topic to a post inorder to make organizing, filter and search of the subreddits easier. The goal of the project will be to determine if the current flair system implemented in the subreddit r/AskScience is succeeding, can it be improved and if auto flair detection and assignment could be possible. Beyond this we will try to better understand reddit and r/AskScience as a community to ensure best the outcomes. We will look at post data from 2016-2020

Is there a domaince of specific types of science as a result of the platform?(i.e. higher voted topics will trend to people asking about those topics
Bigger reddit communities? Bigger population?


First lets try to understand the subreddit as whole.

<br />

### What Flairs are used?

There are 62 unique flairs total, of which 42 have been used less than 5 times and 8 of which are used less than 10,000 times. Many are AMA based and some are a mix of multiple science fields. A few of the middle to less used flair are listed below to the left to gain a sense of what their scope and prevalence looks like.

The majority of posts however can be see in these top flairs in the pie chart on the right. We will ignore the less used flairs for the purpose of this research as many are simply not used enough to be relevant 

<img align="right" src="https://github.com/ChristianSarran/d25/blob/9cffefdb4a6e8db8862096dcfa97f2336bdc542d/pie.png" alt=""/>

<pre>
...
Earth Sciences                  31542 posts
Medicine                        26698 posts 
Engineering                     21112 posts
Psychology                      18921 posts
Neuroscience                    18517 posts
COVID-19                        16172 posts
Planetary Sci.                  15125 posts
Computing                       10297 posts
Mathematics                     9360 posts
Social Science                  5355 posts
Anthropology                    3374 posts
Paleontology                    2712 posts
Linguistics                     2115 posts
Economics                       2007 posts
Political Science               1122 posts
Archaeology                      978 posts
Economics                       2007 posts
Political Science               1122 posts
Archaeology                      978 posts
Biology/Agriculture                5 posts
Neuroscience AMA                   3 posts
Agriculture                        2 posts
Panel Applications                 2 posts 
ACS AMA                            2 posts
Malaria AMA                        2 posts
Weather ❄ 😎                      1 posts 
Neutrino Physics AMA               1 posts
...
</pre>

<br />

### How has the subreddit change over time?

Looking at the number of post over time, the subreddit lost a lot popularity in 2018 and 2019, but than gain a resurrgency in 2020 and is maintaining the popularity in 2021.

<img align="left" src="https://github.com/ChristianSarran/d25/blob/ef0d12eb77a5a72de8dbf23db26a8ae0cd1af063/year.png" alt=""/>


<img align="left" src="https://github.com/ChristianSarran/d25/blob/bb1aa45b76b8215b4126d2aabbe93a64cd0bd9c0/time.png" alt=""/>

The huge spike in popularity conincides with lockdowns starting to occur in North America in early to mid 2020. This would suggest like a lot of internet based media r/AskScience saw a huge boost in activity from covd-19 lockdown. We even see a new flair COVID-19 popup in 2019 and quickly rise to 3% all time popularity in less than 2 years


Looking at the top most used flairs we actually see a suprising consistent pattern between distribution of flair types over time. Flairs tend to fall and grow at the same time
but also maintain close to the same relative popularity. We see almost two groups in the top flairs, the 'dominant flairs' Physics, Biology and Human Body which maintain their
top 3 status and are close together, and then the second group of a wide variety of topics like Chemisty, Engineering, and Astronomy which maintaing a 'middle tier' group which
all stat roughly together with neiter group really jumping between.


There is a noteworthy spike from medicine in 2020 which breaks this pattern which is likely due to the sudden public interest in covid's health measures and the vaccine. This
demonstrates that although the subreddit is relatively set in its ways, massive event like the corona virus can be reflect in large scale change in the behaviour of the subreddit.

<br />

### What do user patterns look like?

<img align="left" src="https://github.com/ChristianSarran/d25/blob/6c86c133cdd98d8d2a0f07ceb944d65eba0544ec/correlation_clustering.png" alt=""/>

<br />
<p align="right">
Looking at the correlation between types of posts (based on flair) by user we see specific flair grouping which tend to be posted by the same person like biology, earth science and medicine. Physics also seems to be uniquely seperate from the other flairs not having high corrleation with any other flair. Biology has the highest correlation with every other flair, which makes sense from the most widely used flair and we also see a tight correlation bettween enginnerring, earth science and biology
<p/>

<br />
<br />
<br />
<br />

<img width="400" height="300" align="left" src="https://github.com/ChristianSarran/d25/blob/88fbb933bf542e6e015fc47a63b907f7923f2b62/sumOfPosts.png" alt=""/>

<img width="350" height="300" align="right" src="https://github.com/ChristianSarran/d25/blob/f2da4d6651ea8a7d3269aa60d264a301f7e26517/scoreOfPosts.png" alt=""/>
  
   <br />
 <br />
 <br />
 <br />
 <br />
 <br />
 <br />
 <br />
 <br />
 <br />
 <br />
 <br />
 <br />
  

  <p align="center">
From the graph on the left we see that although some people do post more than just a few times, more than half the submissions on the subreddit come from one or two time posters
and less than 5% come from people who post more than 5 times. Alternatively on the right graph we see an overwhelmingly large portion of posts will have less than 50 score, and very few will achieve over 500
<p/>


### How well are topics organized now?

In order to answer this question, we will try to use topic modelling to create topics based on the questions asked, and see if the currents flairs meet these topics and if the
flairs can easily be predicted based on the question. 

First we will take the raw question data and remove any stopwords/uninformative wards, punctuation/non alpha characters and lowercase everything. Stemming was applied but found not siginifcant predicitive improvments. This will be our corpus for analysis

![raw](https://user-images.githubusercontent.com/43121654/144928012-4963f6bd-d705-4e80-ac7b-6062e5d1dd9f.PNG)

<img width="100" height="100" align="center" src="https://github.com/ChristianSarran/d25/blob/2038b0a8f008755e62cabe06a77e37042be1af66/output-onlinepngtools.png" alt=""/>

![cleaned2](https://user-images.githubusercontent.com/43121654/144926444-459361a7-961c-4a87-a50f-48e4ddc7b773.PNG)

Next the data is split into training/validation and test. TFIDF is then fitted and applied and then passed through both Multinomial Naivyes Bayes classifier and a Linear Support Vector Classifier, which is then fined tuned with the validation set and applied to the test set

We see the accuracy of MultinomialNB is 0.65 and LinearSVC 0.668

<img width="600" height="600" align="left" src="https://github.com/ChristianSarran/d25/blob/e1e02170d4f4799d86712e673b0667846d4047f7/confusion.png" alt=""/>
