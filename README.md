# ADA - Project Milestone 2: 
# *Analysis of speech behaviours between genders*

## Abstract 

It is common knowledge that women’ speech contains more uncertainties (e.g., “We think this may be correct”) compared to men (e.g., “I know it is correct”). As a result, this project aims at comparing speech behaviors related to uncertainty between genders. As our data, we use quotes from Quotebank, an open corpus of more than 1 million of quotations from 2015 to 2020, as well as the open-source information from wikidata to have access to the speakers' information. The classification of the quotes is done using an uncertainty detection classifier, based on the statistical analysis of multiple lexical and syntactic features. Specifically, we analyze differences in communicative acts in relation to gender within and between professional areas. Furthermore, we emphasis on the roles of nationality, culture/tradition, and education in determining those differences. Finally, we also observe whether there is a possible change over time (from 2015 to 2020).

## Research questions 

We are interested in using this dataset to answer the following question: Do speech behaviours related to confidence and uncertainty vary between men and women?

To answer this question, we'll go through the following points:

1. To what extent can we observe the differences in communicative acts in relation to gender within a professional area? Are there noticeable differences between those professional areas?

2. What are the roles of nationality, culture/tradition (religion, ethnic groups), and education (whether the speaker obtained an academic degree) in determining those differences in speech between men and women? How are the lines drawn between the language we use and the environment around us?

3. Has there been a possible change over time (from 2015 to 2020)?

## Proposed additional datasets
To complement the Quotebank dataset, we use the open source stored data on Wikidata, as well as a classifier.

### Wikidata
It is an open source dataset (https://www.wikidata.org/wiki/Wikidata:Main_Page).

### Uncertainty Detection Classifier
To classify the quotes according to the uncertain lexical and syntactic features, we use the public uncertainty detection classifier from the paper "P. A. Jean, S. Harispe, S. Ranwez, P. Bellot, and J. Montmain, “Uncertainty detection in natural language: A probabilistic model” ACM Int. Conf. Proceeding Ser., vol. 13-15-June, no. June, 2016, doi: 10.1145/2912845.2912873". It is available for download at: https://github.c-om/pajean/uncertaintyDetection. As this was created on python2, we had to adapt it to run on python3.

The data from wikidata and the adapted classifier can be found on this public drive: https://drive.google.com/drive/folders/1UgvnLUFhs14NDcZYH6NuZx2f_YC5i06N. More instructions are provided within the notebook.


## Methods

1. Pre-processing of the data
  - Loading quotebank and wikidata
  - Cleaning quotebank and wikidata  
  We started our cleaning by removing rows containing missing value on mandatory features for our study like the speaker identity and gender. We also made sure that there were no duplicate data (no duplicate quotes in quotebank and speaker id in wikidata). In quotebank, we kept only the quotes where the speaker probability was greater than 0.5. We thaught that lower probabilities could interfere with our study.
  - Exploratory Data Analysis (EDA) of quotebank and wikidata  
  We observed a vast distribution of genders that we decided to reduce to male and female only. The other genders represented less than 0.03% of the data and removing them would greately simplify our study.  
  We also analyzed the language of the quotes in the quotebank dataset and found a minority of non-english quotes, they represent less than 1% of the data. We realized that identifying the language for millions of quotes was extremely time consuming. To help ensure that quotes language didn't become a bias in our study we selected quotes containing words in english, resulting in a much faster way to distinguish them at the cost of some imprecisions.
  - Merging quotebank and wikidata  
2. Creation of the lists of similar professions
To be able to avoid the bias of different backgrounds between male and female, we subdivided our data into 4 professional fields:
  - Artists, scientists, economists, & politicians.
This allows us to be able to hold comparison between genders in the same category of profession. To achieve the separation, we searched for the speker's occupation of each quote with the help of `wikidata`. Then hand-picked the professions to look for as strings and returned them in separate pickle files for each field.
3. Classification of the quotes
  - Uncertainty detection classifier
4. Statistical-analysis
  - Professions (artists, scientists, economists, politicians)
  - Environment (culture/religion, nationality, education)
To extend our research on the question of gender speech uncertainety, we invetigated on how does culture and eduction shape the way men and women speak. We based this study on the `nationality`, `ethnic_group`, `religion` and `academic_degree` columns of the speaker. This allows each time to remove the bias of the cultural influence and to compare the gender speech.
  - Time (2015-2020)
5. Interpretation of results & Conclusion



## Proposed timelize 

Upcoming steps in milestone 3:
- optimization of the classsifier (increase the number of features)
- analyse differences between professions
- analyse a possible change from 2015 to 2020
- analyse the differences within/between nationality, culture/tradition, and/or education


## Organization with the team

- Coralie Grobel: 1, 3
- Assia Ouanaya: 2, 4
- Clement Chaffard: 1
- Fannie Kerff: 3, 4


## Questions for Tas (optional)

