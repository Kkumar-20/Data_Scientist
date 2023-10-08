SQL using Python
In this article, integrating SQLite3 with Python is discussed. Here we will discuss all the CRUD operations on the SQLite3 database using Python. CRUD contains four major operations – 

CRUD operations SQLite3 and Python

Note: This needs a basic understanding of SQL. 

Here, we are going to connect SQLite with Python. Python has a native library for SQLite3 called sqlite3. Let us explain how it works. 


Connecting to SQLite Database
To use SQLite, we must import sqlite3.
import sqlite3
Then create a connection using connect() method and pass the name of the database you want to access if there is a file with that name, it will open that file. Otherwise, Python will create a file with the given name.
sqliteConnection = sqlite3.connect('gfg.db')
After this, a cursor object is called to be capable to send commands to the SQL. 
cursor = sqliteConnection.cursor()
Example: Connecting to SQLite3 database using Python
import sqlite3
 
# connecting to the database
connection = sqlite3.connect("gfg.db")
 
# cursor
crsr = connection.cursor()
 
# print statement will execute if there
# are no errors
print("Connected to the database")
 
# close the connection
connection.close()
Output:

Connected to the database
Cursor Object
Before moving further to SQLite3 and Python let’s discuss the cursor object in brief. 

The cursor object is used to make the connection for executing SQL queries.
It acts as middleware between SQLite database connection and SQL query. It is created after giving connection to SQLite database. 
The cursor is a control structure used to traverse and fetch the records of the database. 
All the commands will be executed using cursor object only.
Executing SQLite3 Queries – Creating Tables
After connecting to the database and creating the cursor object let’s see how to execute the queries.

To execute a query in the database, create an object and write the SQL command in it with being commented. Example:- sql_comm = ”SQL statement”
And executing the command is very easy. Call the cursor method execute() and pass the name of the sql command as a parameter in it. Save a number of commands as the sql_comm and execute them. After you perform all your activities, save the changes in the file by committing those changes and then lose the connection. 
Example: Creating SQLite3 tables using Python
In this example, we will create the SQLite3 tables using Python. The standard SQL command will be used for creating the tables.

import sqlite3
 
# connecting to the database
connection = sqlite3.connect("gfg.db")
 
# cursor
crsr = connection.cursor()
 
# SQL command to create a table in the database
sql_command = """CREATE TABLE emp ( 
staff_number INTEGER PRIMARY KEY, 
fname VARCHAR(20), 
lname VARCHAR(30), 
gender CHAR(1), 
joining DATE);"""
 
# execute the statement
crsr.execute(sql_command)
 
# close the connection
connection.close()
Output:

python sqlite3 create table

Inserting into Table
To insert data into the table we will again write the SQL command as a string and will use the execute() method.

Example 1: Inserting Data into SQLite3 table using Python
# Python code to demonstrate table creation and
# insertions with SQL
 
# importing module
import sqlite3
 
# connecting to the database
connection = sqlite3.connect("gfg.db")
 
# cursor
crsr = connection.cursor()
 
# SQL command to insert the data in the table
sql_command = """INSERT INTO emp VALUES (23, "Rishabh",\
"Bansal", "M", "2014-03-28");"""
crsr.execute(sql_command)
 
# another SQL command to insert the data in the table
sql_command = """INSERT INTO emp VALUES (1, "Bill", "Gates",\
"M", "1980-10-28");"""
crsr.execute(sql_command)
 
# To save the changes in the files. Never skip this.
# If we skip this, nothing will be saved in the database.
connection.commit()
 
# close the connection
connection.close()
Output:

python sqlite3 insert data


Example 2: Inserting data input by the user

# importing module
import sqlite3
 
# connecting to the database
connection = sqlite3.connect("gfg.db")
 
# cursor
crsr = connection.cursor()
 
# primary key
pk = [2, 3, 4, 5, 6]
 
# Enter 5 students first names
f_name = ['Nikhil', 'Nisha', 'Abhinav', 'Raju', 'Anshul']
 
