---
tags:
  - inheritance
  - OOP
  - Python
---
For more detail look into this [link](https://www.geeksforgeeks.org/inheritance-in-python/)

# Syntax 
```python
Class BaseClass:
	{Body}  
Class DerivedClass(BaseClass):  
	{Body}  
```
# Creating parent class
```py
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

```
# Creating child class
```py
class Emp(Person):

	def Print(self):
		print("Emp class called")
		
Emp_details = Emp("Mayank", 103)

# calling parent class function
Emp_details.Display()

# Calling child class function
Emp_details.Print()

```
 So Emp will be inherited from class person. Variable of Emp will then have all functions and attributes from class Person.
# The super() function

The super() function will return the objects that represent the parent class. For example:
```py
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

```
So it will first print out the student Rahul inside the class with obj.display() function from parent class, and displayInfo return the Mayank. 
**Attention :** The class name should be different between parent and children class otherwise it will be overwritten.

# Single and Multiple inheritances
```py
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
```
The child class will be able to call all functions from its parent classes.

