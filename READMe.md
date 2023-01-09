# LOAN DEFAULT PREDICTION

This folder contains a collection of  notebooks I wrote as part of my capstone project 
for the Data Science certificate I did at Ryerson University.

## Introduction

The goal of this project was to use open data (the Lending club, between 2007 to 2018 Quarter 4) and Python  for predicting loan default.
I selected 26 variables from the dataset within over 150 data available. Please see below the data chose:

0	loan_amnt	The listed amount of the loan applied for by the borrower. 
1	term	The number of payments on the loan. Values are in months and can be either 36 or 60.
2	int_rate	Interest Rate on the loan
3	installment	The monthly payment owed by the borrower if the loan originates.
4	grade	LC assigned loan grade
5	sub_grade	LC assigned loan subgrade
6	emp_title	The job title supplied by the Borrower when applying for the loan.*
7	emp_length	Employment length in years. Possible values are between 0 and 10 where 0 means less than one year and 10 means ten or more years.
8	home_ownership	The home ownership status provided by the borrower during registration or obtained from the credit report. Our values are: RENT, OWN, MORTGAGE, OTHER
9	annual_inc	The self-reported annual income provided by the borrower during registration.
10	verification_status	Indicates if income was verified by LC, not verified, or if the income source was verified
11	issue_d	The month which the loan was funded
12	loan_status	Current status of the loan
13	purpose	A category provided by the borrower for the loan request.
14	title	The loan title provided by the borrower
15	addr_state	The state provided by the borrower in the loan application
16	dti	A ratio calculated using the borrower’s total monthly debt payments on the total debt obligations, excluding mortgage and the requested LC loan, divided by the borrower’s self-reported monthly income.
17	earliest_cr_line	The month the borrower's earliest reported credit line was opened
18	open_acc	The number of open credit lines in the borrower's credit file.
19	pub_rec	Number of derogatory public records
20	revol_bal	Total credit revolving balance
21	revol_util	Revolving line utilization rate, or the amount of credit the borrower is using relative to all available revolving credit.
22	total_acc	The total number of credit lines currently in the borrower's credit file
23	initial_list_status	The initial listing status of the loan. Possible values are – W, F
24	application_type	Indicates whether the loan is an individual application or a joint application with two co-borrowers
25	mort_acc	Number of mortgage accounts.
26	pub_rec_bankruptcies	Number of public record bankruptcies


### PREPROCESSING AND EXPLORATORY ANALYSIS

This part of the project essentially consisted to fill out missing values for variables who have missing values. 
Then select the variable that will be useful for the modelling based on the difference between the mean of fully paid and charged off for each of them.
I did also created dummies for caterogical variable selected.



### Modeling

I did the modelling with first the current loan status not including in fully paid status.
Please find the link:https://github.com/laussin86/laussin86/blob/main/Loan_Default_without_current.ipynb
For modeling,I first split my dataset between train and test.
Then scale it. After tried the models(XGBoost,Random Forest and logistics regression) on the imbalance data( distribution of fully paid and charged off is imbalance).
Finally, Resample the train data to balance due to the imbalance and apply the 3 models again to see the difference and if that improve my models.

the same process has been done with current loan status including in fully paid status and check if that will further improve my models.

Please find the link:https://github.com/laussin86/laussin86/blob/main/Loan_Default_with_current.ipynb

