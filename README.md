# Project Objective
Investigate the provided medical insurance cost dataset in a **.csv** file. Perform analysis on this dataset using the skills that have been developed so far, using a mixture of functions and python libraries to breakdown and analyse the provided dataset.
## Body Mass Index (BMI) Overview
BMI is a measure of whether you're a healthy weight for your height. You can use the NHS [BMI healthy weight calculator](https://www.nhs.uk/live-well/healthy-weight/bmi-calculator/) to find out your BMI.

For most adults, if your BMI is:
- below 18.5 – you're in the underweight range
- 18.5 to 24.9 – you're in the healthy weight range
- 25 to 29.9 – you're in the overweight range
- 30 to 39.9 – you're in the obese range
- 40 or above – you're in the severely obese range

If you have an Asian, Chinese, Middle Eastern, Black African or African-Caribbean family background you'll need to use a lower BMI score to measure overweight and obesity:

- 23 to 27.4 – you're in the overweight range
- 27.5 or above – you're in the obese range

BMI score has some limitations because it measures whether a person is carrying too much weight but not too much fat. For example, people who are very muscular, like professional sportspeople, can have a high BMI without much fat.

But for most people, BMI is a useful indication of whether they're a healthy weight.
## Overview of the dataset
The dataset has the following information within it using a `,` as a delimiter between each data item. 

