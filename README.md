# data-science-independent-project-4

### Basic Requirements

Let’s break this project down into a couple different parts.

Exploration: Familiarize yourself with the dataset.

- [X] How many distinct zip codes are in this dataset?

15452

```sql
select count (distinct zip_code) from home_value_data
```

- [X] How many zip codes are from each state?

```sql
select count (distinct zip_code) from home_value_data group by state
```

- [x] What range of years are represented in the data?[^1]

|highest year| lowest year|
|---|---|
|2018|1996|

[^1]: Hint: The date column is in the format yyyy-mm. Try taking a look at using the substr() function to help extract just the year.
```sql
SELECT
	max(substr(date, 1, 4)) as 'highest year',
	min(substr(date, 1, 4)) as 'lowest year'
from home_value_data
```
- [ ] Using the most recent month of data available, what is the range of estimated home values across the nation?[^2]
[^2]: Note: When we imported the data from a CSV file, all fields are treated as a string. Make sure to convert the value field

```sql
select max(value), min(value) from home_value_data where date = '2018-11'
```

into a numeric type if you will be ordering by that field. See [here](https://stackoverflow.com/questions/20240315/how-to-import-csv-file-to-sqlite-with-correct-data-types/20241031#20241031) for a hint.

- [X] Analysis: Explore how home value differ by region as well as change over time.


- [X] Using the most recent month of data available, which states have the highest average home values? How about the lowest?

|function|value|state|
|---|---|---|
|min|112452|MO|
|max|17757800|NY|

- [X] Which states have the highest/lowest average home values for the year of 2017? What about for the year of 2007? 1997?

|year| value|state|
|---|---|---|
|2017|21600|OK|
|2007|91773|OK|
|1997|56326|OK|

```sql
SELECT round(avg(value)),state  from home_value_data where substr(date,1,4) = '1997' and value not null group by state order by 1 ASC limit 1
```


## Additional Challenges

### Intermediate Challenge

What is the percent change 176 in average home values from 2007 to 2017 by state? How about from 1997 to 2017?
Hint: We can use the WITH clause to create temporary tables containing the average home values for each of those years, then join them together to compare the change over time.
How would you describe the trend in home values for each state from 1997 to 2017? How about from 2007 to 2017? Which states would you recommend for making real estate investments?

### Advanced Challenge

- [ ] Join the house value data with the table of zip-code level census data. Do there seem to be any correlations between the estimated house values and characteristics of the area, such as population count or median household income?
