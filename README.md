# Wikiwomen: An analysis on gender bias
*metADAta: Malin Svenberg, Maresa Fees, Greta Tuori, Valgerdur Jónsdóttir*

## Abstract

Throughout history, women have been marginalised in many communities and in the last few years, gender bias against women has become even more visible in internet applications and online search. One example of such is Google Translate when translating from one language to another. This gender bias that appears online is in fact a reflection of the gender bias in our society. Therefore, we would like to investigate whether there exists a gender bias against women when people play the game of Wikispeedia. In Wikispeedia, people are asked to navigate from a given source article to a certain target article on Wikipedia. The Wikispeedia dataset provides human navigation paths on Wikipedia which we can indeed use to answer whether there exists gender bias against women when users navigate from a given source article to a target article, where the target article relates to women.

## Research questions

To answer the question whether there exists a gender bias against women in the game of Wikispeedia, we aim to answer the following questions:
- Controlling for all confounding factors and only the gender being the difference, are the paths to target articles about women longer than those for men?
    - Do users find the paths that have a target article related to women more difficult than the average difficulty of path navigation? 
    - Is the play duration for target article about women longer than the average play duration?
    - Are there more back clicks in the paths that have a target article about women? 
    - Are there more unfinished paths than finished paths related to articles about women?

## Additional datasets

In order to identify between articles about women and men, since we are only interested in paths that go from a certain source article to a target article either about a man or a woman, we aimed to filter out from the original dataset all target articles about women/men, i.e., that are classified in the category *People*. The distribution of number of articles within each caregory in the original dataframe can be seen in fig1. 

<p align="center">
    <img width="645" alt="figure1" src="https://user-images.githubusercontent.com/52750379/202451289-2afddaad-f4dc-492f-ab23-1540b49c2fe6.png">
</p>


Our first idea to identify the gender of articles was to use Wikidata:SPARQL query service to extract and build a list of Wikipedia articles about women, and compare this list to our articles about people. However, this turned out to be an infeasible solution, since this method did not find every woman article in our dataset. Our second attempt was a brute-force method, where we went through a list of all articles about people and identified those who where about women. Out of all the articles, only 6% where about women, so this method turned out to be not as difficult as one would suppose beforehand. The resulting dataframe consists of a list of articles about women and their corresponding subcategory within the *People* category. The file, `listwomen.txt`, can be found in the folder `/data/`.

## Methods

### Step 1

### Step 2

### Step 3

### Step 4

## Proposed timeline and internal milestones
Our timeline consists of internal milestones on every Tuesday and Friday until the project deadline.

- 18.11.22: **Project milestone 2 deadline**
    - Pre-proccesing of data finished, construct a main dataframe for our analysis.
---
- 22.11.22: 
- 25.11.22:
---
- 29.11.22: Project work paused in order to work on Homework 2.
- 2.12.22: **Homework 2 deadline**
---
- 6.12.22: 
- 9.12.22: 
---
- 13.12.22:
- 16.12.22:
---
- 20.12.22: Complete the data story.
- 23.12.22: **Project milestone 3 deadline**

## Organization within the team

Malin: Plotting graphs during data analysis, crawling the data, preliminary data analysis
Maresa: Problem formulation, coming up with the algorithm
Greta: Coding up the algorithm, running tests, tabulating final results
Valgerdur: Writing up the report or the data story, preparing the final presentation


## Sources
[Wikispeedia](https://snap.stanford.edu/data/wikispeedia.html)
