# SQL

\[TOC\]

## Overview

### Statements

```sql
SELECT -- Get data from the database
    - -- All columns
    AS -- Creates an identifier for column ("" for titles)
    DISTINCT -- Unique results
    FROM -- Specifies location

    WHERE -- Select which rows to update
        ORDER BY -- Specify field to order by
            LIMIT -- Limit number of results
                OFFSET -- Offset result
            DESC -- Descending order
        COUNT(*) -- Gives count for given set
            -- Will only count where there is a value
        IN () -- Literal is within list

    CASE ... WHEN ... THEN ... ELSE ... END AS ...

INSERT -- Add a row to a table
    INTO -- Specifies location
        (fields) VALUES (fields) -- Insert values into corresponding fields

        SELECT -- Choose columns from other tables

        DEFAULT VALUES -- Empty values

UPDATE -- Change data
    SET -- Identify changes
        WHERE -- Identify which to change

DELETE -- Remove rows from a table
    FROM
        WHERE
```

_Indenting is used to more clearly organize code_

_Good practice to include a semicolon_

General

* Single quotes \(' '\) for literal Strings
* Equals \(=\) for comparison
* Can leave columns unspecified and they will be filled as NULL
* `DROP`: removes tables

## Fundamental Concepts

### Tables

```sql
CREATE -- Starts creation
    TABLE (fields) -- Initializes a new table
        DEFAULT -- If a field is unspecified
        UNIQUE -- Ignores NULL
        NOT NULL -- Cannot be a NULL value
        PRIMARY KEY -- Unique sequential ID

DROP -- Deletion
    TABLE -- Error thrown when table does not exist
        IF EXISTS

ALTER -- Alters existing table
    TABLE
        ADD -- Add a new column
```

Types

* `INTEGER`, `TEXT`...
  * `DEFUALT`, `UNIQUE`, `NOT NULL`
  * `PRIMARY KEY`

NULL Value

* Special state
* \*Lack- of a value
* Use `IS NULL` and `IS NOT NULL`
* `IF EXISTS` is used to prevent errors

Filtering

* `WHERE` takes a Boolean expression
  * `<`, `>`...
  * `OR`, `AND`...
  * `%'String'%`: like operator
    * `%` at end or beginning specifies location of matching String
  * `_'String'` matches single characters
  * `IN`: results where column is in a list of literals

Duplicates

* `SELECT DISTINCT`: unique results

Ordering

* `ORDER BY` `'field'`
  * `DESC`, `ASC`
    * `NULL` is taken as least
  * Can order by multiple fields, taken in order of declaration

Conditionals

* `CASE` ... `WHEN` ... `THEN` ... `ELSE` ... `END AS` ...

## Relationships

### JOIN

```sql
JOIN -- Takes from tables with equivalent fields
    ON -- Where fields are equivalent

    WHERE...
    GROUP BY...
    ORDER BY...DESC
```

Joined query

* `JOIN`
* Related data from multiple tables
* _Usually matching IDs_
  * `LEFT`, `RIGHT`, `FULL`
  * `OUTER`, `INNER`
  * Inner join: where condition is met
    * Most common
  * Left outer join: condition is met plus where condition is not met on the left
    * Right outer join
    * Full outer join
* `ON` takes a Boolean expression

General

* `table`.`field`: selects the particular column/field

## Strings

```sql
SUBSTR() -- Substring, may have a different name
LENGTH() -- Length

TRIM() -- Removes spaces from sides
LTRIM()
RTRIM()
TRIM(string, string) -- Trims strings

UPPER() -- Forces a case
LOWER()
```

### Functions

Specific functions

* `||`: standard concatenation operator
  * MySQL uses `CONCAT()`
  * MS SQL uses `+`
* Not always supported and will differ between systems
  * `SUBSTR(string, start, length)`
  * `LENGTH(string)`
  * `TRIM(string)`
  * `UPPER/LOWER(string)`
