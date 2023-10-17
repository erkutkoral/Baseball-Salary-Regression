![image](https://github.com/erkutkoral/Baseball-Salary-Regression/assets/107303322/8412716f-74cb-4128-a3b4-23b2c5f8e309)<br/>
<p align="center">
  <a href="https://github.com/erkutkoral/Baseball-Salary-Regression">
    <img src="https://i.pinimg.com/736x/84/6a/b3/846ab377179c48a462725debbd475152.jpg" alt="Logo" width="400" height="400">
  </a>

  <h3 align="center">Hitters Baseball Players Salary Regression</h3>

  <p align="center">
    Performed EDA, Data Preprocessing, Machine Learning, Model Evaluation and Validation steps in Kaggle's Hitters Dataset.Let's get started.
    <br/>
    <br/>
    <a href="https://github.com/erkutkoral/Baseball-Salary-Regression"><strong>Explore the docs »</strong></a>
    <br/>
    <br/>
    <a href="https://github.com/erkutkoral/Baseball-Salary-Regression/issues">Report Bug</a>
    .
    <a href="https://github.com/erkutkoral/Baseball-Salary-Regression/issues">Request Feature</a>
  </p>
</p>

![Contributors](https://img.shields.io/github/contributors/erkutkoral/Baseball-Salary-Regression?color=dark-green) ![Issues](https://img.shields.io/github/issues/erkutkoral/Baseball-Salary-Regression) 

## Table Of Contents

* [About the Project](#about-the-project)
* [Technologies-Libraries-Frameworks](#technologies-libraries-frameworks)
* [Roadmap](#roadmap)
* [Conclusion](#conclusion)
* [Authors](#authors)

## About The Project

This dataset was originally retrieved from the StatLib library at Carnegie Mellon University. The data set is part of the data used in the 1988 ASA Charts Section Poster Session. Salary data originally from Sports Illustrated, April 20, 1987. 1986 and career statistics are obtained from the 1987 Baseball Encyclopedia Update published by Collier Books, Macmillan Publishing Company, New York.

| Variable | Definition |
| :- | -: |
| AtBat | Number of hits made with a baseball bat in the 1986-1987 season |
| Hits | Number of hits in the 1986-1987 season |
| HmRun | Most valuable hits in the 1986-1987 season |
| Runs | The points player scored for her team in the 1986-1987 season |
| RBI | Number of runs a batsman scores when batting |
| Walks | Number of mistakes made by the opposing player |
| Years | Player's playing time in the major league (years) |
| CAtBat | Number of times a player has kicked the ball in career time |
| CHits | Number of hits made by the player throughout in career time |
| CHmRun | The player's most valuable point in career time |
| CRuns | Number of points scored by the player for her team during in career time |
| CRBI | Number of runs made by player in career time |
| CWalks | Number of mistakes a player has made against an opposing player throughout in career time |
| League | A definer with A and N levels indicating the league in which the player played until the end of the season |
| Division | A definer with levels E and W indicating the player's playing position at the end of 1986 |
| PutOuts | Number of helping teammate in the game |
| Assits | Number of assists made by the player in the 1986-1987 season |
| Errors | Number of errors of the player in the 1986-1987 season |
| Salary | Salary of the player in the 1986-1987 season (in thousands) |
| NewLeague | A definer with A and N levels indicating the player's league at the start of the 1987 season |

## Technologies-Libraries-Frameworks

Python Libraries: Numpy, Pandas, Matplotlib, Seaborn, Scikit-Learn.

## Roadmap

1. Exploratory Data Analysis
2. Feature Extraction
3. Handling Outliers
4. Handling Missing Values
5. Machine Learning
6. Model Evaluation

## Conclusion
- **Exploratory Data Analysis Insights:**
  - Between 75% and Max. stages of data, there are some suspicious situations. For example, In CAtBati Chits, CHmRun variables there are some inbalanced view in %75 - Max. stages of data. There may be outliers in these variables.
  - When we go down with more detailed partitioning some variables like Walks, CHmRun seems all proper.
  - But for CAtBat, CHits variables, suspicious view is still continues.This may be due to outliers. At least we reduced to variable possibilities for outliers but going to check with more detailed way.
  - There are 3 categorical variables which have balanced classes.
  - There are not so much difference in playing different leagues but playing in A league make slight difference.
  - Playing in division E created a significant salary difference.
  - Saw thet there are not a significant differences in playing different leagues. Attaching new league effected same.
  - Among the dependent variables, some variables have more than 90% correlation with each other.It means, these variables are expressing same infofrmation. To define these:
    - Runs, Hits --> more than 90% correlation with AtBat.
    - CAtBat, CHits --> more than 90% correlation with Years.
    - CRBI --> more than 90% correlation with CHmRun.

- **Preprocessing Insights**:
  - For variables that are outliers, a trimming will be made from %5 - %95 of data. The reason for this attempt, is not changing distribution of variables too much. Changing distribution can create bias.
  - There were some missing values in target variable. Imputing or modifying these values can change distribution of target variable may create bias in model. In the worst scenario, imputing can be used for dependent variables but changing target variable values is too risky.
  - For feature extraction, there are 0 values in some dependent variables. Explored that in checking numeric variables with describe method. Multiplying or dividing with 0 values might cause math based problems in the next section. Also we dont want to change distribution of data so adding +1 all of dependent variables should be work.
  - There are both current season variables and whole career metrics in variables. Extracting a ratio for in specific season compare to whole career can contain information.
  - Dividing whole career numeric metrics with years can show yearly metrics so it may be contain information.
  - Years can be correlated with experinece so dividing years into categorical classes should be work too.
  - Combining playing position and categorical experince level variables can contain more sensetive information for success. It can be effect target variable. Expecting 4 x 2 = 8 classes in the variable.
  - There are 2 variables defining that new league and last league so creating a progress variables may be contain information.
  - Applied rare encoding classes that lower than 1% in progress variable.
 
    
- **Linear Regression Insights:**
  - There is a large decrease in R square values between the train and test sets.
  - This actually shows that the variables represented the data set well in the training part, but decreased in the testing part, meaning that the model memorized the observations and could not generalize them.This means overfit 🤦‍♂️.
  - It's actually not surprising to see model overfitting. There are 49 features for almost 300 observations in the last stage of feature engineering. There were too many variables for this much data and the number of data in each class was small. Therefore, the model is expected to memorize the data set.
  - If we proceed in the correlation stage by removing dependent variables with high correlations from the data set, this overfit rate will decrease
  - In addition, using different modeling algorithms can change results. In iterative models, we have the ability to see the learning situation on an iteration basis so that evaluation can be made.
  - Of course adding more data intuitively comes to mind as first solution. 😆
  - Reducing the low representation of classes, used rare encoding but this method can not able to evaluate feature importances.
  - Using iterative methods can solve this problem.



## Authors

* **Erkut Koral** - [LınkedIn](https://www.linkedin.com/in/erkutkoral/)
