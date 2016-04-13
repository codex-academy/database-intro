---
layout: default
---

# Running SQL scripts

Typing the same SQL commands all the time is painful. Queries get long and cumbersome and you need to be able to run them repeatedly.

Using SQL scripts makes running queries and database maintenance tasks much easier. They help you to ensure that databases and tables can be reliably queried, dropped, recreated, or changed.

## Creating scripts

SQL scripts are text files that contains SQL commands saved with a `.sql` extension.

Individual SQL commands in a script file are terminated by a semi-colon `;` character. There can be many different SQL commands in the same script.

Here's an example of a script file:

```sql
-- tell the script which database to use
-- use can do this before you run the script
use my_products;

-- you can drop tables
drop table if exists categories;
drop table if exists products;

-- you can create tables in the script;
create table categories(
    id int primary key auto_increment,
    description char(100) not null
);

create table products (
    id int primary key auto_increment,
        description char(100) not null,
    price decimal(10,2),
    category_id int,
    foreign key (category_id) references categories(id)
);

-- you can write a select query to check for data in a table
select * from products;
```

## Running scripts

To run SQL scripts you use the `mysql` terminal command.

Login in to MySQL using, `mysql -u root -p`

Once logged into MySQL run a script like this:
`source <path_to_script_file.sql>`

Note that the path to the file is relative to where you ran the `mysql` command from.
