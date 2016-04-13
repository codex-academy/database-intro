---
layout: default
---

# Constraints

Constraints determine what values are allowed in database columns.

## Foreign keys

Foreign key constraints keep your data consistent by ensuring that values in a column can only contain values that exist in a column in a specified table.

You can create foreign keys between tables when a table already exists like this:

```sql
ALTER TABLE sales ADD CONSTRAINT fk_product_id FOREIGN KEY (product_id) REFERENCES products(id);
```
Or you can create foreign keys between tables when a table is created like this:

```sql
create table products (
    id int primary key auto_increment,
    description char(100) not null,
    price decimal(10,2),
    category_id int,
    foreign key (category_id) references categories(id)
);
```

See more details on StackOverflow: [Basics of Foreign Keys in MySQL?](http://stackoverflow.com/questions/757181/basics-of-foreign-keys-in-mysql)

## Unique Constraints

These ensure that the value in a column is unique. That means that only one column in the table can contain that value.

You can create unique constraints like this:

```sql
ALTER TABLE products ADD UNIQUE product_name_uniq (product_name);    
```

See more details on StackOverflow: [How do I specify unique constraint for multiple columns in MySQL?](http://stackoverflow.com/questions/635937/how-do-i-specify-unique-constraint-for-multiple-columns-in-mysql)
