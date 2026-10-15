# Portfolio Project Biostatistics


Aim of the repo is to review statistics and R skills by applying them to public domain datasets.

The idea is not to produce original results, but rather choose questions to which the answers are known and show the correct application of statistical analyses. 
That makes refining the analysis in some sense easier, but of course poses the risk of methodological "false-positive" errors.

As a first "dipping of toes" I investigated the effect of smoking on other health metrics like blood pressure. 

I use the NHANES dataset as it is readily available and contains real-life data that is used by researchers. 

More info about the data set can be found here: https://cran.r-project.org/web/packages/nhanesA/vignettes/Introducing_nhanesA.html

---

## Analysis steps
1. [cleaning data, overview of data](#cleaning-and-overview-of-the-data)
2. definition variables of interest (one or two health metrics)
3. definition of method to control for confounding
3. selection of confounding variables
4. baseline (i.e. unadjusted) comparison of smoker and non-smoker group
5. adjusted comparison of the two groups (regressions, Stratification?)
6. model diagnosis
7. sensitivity analysis 
8. interpretation

---

## Statistical Considerations: 
Investigating the effect of smoking on other health metrics comes with numerous issues, especially in an obeerservation study. 
The biggest problem (as in all observational studies) are confounding variables. 
Smokers and non-smokers are not drawn at random from a population, therefore the two groups are not directly comparable. 
A preliminary analysis shows that without controlling for confounding variables the smoking group appears to be healthier in some health metrics. 

Comparing the two groups (i.e. without survival analysis that I plan to do later), reverse causality is another big issue. 

---

## Literature:
I use *Introduction to Randomized Controlled Clinical Trials*, by John M.S. Matthews to guide me and 
*All of Statistics - A Concise Course in Statistical Inference* by Larry Wasserman as a reference book for the underlying mathematics. 

---

## Cleaning and Overview of the Data
Although the focus will be on the statistical investigation I will briefly outline the steps to import and clean the data. 
At the very least, to stay aware of any possible biases introduced in the cleaning process.

Importing the dataset is conveniently done with the "nhanesA" library that also provides useful functions to explore the available data 
and download subsets of the dataset.

The dataset consists of five different surveys (DEMOGRAPHICS, DIETARY, EXAMINATION, LABORATORY, QUESTIONNAIRE) and 12 two-year cohorts that always start in uneven years.
Using `View(nhanesTables("EXAM", 2005))` we can get an overview of the available tables for each survey in any particular year. 

In the "Questionnaire" (abbreviated as "Q") survey we find three tables for "Cigarette Use", "Recent Tobacco Use" and "Household Smokers".
The first table holds data for about 38 questions (depending on the cohort) that the participants were asked, including on the number of cigarettes smoked, when they quit smoking or which brand they are/were smoking. 

Using the "Examination" (abbr. "EXAM") we can obtain data on blood pressure, body measures or oral health. 

Age and gender of the participants can be obtained in the "Demographics" ("DEMO") survey. 




TODO: Check if linked mortality data is useful for selected cohort! 


---

## Currently working on:
- data cleaning (-> introduction of bias during cleaning?)
- regression model
- propensity score
- stratification

---

## Future ToDos:
- survival model (Kaplan-Meier); use "linked mortaliy dataset"



