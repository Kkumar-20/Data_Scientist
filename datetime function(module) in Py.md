# Python datetime module
- In Python, date and time are not data types of their own, but a module named DateTime can be imported to work with the date as well as time. Python Datetime module comes built into Python, so there is no need to install it externally. 

Python DateTime module
Python Datetime module supplies classes to work with date and time. These classes provide a number of functions to deal with dates, times, and time intervals. Date and DateTime are an object in Python, so when you manipulate them, you are actually manipulating objects and not strings or timestamps. 

The DateTime module is categorized into 6 main classes – 

date – An idealized naive date, assuming the current Gregorian calendar always was, and always will be, in effect. Its attributes are year, month, and day.
time – An idealized time, independent of any particular day, assuming that every day has exactly 24*60*60 seconds. Its attributes are hour, minute, second, microsecond, and tzinfo.
datetime – Its a combination of date and time along with the attributes year, month, day, hour, minute, second, microsecond, and tzinfo.
timedelta – A duration expressing the difference between two date, time, or datetime instances to microsecond resolution.
tzinfo – It provides time zone information objects.
timezone – A class that implements the tzinfo abstract base class as a fixed offset from the UTC (New in version 3.2).
Python Date Class
The date class is used to instantiate date objects in Python. When an object of this class is instantiated, it represents a date in the format YYYY-MM-DD. The constructor of this class needs three mandatory arguments year, month, and date.


Python Date class Syntax
class datetime.date(year, month, day)
The arguments must be in the following range –  

MINYEAR <= year <= MAXYEAR
1 <= month <= 12
1 <= day <= number of days in the given month and year
Note – If the argument is not an integer it will raise a TypeError and if it is outside the range a ValueError will be raised. 

Date object representing data in Python
Initializing the constructor and passing arguments in the format year, month, and date.


# Python program to 
# demonstrate date class 
  
# import the date class 
from datetime import date 
  
my_date = date(1996, 12, 11) 
  
print("Date passed as argument is", my_date) 
  
# Uncommenting my_date = date(1996, 12, 39) 
# will raise an ValueError as it is 
# outside range 
  
# uncommenting my_date = date('1996', 12, 11) 
# will raise a TypeError as a string is 
# passed instead of integer 
Output: 

Date passed as argument is 1996-12-11
Traceback (most recent call last):
  File "/home/ccabfb570d9bd1dcd11dc4fe55fd6ba2.py", line 14, in 
    my_date = date(1996, 12, 39)
ValueError: day is out of range for month

Traceback (most recent call last):
  File "/home/53b974e10651f1853eee3c004b48c481.py", line 18, in 
    my_date = date('1996', 12, 11)
TypeError: an integer is required (got type str) 
Get the Current Date
To return the current local date today() function of the date class is used. today() function comes with several attributes (year, month, and day). These can be printed individually. 


# Python program to 
# print current date 
  
from datetime import date 
  
# calling the today 
# function of date class 
today = date.today() 
  
print("Today's date is", today) 
Output
Today's date is 2021-08-19
Get Today’s Year, Month, and Date
We can get the year, month, and date attributes from the date object using the year, month and date attribute of the date class.


from datetime import date 
  
# date object of today's date 
today = date.today()  
  
print("Current year:", today.year) 
print("Current month:", today.month) 
print("Current day:", today.day)
Output
Current year: 2021
Current month: 8
Current day: 19
Get Date from Timestamp
We can create date objects from timestamps y=using the fromtimestamp() method. The timestamp is the number of seconds from 1st January 1970 at UTC to a particular date.



from datetime import datetime 
  
# Getting Datetime from timestamp 
date_time = datetime.fromtimestamp(1887639468) 
print("Datetime from timestamp:", date_time) 
Output
Datetime from timestamp: 2029-10-25 16:17:48
Convert Date to String
We can convert date object to a string representation using two functions isoformat() and strftime().


from datetime import date 
    
# calling the today 
# function of date class 
today = date.today() 
    
# Converting the date to the string 
Str = date.isoformat(today) 
print("String Representation", Str) 
print(type(Str))
Output
String Representation 2021-08-19
<class 'str'>
List of Date Class Methods
Function Name 	
Description

ctime()	Return a string representing the date
fromisocalendar()	Returns a date corresponding to the ISO calendar
fromisoformat()	Returns a date object from the string representation of the date
fromordinal()	Returns a date object from the proleptic Gregorian ordinal, where January 1 of year 1 has ordinal 1
fromtimestamp()	Returns a date object from the POSIX timestamp
isocalendar()	Returns a tuple year, week, and weekday
isoformat()	Returns the string representation of the date
isoweekday()	Returns the day of the week as an integer where Monday is 1 and Sunday is 7
replace()	Changes the value of the date object with the given parameter
strftime()	Returns a string representation of the date with the given format
timetuple()	Returns an object of type time.struct_time
today()	Returns the current local date
toordinal()	Return the proleptic Gregorian ordinal of the date, where January 1 of year 1 has ordinal 1
weekday()	Returns the day of the week as integer where Monday is 0 and Sunday is 6
Python Time class
The time class creates the time object which represents local time, independent of any day. 

