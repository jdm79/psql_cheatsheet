# using ‘pg’ gem on irb
```
>require ‘pg'

 => true

>connection = PG.connect(dbname: ‘bookmark_manager_v3')

 => #<PG::Connection:0x007fc9c79700e8>

>result = connection.exec('SELECT * FROM bookmarks’)

 => #<PG::Result:0x007fc9c7958628 status=PGRES_TUPLES_OKntuples=3 nfields=2 cmd_tuples=3>
2.4.1 :005 >

>result.each { |bookmark| p bookmark }

{"id"=>"1", "url"=>"http://makers.tech"}
{"id"=>"2", "url"=>"http://www.destroyallsoftware.com"}
{"id"=>"3", "url"=>"http://www.google.com"}
 => #<PG::Result:0x007fc9c7830cc8 status=PGRES_TUPLES_OK ntuples=3 nfields=2 cmd_tuples=3> 
 ```

# Using psql
```
$psql # gets us into psql
>\l # shows us the databases of that user (normally me - localhost)
>CREATE DATABASE <databasename> # creates a database named ‘whatever’
>\c <databasename> # connects you to whatever database you specify
>\dt # display tables of that db
>CREATE TABLE bookmarks(id SERIAL PRIMARY KEY, url VARCHAR(60)); # whilst connected to a db - creates a table with two columns, first auto ascending id, second 60 characters
>\d <tablename> # displays columns of specified table
>\dn # lists all the schemas
>\x # shows us our tables in pretty mode
```
