---
title: Oracle Data Types
date: 2020-05-31 15:30
categories: howto SQL Oracle
---

*This post heavily relies on official Oracle document. To view the official document, go to [Oracle Data Types](https://docs.oracle.com/cd/B28359_01/server.111/b28318/datatype.htm#CNCPT012) .*

# 0.Index

# 1.Oracle Data Types

A **Data Type** refers to what **type** and **size** of data can be stored in a given column.  
Oracle supports data types that fall into following categories:  
* Character Types
* Numeric Types
* Date Types
* LOB Types
* ROWID Types
* Etc.

# 2.Character Types

Character data types store alphanumeric values.   
Note that character sets (e.g. ASCII, UTF-8) are already designated when creating the database.  

|Data Type|   |size|   |
|---------|---|----|---|
|`CHAR(n)`   |fixed length|1 ~ 2000 bytes|see `1`|
|`VARCHAR2(n)`|variable(max) length|1 ~ 4000 bytes|see `2`|
|`NCHAR(n)`| | | |
|`NVARCHAR(n)`| | | |

*n: numeric parameter denoting the size of the data type*  

#### 2-1. CHAR vs VARCHAR2 ####  
**CHAR**  
`CHAR` type has a fixed length for all rows of the table.  
This means when the input value for this column is shorter than the fixed length,  
Oracle automatically fills the empty space with left-padding.  
When the input value is longer than the fixed length,  
Oracle returns an error.  

**VARCHAR2**  
`VARCHAR2` type has a variable length for any rows of the table.  
*(You can check the byte size of a column with `vsize(column_name)` function)*

This means when the input value for this column is shorter than the fixed length,  
Oracle resizes the column of that specific row to the size of the input.  
However, when the input value is longer than the initial length,  
Oracle returns the same error as in `CHAR` .  

```SQL
CREATE TABLE test_char (
   test_case NUMBER,
   char_type CHAR(3),
   varchar_type VARCHAR2(3)
);

INSERT INTO test_char VALUES (1, 'A', 'A');
INSERT INTO test_char VALUES (2, 'BBB', 'BBB');
SELECT char_type, vsize(char_type), varchar_type, vsize(varchar_type) from test_char;
```

`OUTPUT:`  

|CHAR_TYPE|VSIZE(CHAR_TYPE)|VARCHAR_TYPE|VSIZE(VARCHAR_TYPE)|
|---------|----------------|------------|-------------------|
|A|3|A|1|
|BBB|3|BBB|3|


---

```SQL
INSERT INTO test_char VALUES (3, 'BBBB', 'BBBB'); 
```
`OUTPUT:`  
ORA-12899: value too large for column  

*When should CHAR or VARCHAR2 be used?*
Use CHAR datatype when it is absolutely necessary to compare exact fixed-length of a text (including possible white spaces).  
(e.g. sending formatted data)  
For other uses, VARCHAR2 is preferred as it saves un-used spaces while allowing flexibility to assign maximum length.  

#### 2-1. BYTE vs CHARACTER semantics ####  

Because Oracle provides multi-language support,  
using byte semantics and character semantics can yield different results.  
For numbers, symbols and the English alphabet, 1 character equals 1 byte.
For other languages, 1 character can take up more than 1 byte.
(e.g.)  
