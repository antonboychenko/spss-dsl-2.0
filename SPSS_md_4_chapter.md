# DSL SPSS 

## Part IV: Regression analysis

Welcome to the fourth SPSS workshop from the Digital Skills Lab at LSE.

In the last session, you have learned about inferential statistics. Now, it's time to take a step further and explore one of the most widely used data analytics tools **regressions**. Regressions allow you to (1) make inferences about associations between variables, (2) predict variables' values. By the end of this session, you will learn how to:

- run correlations
- build scatter plots
- build simple and multiple linear regressions
- make predictions with linear regressions
- use categorical variables in regressions
- build logistic regression models

We hope you will enjoy this workshop!

## Table of Contents

- [Introduction to regression](#intro)
- [Simple linear regression](#simple)
- [Multiple linear regression](#multiple)
- [Predictions with regression]()
- [Dummy variables]()
- [Logistic regression]()

## Getting started

We will be using a new dataset today. It's a dataset containing information about different cars sourced from ([Kaggle](https://www.kaggle.com/hellbuoy/car-price-prediction)). The data file that you will be using today is called **cars.sav**. 

Open this file now, either by double-clicking on the file in Finder (Mac) or Windows Explorer, or using *file -> open -> data* in SPSS. 

Follow the example steps provided, then have a go at the challenges for each section. 

## Introduction to regression <a name = "intro"></a>

Linear regressions are arguably the most popular data analysis tool in the world. People like it and use it a lot when they wish to understand relationships between variables. The idea behind **any** regression task is to predict a continuous numerical variable. In other words, we wish to understand an association between one or more **predictors** (other names: independent variables, features) and a continuous **response variable** (other names: dependent variable, target variable). 

Let's consider an example. You want to earn a lot of money and you are trying to understand what qualities you need to possess to achieve that. Your income is a continuous and numeric variable. Ideal! It means that we can run a regression model and understand what predicts people's salaries. It can be their education, their gender, number of Facebook friends, and so on.

💡 Stop for a second and think what are the predictors and what is the response variable in this example. 

In our today's session, we are discussing **linear** regressions. They are called linear because they spot linear relationships between variables. Without going into much maths linear regressions aim to build a linear function that can explain a relationship between a variable and a response variable. Hence it will work well if data looks like this:

![linear relationship](./img/linear_reg.png)

and will perform poorly if data looks like this:

![non-linear relationship](./img/non_linear_reg.png)

If you wish to understand regression in more detail we would recommend this [youtube video](https://www.youtube.com/watch?v=nk2CQITm_eo). It explains the algorithm and a bit of maths behind linear regression models. 

## Simple linear regression <a name = "simple"></a>

We will start our journey from the most basic model called **simple linear regression**. Simple linear regression is a kind of linear regression that uses only one predictor. In our today's session, we will be working with a dataset that contains information about different cars. We will be trying to understand what characteristics of a car predict its **price** in the best way. 

As we are building a simple linear regression we need to select **one** predictor (independent variable) that we will use to predict car prices. For now, we will be using only continuous variables to predict the car price. To understand which one to select for our model we will do two important things:

1. Calculate correlation coefficients between variables and the car price  

You can do it by going to `SPSS -> Analyze –> Correlate -> Bivariate`. For all variables that you put into the **Variables** box, SPSS will compute pairwise correlations. The output of this will be a symmetric correlation matrix. As we do not need to see it fully we can tick the **Show only the lower triangle** box and click **OK**. Once you click **OK** you will see a table. For each pair of variables, it shows (1) the correlation coefficient, (2) the significance level, (3) the number of observations used to calculate the coefficient. Also, SPSS will mark those coefficients that are significant with asterisks. One asterisk means the correlation is significant at the **0.05 level**, two asterisks that it is significant at the **0.01 level**.

2. Plot variables against car prices in a scatter plot

You can create scatter plots in two ways: 
 - `SPSS -> Graphs –> Legacy Dialogs -> Scatter/Dot... -> Simple Scatter`. After you see a new window you can put the needed X and Y variables. However, in the case of building regressions, it might be tedious to build those scatter plots one by one for each variable. That's why we suggest another method below.
 - `SPSS -> Graphs –> Regression Variable Plots`. In the new window, we would recommend putting a dependent variable into the **Vertical-Axis Variables** and potential predictors into the **Horizontal-Axis Variables**. Once you click **OK** it will show you scatter plots of all your variables plotted against your dependent variable. 

---

### Challenge 1: Choosing a predictor

- Find pair-wise correlations of all continuous variables in this dataset. What variables are associated with the car price?
- Plot all continuous variables against the car price. What variables are **linearly** associated with the car prices? Discuss it in the group. 

---

After completing the challenge you might notice that several variables are associated with the car price. However, some of the associations will not work well with linear regression. Take a look at the `highwaympg` variable (*Mileage on highway*) plotted against car price. 

![quadratic relationship](./img/quadratic.png)

You will notice that the relationship is **not** linear. It's somewhat quadratic. Hence, building a linear regression model with *Mileage on highway* would be a bad idea as we assume linearity in this model. 

💡 Can you spot a variable that is linearly associated with the car price?

Once we decided on the predictor that will be used we can finally build our model. To do that go to `SPSS -> Analyze –> Regression -> Linear...`. In the new window you can put your dependent variable in the **Dependent:** box and all predictors into the **Independent(s)** one. The default settings will do the job for now, but you can always experiment with your model and the output. Once you click **OK** you will see several tables. **Model Summary** contains some quality metrics of the model including R<sup>2</sup>. **ANOVA** will show you the RSS and F-statistics. **Coefficients** shows the coefficients of the model including the intercept (Constant). 

---

### Challenge 2: Your first model

After examining the scatter plots that you have built in the last challenge you might have noticed that `enginesize` (*Size of engine*) is linearly associated with the car price. Go ahead and build a simple linear regression model using `enginesize` as a predictor. What do you find? 

---

We will not go into much detail here as it is beyond the scope of this course, but here is a brief explanation of some of the numbers in those tables:

**R<sup>2</sup>** - the share of variance of the dependent variable "explained" by the independent variables, i.e., to what extent the chosen predictors explain the changes in the dependent variable.
**Constant** (intercept) - the expected value of the dependent variable if all predictors are equal to zero.
**Coefficients** show the change of a dependent variable if the independent variable changes by 1 unit. In our example, the unstandardized coefficient for the engine size will show the car price will increase on average by 167.698, if you increase the size of the car engine by 1 unit.

## Multiple linear regression <a name = "multiple"></a>

Multiple linear regression is a type of linear regression where we use more than one predictor. In SPSS it is done in a very similar manner by simply putting more variables into the **Independent(s)** box in the regression window. However, you might wish to change one thing there and run collinearity diagnostics. Multicollinearity is a phenomenon of predictors' associations in-between each other. 

To add collinearity diagnostics go to `SPSS -> Analyze –> Regression -> Linear...`, add all the variables that you want to the **Independent(s)** box. Then, click on **Statistics** and tick the box for **Collinearity diagnostics**. Once you click **Continue** and then **OK** you will see that now in the *Coefficients* table there are two new columns: *Tolerance* and *VIF*. The rule of thumb here is that if all the values in the VIF column are below 10, you are not experiencing multicollinearity. If you do, we would recommend running correlations between all the variables to find associated ones. We can also recommend to explore [this video](https://www.youtube.com/watch?v=IRVd4m8ulHs&t=210s) on how to read collinearity diagnostics in SPSS in more detail 

---

### Challenge 3: More predictors

Now it's time for more predictors! Using the scatter plots that you have built find at least 2 more variables that are associated with the car price. Add them to the model and explore the results. 

---

When interpreting coefficients for the multiple linear regressions do remember that a coefficient shows a change of a dependent variable if the independent variable changes by 1 unit *holding all the other independent variables constant*. The last part is very important as we must see these coefficients as being independent of others. 