# DSL SPSS 

## Part I: Foundations of data management 

Hello and welcome to the first SPSS workshop from the Digital Skills Lab at LSE. It is the first out of four workshops that will enable you to gain fundamental skills of working with SPSS. 
This session is dedicated to the fundamentals of data management. By the end of this session, you will learn how to:

- open existing SPSS datasets
- work with SPSS interface
- import data from CSV and Excel files to SPSS
- process imported datasets
- recode variables
- compute new variables

It may sound like a lot, but it will take less than it seems. Let’s go through them one by one. 

### Opening SPSS datasets

There is a high chance that you will be using a dataset that is already saved in the SPSS format, so you do not need to do any preprocessing and can use the file straight away. SPSS uses `.sav` extensions, and, for instance, the file that we will be using for our workshops is called **ESS5GB.sav**. This comes from the ESS ([European Social Survey](https://www.europeansocialsurvey.org), which is used in a lot of research (and may be useful in yours). We simply downloaded these data from the ESS site in the SPSS format. 

You can use this file now. Simply double-click the **ESS5GB.sav** and wait till it loads (it might take some time). Once it is open you will see two windows opened:

1. **The data editor**
This window is for you to access your data, manipulate it and look through it.
2. **The output**
This is an output window. SPSS warnings, messages and (what's important) all the results of your operations will be shown in this window.

We will now explore the first one a little more thoroughly. The output window will be most relevant once we start conducting some analysis. 

### SPSS interface

Let's explore the interface of the data editor window. You should see something similar to this:

![data editor](./img/data_edit.png)

You can see two buttons at the bottom of this window that say: "Data View" and "Variable View". Go ahead and click on the first one. 

### Data View

It opens a data view of your dataset. Here you can see and manually change all the observations. You can think of that as an Excel spreadsheet, where each rows represents one observation (for instance, a person you surveyed) and each column is an variable that stores some information about those observations (for instance, age of your repsondents or their salary). 

### Variable View

Let's now click on "Variable View" at the bottom of this window and explore it. This section stores information on the variables that you have in your dataset. Each variable has several characteristics. We provided comments on some of the most used ones. You will use this information for a challenge below.

1. **Name** - the name of the variable 
> It is usually a code short name for a variable. An explanation of what it stores is usually in **Label**.
2. **Type** - a data type of the variable. The way it stores information (e.g., numbers, texts, dates, etc.)
3. **Width** - the lenght of a value displayed (e.g., a number of digits, a sting length)
4. **Decimals** - the number of decimals used after a decimal point
5. **Label** - a label that describes what the variable stores
> This is where you would store an elaborate description of what this variable contains. 
6. **Values** - all possible values that this variable can take
> This parameter is used for categorical variables. If you double-click the values box for a variable you will see a button with 3 dots:
![values button](./img/values.png)  
> After clicking on this button you will see a new window. In this window you can create new values for a categorical variable. For instance, you can create a variable that records whether a person is left or rigt-handed. You would create a value 1 and label it as "right-handed" and value 2 and label it as "left-handed". To do that you will need to create a value and a corresponding value in the window that opened and click "Add".
7. **Missing** - the codes for missing values (for instance, people can code 997 as a rejection to answer and 999 no answer.)
9. **Columns** - the width of each column in the Data View window
10. **Allign** - the allignemnt of cells' content
11. **Measure** - a type of measurment that variable uses, can be Scale, Ordinal and Nominal 
> This is one of the key parameters of a variable that defines how SPSS will treat it. Failing to correctly identify a type of measurment can result in wrong calculations. There are three types of varibales used in SPSS:
> 1. **Scale** Scale varibales or so called interval variables imply that there is an interval and a variable can take any value in this interval. For instance, temperature or age. You can be 30 years old, you can be 30,5 years old, but also it is definetely possible that you are 30.003 years old. Same applies to temperature, height, years of education and so on. 
> 2. **Ordinal** An ordidinal variable implies creating seprate categories that are somehow **ordered/ranked**. For instance, if you have a variable that stores people's highest achieved level of education, where 1 is High School, 2 is a Bachelor's degree and 3 is a Master's degree. They are all ranked: each one is higher than the next one. 
> 3. **Nominal** A nominal variable implies creating categories that are **NOT** in any way **ranked**. For instance, right and left handed people are two categories. These categories do not have any order/hiearchy. 
12. **Role** - the role of the variable in your analysis

---

### Challenge 1: Creating variables

Now it's time for your first challenge! Go to the **Variable View** and create 3 variables (to do it simply scroll down all the variables and click on the first empty row in **Variable View**):

1. **Name**: height, **Label**: Person's height, **Values**: None (as it's a scale variable), **Measure**: Scale (To change the Measure, simply click on the corresponding cell)
2. **Name**: pln_class, **Label**: Plane ticket class, **Values**: 1-First, 2-Second, 3-Third, **Measure**: Ordinal
3. **Name**: fav_col, **Label**: Favorite colour, **Values**: 1-Red, 2-Green, 3-Blue, **Measure**: Nominal

---

### Importing data from CSV and Excel

Now when you have a basic understanding of how SPSS looks and works, we can take one step further and explore how to import spreadsheets into SPSS. During the years of teaching SPSS we encountered a question of how to import `.csv` or `.xlsx` files into SPSS. Indeed, it's a very useful skill, becuase a lot of datasets are stored as Excel of CSV (Comma-Separated Values) files. To do that go to `SPSS -> File –> Import Data -> ...`

1. **Excel**

Let's consider our example. Go to `SPSS -> File –> Import Data -> Excel` and let's import a file called `dem_data.xlsx`. You should see this window after selecting this file and clicking "Open":

![read excel](./img/read_excel.png)

You can see that you can select a sheet from which to read the data and then we have a number of parameters that are quite straightforward. Let's click "OK" once we are satisfied with our settings. Now go to the variable view and look at the **Measure** settings SPSS used. Are they correct? 


2. **CSV**

Now let's take the same file but saved as a CSV file. Go to `SPSS -> File –> Import Data -> CSV` and let's import a file called `dem_data.csv`. Now after clicking "Open" we will see a different window:

![read csv](./img/read_csv.png)

When importing CSV one should be careful, because as **columns are separated by a special symbol** (usually a comma). You can see in the preview of our data that they are indeed seprated by commas, and we select it in our `Delimiter between values` parameter. For your own research also pay attention to how decimal points are marked (commas or periods in `Decimal symbol` parameter).Let's click "OK" once we are satisfied with our settings. Are the **Measure** settings here are correct again?

3. **You can use other dataset types to import to SPSS using the same sequence of steps again**.

---

### Challenge 2: Correcting imported datasets

As your second task:

1. Import the `dem_data` in either Excel of CSV format
2. Check if the **Measure** settings are correct
3. Add labels to your variables, namely  "Respondent's salary", "Age of a respondent",  and "Gender" to corresponding variables
4. For the gender variables add values: 1 - Male, 2 - Female, 3 - Other (specified)


---


### Recoding variables

Now as we learned how to open datasets and import them from other file formats we can finally work with data. The first thing to do with data is preprocessing, so in this section we will take one step into that and learn how to **recode** variables. There are many cases when it may be useful. For instance you want to group your respondents into age groups. You want to have those that are younger than 30, from 31 to 50 and 50 and older. To do that, we can use SPSS functionality. 

Let's use our **ESS5GB.sav** file again (you can close the imported ones). Let's take the following path `SPSS -> Transform –> Recode into Different Variables`. Recoding into Different Variables will create new recoded variables compared to Recode into Same Variables that will **change the exisiting ones**. We choose the former in order to **avoid changing the original data**. Once you clicked on Recode into Different Variables you will see the follwing window:

![recode window](./img/recoding_window.png)

> **Lifehack not to get lost in variables**
> You can see that there is an overwhelming number of variables in this dataset. No to get lost in them right-click in the area of variables (like in the picture below) and select `Display Variable Names` and `Sort Alpahbetically`. This way you will have short names ordered in a nice order.

![lifehack](./img/lifehack.png)

We will be working with a variable called `agea` (Age of respondent...). Find and click on this variable (it will be highlighted in blue) and click on the blue arrow in the middle of the window so it moves to the box on the right like this:

![moved variable](./img/moved_var.png)

![age group 1](./img/age_group_1.png)

![age group 2](./img/age_group_2.png)

![age group 3](./img/age_group_3.png)

![output window](./img/output.png)