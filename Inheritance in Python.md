# Inheritance in Python
- One of the core concepts in object-oriented programming (OOP) languages is inheritance. It is a mechanism that allows you to create a hierarchy of classes that share a set of properties and methods by deriving a class from another class. Inheritance is the capability of one class to derive or inherit the properties from another class. 

Benefits of inheritance are:

Inheritance allows you to inherit the properties of a class, i.e., base class to another, i.e., derived class. The benefits of Inheritance in Python are as follows:

It represents real-world relationships well.
It provides the reusability of a code. We don’t have to write the same code again and again. Also, it allows us to add more features to a class without modifying it.
It is transitive in nature, which means that if class B inherits from another class A, then all the subclasses of B would automatically inherit from class A.
Inheritance offers a simple, understandable model structure. 
Less development and maintenance expenses result from an inheritance. 
Python Inheritance Syntax
The syntax of simple inheritance in Python is as follows:


Class BaseClass:
    {Body}
Class DerivedClass(BaseClass):
    {Body}
Creating a Parent Class
A parent class is a class whose properties are inherited by the child class. Let’s create a parent class called Person which has a Display method to display the person’s information.


# A Python program to demonstrate inheritance
class Person(object):
   
  # Constructor
  def __init__(self, name, id):
    self.name = name
    self.id = id
 
  # To check if this person is an employee
  def Display(self):
    print(self.name, self.id)
 
 
# Driver code
emp = Person("Satyam", 102) # An Object of Person
emp.Display()
Output:

Satyam 102
Creating a Child Class
A child class is a class that drives the properties from its parent class. Here Emp is another class that is going to inherit the properties of the Person class(base class).


class Emp(Person):
   
  def Print(self):
    print("Emp class called")
     
Emp_details = Emp("Mayank", 103)
 
# calling parent class function
Emp_details.Display()
 
# Calling child class function
Emp_details.Print()
Output:

Mayank 103
Emp class called
Example of Inheritance in Python 
Let us see an example of simple Python inheritance in which a child class is inheriting the properties of its parent class. In this example, ‘Person’ is the parent class, and ‘Employee’ is its child class.

# A Python program to demonstrate inheritance
 
# Base or Super class. Note object in bracket.
# (Generally, object is made ancestor of all classes)
# In Python 3.x "class Person" is
# equivalent to "class Person(object)"
 
 
class Person(object):
 
    # Constructor
    def __init__(self, name):
        self.name = name
 
    # To get name
    def getName(self):
        return self.name
 
    # To check if this person is an employee
    def isEmployee(self):
        return False
 
 
# Inherited or Subclass (Note Person in bracket)
class Employee(Person):
 
    # Here we return true
    def isEmployee(self):
        return True
 
 
# Driver code
emp = Person("Geek1")  # An Object of Person
print(emp.getName(), emp.isEmployee())
 
emp = Employee("Geek2")  # An Object of Employee
print(emp.getName(), emp.isEmployee())
Output: 

Geek1 False
Geek2 True
What is an object class in Python?
Like the Java Object class, in Python (from version 3. x), the object is the root of all classes. 

In Python 3.x, “class Test(object)” and “class Test” are same. 
In Python 2. x, “class Test(object)” creates a class with the object as a parent (called a new-style class), and “class Test” creates an old-style class (without an objecting parent). 
Subclassing (Calling constructor of parent class)
A child class needs to identify which class is its parent class. This can be done by mentioning the parent class name in the definition of the child class. 

Example: class subclass_name (superclass_name)


In this example, ‘a’ is the instance created for the class Person. It invokes the __init__() of the referred class. You can see ‘object’ written in the declaration of the class Person. In Python, every class inherits from a built-in basic class called ‘object’. The constructor i.e. the ‘__init__’ function of a class is invoked when we create an object variable or an instance of the class.

The variables defined within __init__() are called instance variables or objects. Hence, ‘name’ and ‘idnumber’ are the objects of the class Person. Similarly, ‘salary’ and ‘post’ are the objects of the class Employee. Since the class Employee inherits from class Person, ‘name’ and ‘idnumber’ are also the objects of class Employee.

# Python code to demonstrate how parent constructors
# are called.
 
# parent class
class Person(object):
 
    # __init__ is known as the constructor
    def __init__(self, name, idnumber):
        self.name = name
        self.idnumber = idnumber
 
    def display(self):
        print(self.name)
        print(self.idnumber)
 
# child class
class Employee(Person):
    def __init__(self, name, idnumber, salary, post):
        self.salary = salary
        self.post = post
 
        # invoking the __init__ of the parent class
        Person.__init__(self, name, idnumber)
 
# creation of an object variable or an instance
a = Employee('Rahul', 886012, 200000, "Intern")
 
# calling a function of the class Person using its instance
a.display()
Output: 

Rahul
886012
Python program to demonstrate error if we forget to invoke __init__() of the parent
If you forget to invoke the __init__() of the parent class then its instance variables would not be available to the child class. The following code produces an error for the same reason. 

class A:
    def __init__(self, n='Rahul'):
        self.name = n
 
class B(A):
    def __init__(self, roll):
        self.roll = roll
 
object = B(23)
print(object.name)
Output : 

Traceback (most recent call last):
  File "/home/de4570cca20263ac2c4149f435dba22c.py", line 12, in 
    print (object.name)