Constructor Syntax:

class datetime.time(hour=0, minute=0, second=0, microsecond=0, tzinfo=None, *, fold=0)

All the arguments are optional. tzinfo can be None otherwise all the attributes must be integer in the following range – 

0 <= hour < 24
0 <= minute < 60
0 <= second < 60
0 <= microsecond < 1000000
fold in [0, 1]
Example 1: Time object representing time in Python

# Python program to 
# demonstrate time class 
  
from datetime import time 
  
# calling the constructor 
my_time = time(13, 24, 56) 
  
print("Entered time", my_time) 
  
# calling constructor with 1 
# argument 
my_time = time(minute=12) 
print("\nTime with one argument", my_time) 
  
# Calling constructor with 
# 0 argument 
my_time = time() 
print("\nTime without argument", my_time) 
  
# Uncommenting time(hour = 26) 
# will rase an ValueError as 
# it is out of range 
  
# uncommenting time(hour ='23') 
# will raise TypeError as 
# string is passed instead of int 
Output: 

Entered time 13:24:56

Time with one argument 00:12:00

Time without argument 00:00:00
Traceback (most recent call last):
  File "/home/95ff83138a1b3e67731e57ec6dddef25.py", line 21, in 
    print(time(hour=26))
ValueError: hour must be in 0..23

Traceback (most recent call last):
  File "/home/fcee9ba5615b0b74fc3ba39ec9a789fd.py", line 21, in 
    print(time(hour='23'))
TypeError: an integer is required (got type str)
Example 2: Get hours, minutes, seconds, and microseconds
After creating a time object, its attributes can also be printed separately. 


from datetime import time 
  
Time = time(11, 34, 56) 
  
print("hour =", Time.hour) 
print("minute =", Time.minute) 
print("second =", Time.second) 
print("microsecond =", Time.microsecond) 
Output: 

hour = 11
minute = 34
second = 56
microsecond = 0
Example 3: Convert Time object to String
We can convert time object to string using the isoformat() method.


from datetime import time 
  
# Creating Time object 
Time = time(12,24,36,1212) 
  
# Converting Time object to string 
Str = Time.isoformat() 
print("String Representation:", Str) 
print(type(Str))
Output
String Representation: 12:24:36.001212
<class 'str'>
List of Time class Methods
Function Name	
Description

dst()	Returns tzinfo.dst() is tzinfo is not None
fromisoformat()	Returns a time object from the string representation of the time
isoformat()	Returns the string representation of time from the time object
replace()	Changes the value of the time object with the given parameter
strftime()	Returns a string representation of the time with the given format
tzname()	Returns tzinfo.tzname() is tzinfo is not None
utcoffset()	Returns tzinfo.utcffsets() is tzinfo is not None
Python Datetime class
The DateTime class contains information on both date and time. Like a date object, datetime assumes the current Gregorian calendar extended in both directions; like a time object, datetime assumes there are exactly 3600*24 seconds in every day.

Constructor Syntax: 

class datetime.datetime(year, month, day, hour=0, minute=0, second=0, microsecond=0, tzinfo=None, *, fold=0) 
 

The year, month, and day arguments are mandatory. tzinfo can be None, rest all the attributes must be an integer in the following range –  

MINYEAR <= year <= MAXYEAR
1 <= month <= 12
1 <= day <= number of days in the given month and year
0 <= hour < 24
0 <= minute < 60
0 <= second < 60
0 <= microsecond < 1000000
fold in [0, 1]
Note – Passing an argument other than integer will raise a TypeError and passing arguments outside the range will raise ValueError.

DateTime object representing DateTime in Python 

# Python program to 
# demonstrate datetime object 
  
from datetime import datetime 
  
# Initializing constructor 
a = datetime(1999, 12, 12) 
print(a) 
  
# Initializing constructor 
# with time parameters as well 
a = datetime(1999, 12, 12, 12, 12, 12, 342380) 
print(a) 
Output: 

1999-12-12 00:00:00
1999-12-12 12:12:12.342380
Get year, month, hour, minute, and timestamp
After creating a DateTime object, its attributes can also be printed separately.


from datetime import datetime 
  
a = datetime(1999, 12, 12, 12, 12, 12) 
  
