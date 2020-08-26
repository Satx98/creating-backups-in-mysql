#### ****Logging into a mySQL account: (Getting into mySQL command shell)****

$ mysql -u username -p
Enter password: password




#### ****Basic mysql shell commands:****

mysql> show databases;
	*--to view our databses (can also be used to put ourselves out of a single database selection)*

mysql> use database_name;
	*--to put us into a single database named 'database_name'*

mysql> show tables;
	*--to view our tables in a particular databse*




#### ****Copying a table: (to copy tables we get into the mysql command shell)****

mysql> create table if not exists parts_bak like parts;
	*--copies only the schema of 'parts' table to 'parts_bak' table*

mysql> desc parts;					
	*--describe the 'parts' table (shows the schema structure of 'parts' table)*

mysql> select * from parts;
	*--selects all from 'parts' table (shows all data of 'parts' tablle)*

mysql> insert parts_bak select * from parts;
	*--selects all data from the 'parts' table and inserts them into the 'parts_bak' (i.e. copy the data of 'parts' table to 'parts_bak' table)*




#### ****Getting out of mySQL command shell: (to the linux command line)****

mysql> exit;




#### ****Copying a database:****

 To copy databases we have to be inside linux command line. We can't do that from inside mysql command shell!


##### ****Backing Up a database:****

$ mysqldump -u username -p database_name > /home/bob/Desktop/backup.sql
Enter password: password
	*--'-u' to give whatever username we have, '--p' so that the bash asks for the password. Then we need to give the name of the database we want to backup ,i.e., 'database_name', & then we need to provide '>' to signify whatever we put in next is where we will copy our database & then we have to specify the absolute path to a directory where we have a permission to write & then '/file_name' & then we have to enter our password.*

##### ****Creating a database from linux command bash:****

$ mysqladmin -u username -p create restore_database_name
Enter password: password

##### ****Restoring the database from our backup file:**** (Be careful while typing this)

$ mysql -u username -p restore_database_name < /home/bob/Desktop/backup.sql
Enter password: password
