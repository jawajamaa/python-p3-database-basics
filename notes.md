# SQLite commands

commands are CAPITAL (unfortunately...)
column names are snake and lowercase

<!-- below command creates a table with the name of table_name -->
CREATE TABLE table_name;

<!-- below command opens sqlite3 in CLI the the db chinook -->
sqlite3 chinook.db

<!-- command shows list of artists from chinook.db -->
SELECT * FROM artists;

.tables
<!-- above command shows below -->
albums          employees       invoices        playlists     
artists         genres          media_types     tracks        
customers       invoice_items   playlist_track

<!-- command shows list of albums from chinook.db as choices above show -->
SELECT * FROM albums;

<!-- below commands -->
 CREATE TABLE cats (                <!--create table from db cats -->
    id INTEGER PRIMARY KEY,         <!--lowercase column name, cap command -->
    name TEXT,                      <!--lowercase column name, cap command -->
    age INTEGER                     <!--lowercase column name, cap command -->
);     <!--close paren - all commands end with ; except if start with . such as    .quit or .help-->  

ALTER TABLE cats ADD COLUMN breed TEXT;
<!-- adds column 'breed' of type 'text' -->

sqlite>  .schema <!-- command shows us below layout now -->
CREATE TABLE cats (
  id INTEGER PRIMARY KEY,
  name TEXT,
  age INTEGER,
  breed TEXT
);

<!-- if you would like to delete a table use -->
DROP TABLE cats;
<!-- where cats would be replaced with the name of the table -->
<!-- then use .quit to exit sqlite in CLI> -->
sqlite>  .quit
