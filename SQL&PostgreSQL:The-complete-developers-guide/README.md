# SQL & PostgreSQL: The Complete Developer's Guide

## Database Design Process

When thinking about how to design your database think of these questions:

- What kind of thing are we storing? (A: list of cities)
- What properties does this thing have? (A: name, country, population area)
- What type of data does each of those properties contain?(A: name: string, country: string, population: number, area: number)

## Creating Table:

In this section we discussed how to create a table within our datbase and create the columns and their datatypes within our table here's an example of creating a table called cities and it's properties:

```
CREATE TABLE cities (
  name VARCHAR(50),
  country VARCHAR(50),
  population INTEGER,
  area INTEGER
  );
```

## Inserting Data Into a Table:

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
