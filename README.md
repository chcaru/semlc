
# Stack Exchange Machine Learning Competition

## Overview

Stack Exchange is a network of question and answer websites that cover a wide range of topics from physics to boardgames. 
Users may rank answers using an upvote / downvote system, and also select an answer as "correct" if they are the orignal question owner and found it to be the best.
These sites are modeled after the well known Stack Overflow site.
If you are not familiar with Stack Exchange, please poke around [here](http://stackexchange.com/) to get a feel for what it is and how it works.

In this competition, you will use a slightly slimmed down subset of the [Stack Exchange Data Dump](https://archive.org/details/stackexchange) to make predictions about whether or not an answer is the selected answer for a question.
This presents various challenges, and is a good starting point to dive right in and learn about data science and/or machine learning.

Below is an outline of the competition details, how to get the data, and how to submit an answer.

## Competition Details

The objective of this competition is to predict the probability that an answer to a question is the selected answer.

The setup below will provide the following files for each of the choosen Stack Exchange sites:

1. `badges.csv`

    - Please see `Badges.xml` [here](https://ia800500.us.archive.org/22/items/stackexchange/readme.txt)

2. `comments.csv`

    - Please see `Comments.xml` [here](https://ia800500.us.archive.org/22/items/stackexchange/readme.txt)

3. `posthistory.csv`

    - Please see `PostHistory.xml` [here](https://ia800500.us.archive.org/22/items/stackexchange/readme.txt)
    
4. `postlinks.csv`

    - Please see `PostLinks.xml` [here](https://ia800500.us.archive.org/22/items/stackexchange/readme.txt)
    
5. `questions.csv`

    - Please see `Post.xml` [here](https://ia800500.us.archive.org/22/items/stackexchange/readme.txt) where `PostTypeId=1`
    
6. `tags.csv`

    - Please see `Tags.xml` [here](https://ia800500.us.archive.org/22/items/stackexchange/readme.txt)
    
7. `test.answers.csv`

    - Please see `Post.xml` [here](https://ia800500.us.archive.org/22/items/stackexchange/readme.txt) where `PostTypeId=2`
    - These are related to `questions.csv` (`ParentId` is the `Id` of the question in `questions.csv`)
    - These are the answers used to test your model and produce a submission

8. `train.not-selected-answers.csv`

    - These are the answers which were NOT selected as an answer to their corresponding question
    - Please see `Post.xml` [here](https://ia800500.us.archive.org/22/items/stackexchange/readme.txt) where `PostTypeId=2`
    - These are related to `questions.csv` (`ParentId` is the `Id` of the question in `questions.csv`)

9. `train.selected-answers.csv`

    - These are the answers which WERE selected as an answer to their corresponding question
    - Please see `Post.xml` [here](https://ia800500.us.archive.org/22/items/stackexchange/readme.txt) where `PostTypeId=2`
    - These are related to `questions.csv` (`ParentId` is the `Id` of the question in `questions.csv`)
    
10. `users.csv`

    - Please see `Users.xml` [here](https://ia800500.us.archive.org/22/items/stackexchange/readme.txt)

11. Additionally, the name of the site (from the container directory) may be used as part of the dataset.

- No data other than that explicitly stated above may be used for the objective of this competition
- All files except for 7 (`test.answers.csv`) may be used for training.
- **7 (`test.answers.csv`) is ONLY to be used to produce submissions!!** It is cheating to do otherwise and would be against the spirit of the competition.

### Submission Objective

Given a site name and an answer `Id` from `test.answers.csv`, and / or any other data that can be associated using the provided files above, predict the probability that it is the selected answer. Specifically, 0.0 represents a 0% probability that the answer is the selected answer and 1.0 represents a 100% probability that an answer is the selected answer.
    - You may not use an answer's `Id` to associate it with a question's `AcceptedAnswerId`
    - Furthermore, you may not use any data that directly identifies whether or not it was the accepted answer.

#### Submission

A single submission file will be generated such that is has a row for each answer in `./data/*/test.answers.csv` (for all sites), such that it is a space delimited string `FullSiteName AnswerId PredictedProbabilityOfSelectedAnswer` (ex. `ai.stackexchange.com 1337 0.5`).

Please see `sample.submission.txt`. (The sample is also the baseline for equal guessing, and is a reliable list of the necesary test `AnswerId`s for a valid submission)

## Getting the Data

1. Download and unzip [data.7z](http://semlc7796.cloudapp.net/data.7z)
2. Data will be located in `./data/*/*.csv`

## Submit predictions

`TODO`