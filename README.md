README.md 

Please look at the gh-pages branch in the repo

Project url: https://christiansarran.github.io/d25/
Repo url:  https://github.com/ChristianSarran/d25/tree/gh-pages

# **Choosing Reddit Flairs on r/AskScience**

## Abstract:

Reddit had an estimated 303.4 million (https://www.redditinc.com/blog/reddits-2020-year-in-review/) new posts in 2020. It is a social media platform with growing popularity and with that comes better need for structure and organization of the platform. Some Subreddits including r/AskScience use a manual flair method where a mod will assign a topic to a post in order to make organizing, filter and search of the subreddits easier. The goal of the project will be to determine if the current flair system implemented in the subreddit r/AskScience is succeeding, can it be improved and if auto flair detection and assignment could be possible. Beyond this we will try to better understand reddit and r/AskScience as a community. The data that will be examined is post data from r/AskScience from Jan. 1st, 2016, and May 31st, 2021

## Research Questions: 
 The main questions to be answered are does r/AskScience do a good job of choosing Flairs for thier posts? 
    Additional Research questions include:
        Can they do a better job?
        Is the subreddit stagnant, or does it change alot?
        Do particular fields of study dominant the questions?
        Are certain flairs often asked by the same person?

## Methods:
What exploratory analyses, statistical summaries, modeling approaches, and visualization techniques do you plan to use to answer your research question(s)? You should address the considerations listed above here. 

Alot of the flairs will be hardly used. For the purpose of this project I will only look at the top flairs which are used >4% which are the top 8 most used flairs out of the 62 total found in the datset.
Reddit posts are also generally very short so we often won't have alot of data per post.

The first exploratory analyses I will perform will be to go through the dataset and understand each feature, an understand the value if any, it brings to our model. Features 'url' and 'link' for example only
contain the url of r/AskReddit and then the question. The origin from AskReddit is already implied in the dataset and the question is inidcated in the question column, thus we can remove these features as they bring
no value. Looking at the boxsplot for the continuous variables like score or num of comments will allows to visualize them easily and understand their range and variance. Visualling a pie chart of the categorical
variables like banned, year, or flair will allow us to understand the spread of these variables. Doing these visualization will also allow us to understand any errors in the data, like missing values or outliers. A 
Confusion matrix with the topic flair will allow us to see relations between this feature and others. Understanding submissions over time, and by flair may give us some understanding of paterns in the subreddit

Further I will try to explore relation between the topic of the post and other meta data of the post. These relationships will allow us to go beyond just using NLP to classify the topic

Next to interpret the text data like from the description of the question and from the question, into vector space, I will use TF-IDF, reducing stopwords and calculating important words

I will split the data into 60% training, 15% validation and 15% testing sets so we can objectively measure the success of our models.

To evaluate performance of the models I will use:
Accuracy, Sensitivity, specificity and F1 Score(the average of both Sensitivity and specificity )

The methods I wish to try to explore to Topic Model this data set are Linear Support Vector Classifier  (LinearSVC) and Naive Bayes.
 
A visualization technique to determine efficacy of our models would be to create a confusion matrix between our predicted label and true label. This will help us to understand which labels the model is having trouble distinquishing between and which are easily distinquished.

 

## Additional Datasets:
 I plan on using an external datasource (Mishra, Sumit (2021), “Reddit r/AskScience Flair Dataset”, Mendeley Data, V1, doi: 10.17632/k9r2d9z999.1) which extracted posts from 01-01-2016 and 31-05-2021 from the /r/AskScience from Reddit. The data contains 519054 Datapoints and 26 Columns which include: 

        author - Redditor Name 

        author_fullname - Redditor Full name 

        contest_mode - Contest mode [implement obscured scores and randomized sorting]. 

        created_utc - Time the submission was created, represented in Unix Time. 

        domain - Domain of submission. 

        edited - If the post is edited or not. 

        full_link - Link of the post on the subreddit. 

        gilded - If the submission is gilded i.e. if someone awarded the submission Reddit gold. 

        id - ID of the submission. 

        is_self - Whether or not the submission is a self post (text-only). 

        link_flair_css_class - CSS Class used to identify the flair. 

        link_flair_text - Flair on the post or The link flair’s text content. 

        locked - Whether or not the submission has been locked. 

        num_comments - The number of comments on the submission. 

        over_18 - Whether or not the submission has been marked as NSFW. 

        permalink - A permalink for the submission. 

        retrieved_on - time ingested. 

        score - The number of upvotes for the submission. 

        description - Description of the Submission. 

        spoiler - Whether or not the submission has been marked as a spoiler. 

        stickied - Whether or not the submission is stickied. 

        thumbnail - Thumbnail of Submission. 

        question - Question Asked in the Submission. 

        url - The URL the submission links to, or the permalink if a self post. 

        year - Year of the Submission. 

        banned - Banned by the moderator or not. 

 
        The data is in a very useable format and contains a lot of the features contained in our original dataset, but with additional features including the full question, flairs and description 

        which will be required in order to create a prediction model. I have found this dataset publicly available on kaggle and much of the dataset. I could possibly try to enrich this data by linking the posts to its comments to gain some insight from the comments/answers on the post. I could do this by linking another dataset containing the comments history of r/AskScience via the post id, however to prevent too large of a scope I currently plan on using just these features for now 



This project will be done solo. 
