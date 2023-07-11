# AIML-Assignment1
Related notebook can be found at https://github.com/spiderweb2828/AIML-Assignment1/blob/main/prompt.ipynb 

Data Clean up: In order to find the required data clean up, lets find the unique values of each column by executing the command data.apply(lambda col: col.unique()) on the dataframe "data"

    Results:
![uniquecol_vals.png](images%2Funiquecol_vals.png)
    
    Required data clean up:
    -- Car : Significant number of records with "nan"s and coupon accepted (7148). we cannot drop these rows. so lets replace the nan with "Unknown Transportation"
    -- Bar : had 107 nan. Resolution: check if these persons have any kids with them. if so replace 'nan' with 'never' as a fair assumption. if not then replace 'nan' with mean of means of other values (observed 1~3 would be reasonable value to consider for missing values)
    -- Income: Income column provided textual information of income and its range. So created two more columns "income_min" and "income_max" by splitting the value in income column and assigning the income_min value to income_max column in case income_max is missing
    -- Required to convert age to numeric value. Considered 50plus as 50 and below21 as 20

Some Findings:

a. One observation that is common across all asked above questions is -- rate of acceptance for Bar is higher compared to "not accepted"
b. when compared with age above and below 25, passangers below 25 has higher acceptance rate of coupons
c. Higher Temperature has higher rate of acceptance of the coupon (refer to temperature visualization question 6)


