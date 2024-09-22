- similar to #delete
-
- |__delete__|__truncate__|
  |table structure is not changed | not changed|
  |delete one or all rows| delete __all__ rows|
  |can have #where clause | no where clause|
  |#DML query| #DDL query|
  |can be #rollback #transaction| cannot be rolled back|
  |file storage is not deallocated {{cloze until the table is dropped}} | is reallocated |
  |slower|faster|
-
-
-