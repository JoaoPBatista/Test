---
summary: Use an aggregate with grouped columns to obtain only the distinct values of entity attributes.
tags: support-application_development; support-Database; support-webapps
---

# Get Distinct Values from the Database

Database tables may have columns containing repeated values. There are
situations when you only want to get the distinct values, instead of all the
data including the repetitions. To obtain the distinct values of entity
attributes in OutSystems, you use an aggregate with grouped columns.

To get the distinct values of an entity attribute:

1. In an  aggregate  in the action flow, add the entity; 
2. On the attribute for which you want to obtain distinct values, click ![Aggregate Menu](../../../shared/icons-service-studio/aggregate-menu.png) and choose to group by the attribute.

After grouping an attribute in an aggregate, the aggregate only outputs
the grouped attributes.


## Example

In the GoOutWeb application, an application to review and rate places, we want
to know the end-users that have reviews reported as inappropriate. Since an
end-user can have multiple reviews reported as inappropriate, we want to fetch
only the distinct end-users:

1. Create a new aggregate and drag the entities Review and ReviewReport from the Data tab to the aggregate; 
2. In the  Sources  panel, update the join condition to `Review Only With ReviewReport` so that the  aggregate  only fetches reviews that were reported as inappropriate; 
3. On the  Review.UserId  attribute, click ![Aggregate Menu](../../../shared/icons-service-studio/aggregate-menu.png) and select Group by UserId. The aggregate will return only the distinct values of the  Review.UserId attribute. 

![Get Distinct Values From the
Database](images/distinct.png)