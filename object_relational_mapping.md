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