print("year =", a.year) 
print("month =", a.month) 
print("hour =", a.hour) 
print("minute =", a.minute) 
print("timestamp =", a.timestamp()) 
Output: 

year = 1999
month = 12
hour = 12
minute = 12
timestamp = 945000732.0
Current date and time
You can print the current date and time using the Datetime.now() function. now() function returns the current local date and time. 


from datetime import datetime 
  
# Calling now() function 
today = datetime.now() 
  
print("Current date and time is", today) 
Output: 

Current date and time is 2019-10-25 11:12:11.289834
Convert Python Datetime to String
We can convert Datetime to string in Python using the datetime.strftime and datetime.isoformat methods. 


from datetime import datetime as dt 
  
# Getting current date and time 
now = dt.now() 
  
string = dt.isoformat(now) 
print(string) 
print(type(string)) 
Output
2021-08-19T18:13:25.346259
<class 'str'>
List of Datetime Class Methods
Function Name	
Description

astimezone()	Returns the DateTime object containing timezone information.
combine()	Combines the date and time objects and return a DateTime object
ctime()	Returns a string representation of date and time
date()	Return the Date class object
fromisoformat()	Returns a datetime object from the string representation of the date and time
fromordinal()	Returns a date object from the proleptic Gregorian ordinal, where January 1 of year 1 has ordinal 1. The hour, minute, second, and microsecond are 0
fromtimestamp()	Return date and time from POSIX timestamp
isocalendar()	Returns a tuple year, week, and weekday
isoformat()	Return the string representation of date and time
isoweekday()	Returns the day of the week as integer where Monday is 1 and Sunday is 7
now()	Returns current local date and time with tz parameter
replace()	Changes the specific attributes of the DateTime object
strftime()	Returns a string representation of the DateTime object with the given format
strptime()	Returns a DateTime object corresponding to the date string
time()	Return the Time class object
timetuple()	Returns an object of type time.struct_time
timetz()	Return the Time class object
today()	Return local DateTime with tzinfo as None
toordinal()	Return the proleptic Gregorian ordinal of the date, where January 1 of year 1 has ordinal 1
tzname()	Returns the name of the timezone
utcfromtimestamp()	Return UTC from POSIX timestamp
utcoffset()	Returns the UTC offset
utcnow()	Return current UTC date and time
weekday()	Returns the day of the week as integer where Monday is 0 and Sunday is 6
Python Timedelta Class
Python timedelta class is used for calculating differences in dates and also can be used for date manipulations in Python. It is one of the easiest ways to perform date manipulations.

Constructor syntax:  

class datetime.timedelta(days=0, seconds=0, microseconds=0, milliseconds=0, minutes=0, hours=0, weeks=0)
Returns : Date 

Add days to DateTime object
The timedelta function demonstration


from datetime import datetime, timedelta 
  
# Using current time 
ini_time_for_now = datetime.now() 
  
# printing initial_date 
print("initial_date", str(ini_time_for_now)) 
  
# Calculating future dates 
# for two years 
future_date_after_2yrs = ini_time_for_now + timedelta(days=730) 
  
future_date_after_2days = ini_time_for_now + timedelta(days=2) 
  
# printing calculated future_dates 
print('future_date_after_2yrs:', str(future_date_after_2yrs)) 
print('future_date_after_2days:', str(future_date_after_2days)) 
Output: 

initial_date 2019-10-25 12:01:01.227848
future_date_after_2yrs: 2021-10-24 12:01:01.227848
future_date_after_2days: 2019-10-27 12:01:01.227848
Difference between two date and times
Date and Time differences can also be found using this class.


# Timedelta function demonstration 
from datetime import datetime, timedelta 
  
# Using current time 
ini_time_for_now = datetime.now() 
  
# printing initial_date 
print("initial_date", str(ini_time_for_now)) 
  
# Some another datetime 
new_final_time = ini_time_for_now + \ 
    timedelta(days=2) 
  
# printing new final_date 
print("new_final_time", str(new_final_time)) 
  
  
# printing calculated past_dates 
print('Time difference:', str(new_final_time -
                              ini_time_for_now)) 
Output: 

initial_date 2019-10-25 12:02:32.799814
new_final_time 2019-10-27 12:02:32.799814
Time difference: 2 days, 0:00:00
Operations supported by Timedelta Class
Operator	
Description

