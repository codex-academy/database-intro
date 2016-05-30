---
layout: default
---

# Add data to your database

Populating a relational database from CSV files can be tricky due to the relationships between tables. The relationships are enforced by foreign keys constraints on each table. The foreign key constraints enforce the correct relationships between tables, that is that the foreign key columns contains values that exists in the corresponding column in the referenced table. As a result the order in which rows are added to the tables in a relational database is very important.

Say for example you have a football team database with tables for `Positions`, `Players` and `Teams`. Each player have a position and and each team have multiple players, the database use a `TeamPlayers` table, to link players to teams. The database have foreign key constraints to ensure that `Players` can only use positions that exists in the `Positions` table and that the `TeamPlayers` table can only contains valid `Players` and `Teams` foreign key id's.  

To populate this database from a CSV file you will need to:

* populate the `Positions` table;
* populate the `Players` table using the foreign key from the Position player;
* populate the `Teams` table;
* populate the `TeamPlayers` table using foreign keys from the `Teams` and the `Players` table.

## Database for Nelisa

Once you have a proper database schema in place with foreign keys between the tables, you you will need to add the data in this order:

* Add the Categories to the database;
* add Products to the database with foreign keys that reference the Categories table;
* add Sales & Purchase records to the database, with foreign keys that references entries in the Products table.

## Adding Categories

This one is fairly straightforward, loop through your list of Categories and create a list of lists and use a [bulk insert](/steps/mysql_bulk_insert_using_nodejs.html) add them to the database. The order of the list for each row should match your `sql` insert statement.

## Adding Products

What you need:
* a list of the Categories in the database;
* a map of which Products are in which Category;
* a way of mapping a Category name to it's CategoryId in the database.

Once you have all the above loop through the products and find the CategoryId for each. Then insert the Products into the database using a Bulk insert.

## Adding Sales & Products

You will need a way to easily map Product names to Product Id's. Create a map using a SQL select query from the `Products` table.

Loop through all the Sales records and find the corresponding Product Id for each Sale record. Then use a bulk insert to add all the Sales to the database.

Use a similar approach for adding Products to the database.
