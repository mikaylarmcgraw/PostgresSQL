# SQL & PostgreSQL: The Complete Developer's Guide

# Table of Contents

1. [Database Design Process](#database-design-process)
2. [Creating Tables](#creating-tables)
3. [Inserting Data Into a Table](#inserting-data-into-a-table)
4. [Retrieving Data](#retrieving-data)
5. [Calculation Columns Within Table](#calculation-columns-within-table)
6. [String Operators and Functions](#string-operators-and-functions)

## Database Design Process

When thinking about how to design your database think of these questions:

- What kind of thing are we storing? (A: list of cities)
- What properties does this thing have? (A: name, country, population area)
- What type of data does each of those properties contain?(A: name: string, country: string, population: number, area: number)

## Creating Tables

In this section we discussed how to create a table within our datbase and create the columns and their datatypes within our table here's an example of creating a table called cities and it's properties:

```
CREATE TABLE cities (
  name VARCHAR(50),
  country VARCHAR(50),
  population INTEGER,
  area INTEGER
  );
```

## Inserting Data Into a Table

To insert data into your table you will need to use the `INSERT` keyword followed by the properties you will be including within your inserts. Here's a sample block explaining how to insert a row of data into your cities table:

```
INSERT INTO cities(name, country, population, area)
VALUES ('Tokyo', 'Japan', 38505000, 8223);
```

to insert multiple rows you can add additional those to your query instead of having to add them one by one. Here's an example of inserting multiple rows in the cities table in one query:

```
INSERT INTO cities (name, country, population, area)
VALUES
('Delhi', 'India', 28125000, 2240),
('Shanghai', 'China', 22125000, 4015),
('Sao Paulo', 'Brazil', 20935000, 3043);
```

## Retrieving Data:

You can retrieve data from your table a few different ways. To retrieve all the information of your entries in a specific table you can use the following code snip:

```
SELECT * FROM cities
```

The \* is a wildcard and means to retireve all information from a specific table.

To retrieve only specific columns you can specify those in your query, the sample below will only retriev e the name and country of each city within your table:

```
SELECT name, country FROM cities
```

## Calculation Columns Within Table

You have the ability to do some logic to your data using the columns within your table. For instance if we wanted to calculate the population density of our cities we can run the following query which would divide the population of each city by it's area. You can also see we are labeling this temporary column of data as population_density. This would return the population density of each city without altering your current table:

```
SELECT name, population/area AS population_density FROM cities;
```

## String Operators and Functions

Here is a list of common string opperators and functions below:

- `||` Join two strings
- `CONCAT()` Join two strings
- `LOWER()` Gives a lower case string
- `LENGTH()` Gives number of characters in a string
- `UPPER()` Gives an upper case string

This example shows a use case for the join operators to join the city and country from our data together. The below query will grab the name of the city and join that with a `', '` which adds a space and comma before joining again with the country and renaming this information as a temporary column location:

```
SELECT name ||', ' || country AS location FROM cities;

SELECT CONCAT(name, ', ', country) AS location FROM cities;
```

You can nest functions as well, here is an example of nested string functions, we took the same logic from above but used the uppercase function on both the city and the country name:

```
SELECT CONCAT(UPPER(name), ', ', UPPER(country)) AS location FROM cities;
```