Addition (+)	Adds and returns two timedelta objects
Subtraction (-)	Subtracts and returns two timedelta objects
Multiplication (*)	Multiplies timedelta object with float or int 
Division (/)	Divides the timedelta object with float or int
Floor division (//)	Divides the timedelta object with float or int and return the int of floor value of the output 
Modulo (%)	Divides two timedelta object and returns the remainder
+(timedelta)	Returns the same timedelta object
-(timedelta)	Returns the resultant of -1*timedelta
abs(timedelta)	Returns the +(timedelta) if timedelta.days > 1=0 else returns -(timedelta)
str(timedelta)	Returns a string in the form (+/-) day[s],  HH:MM:SS.UUUUUU
repr(timedelta)	Returns the string representation in the form of the constructor call
Format DateTime in Python
Formatting DateTime can be very necessary as the date representation may differ from place to place. In some countries, it can be yyyy-mm-dd and in other countries, it can be dd-mm-yyyy. To format Python Datetime strptime and strftime functions can be used.

Python Datetime strftime                    
A strftime() method converts the given date, time, or DateTime object to the string representation of the given format.

Python Datetime format
Python program to demonstrate strftime() function


from datetime import datetime as dt 
  
# Getting current date and time 
now = dt.now() 
print("Without formatting", now) 
  
# Example 1 
s = now.strftime("%A %m %-Y") 
print('\nExample 1:', s) 
  
# Example 2 
s = now.strftime("%a %-m %y") 
print('\nExample 2:', s) 
  
# Example 3 
s = now.strftime("%-I %p %S") 
print('\nExample 3:', s) 
  
# Example 4 
s = now.strftime("%H:%M:%S") 
print('\nExample 4:', s) 
Output
Without formatting 2021-08-19 18:16:25.881661

Example 1: Thursday 08 2021

Example 2: Thu 8 21

Example 3: 6 PM 25

Example 4: 18:16:25
Note: For more information, refer to strftime() method.

Python DateTime strptime
The strptime() creates a DateTime object from the given string.

Example: DateTime strptime


# import datetime module from datetime 
from datetime import datetime 
   
# consider the time stamps from a list  in string  
# format DD/MM/YY H:M:S.micros 
time_data = ["25/05/99 02:35:8.023", "26/05/99 12:45:0.003", 
             "27/05/99 07:35:5.523", "28/05/99 05:15:55.523"] 
   
# format the string in the given format : day/month/year   
# hours/minutes/seconds-micro seconds 
format_data = "%d/%m/%y %H:%M:%S.%f"
   
# Using strptime with datetime we will format string  
# into datetime 
for i in time_data: 
    print(datetime.strptime(i, format_data))
Output
1999-05-25 02:35:08.023000
1999-05-26 12:45:00.003000
1999-05-27 07:35:05.523000
1999-05-28 05:15:55.523000
Python DateTime.tzinfo()
The datetime.now() function contains no information regarding time zones. It only makes use of the current system time. Tzinfo is an abstract base class in Python. It cannot be directly instantiated. A concrete subclass must derive from this abstract class and implement the methods offered by it. 

List of Python DateTime.tzinfo() Objects
Function Name	
Description

dst()	Returns tzinfo.dst() is tzinfo is not None
fromutc()	The purpose of this function is to adjust the date time data, 
returning an equivalent DateTime in self’s local time.
tzname()	Returns tzinfo.tzname() is tzinfo is not None
utcoffset()	Returns tzinfo.utcffsets() is tzinfo is not None
Example 

The tzinfo class instance can be provided to the DateTime and time object constructors. It is used in scenarios such as converting local time to UTC or accounting for daylight savings time.


import datetime as dt 
from dateutil import tz 
  
  
tz_string = dt.datetime.now(dt.timezone.utc).astimezone().tzname() 
  
print("datetime.now() :", tz_string) 
  
NYC = tz.gettz('Europe / Berlin') 
dt1 = dt.datetime(2022, 5, 21, 12, 0) 
dt2 = dt.datetime(2022, 12, 21, 12, 0, tzinfo=NYC) 
  
print("Naive Object :", dt1.tzname()) 
print("Aware Object :", dt2.tzname()) 
Output:

datetime.now() : IST
Naive Object : None
Aware Object : None
Python DateTime timezone
Timezones in DateTime can be used in the case where one might want to display time according to the timezone of a specific region. This can be done using the pytz module of Python. This module serves the date-time conversion functionalities and helps users serving international client bases.


from datetime import datetime 
from pytz import timezone 
  
format = "%Y-%m-%d %H:%M:%S %Z%z"
  
# Current time in UTC 
now_utc = datetime.now(timezone('UTC')) 
print(now_utc.strftime(format)) 
  
timezones = ['Asia/Kolkata', 'Europe/Kiev', 'America/New_York'] 
  
for tzone in timezones: 
  
    # Convert to Asia/Kolkata time zone 
    now_asia = now_utc.astimezone(timezone(tzone)) 
    print(now_asia.strftime(format)) 
