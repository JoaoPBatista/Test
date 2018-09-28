---
summary: Use the SQL element to write and execute custom SQL queries.
tags: support-Database
---

# SQL Queries

The SQL element allows you to execute, test, and review custom SQL queries in your applications. The element provides flexibility in data manipulation, but we recommend using Aggregates when applicable. Aggregates are highly optimized and easier to maintain.

SQL queries can access data that is sent through the input parameters only, and other logic can access only what the SQL query returns through the Output Structure.

  Input parameters
  :    Providing Input Parameters allows you to use dynamic data in the SQL query. Input Parameters are optional.

  Output parameter
  :    SQL in OutSystems queries always have two output parameters, even when the query executed does not return a result:

    * List: The list with the result returned by the query. The list is empty if there are no results.
    * Count: The number of records returned by the query without considering the SQL Max Records property.

Output Structure is mandatory. You need to define the structure (data types of the columns) that your query returns. For example, if you perform a query over the Employee Entity that selects the attributes `Id`, `Name`, `Email`, `PhoneNumber`, specify the Output Structure with the same attributes. This enforces that List output parameter of the SQL query returns Employee List data type. Output Structure is needed even if your SQL statement does not return any results.

## Notes and guidelines

Consider the following when using the SQL element:

Avoid Data Definition Language
:   The SQL tool should only be used to execute the following: `SELECT`, `INSERT`, `UPDATE`, and `DELETE` statements. Using Data Definition Language (DDL) statements like `CREATE TABLE`, `ALTER TABLE`, `DROP TABLE`, etc. might make the OutSystems metamodel inconsistent, leading to misbehavior.

No physical layer query
:    To ensure the OutSystems metamodel is always consistent, you cannot perform queries directly to the physical tables of the metamodel. The platform shows an error message if your query uses tables prefixed with `OSLOG`, `OSSYS`, or `OSUSR`.


Exception triggers a rollback
:    OutSystems starts a transaction when the web request arrives to the server, and commits the transaction before sending the reply to the user. If an exception is left uncaught, the transaction is rolled back to ensure your data is always consistent. This means that your queries run inside a transaction and that changes are rolled back if something goes wrong.

Check runtime user permissions
:    Your queries are tested and run in the database using the runtime user specified in the [Configuration Tool](<../../../ref/configuration-tool/tabs/platform.md>). You need to make sure this user has permissions to run the SQL statements specified in your query, otherwise an error will occur when you execute the query at runtime or when you test it.

Database support check
:    If the Database Module Property is set to **All**, OutSystems checks the queries to ensure they are compliant with all supported databases. If not, a warning message is displayed.
