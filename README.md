# homework 4 - Functions II

## Instructions

1.  Use Aimes housing prices data set from the `/data` folder. Variable descriptions can be found [here](https://www.kaggle.com/c/house-prices-advanced-regression-techniques/data)

2.  Your final document should be an `.ipynb` file. Include any other scripts you used to create the report in your HW submission.

In answering each of the questions for the assignment please include:

-   the question as a header in your Jupyter Notebook
-   the raw code that you used to generate any tables
-   the first and last five rows of the resulting data tables you're submitting as your answer

### Assignment items `[100 pts]`

1.  `[15 pts]` **Import the data as a pd.DataFrame object. Use one or more functions from the `pandas` library to split the data into three unique datasets. The first should include columns that are factors only (i.e. - categorical data), the second should include columns that are numeric only, and the third should include columns with logical values only.**

*Hint: There is code we used in the HW last week that can be leveraged to split the dataset based on data types. There is also code in the /General Course Materials/Useful python functions.py file that can do this.*

*Remember that data frames can be thought of as a collection of lists/arrays/pd.Series objects saved in different columns. So think of each column in your data-frame as a pd.Series and split based on column type. Note that pandas has a dtype called "object", which it uses when it cannot determine the datatype. Generally, pandas will save string variables as object data types. For this question, treat the object as a categorical factor.*

2.  `[15 pts]` **Using the second dataset from question #1, for each numeric variable use the apply function to return the mean, median and standard deviation (SD) of all numeric variables.**

3.  `[15 pts]`**Using the second dataset from question #1, create a new dataset that only includes the variable indicating sales price ("SalePrice"). Search for a categorical variable which has between 2-4 categories in the full dataset that you think may be related to the sales price of houses. Give the mean, median and SD for SalePrice based on the different groups of the categorical variables. Does the average price seem to vary by the different levels of the categorical factor you chose?**

4.  `[15 pts]` **First, regress "SalePrice" on "LotArea", "OverallQual", "OverallCond" with the statsmodels library. Use the syntax below to replicate the output shown. Second, write a for loop that loops through each level of the categorical factor you chose in Q3, where each iteration of the for loop subsets your data for one group of the categorical variable at a time, and then fits the same regression model specified above k times, where k refers to the number of unique categories. On each iteration of your for loop, store the model.summary() information as a new element in a list object. Once your for loop is done running, print the list. There should be k regressions which you estimated. Does the effect of LotArea on SalePrice vary within the different levels of the categorical factor you chose? What is another, more common way to answer a question like this (i.e., a question about moderation or effect heterogeneity)?** *Hint: Compare the slope estimates and also account for the standard error.*

    ![](images/paste-37B25969.png)

5.  `[15 pts]` **Using the first dataset from question #1, for each categorical variable use a for loop to print a frequency and relative frequency for every variable. To make your output readable, for each variable you should print the following in this order, placing the variable name where you see blanks below.**

    -   "Frequency table for \_\_\_\_\_\_ ============"

    -   Display the frequency table

    -   Skip a line, and print "Relative frequency table for \_\_\_\_\_\_ ============"

    -   Skip two lines before printing the data for the next categorical variable

        This is what your output should look like for the MSZoning variable.

    For example, for the MSZonig variable your output should look like this:

    ![](images/paste-FC5B1912.png)

6.  `[10 pts]` **Do the same thing as number 5, but with a while loop this time.**

7.  `[15 pts]` **This question does not use the dataset used in the previous HW questions. Give a function that accepts unlimited arguments, checks and counts how many data types are in those arguments. Finally return the total in a list. This list should count the following object types, in this order:**

        [int, str, bool, list, tuple, dictionary]

    Several examples are below. Your function should return the list associated with each input.

        count_datatypes(1, 45, "Hi", False) ➞ [2, 1, 1, 0, 0, 0]

        count_datatypes([10, 20], ("t", "Ok"), 2, 3, 1) ➞ [3, 0, 0, 1, 1, 0]

        count_datatypes("Hello", "Bye", True, True, False, {"1": "One", "2": "Two"}, [1, 3], {"Brayan": 18}, 25, 23) ➞ [2, 2, 3, 1, 0, 2]

        count_datatypes(4, 21, ("ES", "EN"), ("a", "b"), False, [1, 2, 3], [4, 5, 6]) ➞ [2, 0, 1, 2, 2, 0]
