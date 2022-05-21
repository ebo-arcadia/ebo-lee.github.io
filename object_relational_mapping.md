# Object
- Understand what is ORM and why use it
- Know how Objects and database interact with each
- Know how to use SQLAlchemy
__________


## What is SQLAlchemy?

SQL toolkit and object relational mapper used to map classes to the database

## What is ORM (object-oriented)?

A programming technique used to convert data between incompatible type systems in object-oriented languages

## What problems or issues does it solve?

it allows object model and database to develop in a cleanly decoupled way

## What are the key components?

SQL rendering engine
DBAPI integration, transaction integration, schema description service
Expression Language, SQL statements, Python OOP, built-in methods
SQL Expressions

## what is SQL expressions?

A language represents the primitive constructs of reh relational database

## How to use SQLAlchemy?
- what is SQL expressions statements?
  - SELECT, INSERT, UPDATE, DELETE
- how SQL expressions are constructed using methods relative to a class object? 
  - update() => UPDATE; delete() => DELETE; select() => SELECT
- how to insert values into a table?
  - <object>.insert().values(<column_header_name> = "value")
- how to execute SQL expressions in the context of ORM?
  1. obtain a connection object using DBAPI connection resource
     * e.g. conn = engine.connect()
  2. Feed the expression object to the connection object's inherited method execute()
     * e.g. ins = advisor.insert().values(name="mutual fund", fund="Vanguard 500")
- how to select rows in a table object?
  1. create an object using select() method
  2. construct SQL SELECT expression using Python Str() method
  3. execute SQL SELECT expression using execute() passing the object as a parameter
  4. stores data in a variable
  5. fetch data by executing fetchone() method on the variable
  6. appending the where clause with filtering criteria to filter fetched data
- how to update values in a table?
  1. create an object using update() method
  2. append where() clause with parameter to select a specific column
  3. append values() clause and new value as the parameter
  4. store the object in a statement or variable
  5. execute SQL expression using execute() passing the statement as a parameter
- how to delete rows or values in a table?
  1. run delete() on a target table object
  2. append where() clause passing parameter to select specific column value to delete
  3. store the above operation in a variable or statement
  4. execute SQL delete expression using execute() passing the delete statement as a parameter

------------

## Outcomes
1. imported sqlAlchemy and built-in methods
2. created an object of the Engine class using create_engine()
3. created a database using the Engine object in sqlite in-memory
4. imported classes for creating tables
5. created a table using imported classes and methods
6. stored the table in metadata object
7. created insertion of columns and values as object
8. executed SQL expression to insert columns and values in the database
9. executed one SQL expression to insert a list of dictionaries in the database
10. verified the creation of the table, insertion of columns and values using DB Browser for SQLite 
11. executed SQL SELECT statement to fetch data from the database
12. appended where clause to the SELECT statement to customize fetched data from the database
13. verified fetched data from database in the console
14. executed SQL UPDATE statement to update values in a table using table object
15. executed SQL DELETE statement to delete rows in a table using table object
16. deleted multiple columns, rows, tables using delete object to execute SQL DELETE expression
17. updated multiple rows, columns, and tables suing update object to execute SQL UPDATE expressions
18. executed update operation preserving the order when passing parameters using ordered_value() method
19. executed SQL select expression using select object with JOINS to combine rows and columns from multiple tables
20. formed conjunctions of compound SQL expressions using relational operators including AND, OR, NOT functions
21. rendered generic functions, functions passing columns as parameters with the usage of imported keyword func

