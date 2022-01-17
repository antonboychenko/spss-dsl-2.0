# Introduction to Inferential Statistics

## Table of Contents

- [Cross tabulation and Chi-Squared tests](#crosstab)
- [Significance testing	](#sig)
- [T-tests](#ttest)
- [ANOVA](#anova)

## Getting started

We will be using the same dataset we have used in previous sessions, the ESS ([European Social Survey](https://www.europeansocialsurvey.org)) data that is called **ESS5GB.sav**. 

Open this file now, either by double clicking on the file in finder (Mac) or Windows Explorer, or using *file -> open -> data* in SPSS. 

Follow the example steps provided, then have a go at the challenges for each section. 

## Cross tabulation and Chi-Squared tests <a name = "crosstab"></a>

The Chi-squared test looks at associations between two categorical variables. We use it when we are testing frequency data, the number of times something occurs. We review these associations with cross tabulation, that displays these associations in a grid. 

For example, in the table below we look at if smokers are ill or not. We can see that out of 56 smokers 39 are ill, compared to 18 out of 78 non-smokers who are not ill. The chi-square tests lets us assess if this apparent association is significant.  

            | Smoker       | Non-Smoker
:----------:|:------------:|:------------:
Ill         |  39          |  18
Not ill     |  17          |  60
Total       |  56          |  78


To run a chi-square in SPSS we need to go to the crosstabs menu. See the image below how to find crosstabs: 

![Menu to run cross tab](img/crosstabs_1.PNG)

This should bring up the cross tabulation screen. From here we can add our variables to test on, in this case gender and victim of assault/burglary. To run a Chi-square test we need to go into the statistics tab, and select chi-square.

It is also important to get the *expected counts*. Go to cells -> tick expected counts. 

We can also select *display clustered bar charts*, which runs a nice visualisation on our cross tabulation. 
See the image below of what we have done:

![Cross tab and chi-square options](img/crosstabs_2.PNG)

Once you run the cross tabulation you will get several tables and a graph that will pop up in your output viewer. Of most interest are the *Crosstabulation* and the *Chi-Square Tests* tables, shown below:

![](img/chi_square.PNG)

The cross tabulation gives us a visual summary of our data. We can see that more females than males responded to both yes and no to the burglary/assault variable, and we had more female responses overall. 

The expected counts are all greater than 5, which means we don't have any problems with our data. This is an assumption of the chi-square that has to be met. 

> If you don't have expected counts in your input, did you select cells -> expected counts from the crosstabs screen? 

The chi-square tells us if the association is significant between our variables. The green box shows what we are interested in, which is the *Pearson Chi-Square*. In this case the p value (*Asymptotic Significance (2-sided)*) is greater than 0.05, which means our test is not significant and no association between gender and victim of burglary/assault was found. 

### Challenge 1: Run a Chi-Square test

We are interested in testing if subjects who have, and have not, been burgled or assaulted in the last five years have a different attitude in how good a job the police are doing. 

Run a Chi-Square test using the `brghmef` (*how often worry about your home being burgled*) and `crmvct` (*respondent or household member victim of burglary/assault*) variables. 

1. Open the crosstabs page and add `brghmef` as rows and `crmvct` as columns
2. Tick the *display clustered bar charts* option
3. Select the chi-square option
4. Add observed and expected counts and row and column percentages
5. Run the test - how would you interpret the result? 

## Notes on significance testing <a name = "sig"></a>

You will have noticed that with the chi-squared test we just performed we were able to determine if there was, or was not, an association between two variables. This is known as significance testing. 

In order to test significance we must first have a hypothesis. This is the process of taking a theory, and turning it into something we can do a specific test or make a prediction on. This is known as hypothesis testing. 

There are several general steps to hypothesis testing:

1) State your hypothesis  
2) Collect data  
3) Perform statistical test or tests  
4) Decide to reject or fail to reject the null hypothesis  
5) Present/report findings

When stating a hypothesis we always have two, a null (H<sub>0</sub>) and alternate hypothesis (H<sub>a</sub>). The alternate hypothesis is what you predict will happen, the null hypothesis is what you predict will not happen. 

>For example, if I wanted to test out if it rained more days in the UK than Australia, based on your knowledge of UK and Australian weather you might form the following hypothesis:

>- *H<sub>a</sub>*: The UK has, on average, more rainfall than Australia
- *H<sub>0</sub>*: There will be no difference, on average, in rainfall between the UK and Australia

In order to find out if we can reject or fail to reject the null hypothesis, we run statistical tests. We use the p value to determine this. The cut off for rejecting the null hypothesis is 0.05, so if your p-value is less than or equal to 0.05 you can reject your null hypothesis. 

The idea with the 0.05 cut off is that there is a less than 5% chance that the results you are seeing are a result of chance. 

>If we did a statistical test on our rainfall example and found a p-value of 0.01 we could reject the null hypothesis as our test is below the 0.05 cutoff.

### Challenge 2: Make a hypothesis

As we already have the data we will make a hypothesis based on the variables we have. The ESS dataset we are using is survey data with various issues such as politics and policing. 

We will use the below to variables to make a hypothesis:

- Respondent or household member victim of burglary/assault last 5 years (crmvct) *(categorical/nominal)*
- How successful police are at preventing crimes in country (plcpvcr) *(ordinal)*

Using these variables, what do predict the difference, on average, will be between victims and non victims of burglary/assault and their attitudes to how successful the police are at preventing crimes?

Your hypothesis:

- My null hypothesis (H<sub>0</sub>) is...
- My alternate hypothesis (H<sub>a</sub>) is...

We will take your null and alternate hypothesis to the next challenge and test it out! 

## T-Tests <a name = "ttest"></a>

In the last challenge we made a hypothesis and null hypothesis, we will test this out in the challenge. First, we need to learn how to run a t-test in SPSS! 

T-tests are for testing if the average (mean) difference between two variables is significant. There are two main options for running t-tests, the independent or paired-samples t-test. The independent t-test is used to determine if two means collected from independent differ significantly. the paired-samples t-test is used to determine if two means from the same sample differ significantly. 

The ESS dataset we are using is set up in a way that suits the independent samples t-test. If we had collected data from the same recipients over time (repeated measures), then our data would more suit the paired-samples t-test. 

To run an independent samples t-test in SPSS we select the compare means menu from analyze, then find independent samples t-test.

![](img/t_test_1.PNG)

The dialog box for  independent samples t-test should appear. The test variable is the variable we want to compare the two means on, we have used `Police doing good or bad job`. The grouping variable is a nominal (categorical) variable, ideally with two groups (or you select two groups), we have used `gender`. SPSS needs you to *define the groups* before you can run the test; for gender they are labeled 1 for male and 2 for gender. We can find this information in the variable view from the variables value labels. See the images below on how to do this:

![](img/t_test_2.PNG)

![](img/t_test_3.PNG)

Once you've defined the groups you can run your t-test! You'll get an output with group statistics, which is the descriptive statistics, such as mean and standard deviation for your groups, and the t-test output. The green box in the image below indicates the part of the t-test output we are most interested in. In this case, the *Sig. (2-tailed)* is our p-value, which is showing 0.000. This tells us there is a significant difference between someones perception of how good a job the police are doing depending on their gender. 

![](img/t_test_4.PNG)

As a bonus, it can be helpful to visualise the mean values with error bars. We first start by making a bar chart. 

![](img/error_bar_1.PNG)

Once in the bar chart menu, we can add error bars using options. See the image below:

![](img/error_bar_2.PNG)

When you select OK, you should get a nice bar chart with error bars. 

For more information on t-tests, have a look at the [discovering statistics webpage](https://www.discoveringstatistics.com/statistics-hell-p/porus-comparing-means/comparing-two-means/). 

### Challenge 3: Run a t-test (based on your hypothesis from challenge 2)

Using the below variables we used to define our hypothesis, run an independent samples t-test in SPSS:

- Respondent or household member victim of burglary/assault last 5 years (crmvct) *(categorical/nominal)*
- How successful police are at preventing crimes in country (plcpvcr) *(ordinal)*

1) Make a bar plot of your two variables, with error bars  
2) Run an independent samples t-test  
3) Review your output. Was the result significant, and did it match your expectations and hypothesis?  

## ANOVA <a name = "anova"></a>

What does ANOVA mean and what does it do?

As with T-test what are the options, what do they mean, and links to how to decide.

How to run with expected outcome

### Challenge 4: Run an ANOVA

We want to expand our previous hypothesis about how successful the police are at preventing crimes. We've seen there is a significant difference between respondents who have been victims of assault/burglary. 

Which sentence: 25 year old male, house burglary, second time (stcbg2t). 

Just interested in those that have been victim of assault/burglary -> filter them -> do ANOVA with which sentence and how successful are the police

