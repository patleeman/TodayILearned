#title:  How to import large db dumps in mysql
##date:  2016-03-29 11:39:20
##sub-folder:  mysql

Command line commands to import large (~14GB) sql dumps.

Source: http://stackoverflow.com/questions/13717277/how-can-i-import-a-large-14-gb-mysql-dump-file-into-a-new-mysql-database


```sql
mysql -u root -p

set global net_buffer_length=1000000; --Set network buffer length to a large byte number

set global max_allowed_packet=1000000000; --Set maximum allowed packet size to a large byte number

SET foreign_key_checks = 0; --Disable foreign key checking to avoid delays,errors and unwanted behaviour

source file.sql --Import your sql dump file

SET foreign_key_checks = 1; --Remember to enable foreign key checks when procedure is complete!
```

