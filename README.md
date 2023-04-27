# data-science-independent-project-4

### Basic Requirements

Let’s break this project down into a couple different parts.

Exploration: Familiarize yourself with the dataset.

How many distinct zip codes are in this dataset?

- [ ] How many zip codes are from each state?

- [ ] What range of years are represented in the data?[^1]
[^1]: Hint: The date column is in the format yyyy-mm. Try taking a look at using the substr() function to help extract just the year.

- [ ] Using the most recent month of data available, what is the range of estimated home values across the nation?[^2]
[^1]: Note: When we imported the data from a CSV file, all fields are treated as a string. Make sure to convert the value field into a numeric type if you will be ordering by that field. See here 681 for a hint.

- [ ] Analysis: Explore how home value differ by region as well as change over time.

- [ ] Using the most recent month of data available, which states have the highest average home values?

- [ ] How about the lowest?

- [ ] Which states have the highest/lowest average home values for the year of 2017?

- [ ] What about for the year of 2007?

- [ ] 1997?

## Additional Challenges

### Intermediate Challenge

What is the percent change 176 in average home values from 2007 to 2017 by state? How about from 1997 to 2017?
Hint: We can use the WITH clause to create temporary tables containing the average home values for each of those years, then join them together to compare the change over time.
How would you describe the trend in home values for each state from 1997 to 2017? How about from 2007 to 2017? Which states would you recommend for making real estate investments?

### Advanced Challenge

- [ ] Join the house value data with the table of zip-code level census data. Do there seem to be any correlations between the estimated house values and characteristics of the area, such as population count or median household income?
