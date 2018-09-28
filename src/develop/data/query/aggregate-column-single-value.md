---
summary: Use aggregate functions on a column to calculate a single value.
tags: support-application_development; support-Database; support-webapps
---

# Aggregate a Column into a Single Value

Sometimes displaying a single aggregated value can be more meaningful than
displaying the full list of records available in the database. For instance
displaying the total revenue from the orders, instead of displaying every
single order.

To aggregate a column into a single value, hover the column, click
![Aggregate Menu](../../../shared/icons-service-studio/aggregate-menu.png), and choose one of the available aggregate functions:

* Sum: sums all the values in the column;
* Average: calculates the average of the values in the column;
* Max: finds the maximum value in the column;
* Min: finds the minimum value in the column;
* Count: counts how many rows there are in the column.

The list of available aggregate functions depends on the data type of the
column. Sum and Average are only available for numeric data types; textual
data types (text, email, and phone number) only have the Count function
available.


## Example

In GoOutWeb, an application to review and rate places, we want to display the
number of reviews and average rating of places in a Web Block. To do this, we
will use the average and count aggregate functions as follows:

1. Open the Preparation action of the PlaceRating Web Block;
2. Create an aggregate to get all Reviews by the Place ID;
3. Hover the column Id, click ![Aggregate Menu](../../../shared/icons-service-studio/aggregate-menu.png), and select Count to calculate the number of reviews;
4. Hover the column Rate, click ![Aggregate Menu](../../../shared/icons-service-studio/aggregate-menu.png), and select Average to calculate the average rating;  
![Aggregate a Column Into a Single
Value](images/aggregate-column-single-value.png)
5. On the Web Block, add expressions to display the two calculated values,  GetReviewsByPlaceId.List.Current.Count and  GetReviewsByPlaceId.List.Current.RateAvg.