* Use `''` to use a single quote within a string

_NOTE_

* Standard SQL uses `'`
* Others, such as MySQL, uses `"`

## Numbers

```sql
INTEGER, DECIMAL, MONEY

REAL, FLOAR

TYPEOF()
CAST()

ROUND()
ROUND(number, spaces) -- Rounds to specified spaces
```

### Types

Integer

* `INTEGER(precision)`
* `DECIMAL(precision, scale)`
* `MONEY(precision, scale)`

Real

* `REAL(precision)`
* `FLOAT(precision)`
* Large or small numbers
* Sacrifice accuracy for scale
  * May be unable to compare with an expected result

### Functions

General

* `TYPEOF()`: returns number type
  * Plus\(`+`\) operator is arithmetic and using it may be integer-based
* May have unexpected results from operations
  * `INTEGER` ignored decimals
* `CAST()`: convert from one to another
  * `AS REAL`...
* `+`, `-`, `*`, `/`, `%`
* `ROUND()`: rounds to specified spaces

## Dates and Times

### Format

Date

* year-month-day

Time

* hour:minute:second

### Functions

General

* NOT standardized
  * `DATE`, `TIME`, `DATETIME`, `YEAR`, `INTERAVL`...
  * `DATETIME('string')`: gives in UTC
    * `*'now'*`
  * `DATE/TIME()`
    * _\(... '+-1 day/month/year'\)_
    * _\(... '+-1 minute/hour/day/year\)_
* _All dates and times are in UTC \(Coordinated Universal Time\)_

## Aggregates

```sql
GROUP BY -- Group data set together for operation
    HAVING -- 'WHERE'

COUNT() -- Counts columns
AVG() -- Average of the fields
MIN() -- Extrema of a field
MAX()
SUM() -- Sum of fields
    (DISTINCT field) -- Distinct instances
```

Aggregate

* `GROUP BY`: sorts by a field and calls functions by groups
  * `HAVING`: _`WHERE`_ for aggregate data
    * Can use both; ordering matters

Functions

* Ignores `NULL`
* `COUNT(*)`
* `AVG()`
* `MIN/MAX()`
* `SUM()`
  * `DISTINCT`: ignores repeats
    * `UNIQUE` may do the same thing

## Transactions

```sql
BEGIN TRANSACTION -- Starts block of continuous action
    ...
END TRANSACTION -- Ends continuous action

ROLLBACK -- Restores to previous state
```

Transactions

* One, complete operation
* _Restores if a failure occurs_
* _Increased performance_
  * Can be a _dramatic_ difference
* `BEGIN TRANSACTION...`
* `END TRANSACTION`
  * May be differences
* Encompasses block of updates
* `ROLLBACK`: allows control over saved states

## Triggers

```sql
CREATE TRIGGER name ...
    BEGIN
        UPDATE ...

        SELECT RAISE(ROLLBACK, 'message') FROM table ...
            WHERE ...

        INSERT INTO log (...) VALUES (...)
    END
```

Triggers

* _Vary between systems_
* `CREATE TRIGGER`
  * `AFTER INSERT`: begins after a row is inserted on a table
  * `SELECT RAISE(ROLLBACK, 'message')`: interrupts if a case is fulfilled
  * `NEW`...: updated row

## Views and Sub selects

```sql
SELECT field, field FROM (
    SELECT SUBSTR() AS field FROM table
) AS name

SELECT * FROM table -- Search within selected rows
    WHERE id IN (...)

CREATE VIEW name AS SELECT... -- Creates a view
```

Sub select

* Breaking fields into pieces
* `SUBSTR()` used to extract information into separate fields

View

* Saved query
* `CREATE VIEW`: can be saved to be an effective table
  * `*minutes || ':' || SUBSTR('00' || seconds, -2, 2)*`: gives readable time length

## Defined Functions

User Defined Functions

* Required different methods; certain languages are used in different systems
* Unit conversions
* Format conversions
* Aggregations

