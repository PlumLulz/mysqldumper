# PHP/Python MySQL Dumper

This is a MySQL Dumper that uses a Python console to interact with a PHP file uploaded to a target site. This script also uses gevent to create a pool of workers to dump the database in chunks to increase the speed. As of December 2022 this project was updated.

## Speed Comparison
Because every server and database are different your results may vary. Here are some speed comparisons for multiple different databases. Some of these tests were locally and others were from remote servers. Times are from start of database dump
to end of file compression. As I obtain more comparisons I will update this table. 

| Name | Database Size | MSD2.2 Speed | MSDpy Speed |
| --- | --- | --- | --- |
| database1 | 2GB | 3m:19s | 1m:10 |
| database2 | 5.3GB | 13m:46s | 5m:53 |
| database3 | 7.33GB | *2h:30m+ | 36m:40 |
| database4 | 1.84GB | 12m:00s | 7m:44s |

\* = Server went down near the end of dump so there was still time to go. 

Usage:
Upload the mysqlpy.php file to the target then run the Python script with the correct script password and MySQL server credentials. 

python3 mysql.py http://localhost/mysqlpy.php lol localhost root root 3306

Main screen and help command.
![msdpy](https://i.imgur.com/OWpo7XE.png)

Show databases command with -size flag.
![msdpy](https://i.imgur.com/TnCKt8a.png)

Show tables command with -count flag.
![msdpy](https://i.imgur.com/WXmZJJ9.png)

Use database command, dump table, and dump database commands.
![msdpy](https://i.imgur.com/c635777.png)
