# ChatGPT eats STA130: Introduction to Statistical Reasoning and Data Science

- Google "uoft jupyterhub" -> [https://datatools.utoronto.ca](https://datatools.utoronto.ca)
  - Choose "jupyter" [https://jupyter.utoronto.ca/](https://jupyter.utoronto.ca/) -> and then created a "New Python 3 (ipykernel)" to open a notebook
- Get [ChatGPT 3.5](https://chat.openai.com/) or better yet 4.0

|  |Topic         |TUT(Friday)|LEC(Monday)|Draft|Reviewer|
|--|--------------|-----------|-----------|-----|--------|
|01|Data Wrangling|[Sep06](TUT/STA130F24_TUT01_Sep06.ipynb)|[Sep09](LEC/STA130F24_LEC01_Sep09.ipynb)|Scott|Shiraz+Ray  |
|02|Coding        |[Sep13](TUT/STA130F24_TUT02_Sep13.ipynb)|[Sep16](LEC/STA130F24_LEC02_Sep16.ipynb)|Scott|Edric+Serena|
|03|Visualization |[Sep20](TUT/STA130F24_TUT03_Sep20.ipynb)|[Sep23](LEC/STA130F24_LEC03_Sep23.ipynb)|Scott|Ali+Alex    |
|04|Bootstrapping |[Sep27](TUT/STA130F24_TUT04_Sep27.ipynb)|[Sep30](LEC/STA130F24_LEC04_Sep30.ipynb)|Ali|Alex|
|4B|Testing/Review|Oct04|Oct07|   | |
|--|MTexam/Thnxgng|Oct11|Oct14| | |
|05|Regression I  |Oct18|Oct21|Shiraz|Serena|
|06|Testing       |Oct25|     |Alex|Ali|
|--|Reading Week  |     |Oct28|   | |
|--|Reading Week  |Nov01|     |   | |
|06|Testing       |     |Nov04|Alex|Ali|
|07|Regression II |[Nov08](STA130F24_TUT07_Nov08.ipynb)|[Nov11](STA130F24_LEC07_Nov11.ipynb)|Serena|Shiraz|
|08|Classification|[Nov15](STA130F24_TUT08_Nov15.ipynb)|[Nov18](STA130F24_LEC08_Nov18.ipynb)|Ray|Edric|
|09|Ethics        |[Nov22](STA130F24_TUT09_Nov22.ipynb)|Nov25|Edric|Ray|
|10|Review        |     |Dec02|  | |
|11|Projects      |     |Dec03(Tuesday)|  | |

## Learning Objectives

1. Week 1
   1. ChatGPT
      1. can be very helpful both in terms of coding and conceptual understanding
      2. can make mistakes
      3. can be influenced by how it is engaged with
   2. jupyter notebooks
      1. for `python` coding
      2. and Markdown formatting
   3. GitHub.com as a repository for coding files
   4. Data Wrangling
      1. importing libraries `import pandas as pd`
      2. loading data `pd.read_csv() # file or url`
      3. examining missingness `df.isnull().sum()`
      4. removing missingness `df.dropna()` and `del df['col']`
      5. summarizing data `pd.describe()`
      6. mean, variance, standard deviation
      7. group by `df.groupby.describe()`
      8. subsetting `df[], df.loc[], df.iloc[] 
      9. boolean selection
      
