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

|Data Type|Contents|Max Size|Length Semantics|
|---------|--------|----|----------------|
|`CHAR(n)`   |fixed length|2000 bytes|byte or character|
|`VARCHAR2(n)`|variable(max) length|4000 bytes|byte or character|
|`NCHAR(n)`|fixed length|2000 bytes (2000 characters)|character only|
|`NVARCHAR(n)`|varaiable length|4000 bytes (4000 characters)|character only|

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
SELECT test_case, char_type, vsize(char_type), varchar_type, vsize(varchar_type) from test_char;
```
*(You can check the byte size of a column with `vsize(column_name)` function)*  

`OUTPUT:`  

|TEST_CASE|CHAR_TYPE|VSIZE(CHAR_TYPE)|VARCHAR_TYPE|VSIZE(VARCHAR_TYPE)|
|---------|---------|----------------|------------|-------------------|
|1|A|3|A|1|
|2|BBB|3|BBB|3|


---

```SQL
INSERT INTO test_char VALUES (3, 'BBBB', 'BBBB'); 
```
`OUTPUT:`  
ORA-12899: value too large for column  

*+ When should CHAR or VARCHAR2 be used?*  
Use `CHAR` datatype when it is absolutely necessary to compare exact fixed-length of a text (including possible white spaces).  
(e.g. sending formatted data)  
For other uses, **`VARCHAR2` is preferred** as it saves un-used spaces while allowing flexibility in assigning maximum length.  

*+ BYTE vs CHARACTER semantics*  
Because Oracle provides multi-language support, using byte semantics and character semantics can yield different results.  
Byte semantics are the default semantics for character types.
For numbers, symbols and the English alphabet, 1 character equals 1 byte.  
For other languages, 1 character can take up to 3 bytes.  
For example, using UTF-8 character set, if you need a column that can store maximun of 10 characters, you can designate its size by either of the following:  
+ Byte semantics: VARCHAR2(30 bytes) *(= 3bytes * 10 characters)*
+ Character semantics: VARCHAR2(10 char)  


#### 2-2. CHAR(VARCHAR2) vs NCHAR(NVARCHAR2) ####  
As shown above, the size of `CHAR` or `VARCHAR2` types can be set in either bytes or characters.  
As for `NCHAR` or `NVARCHAR2` types, the size is always set in character semantics.  
Whereas `CHAR` or `VARCHAR2` types can support various types of character sets,  
`NCHAR` or `NVARCHAR2` types only support Unicode character sets `UTF-8` and `AL16UTF16`.  

# 3.Numeric types

# 4.Date types

# 5.LOB types

LOB data types store large blocks of unstructured data. i.e.large volume of text, images, sounds, videos, etc.  
LOB types are specified into `BLOB`, `CLOB`, and `NLOB`.  

Oracle recommends using LOB types over `Long` or `Long Raw` types for following reasons:  


# 6.ROWID types

