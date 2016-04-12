---
layout: default
---

# Running SQL scripts

Typing the same sql commands over all the time is painful. Queries gets long and cumbersome and one some times need to run them over and over.

Using SQL scripts makes database maintenance much easier. It helps you to ensure that databases and tables can be reliably dropped, recreated or changed.

SQL scripts are text files that contains SQL commands saved with a `.sql` extension.

## Running scripts

To run SQL scripts you use the `mysql` terminal command.

Login in to mysql using, `mysql -u root -p`

Once logged into mysql run a script like this:
`source <path_to_script_file.sql>`

Note that the path to the file is relative to where you ran the `mysql` command from.
