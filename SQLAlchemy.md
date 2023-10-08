SQLAlchemy – Introduction
Read
Discuss
Courses
Practice
SQLAlchemy is basically referred to as the toolkit of Python SQL that provides developers with the flexibility of using the SQL database. The benefit of using this particular library is to allow Python developers to work with the language’s own objects, and not write separate SQL queries. They can basically use Python to access and work with databases. 

SQLAlchemy is also an Object Relational Mapper which is a technique used to convert data between databases or OOP languages such as Python.

Installation
Let’s take a look at the setup, and how to effectively set up an environment to be able to work with this particular library. Python version of 2.7 or higher is necessary to be able to install the library. There are two ways to install SQLAlchemy:

Step 1: The most efficient and easiest way is by using the Python Package Manager or pip . This can be easily done by typing the following command in the terminal:


pip install sqlalchemy
Step 2: However, in the case of anaconda distribution of Python or if you are using this particular platform, then you can install it from the conda terminal:

conda install -c anaconda sqlalchemy
Confirmation Command: To check if the library is installed properly or to check its version, you can use the following command (the version can be effectively displayed under which in this case, it is 1.3.24, and this is the latest version of SQLAlchemy:

>>> import sqlalchemy
>>>sqlalchemy.__version__
'1.3.24'
flow diagram of the installation Process
flow diagram of the installation Process

Connecting to the Database
Now to start connecting to the database in order to access the data and work with it, we need to first establish a connection by using the following command:

import sqlalchemy as db
 
engine = db.create_engine('dialect+driver://user:pass@host:port/db')
Example 1: 

Let’s say we want to get the details of movies from the file called films where the certification is PG. Assume there is a category called certification. To approach this in SQL, we would enter the following query:

SELECT *
FROM films
WHERE certification = 'PG'
Now using the SQLAlchemy library:

db.select([films]).where(films.columns.certification == 'PG')
There are certain commands used in the SQLAlchemy library, and although many keywords tend to essentially be the same as in SQL such as where the overall query is very different. Let’s take a look at another example and try to spot any differences/similarities between the SQL version and the SQLAlchemy library version.

Example 2: 

Get all details of the movies from the file called films where the certification is R and the release date is over 2003. Assume the following categories exist in the file, films: release_year, and certification

In SQL, we would approach it like this:

SELECT *
FROM files
WHERE certification = 'R' and release_year > 2003  
SQLAlchemy version:

db.select([films]).where(db.and_(films.columns.certification == 'R',
                                 films.columns.release_year > 2003))
