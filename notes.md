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
ALTER TABLE cats DROP COLUMN breed;
<!-- removes column 'breed' - no type 'text' needed; will throw error if included -->

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

## run SQLite on a db from a file instead of CLI

  Folder -    python-p3-writing-db-commands-to-a-file
  Contents -  01_create_cats_table.sql        <!-- .sql file with commands -->
              02_remove_column_from_cats.sql  <!-- .sql file with commands -->
              03_add_column_to_cats.sql       <!-- .sql file with commands -->
              CONTRIBUTING.md                 <!-- usual repo files -->
              LICENSE.md                      <!-- usual repo files -->
              pets_database.db                <!-- db file sql files act on -->
              README.md                       <!-- usual repo files -->

<!-- cli commands -->
<!-- creates cat table by running commands in 01_file -->
sqlite3 pets_database.db < 01_create_cats_table.sql
<!-- adds column 'breed' per file commands; will throw error not duplicate if a column 'breed' already exists -->
sqlite3 pets_database.db < 03_add_column_to_cats.sql
<!-- then run 02_file to remove 'breed' column for practice to then add with 03_file -->
sqlite3 pets_database.db < 02_remove_column_from_cats.sql
<!-- can at any point check work with '.schema' command -->
