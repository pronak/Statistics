---
title: "Chi-Square Analysis"
author: "pronak@business.rutgers.edu"
date: "3/26/2022"
output: html_document
---
### Chi Square

**Chi-Square** Measures how far the observed counts from the sample are from the expected counts. It is represented as $\chi^2$. It is used when data has categorical/qualitative variables. In R, categorical values are represented as factor. 

**Formula**

$$
\chi^2 = \sum_{}\frac{(Observed-Expected)^2}{Expected}
$$

Since the difference is squared, $\chi^2$ is __never__ negative. 

### Goodness of Fit Test
Test to see if a sample distribution fits a known or expected distribution. It involved only one population we have taken the random sample from and we are comparing the sample distribution to the known distribution. 

__Note__ The goodness-of-fit test expands the one-proportion z-test. The one-proportion z-test is used if the outcome has only two categories. The goodness-of-fit test is used if you have two or more categories.

$H_0$ = Sample distribution fits the expected population distribution. 
$H_1$ = Sample distribution __does not__ fit the expected population distribution. 

Degrees of Freedom = $D.F$ = $(number of categories - 1)$

### Test of Independence
Test to see if two variables/categories from a random sample are independent. It is a way of determining whether two categorical variables are associated with one another in the population. If you are curious if race and smoking are related, you would use this test. 

$H_0$ = Two categories are independent
$H_1$ = Two categories are dependent 

Degrees of Freedom = $D.F$ = $(number of categories in First Variable - 1)$ *  $(number of categories in Second Variable - 1)$

___Note__ In the test of independence, two variables are observed for each observational unit. In the goodness-of-fit test there is only one observed variable.


### Test of Homogeneity
Test to see if two unknown population have the same distribution as each other. It is a way of determining whether two or more sub-groups of a population share the same distribution of a single categorical variable. As an example, if you are curious if people of different races have the same proportion of smokers to non-smokers, you would preform this test.

__Note__ The test of homogeneity expands on the two-proportion z-test. The two proportion z-test is used when the response variable has only two categories as outcomes and we are comparing two groups. The homogeneity test is used if the response variable has several outcome categories, and we wish to compare two or more groups.


$H_0$ = Two population have the same distribution
$H_1$ = Two population have different distribution

Degrees of Freedom = $D.F$ = $(number of categories in First Variable - 1)$ *  $(number of categories in Second Variable - 1)$


### FAQ
Is the test of homogeneity and independence the same? 
They are almost same!! The difference is a matter of design. In the test of independence, observational units are collected at random from a population and two categorical variables are observed for each unit. In the test of homogeneity, the data are collected by randomly sampling from each sub-group separately. (Say, 100 blacks, 100 whites, 100 American Indians, and so on.) The null hypothesis is that each sub-group shares the same distribution of another categorical variable. (Say, "chain smoker", "occasional smoker", "non-smoker".) The difference between these two tests is subtle yet important.

| __$\chi^2$ Test__ 	| __Sample__ 	| __Research Question__ 	|
|---	|---	|---	|
| __Test of Homogeneity__ 	| Single variable measured on several samples 	| Are the groups homogeneous? As in do they have the same distribution 	|
| __Test of Independence__ 	| Two variables measured on one sample 	| Are the two categorical variables independent?  	|


### R Exercise


```{r}

ship <- as.table(rbind(c(202, 118, 178,215), c(123, 167, 528,698)))
dimnames(ship) <- list(survived = c("Yes", "No"),class = c("First","Second", "Third","Crew"))
ship
```
