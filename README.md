---
---
---

# Titanic Machine learning from Disaster in Rstudio

#### I will load and display the training dataset by library(readr)

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)

library(readr)

titanic.train <- read_csv("train.csv")

View(titanic.train)
```

### Variable Notes

**So, I have the prediction variable in numeric and categorical variables that explained below...**

-   **Survival:** who was survived for 0 = No and 1 = Yes

-   **Sex:** Gender Male and female

-   **Pclass:** A proxy for socio-economic status (SES) 1st = Upper 2nd = Middle 3rd = Lower

-   **Age:** Age is fractional if less than 1. If the age is estimated, is it in the form of xx.5

-   **Sibsp:** The dataset defines family relations in this way...

Sibling **:** brother, sister, stepbrother, stepsister

Spouse **:**husband, wife (mistresses and fiancés were ignored)

-   **Parch:** The dataset defines family relations in this way...

Some children travelled only with a nanny, therefore parch=0 for them.

Parent : mother, father

Child : daughter, son, stepdaughter, stepson Some children travelled only with a nanny, therefore parch=0 for them.

-   **Embarked :**Port of Embarkation C = Cherbourg, Q = Queenstown, S = Southampton

-   **Cabin :**Cabin number

![](pictintanic/Screenshot%202566-09-15%20at%2013.45.31.png)

![](pictintanic/Screenshot%202566-09-15%20at%2013.43.38.png)

The summary shows the some numeric variables can do a distribution such as Age, Fare and some of category variables are characters such as Embarked, Sex, Cabin.Then some of the numeric variables are discrete data such as Pclass, Survived,Parch, Sibsp. Finally,some variables just show the information but it is not related to analyse the datasets are Passenger Id, Ticket and Fare.

#### I will shows the table describe a subset of training dataset by library(gtsummary)

![](pictintanic/Screenshot%202566-09-15%20at%2021.55.50.png)

![](pictintanic/Screenshot%202566-09-15%20at%2021.56.10.png){width="417"}

![](pictintanic/Screenshot%202566-09-15%20at%2021.56.19.png){width="415"}

**From the table 1.1** above,the original Titanic datasets has been modified to include a subset of variables, including Age, Sex, Passenger Class, Port of Embarkation, Survival status, SibSp (Siblings/Spouses), and Parch (Parents/Children). The table is divided into two sections based on the "Survived" variable: one for passengers who survived ( = 1) and another for passengers who did not survive ( = 0) that shows in the count and percentages.

#### I will do the description by library(dplyr) to explain statistical analysis

![](pictintanic/Screenshot%202566-09-15%20at%2013.40.28.png)

![](pictintanic/Screenshot%202566-09-15%20at%2013.40.00.png)

**From the table1.2 above** shows The Passenger in the 1st class has the oldest age about (38.23 +- 14.80) and The Passenger in the 3rd class has the youngest age about (25.14 +- 12.49). Minimum of the age is in the 3rd class about 0.42 years old and Maximum of the age is in the 1st class about 80 years old.

![](pictintanic/Screenshot%202566-09-15%20at%2013.56.26.png)

![](pictintanic/Screenshot%202566-09-15%20at%2013.50.48.png)

**From the table1.3 above** shows male are older age than female (30.72 +- 14.80) and female are younger age than male about (27.91 +- 14.11). Minimum and maximum of the age is male about 0.42 and 80 years old.

![](pictintanic/Screenshot%202566-09-15%20at%2013.51.16.png)

![](pictintanic/Screenshot%202566-09-15%20at%2013.51.30.png)

**From the table1.4 above** shows who was embarked from Cherbourg has the oldest age about (30.72 +- 14.80) and who was embarked from Queenstown the youngest age about (28.08 +- 16.91). Minimum of the age about 0.42 years old was embarked from Chourbourg and Maximum of the age about 80 years old was embarked from the Southampton. 2 passengers are not applicable.

![](pictintanic/Screenshot%202566-09-15%20at%2013.51.39.png)

![](pictintanic/Screenshot%202566-09-15%20at%2013.51.49.png)

**From the table 1.5 above**, shows was not survived has the older age than who was survived (30.62 +- 14.17) and who was suvived has the younger than age about (28.34 +- 14.95).

### **How do the features 'Age', 'Sex', 'Embarked','Sibsp' and 'Parch' affect the chance of a passenger's survival?**

##### I will do the description by library(ggplot2) to explain in a bar graph to tell more about count of each category of the feature with information about the percentage or counts and box plot to tell about the range of distribution of the feature.

![](pictintanic/Screenshot%202566-09-15%20at%2014.07.02.png){width="572"}

![](pictintanic/Screenshot%202566-09-15%20at%2014.08.23.png){width="570"}

![](pictintanic/Screenshot%202566-09-15%20at%2014.08.37.png){width="630"}

**From graph 2.1 above,** Shows the male in the 3rd class are the most passenger in the titanic sorted by Gender and Class in percentage about 38.94% and female in the 2nd class is the least passenger about 8.52%

![](pictintanic/Screenshot%202566-09-15%20at%2014.12.23.png){width="565"}

![](pictintanic/Screenshot%202566-09-15%20at%2014.12.31.png){width="561"}

![](pictintanic/Screenshot%202566-09-15%20at%2014.12.43.png){width="630"}

**From graph 2.2 above**, Shows the male who was embarked at Southampton are the most passenger in the titanic sorted by Gender and Embarked in percentage about 49.60%

![](pictintanic/Screenshot%202566-09-15%20at%2014.15.37.png){width="564"}

![](pictintanic/Screenshot%202566-09-15%20at%2014.15.43.png){width="564"}

![](pictintanic/Screenshot%202566-09-15%20at%2014.15.56.png){width="634"}

**From graph 2.3 above**, Shows the percentage that female was survived more than male from Titanic sorted by Gender about 26.15.%. Most of male died about 52.52% .

![](pictintanic/Screenshot%202566-09-15%20at%2014.17.46.png){width="559"}

![](pictintanic/Screenshot%202566-09-15%20at%2014.17.53.png){width="556"}

![](pictintanic/Screenshot%202566-09-15%20at%2014.18.04.png){width="621"}

**From graph 2.4 above**, Shows the percentage that 1st class was survived more than 2nd and 3rd class from Titanic sorted by Passenger class about 15.26% and the most of 3rd class died about 41.75%

![](pictintanic/Screenshot%202566-09-15%20at%2014.18.18.png){width="557"}

![](pictintanic/Screenshot%202566-09-15%20at%2014.18.25.png){width="557"}

![](pictintanic/Screenshot%202566-09-15%20at%2014.18.33.png){width="630"}

**From graph 2.5 above,** Shows the percentage that who was embarked as Southampton was survived more than Cherbourg and Queenstown from Titanic sorted by Embarkation about 24.40% and most of them died about 48.03%

#### In the Age variables, I will separate the age year in to a range.

![](pictintanic/Screenshot%202566-09-15%20at%2014.24.26.png){width="549"}

![](pictintanic/Screenshot%202566-09-15%20at%2014.27.04.png){width="544"}

![](pictintanic/Screenshot%202566-09-15%20at%2014.23.34.png){width="596"}

**From graph 2.6 above**, Shows the range age of the passenger in titanic sorted by Gender. The range about 21 -30 years old of male is the most passenger in titanic about 20.86% and Most of female 11.34%

![](pictintanic/Screenshot%202566-09-15%20at%2014.28.34.png){width="554"}

![](pictintanic/Screenshot%202566-09-15%20at%2014.28.43.png){width="551"}

![](pictintanic/Screenshot%202566-09-15%20at%2014.28.56.png){width="624"}

**From graph 2.7 above**, Shows the range age of the passenger in titanic sorted by Class. The range of not applicable in 3rd class is the most passenger in titanic about 18.06 %

![](pictintanic/Screenshot%202566-09-15%20at%2014.30.54.png){width="602"}

![](pictintanic/Screenshot%202566-09-15%20at%2014.31.02.png){width="600"}

![](pictintanic/Screenshot%202566-09-15%20at%2014.31.12.png){width="667"}

**From graph 2.8 above**, Shows the range age of the passenger in titanic sorted by Embarked. The range of 21-30 years old from Southampton is the most passenger in titanic about 25.56%

![](pictintanic/Screenshot%202566-09-15%20at%2014.32.52.png){width="584"}

![](pictintanic/Screenshot%202566-09-15%20at%2014.33.00.png){width="584"}

![](pictintanic/Screenshot%202566-09-15%20at%2014.33.10.png){width="656"}

**From graph 2.9 above,** Shows the range age of the passenger in titanic sorted by who was survived. The range of 21-30 years old was survived the most about 11.76% and most of them died about 20.44%

![](pictintanic/Screenshot%202566-09-15%20at%2014.35.32.png){width="583"}

![](pictintanic/Screenshot%202566-09-15%20at%2014.35.39.png){width="582"}

![](pictintanic/Screenshot%202566-09-15%20at%2014.35.50.png){width="652"}

**From graph 2.10 above**, Shows the family relations(Siblings and spouse) of the passenger in titanic sorted by who was survived. The passenger who was not have a family relations was survived the most about 23.56% and mostly of them died about 44.66%.

![](pictintanic/Screenshot%202566-09-15%20at%2014.37.31.png){width="587"}

![](pictintanic/Screenshot%202566-09-15%20at%2014.37.39.png){width="584"}

![](pictintanic/Screenshot%202566-09-15%20at%2014.37.49.png){width="653"}

**From graph 2.11 above**, Shows the family relations(Parents and children) of the passenger in titanic sorted by who was survived. The passenger who was not have a family relations was survived the most about 26.15% and mostly of them died about 49.94%.

##### The boxplot tell about the range of distribution of the feature shows a skewed distribution which is contained

##### 1. Interquartile range (IQR): it is drawn as a rectangle between the first quartile (Q1) and the third quartile (Q3). The difference between the third quartile and first quartile known as the interquartile range = Q3-Q1

##### 2. Median: which is the middle value when the data is ordered

##### 3. Potential outliers: The extreme data is individual data points that fall beyond the whiskers of the boxplot marked to draw attention to their deviation from the central data distribution.

##### 4. Line (or Whisker): represents the range of the data outside the IQR. A common approach is to extend them to a minimum and maximum of 1.5 times the IQR beyond Q1 and Q3

##### Minimum: Q1 - 1.5\*IQR

##### Maximum: Q3 + 1.5\*IQR

![](pictintanic/68747470733a2f2f63646e312e62796a75732e636f6d2f77702d636f6e74656e742f75706c6f6164732f323032302f31302f426f782d506c6f742d616e642d576869736b65722d506c6f742d312e706e67.png){width="565"}

![](pictintanic/Screenshot%202566-09-15%20at%2014.43.04.png){width="607"}

![](pictintanic/Screenshot%202566-09-15%20at%2014.44.13.png){width="598"}

**From the graph3.1** above Shows the range of distribution between Age and who was survived.

![](pictintanic/Screenshot%202566-09-15%20at%2014.45.58.png){width="603"}

![](pictintanic/Screenshot%202566-09-15%20at%2014.46.22.png){width="638"}

**From the graph3.2** above Shows the range of distribution between Age and and Passenger class who was survived.

![](pictintanic/Screenshot%202566-09-15%20at%2014.48.02.png){width="587"}

![](pictintanic/Screenshot%202566-09-15%20at%2014.48.27.png){width="645"}

**From the graph3.3** above Shows the range of distribution between Age and Embarkation and who was survived.

## References:

<https://rstudio-pubs-static.s3.amazonaws.com/143316_106d643df86c4e4c8ae20e9775ab0ec7.html>

<https://www.kaggle.com/competitions/titanic>

<https://www.danieldsjoberg.com/gtsummary/>

<https://www.r-bloggers.com/2016/02/titanic-machine-learning-from-disaster-part-1/>

<https://medium.com/analytics-vidhya/titanic-dataset-analysis-80-accuracy-9480cf3db538>

<https://byjus.com/maths/box-plot/>