AttributeError: 'B' object has no attribute 'name'
The super() Function
The super() function is a built-in function that returns the objects that represent the parent class. It allows to access the parent class’s methods and attributes in the child class.

Example: super() function with simple Python inheritance

In this example, we created the object ‘obj’ of the child class. When we called the constructor of the child class ‘Student’, it initialized the data members to the values passed during the object creation. Then using the super() function, we invoked the constructor of the parent class.


# parent class
class Person():
  def __init__(self, name, age):
    self.name = name
    self.age = age
 
  def display(self):
    print(self.name, self.age)
 
# child class
class Student(Person):
  def __init__(self, name, age):
    self.sName = name
    self.sAge = age
    # inheriting the properties of parent class
    super().__init__("Rahul", age)
 
  def displayInfo(self):
    print(self.sName, self.sAge)
 
obj = Student("Mayank", 23)
obj.display()
obj.displayInfo()
Output:

Rahul 23
Mayank 23
Adding Properties
One of the features that inheritance provides is inheriting the properties of the parent class as well as adding new properties of our own to the child class. Let us see this with an example:


# parent class
class Person():
  def __init__(self, name, age):
    self.name = name
    self.age = age
 
  def display(self):
    print(self.name, self.age)
 
# child class
class Student(Person):
  def __init__(self, name, age, dob):
    self.sName = name
    self.sAge = age
    self.dob = dob
    # inheriting the properties of parent class
    super().__init__("Rahul", age)
 
  def displayInfo(self):
    print(self.sName, self.sAge, self.dob)
 
obj = Student("Mayank", 23, "16-03-2000")
obj.display()
obj.displayInfo()
Output:

Here we can see that we added a new property to the child class, i.e., date of birth (dob).

Rahul 23
Mayank 23 16-03-2000
Different types of Python Inheritance
There are 5 different types of inheritance in Python. They are as follows:

Single inheritance: When a child class inherits from only one parent class, it is called single inheritance. We saw an example above.
Multiple inheritances: When a child class inherits from multiple parent classes, it is called multiple inheritances. 
Unlike Java, python shows multiple inheritances.

# Python example to show the working of multiple
# inheritance
 
class Base1(object):
    def __init__(self):
        self.str1 = "Geek1"
        print("Base1")
 
 
class Base2(object):
    def __init__(self):
        self.str2 = "Geek2"
        print("Base2")
 
 
class Derived(Base1, Base2):
    def __init__(self):
 
        # Calling constructors of Base1
        # and Base2 classes
        Base1.__init__(self)
        Base2.__init__(self)
        print("Derived")
 
    def printStrs(self):
        print(self.str1, self.str2)
 
 
ob = Derived()
ob.printStrs()
Output: 

Base1
Base2
Derived
Geek1 Geek2
Multilevel inheritance: When we have a child and grandchild relationship. This means that a child class will inherit from its parent class, which in turn is inheriting from its parent class.

# A Python program to demonstrate inheritance
 
# Base or Super class. Note object in bracket.
# (Generally, object is made ancestor of all classes)
# In Python 3.x "class Person" is
# equivalent to "class Person(object)"
 
class Base(object):
 
    # Constructor
    def __init__(self, name):
        self.name = name
 
    # To get name
    def getName(self):
        return self.name
 
 
# Inherited or Sub class (Note Person in bracket)
class Child(Base):
 
    # Constructor
    def __init__(self, name, age):
        Base.__init__(self, name)
        self.age = age
 
    # To get name
    def getAge(self):
        return self.age
 
# Inherited or Sub class (Note Person in bracket)
 
 
class GrandChild(Child):
 
    # Constructor
    def __init__(self, name, age, address):
        Child.__init__(self, name, age)
        self.address = address
 
    # To get address
    def getAddress(self):
        return self.address
 
 
# Driver code
g = GrandChild("Geek1", 23, "Noida")
print(g.getName(), g.getAge(), g.getAddress())
Output: 

Geek1 23 Noida
Hierarchical inheritance More than one derived class can be created from a single base.
Hybrid inheritance: This form combines more than one form of inheritance. Basically, it is a blend of more than one type of inheritance.
For more details please read this article: Types of inheritance in Python

Private members of the parent class 
We don’t always want the instance variables of the parent class to be inherited by the child class i.e. we can make some of the instance variables of the parent class private, which won’t be available to the child class. 

In Python inheritance, we can make an instance variable private by adding double underscores before its name. For example:


# Python program to demonstrate private members
# of the parent class
 
class C(object):
    def __init__(self):
        self.c = 21
 
        # d is private instance variable
        self.__d = 42
 
 
class D(C):
    def __init__(self):
        self.e = 84
        C.__init__(self)
 
object1 = D()
 
# produces an error as d is private instance variable
print(object1.c)
print(object1.__d)
Output : 

Here we can see that when we tried to print the variable ‘c’, its value 21 is printed on the console. Whereas when we tried to print ‘d’, it generated the error. This is because the variable ‘d’ is made private by using the underscores. It is not available to the child class ‘D’ and hence the error.

21
  File "/home/993bb61c3e76cda5bb67bd9ea05956a1.py", line 16, in 
    print (object1.d)                     
AttributeError: type object 'D' has no attribute 'd'
