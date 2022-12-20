# Wikiwomen: An analysis on gender bias
*metADAta: Malin Svenberg, Maresa Fees, Greta Tuori, Valgerdur Jónsdóttir*

## Datastory
Please visit our datastory here: [Wikiwomen](https://gretasaskia.github.io/wikiwomen/)

## Abstract

Throughout history, women have been marginalised in many communities and in the last few years, gender bias against women has become even more visible in internet applications and online search. In Wikipedia, women are more linked to men than vice versa (Wagner et al. 2021) and Google Translate has tendency towards male defaults (Prates et al. 2020). Gender bias that appears online is in fact a reflection of the gender bias in our society. Therefore, we would like to investigate whether there exists a gender bias against women in Wikispeedia. In Wikispeedia, people are asked to navigate from a given source article to a certain target article on Wikipedia. The Wikispeedia dataset provides human navigation paths on Wikipedia which we can indeed use to answer whether there exists gender bias against women when users navigate from a given source article to a target article, where the target article relates to women.

## Research questions

To answer the question whether there exists a gender bias against women in the game of Wikispeedia, we aim to answer the following:
- Controlling for all confounding factors and only the gender being the difference, do the paths that end in target articles about women differ in any way from the paths that end in target articles about men?
    - Are the paths to target articles about women longer than those for men?
    - Do users find the paths that have a target article related to women more difficult than the average difficulty of path navigation? 
    - Is the play duration for target article about women longer than the average play duration?
    - Are there more back clicks in the paths that have a target article about women? 
    - Are there more unfinished paths than finished paths related to articles about women?

## Methods

### Pre-proccessing and dataset construction

In order to carry on with meaningful analysis of our project goals, we need to construct a framework with relevant information, i.e., information about articles about people and the paths that point to target articles within the category of *People*. In the following figure, this is emphasized with respect to the distribution of number of articles within each category in the original dataframe (where the odd colored bar contains the number of articles that are about people).

<p align="center">
<img width="634" alt="figure1" src="https://user-images.githubusercontent.com/52750379/202790954-5ad2f764-dc05-4f26-b065-74d367f88d6e.png">
</p>

Additionally, labelling articles about women and men is necessary and provides us with the possibility to compare the paths that have women as a target article versus the ones that have men as a target arcticle. In the following figure, we can see the amount of articles about women compared to those about men within each subcategory of the *People* category.
 
<p align="center">
<img width="634" alt="figure2" src="https://user-images.githubusercontent.com/52750379/208609919-1f2c8e6f-31c1-4116-b451-dd8240dc77d3.png">
</p>

In order to identify between articles about women and men, since we are only interested in paths that go from a certain source article to a target article either about a man or a woman, we aimed to filter out from the original dataset all target articles about women/men, i.e., that are classified as *People*. 

Our first idea to identify the gender of articles was to use Wikidata:SPARQL query service to extract and build a list of Wikipedia articles about women, and compare this list to our articles about people. However, this turned out to be an infeasible solution, since this method did not find every woman article in our dataset. Our second attempt was a brute-force method, where we went through a list of all articles about people and identified those who where about women. Out of all the articles, only 6% where about women. The resulting dataframe consists of a list of articles about women and their corresponding subcategory within the *People* category. The file, *listwomen.txt*, can be found in the folder `/data/`. Additionally, there are two more datasets in the folder `/data/`, called *all_paths_overview.csv* and *people_overview.csv*, that are the results of our pre-proccessing further elaborated on in our project notebook.

Calculation of statistical metrics and other relevant information concerning our project goals has to be extracted and added to our main dataframes, such as the human path length (the number of steps it takes a human to navigate from a source to a target), the shortest path lenght (the lowest possible number of steps it takes to navigate from a source to a target) and other statistical metrics mentioned in the following section.

### Statistical analysis

In order for us to make statements about the dataset we have defined a few metrics that will guide us during our analysis. They are the following:  

- **success**: what influence does the gender of the article have on the success of being reached
- **in_degree**: what influence does the gender have on the in_degree of the article
- **playtime**: what, if any, influence does the gender of the target article have on the playtime of the path
- **path_deviation**: what influence does the gender of the article have on the path deviation between a human path and the shortest path
- **number_backclicks**: what influence does the gender of the article have on the number of backclicks a user takes when navigating thorugh a path
- **difficulty_rating**: what influence does the gender of the article have on the difficulty rating that a user rates a path

#### Naive analysis

The first step of our data analysis will be a naive statistical analysis, where we will check for differences in the metrics defined above. These differences will be checked for significance using bootstrap confidence intervals among others. One key point to note, is the fact that we are working with a power law (network), therefore the median will be the main metric. We are aware that these statements cannot be used on their own, as there is no control over the confounding factors.

#### Controlling for confounding factors

Our next step will focus on controlling for the confounding factors to get a meaningful results whether there exists a gender bias against women.
Depending on the amount of data available, the matching will be constrained by different parameters. 

The strongest matching would control for 

1. starting a path at the same source article
2. having the same shortest path length between a source article and a target article
3. having target articles in the same sub-category (e.g. male scientist vs. female scientist)
4. having target articles with a similiar or the same in_degree

Constraint (1) is the minimum requirement. Simultaneously, all four constraints might be too strict so we will relax our constraints by either omitting constraints (2), (3) and (4) or using a variation of constraint (3).

One suggestions for a variation of (3) is to manually group sub-categories into bigger categories (e.g. combine *Political_People* and *USA_Presidents* into one group).

### Further explorations

We have also started to explore the textual context of articles within the *People* category, e.g. the use of specific words for female and male articles. After finishing the analysis on the metrics, we would like to further discover the relationship between the usage of gender-related words leading to a gender bias in the dataset. 

## Proposed timeline and internal milestones
Our timeline consists of internal milestones on every Tuesday and Friday until the project deadline.

- 18.11.22: **Project milestone 2 deadline**
    - Pre-proccesing and cleaning of data finished, initial data analysis started.
---
- 22.11.22: Review previous work, carry on with statistical analysis.
- 25.11.22: Finish naive analysis. 
---
- 29.11.22: Project work paused in order to work on Homework 2.
- 2.12.22: **Homework 2 deadline**
---
- 6.12.22: Finish statistical analysis when controlling for all confounding factors.
- 9.12.22: Visualizations and refinements. Explore the use of gender-related words.
---
- 13.12.22: Construct a rought draft of the data story.
- 16.12.22: Work on data story.
---
- 20.12.22: Complete the data story, add all necessary information to the final notebook and update README.
- 23.12.22: **Project milestone 3 deadline** 

## Organization within the team

Malin: Initial data analysis and plots. Statistical analysis. Website development.

Maresa: Pre-proccessing data. Initial data analysis and plots. Visualizations for data story.

Greta: Develop textual context for data story. Website development. Visualizations for data story.

Valgerdur: Statistical analysis. Develop textual context for data story. Overview of notebook and README.

## Sources
Prates, M.O.R., Avelar, P.H. & Lamb, L.C. (2020) Assessing gender bias in machine translation: a case study with Google Translate. Neural Comput & Applic 32, 6363–6381. https://doi.org/10.1007/s00521-019-04144-6

Wagner, C., Garcia, D., Jadidi, M., & Strohmaier, M. (2021). It’s a Man’s Wikipedia? Assessing Gender Inequality in an Online Encyclopedia. Proceedings of the International AAAI Conference on Web and Social Media, 9(1), 454-463. https://doi.org/10.1609/icwsm.v9i1.14628

[Wikispeedia](https://snap.stanford.edu/data/wikispeedia.html)
