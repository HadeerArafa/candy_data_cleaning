# candy_data_cleaning
cleaning candy data as practice to data cleaning course in data camp

# Project: cleanning - [candy data]
### this notebook is for educational purpose . in this notebook we will do some cleanning

## Table of Contents
<ul>
<li><a href="#intro">Introduction</a></li>
<li><a href="#cleaning summary">cleaning summary</a></li>
  
</ul>

<a id='intro'></a>
## Introduction

### Dataset Description 

> i will go through candy data 2017 , this data has :
>- Internal_ID
>- Q1-Going Out?: Are you actually going trick or treating yourself? "has values `Yes or No`"
>- Q2-Gender: It has four different options, `Femal ,Male ,Other ,I'd rather not say`
>- Q3-Age: Numerical field
>- Q4-Country: Text Field, but users have written their own version of the names. Example, for America, there are entries such as USA, us, US, America so we should consider that while cleaning
>- Q5-State/Province: Text Field, but users have written their own version of the names. Same as the country data.
>- Q6-Joy Or Despair: All kinds of chocolate bars are the questions with three distinct options to choose from (Joy, Meh, Despair).
>- Q7-Joy Other: Text Field to write items not included above that give you JOY. Lots of missing values.
>- Q8-Despair Other: Text Field ti write items not included above that give you DESPAIR. Lots of missing values.
>- Q9-Other Comments: Text Field. Lots of missing values.
>- Q10-Dress: Binary field. Missing values present
>- Unnamed: 113
>- Q11-Day: Binary Answer Field. Missing values present

<a id='cleaning summary'></a>
## cleaning summary :
> - we dropped the `rows` that have NaN values more than 15 , the `columns` that were not in survay pdf and some columns that have Nan > 300
>- we impute the NaN values in `going_out` column with the most frequency responce `No`
>- the same with `gender` we impute the NaN values and the values with no answer to the most frequency responce `Male`
>- the `age` column had string so we were not able to convert to int , so we used pd.to_numeric to convert to numbers and the rows that was not able to convert became NaN , then we started the impute the age considering the gender
>- we let all the `country` to be upper , then using match algorism because there were different writting to the same cpuntry ,then we did some manual replacement ,and finally to put all the countries with value = 1 to a new category called other
>- `area column` had too much nuique values so i dropped it
>- we go through each column of `Q6` and impute the NaN values in each column with the most frequency value in each column
>- we also impute `dress` and `day` with the most frequency value in each column
