---
layout: default
---

# Constraints

Constraints determines what values are allowed in database columns.

## Foreign keys

Foreign key constraints keep your data consistent by ensuring that values in a column can only contains values that exists in a column in a specified table.

One can create foreign keys between tables when the tables already exists.

Like this:

```sql
ALTER TABLE sales ADD CONSTRAINT fk_product_id FOREIGN KEY (product_id) REFERENCES products(id);
```
OR

One can create foreign keys between tables when a table is created.

Like this:

```sql
create table products (
    id int primary key auto_increment,
    description char(100) not null,
    price decimal(10,2),
    category_id int,
    foreign key (category_id) references categories(id)
);
```

See more details [here](http://stackoverflow.com/questions/757181/basics-of-foreign-keys-in-mysql)

## Unique Constraints

Ensure that the value in a column is unique. That means that only one column in the table can contain that value.

One create unique constraints like this:

```sql
ALTER TABLE products ADD UNIQUE product_name_uniq (product_name);    
```

See more details [here](http://stackoverflow.com/questions/635937/how-do-i-specify-unique-constraint-for-multiple-columns-in-mysql)
