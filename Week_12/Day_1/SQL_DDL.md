## Data Definition Language (DDL)
SQL commands used to define database schema

---

### Creating Tables
---
- Use keyword CREATE
- Must define the data type
- Identify PRIMARY KEY
  - Use SERIAL PRIMARY KEY to make auto-incrementing PK. 

```SQL
CREATE TABLE users (
id SERIAL PRIMARY KEY,
name VARCHAR(255),
birth_year SMALLINT,
member_since TIMESTAMP
); 
```
---
### Data Types
---

Review summary of data types here:
https://www.postgresqltutorial.com/postgresql-data-types/

---
### Altering a Table
---

Basic syntax to modifiy a table:

```SQL
ALTER TABLE table_name action;
```

#### Add a Column

```SQL
ALTER TABLE table_name 
ADD COLUMN column_name datatype column_constraint;
```

#### Remove (Drop) a Column

```SQL
ALTER TABLE table_name 
DROP COLUMN column_name;
```

#### Renaming

1. Column 
```SQL
ALTER TABLE table_name 
RENAME COLUMN column_name 
TO new_column_name;
```
2. Table

```SQL
ALTER TABLE table_name 
RENAME TO new_table_name;
```

#### Remove a Table

**BE CAREFUL** - there is no undo in SQL!

Will delete table and all its data
```SQL
DROP TABLE users;
```

Drop table and delete all records in other tables that rely on this table
```SQL 
DROP TABLE users CASCADE;
```

** BEST PRACTICE ** to make sure table exists and avoid SQL errors :)
```SQL 
DROP TABLE if exists users CASCADE
```
---
### Not Null
---

Constraint can be added to table schema that ensures no null data is added to the table

``` SQL
CREATE TABLE users (
id SERIAL PRIMARY KEY,
name VARCHAR(255) NOT NULL
);
```
---
### Default Values
---

Set default value on a column - if row data is entered without value, then default is used

```SQL
CREATE TABLE users (
id SERIAL PRIMARY KEY NOT NULL,
name VARCHAR(255) NOT NULL,
member_since TIMESTAMP NOT NULL DEFAULT Now()
);
```

---
### Foreign Keys

Reference keys from other tables like this:

```SQL
CREATE TABLE pets (
  id SERIAL PRIMARY KEY,
  name VARCHAR(255) NOT NULL,
  owner_id INTEGER NOT NULL REFERENCES users(id)
);
```

What if the owner gets deleted from the user table? We want the pet data to get deleted too, like this:

```SQL
CREATE TABLE pets (
  id SERIAL PRIMARY KEY,
  name VARCHAR(255) NOT NULL,
  owner_id INTEGER NOT NULL REFERENCES users(id) ON DELETE CASCADE
);
```

```ON DELETE CASCADE``` on a foreign key ensures the row will be deleted if the thing that it's referencing is deleted elsewhere

