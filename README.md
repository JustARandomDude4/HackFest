# BugBusting with BugBusters [Team IC-6]


Made with ❤ by **Bug Busters**  
We built a Machine Learning model that can detect anomalous code commits that are likely to result in bugs or errors in the software.

>> Team Mates :  
>>|| Dheeraj Reddy Meka ||
>> Abhinay Katta ||
>> Hima Satwika Katragadda||

                                                                                                                            
## Installation & Deployment 📦    & ## Tools Used 🛠️
- Clone the repository and modify the content 
- Dependencies to be installed :
```

#Dependencies:
import pickle
import numpy as np # linear algebra
import pandas as pd # data processing, CSV file I/O (e.g. pd.read_csv)
import matplotlib.pyplot as plt
import seaborn as sns
sns.set_style("darkgrid")

from datetime import datetime as dt
from sklearn.feature_extraction.text import CountVectorizer
from sklearn import preprocessing

import statsmodels.api as sm
import statsmodels.graphics as smg
import statsmodels.stats as sm_stats
import statsmodels.tsa.api as tsa

from scipy import stats

```
## CODE EXPLANATION    
Commit Classification
Reference
Idan Amit, and Dror G. Feitelson. (2020). The Corrective Commit Probability Code Quality Metric.
https://arxiv.org/abs/2007.10912
https://github.com/evidencebp/commit-classification


*Exploratory Data Analysis: In this step, we analyzed the "Github Commit Messages Dataset" for performing Exploratory Data Analysis (EDA) on a dataset containing information about Git commits in different repositories.
*Here's a breakdown of the code:
```
ustats = df.groupby('repo').nunique(): This groups the data by the "repo" column and calculates the number of unique values for each column. The result is stored in a new dataframe called "ustats".

ustats = ustats.sort_values(by="message", ascending=False): This sorts the "ustats" dataframe by the "message" column in descending order.
fig, (ax1,ax2) = plt.subplots(2,1, figsize=(18,8)): This creates a figure with two subplots of size 18x8. The subplots are stored in variables "ax1" and "ax2".

fig.autofmt_xdate(rotation=90): This rotates the x-axis labels by 90 degrees to prevent overlap.

ax1.bar(x=ustats.index, height=ustats['message']): This creates a bar chart on the first subplot, with the x-axis showing the repository names and the y-axis showing the count of commits for each repository.

ax1.set_title('Count of Commits'): This sets the title of the first subplot to "Count of Commits".

ax2.bar(x=ustats.index, height=ustats['user']): This creates a bar chart on the second subplot, with the x-axis showing the repository names and the y-axis showing the count of unique users who made commits to each repository.


ax2.set_title('Count of Users'): This sets the title of the second subplot to "Count of Users".

df_sort = df.sort_values('dday'): This sorts the original dataframe "df" by the "dday" column.

df_sort.head(20): This prints the first 20 rows of the sorted dataframe.

message_day = df.pivot_table(index='dday', columns='repo', values='message', aggfunc='count', fill_value=0, margins=True): This creates a pivot table of the "df" dataframe, with "dday" as the index, "repo" as the columns, and "message" as the values. The values are aggregated using the count function, and any missing values are filled with 0. The "margins" parameter is set to True to add a row and column showing the total count.

message_day.drop('All')[100:-5].rolling(90)['All'].mean().plot(figsize=(20,6)): This plots a rolling average of the total number of commits per day (across all repositories), with a window size of 90 days. The first 100 rows and last 5 rows of the pivot table are dropped to remove outliers, and the plot is displayed with a figure size of 20x6.

message_day.drop('All')[100:-5].rolling(30)['All'].mean().plot(figsize=(20,6)): This plots a rolling average of the total number of commits per day (across all repositories), with a window size of 30 days. The first 100 rows and last 5 rows of the pivot table are dropped to remove outliers, and the plot is displayed with a figure size of 20x6.

message_day.drop('All')[100:-5].rolling(30)['torvalds/linux'].mean().plot(figsize=(20,6)): This plots a rolling average of the number of commits per day for the "torval
```

*This contains lists of regular expressions, negation terms, modals, security terms, and documentation entities.*
*The regular expressions are used for pattern matching and extracting information from text data. The regular expression file_scheme matches any file name that consists of one or more alphanumeric characters, underscores, asterisks, and dots, followed by a period and a file extension of 1 to 4 letters.*
*The negation_terms list contains common words and contractions used to indicate negation in text, such as "aren't", "cannot", "didn't", "never", etc.*
*The modals list contains modal verbs like "can", "could", "may", "might", "must", etc., which are used to express modalities in text.*
*The security_terms list contains security-related terms like "attack", "credential(s)", "exploit", "security", etc., which are used to detect security-related issues in text.*
*The documentation_entities list contains terms related to documentation like "README", "man pages", "Java docs", etc., which are used to identify documentation-related issues in text.*
*Each list is defined as a Python list of strings containing regular expressions, words, or phrases, and the term_seperator variable contains a regular expression to separate terms in a given text.*


## Contributing 💡
#### Step 1
- **Option 1**
    - 🍴 Fork this repo!
- **Option 2**
    - 👯 Clone this repo to your local machine.


#### Step 2
- **Build your code** 🔨🔨🔨

#### Step 3
- 🔃 Create a new pull request.


# Contributing 💡

If you can help us to add other pages. Please don't hesitate to open an [pull request](https://github.com/https://github.com/JustARandomDude4/MemEthereum/pulls) or facing any problem create [issue](https://github.com/JustARandomDude4/issues) here.


