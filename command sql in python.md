Introduction to Psycopg2 module in Python
Read
Discuss
Courses
Practice
Psycopg is the most popular PostgreSQL adapter used in  Python.  Its works on the principle of the whole implementation of Python DB API 2.0 along with the thread safety (the same connection is shared by multiple threads). It is designed to perform heavily multi-threaded applications that usually create and destroy lots of cursors and make a large number of simultaneous INSERTS or UPDATES. Psycopg features client-side and server-side cursors, asynchronous communication, and notification. Psycopg 2 is both Unicode and Python 3 friendly.

Installation:
The current psycopg2 implementation supports:

Python versions from 3.6 to 3.10
PostgreSQL server versions from 7.4 to 14
PostgreSQL client library version from 9.1
pgAdmin 4
For most of the available Operating Systems, the quickest way to install this package is through the wheel package available in the PyPI library. We must make sure that we use the latest version of pip, which can be updated using the following command in the terminal.

$ pip install -U pip
$ pip install psycopg2-binary
This will install the pre-compiled binary version of the module which doesn’t require the built or runtime prerequisites. Then we can import the psycopg2 package in the usual manner:


Basic module usage:
The basic use of Psycopg is in implementing the DB API 2.0 protocol to all the database adapters. Here is the basic interactive session of the basic commands.

Example 1: Program to establish a connection between python program and a PostgreSQL database.

import psycopg2
 
DB_NAME = "tkgafrwp"
DB_USER = "tkgafrwp"
DB_PASS = "iYYtLAXVbid-i6MV3NO1EnU-_9SW2uEi"
DB_HOST = "tyke.db.elephantsql.com"
DB_PORT = "5432"
 
try:
    conn = psycopg2.connect(database=DB_NAME,
                            user=DB_USER,
                            password=DB_PASS,
                            host=DB_HOST,
                            port=DB_PORT)
    print("Database connected successfully")
except:
    print("Database not connected successfully")
 
 



 

Example 2: Creating a table using python

 

import psycopg2
 
DB_NAME = "tkgafrwp"
DB_USER = "tkgafrwp"
DB_PASS = "iYYtLAXVbid-i6MV3NO1EnU-_9SW2uEi"
DB_HOST = "tyke.db.elephantsql.com"
DB_PORT = "5432"
conn = psycopg2.connect(database=DB_NAME,
                        user=DB_USER,
                        password=DB_PASS,
                        host=DB_HOST,
                        port=DB_PORT)
print("Database connected successfully")
 
cur = conn.cursor()  # creating a cursor
 
# executing queries to create table
cur.execute("""
CREATE TABLE Employee
(
    ID INT   PRIMARY KEY NOT NULL,
    NAME TEXT NOT NULL,
    EMAI TEXT NOT NULL
)
""")
 
# commit the changes
conn.commit()
print("Table Created successfully")



Example 3: Inserting data into the table:

import psycopg2
 
DB_NAME = "tkgafrwp"
DB_USER = "tkgafrwp"
DB_PASS = "iYYtLAXVbid-i6MV3NO1EnU-_9SW2uEi"
DB_HOST = "tyke.db.elephantsql.com"
DB_PORT = "5432"
conn = psycopg2.connect(database=DB_NAME, user=DB_USER, password=DB_PASS,
                        host=DB_HOST, port=DB_PORT)
print("Database connected successfully")
 
cur = conn.cursor()
cur.execute("""
    INSERT INTO Employee (ID,NAME,EMAIL) VALUES
    (1,'Alan Walker','awalker@gmail.com'), 
    (2,'Steve Jobs','sjobs@gmail.com')
  """)
conn.commit()
conn.close()


Passing parameters to SQL queries
Python variables are converted to SQL values with Psycopg, Python determines the function used to convert the object into a string representation suitable for PostgreSQL.Passing parameters to an SQL statement happens in functions such as cursor.execute() by using %s as the placeholder into the SQL statement.

Example 4: Fetching the data from the database and displaying it into the terminal.

from mysqlx import Row
import psycopg2
 
DB_NAME = "tkgafrwp"
DB_USER = "tkgafrwp"
DB_PASS = "iYYtLAXVbid-i6MV3NO1EnU-_9SW2uEi"
DB_HOST = "tyke.db.elephantsql.com"
DB_PORT = "5432"
conn = psycopg2.connect(database=DB_NAME,
                        user=DB_USER,
                        password=DB_PASS,
                        host=DB_HOST,
                        port=DB_PORT)
print("Database connected successfully")
 
cur = conn.cursor()
cur.execute("SELECT * FROM Employee")
rows = cur.fetchall()
for data in rows:
    print("ID :" + str(data[0]))
    print("NAME :" + data[1])
    print("EMAIL :" + data[2])
 
print('Data fetched successfully')
conn.close()


Example 5: Updating the data in the database.

from turtle import st
from mysqlx import Row
import psycopg2
 
DB_NAME = "tkgafrwp"
DB_USER = "tkgafrwp"
DB_PASS = "iYYtLAXVbid-i6MV3NO1EnU-_9SW2uEi"
DB_HOST = "tyke.db.elephantsql.com"
DB_PORT = "5432"
conn = psycopg2.connect(database=DB_NAME, user=DB_USER, password=DB_PASS,
                        host=DB_HOST, port=DB_PORT)
print("Database connected successfully")
 
cur = conn.cursor()
cur.execute("UPDATE Employee set EMAI = 'updated@gmail.com' WHERE ID =1 ")
conn.commit()
print("Data updated Successfully")
print("Total row affected "+str(cur.rowcount))
conn.close()


Example 6: Deleting data from the database.

from turtle import st
from mysqlx import Row
import psycopg2
 
DB_NAME = "tkgafrwp"
DB_USER = "tkgafrwp"
DB_PASS = "iYYtLAXVbid-i6MV3NO1EnU-_9SW2uEi"
DB_HOST = "tyke.db.elephantsql.com"
DB_PORT = "5432"
conn = psycopg2.connect(database=DB_NAME,user=DB_USER,password=DB_PASS,
                        host=DB_HOST,port=DB_PORT)
print("Database connected successfully")
 
cur = conn.cursor()
cur.execute("DELETE FROM Employee WHERE ID =1 ")
conn.commit()
print("Data deleted Successfully")
print("Total row affected "+str(cur.rowcount))
conn.close()