# Enter 5 students last names
l_name = ['Aggarwal', 'Rawat', 'Tomar', 'Kumar', 'Aggarwal']
 
# Enter their gender respectively
gender = ['M', 'F', 'M', 'M', 'F']
 
# Enter their joining data respectively
date = ['2019-08-24', '2020-01-01', '2018-05-14', '2015-02-02', '2018-05-14']
 
for i in range(5):
 
    # This is the q-mark style:
    crsr.execute('INSERT INTO emp VALUES ({pk[i]}, "{f_name[i]}", "{l_name[i]}", "{gender[i]}", "{date[i]}")')
 
# To save the changes in the files. Never skip this.
# If we skip this, nothing will be saved in the database.
connection.commit()
 
# close the connection
connection.close()
Output:

insert into table python sqlite3

Fetching Data
In this section, we have discussed how to create a table and how to add new rows in the database. Fetching the data from records is simple as inserting them. The execute method uses the SQL command of getting all the data from the table using “Select * from table_name” and all the table data can be fetched in an object in the form of a list of lists.

Example: Reading Data from sqlite3 table using Python

# importing the module
import sqlite3
 
# connect with the myTable database
connection = sqlite3.connect("gfg.db")
 
# cursor object
crsr = connection.cursor()
 
# execute the command to fetch all the data from the table emp
crsr.execute("SELECT * FROM emp")
 
# store all the fetched data in the ans variable
ans = crsr.fetchall()
 
# Since we have already selected all the data entries
# using the "SELECT *" SQL command and stored them in
# the ans variable, all we need to do now is to print
# out the ans variable
for i in ans:
    print(i)
Output:

fetch data python sqlite3

Note: It should be noted that the database file that will be created will be in the same folder as that of the python file. If we wish to change the path of the file, change the path while opening the file.

Updating Data
For updating the data in the SQLite3 table we will use the UPDATE statement. We can update single columns as well as multiple columns using the UPDATE statement as per our requirement.

UPDATE table_name SET column1 = value1, column2 = value2,…  
WHERE condition; 
In the above syntax, the SET statement is used to set new values to the particular column, and the WHERE clause is used to select the rows for which the columns are needed to be updated. 

Example: Updating SQLite3 table using Python

# Import module
import sqlite3
 
# Connecting to sqlite
conn = sqlite3.connect('gfg.db')
 
# Creating a cursor object using
# the cursor() method
cursor = conn.cursor()
 
# Updating
cursor.execute('''UPDATE emp SET lname = "Jyoti" WHERE fname="Rishabh";''')
 
# Commit your changes in the database
conn.commit()
 
# Closing the connection
conn.close()
Output:

update sqlite3 table using Python

Deleting Data
For deleting the data from the SQLite3 table we can use the delete command. 

DELETE FROM table_name [WHERE Clause]
Example: Deleting from SQLite3 table using Python

# Import module
import sqlite3
 
# Connecting to sqlite
conn = sqlite3.connect('gfg.db')
 
# Creating a cursor object using
# the cursor() method
cursor = conn.cursor()
 
# Updating
cursor.execute('''DELETE FROM emp WHERE fname="Rishabh";''')
 
# Commit your changes in the database
conn.commit()
 
# Closing the connection
conn.close()
Output:

Deleting from SQLite3 table using Python

Deleting Table
DROP is used to delete the entire database or a table. It deleted both records in the table along with the table structure.

Syntax: 

DROP TABLE TABLE_NAME;
Example: Drop SQLite3 table using Python
Total tables in the gfg.db before dropping

drop sqlite3 table using Python

Now let’s drop the Student table and then again check the total table in our database.


# Import module
import sqlite3
 
# Connecting to sqlite
conn = sqlite3.connect('gfg.db')
 
# Creating a cursor object using
# the cursor() method
cursor = conn.cursor()
 
# Updating
cursor.execute('''DROP TABLE Student;''')
 
# Commit your changes in the database
conn.commit()
 
# Closing the connection
conn.close()