| age | sex                     | bmi   | children | smoker             | region | charges |
| --- | ----------------------- | ----- | -------- | ------------------ | ------ | ------- |
| int | string('male'/'female') | flost | int      | string('yes'/'no') | string | float   |
### Example
| age | sex    | bmi   | children | smoker | region    | charges   |
| --- | ------ | ----- | -------- | ------ | --------- | --------- |
| 19  | female | 27.9  | 0        | yes    | southwest | 16994.924 |
| 18  | male   | 33.77 | 1        | no     | southeast | 1725.5523 |
### Dataset limitations
Although this dataset provides us with a lot of information we will not be able to accurately identify whether or not all people within the dataset are with healthy or unhealthy zones for their weight as we do not have the ethnicity information which would have an impact on what bmi a person needs to be considered overweight or not.
Our dataset also only includes people in the ages of 18 - 64 meaning that we are not getting a sample size that fully represents all of the population within each of the categories.
## Analysis Goals
Some analysis that I find interesting to to have a look at the different variables that might have an effect on a person bmi and see if we can identify whether or not being within a certain category has a correlation between being more healthy or not.
## Expectations
### Age
My expectation would be that the younger a person is the higher likely hood that they would be within the healthier bmi zones. This is due to the fact the people between the ages of 18 - 25 are within their physical prime and after that age most people start to decline. This makes it harder to people to keep a lower bmi and only people who live a healthy active lifestyle at these older ages are likely to in the healthier ranges.
### Sex
My expectation would be that men will have a lower bmi score than women, this is due to the fact that men naturally carry less fat then women. Although it is important to note that due to this women with a higher bmi value might not be be an unhealthy weight.
### Children
My expectation would be that people with less children will have lower bmi scores than people who do have children, this is due to the fact the people with no children have more time to focus on them selves and their fitness and people who do have children. Meaning that they are more likely to live healthier life styles.
### Smoker
My expectation would be that people who smoke will have lower bmi scores. This is due to the fact the through numerous studies it has been identified that smokers in general have a lower bmi score than non-smokers and then when smokers quit smoking they tend of have an increase in bmi.
### Region
I am not sure what to expect when it to regions links to higher or lower bmi scores as I am not so familiar with the regions of the United States. But my assumption would be that the states that generally have a lower standard of living will have higher bmi scores as the people from these areas have less access to high quality and healthily food. As well as having less opportunity for healthy activities and lower standards of health care.
## Implementation
To analysis this data set effectively I will be performing a number of different operations to split the dataset up into different categorises, find the average of each categories, ... 
### Importing CSV data
To start with I imported the `insurance.csv` data into a list of objects (`medical_records`) using Pythons csv library and `DictReader` appending each line returned from the dict reader to the `medical_records` variable.
### Spiting dataset into Categories
To split `medical_records` in specific categories datasets I created the `get_bmi_by_category()` function. This function takes two parameters:
1. A dataset (`medical_records`) that you would like to process
2. A category that you would like to have the bmi's within the dataset grouped.
This function then returns a dictionary where each key is a specific option under that category and the value is a list of all of the bmi's that is linked to that option.
### Getting Category Averages
To get the average bmi from a specified category dataset I made a `get_average()` function. This function takes one parameter:
1. A dictionary with key value pairs. With the keys being the options under a category and the values being a list of all of the bmi's that is linked to that option.
This function returns a dictionary where each key is a specific option under a category and the values is the average of all of the bmi's linked to that option.
### Getting Category Max
To get the biggest bmi from a specified category dataset I made a `get_max()` function. This function takes one parameter:
1. A dictionary with key value pairs. With the keys being the options under a category and the values being a list of all of the bmi's that is linked to that option.
This function returns a dictionary where each key is a specific option under a category and the value is the biggest bmi within the list that was linked to that option.
### Getting Category Min
To get the smallest bmi from a specified category dataset I made a `get_min()` function. This function takes one parameter:
1. A dictionary with key value pairs. With the keys being the options under a category and the values being a list of all of the bmi's that is linked to that option.
This function returns a dictionary where each key is a specific option under a category and the value is the smallest bmi within the list that was linked to that option.
### Identifying Health of Category
To identify what bmi health category a specified category dataset fell under I made a `get_bmi_category()` function. This function takes one parameter:
1. A dictionary with key value pairs. With the keys being the options under a category and the values the average bmi score linked to that key.
This function returns a dictionary where each key is a specific option under a category and the value is the bmi category that is linked to the average score provided.
## Results
### Age
| Age | Number of Participants | Average BMI | BMI Categorisation | Max   | Min    |
| --- | ---------------------- | ----------- | ------------------ | ----- | ------ |
| 18  | 69                     | 31.33       | obese              | 53.13 | 15.96  |
| 19  | 68                     | 28.6        | over-weight        | 44.88 | 17.48  |
| 20  | 29                     | 30.63       | obese              | 40.47 | 21.8   |
| 21  | 28                     | 28.19       | over-weight        | 39.49 | 16.81  |
| 22  | 28                     | 31.09       | obese              | 52.58 | 19.95  |
| 23  | 28                     | 31.45       | obese              | 50.38 | 17.385 |
| 24  | 28                     | 29.14       | over-weight        | 40.15 | 20.52  |
| 25  | 28                     | 29.69       | over-weight        | 45.54 | 20.8   |
| 26  | 28                     | 29.43       | over-weight        | 46.53 | 17.19  |
| 27  | 28                     | 29.33       | over-weight        | 45.9  | 17.95  |
| 28  | 28                     | 29.48       | over-weight        | 38.06 | 17.29  |
| 29  | 27                     | 29.38       | over-weight        | 38.94 | 20.23  |
| 30  | 27                     | 30.56       | obese              | 44.22 | 19.95  |
| 31  | 27                     | 29.92       | obese              | 39.49 | 20.4   |
| 32  | 26                     | 31.6        | obese              | 46.53 | 17.76  |
| 33  | 26                     | 31.16       | obese              | 42.94 | 18.5   |
| 34  | 26                     | 30.27       | obese              | 42.9  | 19     |
| 35  | 25                     | 31.29       | obese              | 43.34 | 17.86  |
| 36  | 25                     | 29.37       | over-weight        | 41.89 | 19.85  |
| 37  | 25                     | 31.22       | obese              | 47.6  | 17.29  |
| 38  | 25                     | 29.0        | over-weight        | 40.56 | 16.81  |
| 39  | 25                     | 29.91       | over-weight        | 45.43 | 18.3   |
| 40  | 27                     | 30.14       | obese              | 41.69 | 19.8   |
| 41  | 27                     | 31.51       | obese              | 40.26 | 21.75  |
| 42  | 27                     | 30.33       | obese              | 41.32 | 23.37  |
| 43  | 27                     | 30.2        | obese              | 46.2  | 20.04  |
| 44  | 27                     | 30.84       | obese              | 43.89 | 20.23  |
| 45  | 29                     | 29.78       | over-weight        | 39.99 | 20.35  |
| 46  | 29                     | 30.66       | obese              | 48.07 | 19.85  |
| 47  | 29                     | 30.66       | obese              | 47.52 | 19.19  |
| 48  | 29                     | 31.93       | obese              | 41.23 | 22.8   |
| 49  | 28                     | 30.31       | obese              | 42.68 | 21.3   |
| 50  | 29                     | 31.13       | obese              | 46.09 | 23.54  |
| 51  | 29                     | 31.73       | obese              | 42.9  | 18.05  |
| 52  | 29                     | 32.94       | obese              | 47.74 | 18.33  |
| 53  | 28                     | 32.72       | obese              | 41.47 | 20.9   |
| 54  | 28                     | 31.23       | obese              | 47.41 | 21.01  |
| 55  | 26                     | 31.95       | obese              | 40.81 | 21.5   |
| 56  | 26                     | 31.6        | obese              | 41.91 | 19.95  |
| 57  | 26                     | 30.84       | obese              | 43.7  | 18.33  |
| 58  | 25                     | 32.72       | obese              | 49.06 | 22.77  |
| 59  | 25                     | 30.57       | obese              | 41.14 | 23.65  |
| 60  | 23                     | 30.33       | obese              | 40.92 | 18.33  |
| 61  | 23                     | 32.55       | obese              | 44.0  | 21.09  |
| 62  | 23                     | 32.34       | obese              | 39.93 | 21.4   |
| 63  | 23                     | 31.92       | obese              | 41.47 | 21.66  |
| 64  | 22                     | 32.98       | obese              | 40.48 | 22.99  |
The results of the analysis shows that there is a bit of an impact on a persons bmi depending on their age. but it does not seem to have an more significant impact until you get past the age of 46 and onwards, with the averages before then bouncing between 29 - high 31. Out of the whole data set the sample size for each of the ages is the most consistent.
### Sex

