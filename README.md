java c
MATH6166/6173 Statistical Computing for Data Scientists/Statistical Computing — Coursework 1 Example 
Question
Information To help you with the completion of Coursework 1, this file contains an example Coursework question.  On the Blackboard page you can find an example answer template file, example Markdown solution file, and example html output file.
Example Question 1: Linear Regression for Advertising Data [24 marks] A researcher is interested in modelling the relationship between the amount of money a company spends on advertising and the corresponding number of sales.  The researcher has access to a data set that describe the results of a repeated experiment, in which a certain amount of money is spent on Youtube advertising a given product, and the number of sales of the product for a given amount of money spent on advertising are recorded.  The data set is stored in the data file youtube-ad-sales.txt, which has two variables:
•  sales: the number of sales of the product,
• youtube: the amount of money spent on advertising the product on Youtube (in thousands of dollars).
(a)  [3 marks] Import the data set from the youtube-ad-sales .txt file into the R workspace in a variable named my_data1.  What are the dimensions of the object my_data1?   Store this in a variable called dim_data.  Compute the mean and variance of the sales variable in my_data1, and store them in variables called mean_sales and var_sales, respectively.
(b)  [2 marks] How many of the observations in my_data1 have a sales value that is larger than 20?  Store this number in a variable num_obs_sales_gt20.  How many of the observations in my_data1 have a sales value that is larger than 20 and a youtube value less than 200?  Store this number in a variable num_obs_sales_gt20_youtube_lt200.To model the relationship between sales and advertising spending, the researcher decides to fit the following linear regression. Denoting n for the number of observations, Y1, . . . , Yn for the values of sales and x1 , . . . , xn for the values of Youtube advertising spending, the researcher fits the modelYi  = β0 + β1 xi + εi ,        i = 1, . . . , n,                                                     (1)
where εi , i = 1, . . . , n are independent identically distributed noise terms with mean zero. In matrix notation, this is equivalent toY = Xβ + ε ,                                                                        (2)
where

For model (2), the least squares estimator ˆβ for the regression coefficients β is given by:ˆβ = (X TX ) −1 XTY .                                                                  (3)
(c)  [2 marks] Using the lm command in R, fit the model (2), storing the result in the variable data_model1. What are the estimated coefficients β0  and β1 ?
(d)  [3 marks] Using the val代 写MATH6166/6173 Statistical Computing for Data Scientists/Statistical Computing — Coursework 1 Example QuestionR
代做程序编程语言ues stored in the data_model1 variable computed in part (c) or otherwise, plot the original data in a scatter plot format, and add a line to this plot of the fitted values of the estimated model, i.e. add the line
ˆY = Xˆβ 
to your plot. Include a legend to distinguish between the observed data and the fitted values.
The researcher has access to two additional explanatory variables:
•  facebook - the amount of money spent on advertising the product on Facebook  (in thousands of dollars),
• newspaper - the amount of money spent on advertising the product in the newspaper (in thousands of dollars).
For the general case where there are p explanatory variables, the terms in Equation (2) can be written as 

where xi  = [x1(i), . . . , xn(i)] is the vector of the i-th explanatory variable.
(e)  [5 marks] Without using the lm function, write a function called estimate_lm, that takes as input a data frame. of dimension n × (p + 1), whose first p columns represent the n observations of the p explanatory variables x1 , . . . , xp , and whose last column is the response variable Y .   The function should compute the least squares estimator of the form. given in Equation (3), where here X should be a general n × (p + 1) dimensional matrix.  The estimate_lm function should have the following features:
Argument:
1.  data_frame. a data frame. with n rows and p + 1 columns.  The first p columns represent the p explanatory variables x1 , . . . , xp , and the last column is the response variable Y.
Computation:
The estimate_lm function should compute the p + 1-dimensional least squares estimator given in Equation (3).
Return:
1. beta_hat: a numeric (p + 1)-dimensional vector containing the least squares estimator ˆβ .
(f)  [2 marks] Import the data set from the all-ad-sales .txt file into the R workspace in a variable named my_data2.  Using the estimate_lm function you wrote in part (e), compute the least squares estimator ˆβ for the model:
(a) with Youtube advertising as the only explanatory variable (i.e. using my_data1),
(b) with all 3 explanatory variables in the data file all-ad-sales .txt (i.e. using my_data2). Store these variables with variable names beta_youtube, and beta_all, respectively.
(g)  [4 marks] Using only the results of part (f) and the variables my_data1 and my_data2, compute the vector of residuals:
ˆε = Y − ˆYfor both the 1 variable and 3 variable models, and store these in the variables residuals_youtube, and residuals_all respectively.
(h)  [3 marks] Plot the residuals residuals_youtube, and residuals_all, in two separate figures, side-by- side within one plotting window. You should appropriately label all axes, and choose different colours and plotting symbols for the two figures.

         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
