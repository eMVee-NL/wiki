MySQL cheatsheet
=======

__Attention: The articles published on this wiki are for education purpose, to use during a CTF or for an authorized penetrationtest. By using the wiki, you've agreed to use this knowledge in an ethical way and do not evil in any perspective.__

Oneliners
---------
The oneliners can be created with a few arguments as shown below. It explaines how the command is created and what it should do.

  * mysql – This launches the MySQL shell
  * –u username – Replace username with the actual username for the database
  * –p password – Replace password with the actual password for the user
  * –e – Executes the following statement, then exits MySQL shell
  * “show databases;” – Specifies the command to execute
  * –D database-name – Replace database-name with the actual database-name


Show databases.
```bash
mysql –u 'username' –p 'password' –e 'show databases;'
```
Show tables in a database.
```bash
mysql –u 'username' –p 'password' -D database-name –e 'show tables;'

```
Select username,passworf from users in databases-name.
```bash
mysql –u 'username' –p 'password' -D database-name –e 'select username,password from users;'
```


Useful commands
---------

| Description                                                                               | Command                                                               |
| ----------------------------------------------------------------------------------------- | --------------------------------------------------------------------- |
| Logon to MySQL (will prompt for password)                                                 | mysql -u [username] -p;                                               |
| Show all databases                                                                        | show databases;                                                       |
| Access database (will prompt for password)                                                | mysql -u [username] -p [database]                                     |
| Select database                                                                           | use [database];                                                       |
| Determine what database is in use                                                         | select database();                                                    |
| Show all tables                                                                           | show tables;                                                          |
| Show table structure                                                                      | describe [table];                                                     |
| Selecting records                                                                         | SELECT * FROM [table];                                                |
| Explain records                                                                           | EXPLAIN SELECT * FROM [table];                                        |
| Selecting parts of records                                                                | SELECT [column], [another-column] FROM [table];                       |
| Counting records                                                                          | SELECT COUNT([column]) FROM [table];                                  |
| Selecting specific records (Selectors: <, >, !=; combine multiple selectors with AND, OR) | SELECT * FROM [table] WHERE [column] = [value];                       |
| Select records containing [value]                                                         | SELECT * FROM [table] WHERE [column] LIKE '%[value]%';                |
| Select records starting with [value]                                                      | SELECT * FROM [table] WHERE [column] LIKE '[value]%';                 |
| Select records starting with val and ending with ue                                       | SELECT * FROM [table] WHERE [column] LIKE '[val_ue]';                 |
| Select a range                                                                            | SELECT * FROM [table] WHERE [column] BETWEEN [value1] and [value2];   |
| Updating records                                                                          | UPDATE [table] SET [column] = '[updated-value]' WHERE [column] = [value];         |
| Deleting records                                                                          | DELETE FROM [table] WHERE [column] = [value];                                     |
| Delete all records from a table (without dropping the table itself, also resets the incrementing counter for auto generated columns like an id column.)| DELETE FROM [table]; |
| Delete all records in a table                                                             | truncate table [table];                                                           |
| Removing table columns                                                                    | ALTER TABLE [table] DROP COLUMN [column];                                         |
| Deleting tables                                                                           | DROP TABLE [table];                                                               |
| Deleting databases                                                                        | DROP DATABASE [database];                                                         |