| Sex    | Number of Participants | Average BMI | BMI Categorisation | Max   | Min   |
| ------ | ---------------------- | ----------- | ------------------ | ----- | ----- |
| female | 622                    | 30.38       | obese              | 48.07 | 16.81 |
| male   | 676                    | 30.94       | obese              | 53.13 | 15.96 |
The results from the analysis show that on average males have a higher bmi than females. This could be due to the fact there is are 48 more men within the sample compared to women. 
### Children
| Number of Children | Number of Participants | Average BMI | BMI Categorisation | Max   | Min    |
| ------------------ | ---------------------- | ----------- | ------------------ | ----- | ------ |
| 0                  | 574                    | 30.55       | obese              | 53.13 | 15.96  |
| 1                  | 324                    | 30.62       | obese              | 52.58 | 16.81  |
| 2                  | 240                    | 30.98       | obese              | 48.07 | 16.81  |
| 3                  | 157                    | 30.68       | obese              | 46.53 | 18.90  |
| 4                  | 25                     | 31.39       | obese              | 41.47 | 24.415 |
| 5                  | 18                     | 29.61       | over-weight        | 46.75 | 18.3   |
The results from this analysis shows that in general the more children a person has the higher average bmi. Where this trend deviates is when we get to 3 or more children, this could be down the the reduction of sample size between each of the groups.
### Smoker
| Smoker | Number of Participants | Average BMI | BMI Categorisation | Max   | Min   |
| ------ | ---------------------- | ----------- | ------------------ | ----- | ----- |
| yes    | 274                    | 30.71       | obese              | 52.58 | 17.19 |
| no     | 1064                   | 30.65       | obese              | 53.13 | 15.96 |
The results of the analysis shows that smokers in on average have a higher bmi than non-smokers. However there is a large disparity in the sample size between the two groups that could be having an impact on the average bmi.
### Region
| Region    | Number of Participants | Average BMI | BMI Categorisation | Max   | Min   |
| --------- | ---------------------- | ----------- | ------------------ | ----- | ----- |
| southwest | 325                    | 30.6        | obese              | 47.6  | 17.4  |
| southeast | 364                    | 33.36       | obese              | 53.13 | 19.8  |
| northwest | 325                    | 29.2        | over-weight        | 42.94 | 17.38 |
| northeast | 324                    | 29.17       | over-weight        | 48.07 | 15.96 |
The results of the analysis shows that the region that you are located in does have an impact a persons bmi. You can see a clear correlation between being located in southern states and an increase in a persons bmi. There could be a bit a skewed results when it comes to the south east region due to the increased number of participants from that region.
