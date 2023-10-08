What are Pickling and Unpickling in Python?
PythonProgrammingServer Side Programming

To serialize and de-serialize a Python object structure, we have the Pickle module in Python. The pickle module implements binary protocols for serializing and de-serializing a Python object structure.

Pickling is the process through which a Python object hierarchy is converted into a byte stream. To serialize an object hierarchy, you simply call the dumps() function.

Unpickling is the inverse operation. A byte stream from a binary file or bytes-like object is converted back into an object hierarchy. To de-serialize a data stream, you call the loads() function.

Pickling and unpickling are alternatively known as serialization.

What can be pickled and unpickled?
In Python, the following types can be pickled −

None, True, and False.
integers, floating-point numbers, complex numbers.
strings, bytes, bytearrays.
tuples, lists, sets, and dictionaries containing only picklable objects.
functions, built-in and user-defined.
Pickle Module Constants
The following are the constants provided by the pickle module −

pickle.HIGHEST_PROTOCOL − The highest protocol version available. Integer value.

pickle.DEFAULT_PROTOCOL − The default protocol version used for pickling. Integer value. Currently the default protocol is 4

Pickle Module Functions
The following are the functions provided by the pickle module −

pickle.dump() − Write the pickled representation of the object to the open file object file.

pickle.dumps() − Return the pickled representation of the object as a bytes object, instead of writing it to a file.

pickle.load() − Read the pickled representation of an object from the open file object file.

pickle.loads() − Return the reconstituted object hierarchy of the pickled representation data of an object

Example
First, the pickle module is imported −

import pickle
We have created the following input to be pickled.

my_data = { 'BMW', 'Audi', 'Toyota', 'Benz'}
The demo.pickle file is created. This same .pickle file is pickled with the above list

with open("demo.pickle","wb") as file_handle:
   pickle.dump(my_data, file_handle, pickle.HIGHEST_PROTOCOL)
Now, unpickle the above pickled file and get the input values back.

with open("demo.pickle","rb") as file_handle:
   res = pickle.load(file_handle)
   print(res_data)
Let us now see the complete example

import pickle

# Input Data
my_data = { 'BMW', 'Audi', 'Toyota', 'Benz'}

# Pickle the input
with open("demo.pickle","wb") as file_handle:
   pickle.dump(my_data, file_handle, pickle.HIGHEST_PROTOCOL)

# Unpickle the above pickled file
with open("demo.pickle","rb") as file_handle:
   res = pickle.load(file_handle)
   print(my_data) # display the output
Output
{'Benz', 'Toyota', 'Audi', 'BMW'}
