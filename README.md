![](img1.png)
## Introduction

In this research, I have given a brief overview of advanced topics in Python and Django. This article does not provide
in-depth knowledge on various topics and the purpose of this research is to collect topics in one place to provide the
reader with a mental framework. In this article, I have used very simple examples to explain the topics easily.
Naturally, studying and examining more and more practical examples will help a lot to understand each topic. I hope
reading this article is useful for you. (**Hamid Asgari**)

I am grateful to all my friends who have guided me in writing this article:
__Alireza Amouzadeh__ , __Zahra Rezaei__, __Shokooh Rigi__, __Saharnaz Rashidi__, __Ali Emamalinejad__
, __Malihe Sheidaiefar__, __Ali Lavasani__, __Fatemeh Pasandideh__

<!-- TOC -->
  * [Introduction](#introduction)
  * [Python related topics:](#python-related-topics)
    * [object-oriented programming (OOP)](#object-oriented-programming-oop)
      * [Inheritance](#inheritance)
      * [Polymorphism](#polymorphism)
      * [Encapsulation](#encapsulation)
      * [Abstraction](#abstraction)
    * [Decorators](#decorators)
    * [Map function](#map-function)
    * [Itertools](#itertools)
    * [Lambda function](#lambda-function)
    * [Exception Handling](#exception-handling)
    * [SOLID principles](#solid-principles)
    * [Python collection](#python-collection)
    * [Generators and Iterators](#generators-and-iterators)
    * [Magic methods](#magic-methods)
    * [GIL](#gil)
    * [concurrency and parallelism](#concurrency-and-parallelism)
    * [Main types of methods in python classes](#main-types-of-methods-in-python-classes)
    * [Data serialization](#data-serialization)
    * [Data class in python](#data-class-in-python)
    * [Shallow copy and deep copy](#shallow-copy-and-deep-copy)
    * [Local and global variables](#local-and-global-variables-)
    * [Comprehension](#comprehension)
    * [Pydantic](#pydantic)
    * [Args and Kwargs in Python](#args-and-kwargs-in-python)
    * [Operator overloading](#operator-overloading)
    * [Recursive function](#recursive-function)
    * [Context manager](#context-manager)
    * [More decorators in Python](#more-decorators-in-python)
  * [Django related topics:](#django-related-topics)
    * [Django signals](#django-signals)
    * [Django middleware](#django-middleware)
    * [Django custom template tags](#django-custom-template-tags)
    * [Django permissions](#django-permissions)
    * [Django custom user models](#django-custom-user-models)
    * [Django Custom Managers](#django-custom-managers)
    * [Django Custom validators](#django-custom-validators)
    * [Custom management commands](#custom-management-commands)
    * [Django's Query API](#djangos-query-api)
    * [Custom query expressions or Custom Lookup](#custom-query-expressions-or-custom-lookup)
    * [Django Filterset](#django-filterset)
    * [Context managers](#context-managers)
    * [Django Channels](#django-channels)
    * [HTTP methods in Django](#http-methods-in-django)
    * [annotate and aggregate in Django](#annotate-and-aggregate-in-django)
    * [Mixin in Django](#mixin-in-django)
    * [Cache in Django](#cache-in-django)
    * [Django constraint](#django-constraint)
      * [Django constraints and model validators differences](#django-constraints-and-model-validators-differences)
    * [bulk creation in Django](#bulk-creation-in-django)
    * [prefetch_related and select_related in Django](#prefetchrelated-and-selectrelated-in-django)
    * [Third-party packages in Django](#third-party-packages-in-django)
    * [Property decorators](#property-decorators)
    * [WSGI and ASGI](#wsgi-and-asgi)
      * [WSGI (Web Server Gateway Interface):](#wsgi-web-server-gateway-interface)
      * [ASGI (Asynchronous Server Gateway Interface):](#asgi-asynchronous-server-gateway-interface)
    * [Advanced features in ORM](#advanced-features-in-orm)
      * [Q objects:](#q-objects)
      * [F expressions:](#f-expressions-)
      * [QuerySet methods](#queryset-methods)
      * [Model managers](#model-managers)
      * [Model inheritance](#model-inheritance)
    * [Class-based views methods](#class-based-views-methods)
    * [Django optimization](#django-optimization)
      * [**Database Optimization:**](#database-optimization)
      * [**Caching:**](#caching-)
      * [**Code Optimization:**](#code-optimization-)
      * [**Distributed Task Queues:**](#distributed-task-queues-)
      * [**Scaling Horizontally:**](#scaling-horizontally)
      * [**Benchmarking:**](#benchmarking-)
    * [Generic Foreign Key in Django](#generic-foreign-key-in-django)
    * [Django custom exceptions](#django-custom-exceptions)
    * [select_for_update in Django](#selectforupdate-in-django)
<!-- TOC -->

## Python related topics:

### object-oriented programming (OOP)

Here are some of the most important topics in object-oriented programming (**OOP**) in Python, along with simple
examples of each:

#### Inheritance

Inheritance is a mechanism that allows a class to inherit properties and methods from another class. The class that
inherits from another class is called a subclass or derived class, while the class that is being inherited from is
called a superclass or base class.



```
class Animal:
    def __init__(self, name):
        self.name = name

    def speak(self):
        raise NotImplementedError("Subclass must implement abstract method")


class Dog(Animal):
    def speak(self):
        return "Woof!"

class Cat(Animal):
    def speak(self):
        return "Meow!"

dog = Dog("Fido")
print(dog.name)  # Output: Fido
print(dog.speak())  # Output: Woof!

cat = Cat("Whiskers")
print(cat.name)  # Output: Whiskers
```

In this example, Animal is the superclass, and Dog and Cat are subclasses that inherit from it. The speak method is an
abstract method in the Animal class that is implemented in the subclasses.

#### Polymorphism

Polymorphism is the ability of objects to take on different forms or perform different actions depending on the context.
In Python, polymorphism is achieved through **method overriding** and **method overloading**.

```
class Shape:
    def area(self):
        raise NotImplementedError("Subclass must implement abstract method")


class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def area(self):
        return self.width * self.height


class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return 3.14 * self.radius ** 2


shapes = [Rectangle(5, 10), Circle(7)]
for shape in shapes:
    print(shape.area())
```

In this example, Shape is an abstract class that defines the area method as an abstract method. Rectangle and Circle are
concrete subclasses that implement the area method. The shapes list contains instances of both Rectangle and Circle, and
the area method is called on each instance, demonstrating polymorphism.

#### Encapsulation

Encapsulation is the practice of hiding the internal details of an object and providing a public interface for
interacting with it. In Python, encapsulation is achieved through the use of public and private methods and attributes.

```
class BankAccount:
    def __init__(self, balance):
        self._balance = balance

    def deposit(self, amount):
        self._balance += amount

    def withdraw(self, amount):
        if self._balance >= amount:
            self._balance -= amount
        else:
            raise ValueError("Insufficient balance")

    def get_balance(self):
        return self._balance


account = BankAccount(1000)
account.deposit(500)
account.withdraw(200)
print(account.get_balance())  # Output: 1300
```

In this example, BankAccount is a class that represents a bank account. The **_balance** attribute is marked as private
by convention (using a single underscore), and can only be accessed through public methods such as deposit, withdraw,
and get_balance.

#### Abstraction

Abstraction is the process of simplifying complex systems by breaking them down into smaller, more manageable parts. In
Python, abstraction is achieved through the use of abstract classes and interfaces.

```
from abc import ABC, abstractmethod

class Shape(ABC):
    @abstractmethod
    def area(self):
        pass


class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def area(self):
        return self.width * self.height


shapes = [Rectangle(5, 10)]
for shape in shapes:
    print(shape.area())
```

In this example, Shape is an abstract class that defines the area method as an abstract method. Rectangle is a concrete
subclass that implements the area method. The shapes list contains an instance of Rectangle, demonstrating abstraction.

### Decorators

In Python, decorators are a way to modify the behavior of functions or classes by wrapping them with other functions.
Here's a simple example to demonstrate the basic concept of decorators:

```
def decorator_function(original_function):
    def wrapper_function():
        print("Before the original function is called.")
        original_function()
        print("After the original function is called.")
    return wrapper_function

@decorator_function
def greet():
    print("Hello, world!")

greet()
```

out put

```
Before the original function is called.
Hello, world!
After the original function is called.
```

Here is an example of how to implement the previous decorator in a class-based way:

```angular2html
class DecoratorClass:
    def __init__(self, original_function):
        self.original_function = original_function

    def __call__(self):
        print("Before the original function is called.")
        self.original_function()
        print("After the original function is called.")

@DecoratorClass
def greet():
    print("Hello, world!")

greet()
```

In this example, the DecoratorClass is a class-based decorator that takes the original function as an argument in its constructor. The __call__ method is used to define the behavior of the decorator when the decorated function is called.



Here are a few examples of decorators commonly used in Django:

-     @login_required
-     @permission_required
-     @csrf_exempt
-     @cache_page
-     @transaction.atomic

Here is an example of creating a custom decorator in Django:

In this example, the my_view function is decorated with the log_execution_time decorator, which will log the execution time of the view function every time it is called.

```angular2html
from django.shortcuts import render
from .decorators import log_execution_time

@log_execution_time
def my_view(request):
    # your view code here
    return render(request, 'my_template.html', context)
```
here is the implementation of the custom decorator in previous code: 

```angular2html
import time

def log_execution_time(view_func):
    def wrapper(request, *args, **kwargs):
        start_time = time.time()
        response = view_func(request, *args, **kwargs)
        end_time = time.time()
        execution_time = end_time - start_time
        print(f"Execution time: {execution_time:.2f} seconds")
        return response
    return wrapper

```
Overall, creating a custom decorator in Django is a simple process that can help you add reusable functionality to your views and improve the maintainability of your code.


### Map function

The __map()__ function in Python is a built-in function that applies a given function to each item in an iterable (such as a
list, tuple, or string) and returns an iterator with the results. It takes two or more arguments: the __function__ to apply
and one or more iterables. The basic syntax of the __map()__ function is as follows:

```
map(function, iterable1, iterable2, ...)
```

Here's an example that demonstrates the usage of the **map()** function:

```
# Example 1: Squaring numbers using map()
numbers = [1, 2, 3, 4, 5]
squared = map(lambda x: x**2, numbers)
print(list(squared))
# Output: [1, 4, 9, 16, 25]
```

The **map()** function can be useful in various scenarios when working with Django. In the following gives an example of
mapping a function to a query set:

```
from django.contrib.auth.models import User

# Get a queryset of all users
users = User.objects.all()

# Get a list of usernames using map() and a lambda function
usernames = list(map(lambda user: user.username, users))

# Output: ['user1', 'user2', 'user3', ...]
```
The best practice of last example is :

```
usernames = User.objects.all().values_list('username', flat=True)

# Output: ['user1', 'user2', 'user3', ...]

```

### Itertools

Itertools is a Python module that provides a collection of functions for creating and manipulating iterators, which are
objects that can be iterated (looped) over. Here are some commonly used functions provided by the itertools module

- **count()**: Generates an infinite sequence of numbers starting from a specified value.
- **chain()**: Combines multiple iterators into a single iterator.
- **groupby()**: Groups consecutive elements in an iterable based on a common key
- **cycle()**: cycles through the elements of an iterable object infinitely
- **combinations()**: generates all possible combinations of a given iterable object

example of cycle():

```
import itertools

colors = ['red', 'green', 'blue']
color_cycle = itertools.cycle(colors)

for _ in range(5):
    print(next(color_cycle))
```

out put:

```
red
green
blue
red
green
```

example of combinations():

```
import itertools

numbers = [1, 2, 3]
combinations = itertools.combinations(numbers, 2)

for combination in combinations:
    print(combination)
```

output:

```
(1, 2)
(1, 3)
(2, 3)
```

Here are a few examples of how you can utilize itertools in the context of Django. In the following example, we use
itertools.chain() to combine the querysets of posts and comments into a single iterable. We then sort the combined
results based on the creation date, using sorted().

```
import itertools
from myapp.models import Post, Comment

posts = Post.objects.filter(published=True)
comments = Comment.objects.filter(approved=True)

combined_results = itertools.chain(posts, comments)
sorted_results = sorted(combined_results, key=lambda item: item.created_at, reverse=True)
```

### Lambda function

In Python, a **lambda** function is a small anonymous function that can be defined without a name. It is also known as an
inline function or a lambda expression. Lambda functions are typically used when you need a simple function that will be
used only once or as a parameter to another function. The general syntax of a lambda function in Python is:

```
lambda arguments: expression
```

For example, let's say we want to create a lambda function that takes two arguments and returns their sum:

```
add = lambda x, y: x + y
result = add(3, 5)
print(result)  # Output: 8
```

Lambda functions are often used with built-in functions like **map()**, **filter()**, and **reduce()**. These functions take another
function as a parameter, and lambda functions provide a convenient way to define these functions on the fly without
explicitly defining a separate function. Here's an example using the **map()** function with a **lambda** function to square a
list of numbers:

```
numbers = [1, 2, 3, 4, 5]
squared_numbers = list(map(lambda x: x ** 2, numbers))
print(squared_numbers)  # Output: [1, 4, 9, 16, 25]
```

For more complex or reusable functions, it's often better to define a regular named function using the **def** keyword. 

### Exception Handling

Exception handling in Python allows you to gracefully handle and recover from runtime errors or exceptional conditions
that may occur during the execution of your program. Here's an example that demonstrates the usage of exception
handling:

```
try:
    # Code that may raise an exception
    x = 10 / 0  # division by zero raises a ZeroDivisionError
except ZeroDivisionError:
    # Code to handle ZeroDivisionError
    print("Division by zero is not allowed.")


# Output:
# Division by zero is not allowed.
```

here are some examples of Exception Handling in Django:

- Catching exceptions in views:

```
from django.http import HttpResponseServerError
def my_view(request):
    try:
        # Code that may raise an exception
        # ...
    except SomeException as e:
        # Code to handle SomeException
        return HttpResponseServerError("An error occurred: {}".format(str(e)))
```

In this example, if SomeException is raised within the try block, the corresponding except block will be executed. It
returns an HTTP 500 response with a custom error message.

- Handling database-related exceptions:

When working with Django's ORM (Object-Relational Mapping) and database operations, you may encounter exceptions related
to database errors.

```
from django.db import DatabaseError

def my_view(request):
    try:
        # Perform database operations
        # ...
    except DatabaseError as e:
        # Handle database-related exception
        return render(request, 'error.html', {'message': str(e)})
```

In this example, if a DatabaseError occurs during database operations, you can render an error template with the
exception message.

### SOLID principles

The SOLID principles are a set of design principles that help in creating maintainable, scalable, and flexible software
systems.

- Single Responsibility Principle (SRP)
  This principle states that a class should have only one
  responsibility. Let's say we have a User class that handles both user authentication and user data management.
  Instead, we can separate these responsibilities into two classes: Authenticator and UserManager. Here's a Python
  example:

```
class Authenticator:
    def authenticate(self, username, password):
        # Authentication logic here

class UserManager:
    def create_user(self, user_data):
        # User creation logic here

    def delete_user(self, user_id):
        # User deletion logic here
```

- Open/Closed Principle (OCP)
  This principle states that software entities (classes, modules, functions) should be open for extension but closed for
  modification. In other words, you should be able to add new functionality without modifying existing code. Let's say
  we have a Shape class with different subclasses such as Circle and Rectangle. Instead of modifying the Shape class
  every time we want to add a new shape, we can use inheritance and polymorphism to extend the functionality:

```
class Shape:
    def area(self):
        raise NotImplementedError()

class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return 3.14 * self.radius * self.radius

class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def area(self):
        return self.width * self.height
```

- Liskov Substitution Principle (LSP)
  This principle states that objects of a superclass should be replaceable with objects of its subclasses without
  affecting the correctness of the program. Let's say we have a function that expects a Shape object. According to LSP,
  we should be able to pass any subclass of Shape without causing any issues. In simpler terms, it means that a subclass should be able to be used wherever its superclass is expected, without causing any issues or breaking the functionality of the program.

Here's a simple Python example to illustrate the Liskov Substitution Principle:

```angular2html
class Shape:
    def area(self):
        pass

class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def area(self):
        return self.width * self.height

class Square(Shape):
    def __init__(self, side):
        self.side = side

    def area(self):
        return self.side * self.side
```
In this example, we have a superclass called Shape with a method **area()** that calculates the area of a shape. We then have two subclasses, **Rectangle** and **Square**, that inherit from the **Shape** class and override the **area()** method to calculate the area specific to each shape.
According to the Liskov Substitution Principle, we should be able to use objects of the Rectangle and Square classes interchangeably with objects of the Shape class. For example:

```angular2html
def print_area(shape):
    print(f"The area is: {shape.area()}")

rectangle = Rectangle(4, 5)
square = Square(4)

print_area(rectangle)  # Output: The area is: 20
print_area(square)  # Output: The area is: 16
```
In this example, we can see that both the **Rectangle** and **Square** objects can be passed to the **print_area()** function, which expects an object of the **Shape** class. This demonstrates the Liskov Substitution Principle, as the subclasses can be used in place of the superclass without any issues or breaking the functionality of the program.


- Interface Segregation Principle (ISP)

This principle states that clients should not be forced to depend on interfaces they do not use. It promotes the idea of
having smaller, focused interfaces rather than large, general-purpose ones. Let's say we have an Animal interface with
methods like walk(), swim(), and fly(). Instead of having a single interface, we can split it into smaller interfaces
based on functionality:

```
class Walker:
    def walk(self):
        raise NotImplementedError()

class Swimmer:
    def swim(self):
        raise NotImplementedError()

class Flyer:
    def fly(self):
        raise NotImplementedError()

class Dog(Walker):
    def walk(self):
        print("Dog is walking")

class Fish(Swimmer):
    def swim(self):
        print("Fish is swimming")

```

- Dependency Inversion Principle (DIP)
  This principle states that high-level modules should not depend on low-level modules. Both should depend on
  abstractions. It encourages the use of interfaces or abstract classes to decouple dependencies. . This helps to decouple the high-level and low-level modules, making it easier to change the low-level ones without affecting the high-level ones


### Python collection

Python provides several built-in collection types, such as lists, tuples, sets, and dictionaries. These collections can
be used to store and organize data efficiently.

- **lists**:
  A list is a mutable collection that can store an ordered sequence of elements. It is defined using square
  brackets (**[]**). Here's an example:

```
# Creating a list
fruits = ['apple', 'banana', 'orange']

# Accessing elements
print(fruits[0])  # Output: apple

# Modifying elements
fruits[1] = 'kiwi'
print(fruits)  # Output: ['apple', 'kiwi', 'orange']

# Adding elements
fruits.append('grape')
print(fruits)  # Output: ['apple', 'kiwi', 'orange', 'grape']

# Removing elements
fruits.remove('kiwi')
print(fruits)  # Output: ['apple', 'orange', 'grape']

```

- **Tuples**:
  A tuple is an immutable collection that can store an ordered sequence of elements. It is defined using
  parentheses (). Here's an example:

```
# Creating a tuple
point = (3, 4)

# Accessing elements
print(point[0])  # Output: 3

# Unpacking tuple
x, y = point
print(x, y)  # Output: 3 4

```

- **Sets**:
  A set is an unordered collection that stores unique elements. It is defined using curly braces ({}) or the set()
  function. Here's an example:

```
# Creating a set
numbers = {1, 2, 3, 4}

# Adding elements
numbers.add(5)
print(numbers)  # Output: {1, 2, 3, 4, 5}

# Removing elements
numbers.remove(2)
print(numbers)  # Output: {1, 3, 4, 5}

```

- **Dictionaries**:
  A dictionary is a collection that stores key-value pairs. It is defined using curly braces ({}) and colons (:). Here's
  an example:

```
# Creating a dictionary
student = {
    'name': 'Alice',
    'age': 20,
    'university': 'XYZ'
}

# Accessing values
print(student['name'])  # Output: Alice

# Modifying values
student['age'] = 21
print(student)  # Output: {'name': 'Alice', 'age': 21, 'university': 'XYZ'}

# Adding new key-value pair
student['major'] = 'Computer Science'
print(student)  # Output: {'name': 'Alice', 'age': 21, 'university': 'XYZ', 'major': 'Computer Science'}

# Removing key-value pair
del student['university']
print(student)  # Output: {'name': 'Alice', 'age': 21, 'major': 'Computer Science'}

# Updating a field
student.update({'age': 21})

```

### Generators and Iterators

Generators and iterators are powerful constructs in Python used for efficient iteration and lazy evaluation. They
provide a way to generate or yield values on the fly, enabling you to work with large or infinite sequences without
loading everything into memory at once.

- Lazy file reading using generators:

```
def read_lines(filename):
    with open(filename, 'r') as file:
        for line in file:
            yield line.strip()

lines = read_lines('large_file.txt')
for line in lines:
    print(line)

```

Here, the **read_lines()** function returns a generator that yields one line at a time. This approach is memory-efficient
and allows you to process large files without loading the entire contents into memory.
Here is the implementation of the previous example with custom iterator:

```
class LineIterator:
    def __init__(self, filename):
        self.filename = filename
        self.file = None

    def __iter__(self):
        self.file = open(self.filename, 'r')
        return self

    def __next__(self):
        line = self.file.readline().strip()
        if not line:
            self.file.close()
            raise StopIteration
        return line

lines = LineIterator('large_file.txt')
for line in lines:
    print(line)

```

The main advantage of the generator approach is its simplicity and conciseness. The generator function hides most of the
implementation details required for iterators, resulting in cleaner code. On the other hand, the iterator approach
provides more control and flexibility, allowing for more complex iterator implementations beyond what generators can
offer.

Ultimately, the choice between generators and iterators depends on the specific requirements of your program. Generators
are often the preferred choice for simpler iterations and lazy evaluation, while iterators offer more customization and
control when dealing with complex iteration scenarios.

### Magic methods

Magic methods, also known as dunder methods, are special methods in Python that start and end with double underscores.
They are not meant to be invoked directly by the user, but are called internally by the class on certain actions.
Here are some examples of commonly used magic methods in Python:

`__new__(self)`: It is a static method that is called before the **__init__** method when creating an object. The primary purpose of **__new__** is to handle the object construction process and return an instance of the class.

`__init__(self, ...)` : This method is called when an object is created and initialized. It takes arguments that are
used to initialize the object's attributes.

`__str__(self)` : This method is called when the object is printed as a string. It returns a string representation of
the object.

`__len__(self)` : This method is called when the built-in **len()** function is called on the object. It returns the length
of the object.

`__add__(self, other)` : This method is called when the + operator is used on the object. It takes another object as an
argument and returns the result of the addition.

`__call__(self, other)`: The method in Python is a special method that allows an object to be called like a function

Here's an example of a class that defines some of these magic methods:

```
class Person:
   def __init__(self, name, age):
       self.name = name
       self.age = age

   def __str__(self):
       return f"{self.name} is {self.age} years old."

   def __repr__(self):
       return f"Person('{self.name}', {self.age})"

   def __eq__(self, other):
       return self.name == other.name and self.age == other.age
```

Here is a simple example that demonstrates the difference between __str__ and __repr__:

```angular2html
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def __str__(self):
        return f"{self.name} ({self.age})"

    def __repr__(self):
        return f"Person(name='{self.name}', age={self.age})"

person = Person("Alice", 30)
print(str(person))    # Output: Alice (30)
print(repr(person))   # Output: Person(name='Alice', age=30)
```

In this example, we define a Person class that has a name and an age attribute. We define both __str__ and __repr__ methods for the class. The __str__ method returns a string that is intended to be readable by humans, while the __repr__ method returns a string that is intended to be unambiguous and can be used to recreate the object.
When we create a Person object and print it using the **str()** and **repr()** functions, we get different outputs. The **str()** function calls the __str__ method, which returns a user-friendly string representation of the object. The **repr()** function calls the __repr__ method, which returns a developer-friendly string representation of the object.


### GIL
The **_Global Interpreter Lock_** is a mechanism in CPython (the most common implementation of Python) that serves to serialize access to Python objects, preventing multiple threads from executing Python bytecodes at once.
In simple words, the GIL is a mutex (or a lock) that allows only one thread to hold the control of the Python interpreter.This means that _only one thread can be in a state of execution at any point in time_.



### concurrency and parallelism

**Concurrency** involves allowing multiple tasks to take turns accessing the same shared resources, like disk, network, or a
single CPU core. **Parallelism**, on the other hand, is about maximizing the use of hardware resources, such as multiple CPU
cores, to execute multiple tasks simultaneously. **Threading** is a way to achieve concurrency by running multiple threads
within a single process, while **asyncio** is a way to achieve concurrency by running a single thread that can switch
between multiple tasks.

- **Threading**:
  The following code snippet demonstrates how to use threading to execute multiple tasks concurrently within a single
  process.

```
import threading

def task1():
    # do some work

def task2():
    # do some work

# create two threads to execute the tasks concurrently
t1 = threading.Thread(target=task1)
t2 = threading.Thread(target=task2)

# start the threads
t1.start()
t2.start()

# wait for the threads to finish
t1.join()
t2.join()
```

- **Asyncio**:
  The following code snippet demonstrates how to use asyncio to execute multiple tasks concurrently within a single
  thread:

```
import asyncio

async def task1():
    # do some work

async def task2():
    # do some work

# create an event loop
loop = asyncio.get_event_loop()

# execute the tasks concurrently within the event loop
loop.run_until_complete(asyncio.gather(task1(), task2()))

# close the event loop
loop.close()

```

- **Multiprocessing**:
  The following code snippet demonstrates how to use multiprocessing to execute multiple tasks in parallel across
  multiple processes:

```
import multiprocessing

def task1():
    # do some work

def task2():
    # do some work

# create two processes to execute the tasks in parallel
p1 = multiprocessing.Process(target=task1)
p2 = multiprocessing.Process(target=task2)

# start the processes
p1.start()
p2.start()

# wait for the processes to finish
p1.join()
p2.join()

```

In general, **concurrency** is preferred for **IO-bound** tasks, as it allows you to do something else while the IO resources
are being fetched. **Parallelism**, on the other hand, is preferred for **CPU-bound** tasks, as it allows you to take advantage
of multiple CPU cores to execute multiple tasks simultaneously.

### Main types of methods in python classes

In Python, there are three main types of methods that can be defined in a class:

1. **Instance Methods:**
   Instance methods are the most common type of methods used in Python classes. They are defined using the **self**
   parameter as the first argument. Instance methods can access and modify the instance attributes of the class.

```
class MyClass:
    def my_instance_method(self, x, y):
        self.x = x
        self.y = y
        return self.x + self.y

my_object = MyClass()
result = my_object.my_instance_method(3, 4)
print(result)  # Output: 7
```

2. **Class Methods**:
   Class methods are methods that are bound to the class and not the instance of the class. They are defined using the \*
   **@classmethod** decorator, and they take the class itself as their first argument, typically named **cls**. Class
   methods can be called on the class itself, rather than on an instance of the class.

```
class MyClass:
    class_attribute = 0

    @classmethod
    def my_class_method(cls, x, y):
        cls.class_attribute += 1
        return cls.class_attribute + x + y

result1 = MyClass.my_class_method(3, 4)
print(result1)  # Output: 1 + 3 + 4 = 8

result2 = MyClass.my_class_method(1, 2)
print(result2)  # Output: 2 + 1 + 2 = 5
```

3. **Static Methods:**
   Static methods are methods that don't depend on the class or instance. They are defined using the **@staticmethod**
   decorator and take no special first argument. Static methods are typically used for utility functions that don't
   require access to the class or instance.

```
class MyClass:
    @staticmethod
    def my_static_method(x, y):
        return x + y

result = MyClass.my_static_method(3, 4)
print(result)  # Output: 7
```

### Data serialization
Data serialization is the process of converting structured data into a format that allows sharing or storage of the data in a form that allows recovery of its original structure. In Python, there are several built-in modules for data serialization, including **pickle**, **json**, and **marshal**.
**Note** that the marshal module is not suitable for serializing data that needs to be exchanged between different programming languages or platforms, as the binary format is specific to Python. For that purpose, you may want to consider using a different serialization library such as JSON, pickle, or protobuf.

Here's an example of using the **pickle** module to serialize and deserialize a Python object:

```
import pickle

# Define a Python object
grades = {'Alice': 89, 'Bob': 72, 'Charles': 87}

# Serialize the object to a byte stream
serial_grades = pickle.dumps(grades)

# Deserialize the byte stream back into a Python object
received_grades = pickle.loads(serial_grades)

# Print the original and received objects
print('Original object:', grades)
print('Serialized object:', serial_grades)
print('Received object:', received_grades)

# Out put
# Original object: {'Alice': 89, 'Bob': 72, 'Charles': 87}
# Serialized object: b'\x80\x04\x95#\x00\x00\x00\x00\x00\x00\x00}\x94(\x8c\x05Alice\x94KY\x8c\x03Bob\x94KH\x8c\x07Charles\x94KWu.'
# Received object: {'Alice': 89, 'Bob': 72, 'Charles': 87}

```

In this example, we define a Python dictionary grades and serialize it using the **pickle.dumps()** function. We then deserialize the byte stream back into a Python object using the **pickle.loads()** function and print the original and received objects.

### Data class in python
Overall, data classes provide a convenient way to define classes that mainly hold data values, without having to write boilerplate code for initialization, representation, and comparisons.
A **data class** is a class that is designed to only hold data values. It is similar to a regular class, but it usually doesn't have any other methods. It is typically used to store information that will be passed between different parts of a program or a system.
Here's a simple example of a data class in Python:

```angular2html
from dataclasses import dataclass

@dataclass
class Person:
    name: str
    age: int
```

In the above example, the **@dataclass** decorator is used to create a data class called **Person**. The class has two attributes, name and age, which are defined using type annotations. The dataclass decorator automatically generates several special methods such as __init__(), __repr__(), and __eq__() for the class.

To add custom validation to the example using dataclasses, you can define a custom **__post_init__** method that runs after the object is initialized. Within this method, you can perform your custom validation logic. Here's how you can do it:

```
from dataclasses import dataclass

@dataclass
class Person:
    name: str
    age: int

    def __post_init__(self):
        if self.age < 18:
            raise ValueError("Age must be greater than or equal to 18")
            
```

### Shallow copy and deep copy
In Python, there are two types of copying: **shallow copy** and **deep copy**. A **shallow copy** creates a new object that stores references to the child objects of the original object. In contrast, a **deep copy** creates a new object that is completely independent of the original object.
To create a shallow copy of an object, we can use the copy method provided by the copy module in Python. The copy method returns a shallow copy of the object. For example:

```angular2html
import copy

list1 = [1, 2, [3, 4]]
list2 = copy.copy(list1)

print(list1)  # [1, 2, [3, 4]]
print(list2)  # [1, 2, [3, 4]]

list2[2][0] = 5

print(list1)  # [1, 2, [5, 4]]
print(list2)  # [1, 2, [5, 4]]
```

In this example, we create a shallow copy of **list1** using the copy method. When we modify the nested list in **list2**, the same change is reflected in **list1** because both lists share the same reference to the nested list.
To create a deep copy of an object, we can use the deepcopy method provided by the copy module. The deepcopy method returns a deep copy of the object. For example:

```angular2html
import copy

list1 = [1, 2, [3, 4]]
list2 = copy.deepcopy(list1)

print(list1)  # [1, 2, [3, 4]]
print(list2)  # [1, 2, [3, 4]]

list2[2][0] = 5

print(list1)  # [1, 2, [3, 4]]
print(list2)  # [1, 2, [5, 4]]
```

In this example, we create a deep copy of **list1** using the deepcopy method. When we modify the nested list in **list2**, the change is not reflected in **list1** because both lists have independent copies of the nested list.

### Local and global variables 
In summary, local variables are declared inside a function or method and can only be accessed within that specific block, while global variables are declared outside any function or method and can be accessed throughout the program and inside every function. To modify a global variable inside a function, we need to use the **global** keyword.
Here are some simple examples of local and global variables in Python:

```angular2html
# Example of a local variable
def my_function():
    x = 5
    print(x)

my_function()  # Output: 5

# Example of a global variable
y = 10

def my_function():
    print(y)

my_function()  # Output: 10
```

In this example, **x** is a local variable that is declared inside the **my_function** function and can only be accessed within that function. **y**, on the other hand, is a global variable that is declared outside any function and can be accessed inside the **my_function** function.
To modify a global variable inside a function, we need to use the **global** keyword. Here's an example:

```angular2html
# Example of modifying a global variable inside a function
z = 15

def my_function():
    global z
    z = 20

my_function()
print(z)  # Output: 20
```

### Comprehension
Comprehension is a concise and efficient way to create lists, dictionaries, and sets in Python. Multiple and nested comprehensions can be used to create complex data structures in a single line of code.
Here's a very simple example of list comprehension:

```angular2html
# Example of list comprehension
my_list = [x for x in range(10)]
print(my_list)  # Output: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```
In this example, we use list comprehension to create a list of numbers from 0 to 9. The list comprehension is enclosed in square brackets and consists of an expression x followed by a for loop that iterates over a range of numbers from 0 to 9.

Here's a very simple example of nested list comprehension:

```angular2html
# Example of nested list comprehension
my_list = [[x*y for y in range(5)] for x in range(5)]
print(my_list)  # Output: [[0, 0, 0, 0, 0], [0, 1, 2, 3, 4], [0, 2, 4, 6, 8], [0, 3, 6, 9, 12], [0, 4, 8, 12, 16]]
```

In this example, we use nested list comprehension to create a list of multiplication tables for numbers from 0 to 4. The outer list comprehension iterates over numbers from 0 to 4, and the inner list comprehension iterates over numbers from 0 to 4 to create a list of products.

### Pydantic
Pydantic is a Python package that provides data validation and settings management using Python type annotations. It is a lightweight and flexible package that can be used to validate and parse data from various sources such as JSON, YAML, and databases.
 Here's a simple example of using Pydantic to define a data model and validate input data: 

```angular2html
from pydantic import BaseModel

class Person(BaseModel):
    name: str
    age: int

person_data = {
    "name": "John Doe",
    "age": 30
}

person = Person(**person_data)
print(person)


```
To add custom validation to the example using Pydantic, you can use Pydantic's validation decorators like @validator. These decorators allow you to define custom validation functions that run when the model is being initialized. Here's how you can add custom validation to the Person model to ensure that the age is greater than or equal to 18:

```
from pydantic import BaseModel, validator

class Person(BaseModel):
    name: str
    age: int

    @validator("age")
    def validate_age(cls, value):
        if value < 18:
            raise ValueError("Age must be greater than or equal to 18")
        return value

person_data = {
    "name": "John Doe",
    "age": 30
}

```
In this example, we define a custom validation function **validate_age** using the **@validator** decorator. This function checks if the age value is less than 18, and if so, raises a **ValueError** with a custom error message. If the validation passes, the function returns the value as it is. 

In this example, we define a Pydantic data model Person that has two fields: name of type str and age of type int. 
Pydantic automatically validates the input data against the data model and raises a **ValueError** if the data is invalid. If the data is valid, Pydantic creates a new Person object with the validated data and assigns it to the person variable. We then print the person object to verify that it was created correctly.


### Args and Kwargs in Python
In Python, ***args** and ****kwargs** are used to pass a variable number of arguments to a function. They allow you to handle arbitrary numbers of positional and keyword arguments, respectively. 
__args__ is used to pass a variable number of positional arguments to a function. It allows you to pass any number of arguments to a function without explicitly specifying them in the function definition. The arguments passed using *args are collected into a tuple within the function.

```angular2html
def print_args(*args):
    for arg in args:
        print(arg)
print_args('Hello', 'World', '!')
```
 Output:

```angular2html
Hello
World
!
```

****kwargs** is used to pass a variable number of keyword arguments to a function. It allows you to pass key-value pairs as arguments to a function without explicitly specifying them in the function definition. The arguments passed using ****kwargs** are collected into a dictionary within the function.
Here's a simple example: 

```angular2html
def print_kwargs(**kwargs):
    for key, value in kwargs.items():
        print(key, value)
print_kwargs(name='John', age=25, city='New York')
```

Output: 

```angular2html
name John
age 25
city New York
```
In this example, the **print_kwargs()** function takes any number of keyword arguments using ****kwargs**. The key-value pairs are then printed one by one using a loop.
You can also combine ***args** and ****kwargs** in a function definition to accept both positional and keyword arguments


### Operator overloading
Operator overloading in Python refers to the ability to redefine the behavior of built-in operators **(+, -, *, /, etc.)** for user-defined classes.
This feature provides flexibility and allows you to make your classes work with operators in a way that makes sense for your specific use case.

Here's a simple example to illustrate operator overloading using the **+** operator:

```angular2html
class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y
    
    def __add__(self, other):
        new_x = self.x + other.x
        new_y = self.y + other.y
        return Point(new_x, new_y)

point1 = Point(2, 3)
point2 = Point(4, 5)
result = point1 + point2
print(result.x, result.y)  # Output: 6 8
```

When we use the "+" operator between point1 and point2, it calls the **__add__()** method behind the scenes, allowing us to perform the addition operation in a customized way. The result is a new Point object with the summed coordinates.

### Recursive function
A recursive function in Python is a function that calls itself during its execution. It is a powerful technique used to solve problems by breaking them down into smaller, more manageable subproblems. Here's a simple example of a recursive function to calculate the factorial of a number:

```angular2html
def factorial(n):
    if n == 0 or n == 1:
        return 1
    else:
        return n * factorial(n - 1)

result = factorial(5)
print(result)  # Output: 120

```

Recursive functions are particularly useful when solving problems that can be divided into smaller subproblems of the same nature. They provide an elegant and concise way to express repetitive computations and can simplify complex algorithms.
However, it's important to ensure that recursive functions have proper termination conditions to avoid infinite recursion. Recursive functions can consume more memory and may have performance implications compared to iterative solutions, so they should be used judiciously based on the problem at hand.

### Context manager
In Python, a context manager is an object that defines the methods **__enter__** and **__exit__**.
It allows you to manage resources, such as files or database connections, in a structured and efficient manner. The **with** statement is used to create a context, and the context manager ensures that the resources are properly set up and cleaned up, even if an exception occurs.
When you use the context manager with the **with** statement, the **__enter__** method is called at the beginning of the block, and the **__exit__** method is called at the end, regardless of whether an exception occurred or not. This ensures that resources are properly managed and cleaned up.

Let's consider a practical example of a context manager for working with files. We'll create a context manager that opens a file, performs some operations, and automatically closes the file when exiting the context.

```
class FileManager:
    def __init__(self, filename, mode):
        self.filename = filename
        self.mode = mode
        self.file = None

    def __enter__(self):
        self.file = open(self.filename, self.mode)
        return self.file

    def __exit__(self, exc_type, exc_value, traceback):
        self.file.close()

# Using the file manager context manager with the 'with' statement
with FileManager("example.txt", "w") as file:
    file.write("Hello, World!")

# File is automatically closed outside the context

```

In this example, the **FileManager** class is a context manager that takes a **filename** and a **mode** (such as 'r', 'w', or 'a') as parameters. In the **__enter__** method, it opens the file in the specified mode and returns the file object. This allows us to work with the file within the with block.

The **__exit__** method is responsible for closing the file when exiting the context. Regardless of whether an exception occurs or not, the **__exit__** method will be called, ensuring that the file is closed properly.


### More decorators in Python
In Python, class decorators are functions or callable objects that are used to modify or enhance the behavior of a class. They are applied to the class definition itself and can add or modify class-level attributes, methods, or perform other operations on the class.
Here are a few examples of class decorators:

1- classmethod
The **classmethod** decorator is a built-in decorator that transforms a method into a class method. Class methods can be called on the class itself, rather than on instances of the class.
Here's a simple example of a class method in Python

```
class Car:
    total_cars = 0  # Class variable to keep track of the total number of cars

    def __init__(self, name):
        self.name = name
        Car.total_cars += 1

    def get_name(self):
        return self.name

    @classmethod
    def get_total_cars(cls):
        return cls.total_cars


car1 = Car("Toyota")
car2 = Car("Honda")
car3 = Car("Ford")

print(car1.get_name())  # Output: "Toyota"
print(Car.get_total_cars())  # Output: 3
```
In this example, we have a **Car** class with a class variable **total_cars**, which keeps track of the total number of car objects created. The **__init__** method increments **total_cars** by 1 whenever a new car object is created.

2- staticmethod
The **staticmethod** decorator is another built-in decorator that transforms a method into a static method. Static methods are similar to regular functions and do not have access to the class or instance.
Here's a simple example of a static method in Python:

```angular2html
class MathUtils:
    @staticmethod
    def add_numbers(x, y):
        return x + y

    @staticmethod
    def multiply_numbers(x, y):
        return x * y


sum_result = MathUtils.add_numbers(5, 3)
print(sum_result)  # Output: 8

product_result = MathUtils.multiply_numbers(4, 2)
print(product_result)  # Output: 8
```

Static methods are defined using the **@staticmethod** decorator. They don't receive any special first parameter like instance methods or class methods. They behave like regular functions defined within the class.



3- property
The **property** decorator allows you to define methods that can be accessed like attributes, providing a way to implement computed or dynamic properties.

```angular2html
class Circle:
    def __init__(self, radius):
        self.radius = radius

    @property
    def diameter(self):
        return self.radius * 2

    @property
    def area(self):
        return 3.14 * self.radius**2

# Creating an instance of Circle
my_circle = Circle(5)

print(my_circle.diameter)  # Output: 10
print(my_circle.area)  # Output: 78.5
```
In this example, we use the **property** decorator to define the **diameter** and **area** methods.


4- abstractmethod
The **abstractmethod** decorator is used in combination with the **ABC** module to define abstract methods in abstract base classes
The **abstractmethod** decorator ensures that any subclass of super class must implement this method.

```
from abc import ABC, abstractmethod

class Shape(ABC):
    @abstractmethod
    def calculate_area(self):
        pass

class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def calculate_area(self):
        return self.width * self.height

# Creating an instance of Rectangle
my_rectangle = Rectangle(5, 10)

print(my_rectangle.calculate_area())  # Output: 50
```
The **abstractmethod** decorator ensures that any subclass of **Shape** must implement this method.

5- dataclass 
The **dataclass** decorator is available in the **dataclasses** module (introduced in Python 3.7) and provides a concise way to define classes that are primarily used to store data.

```angular2html
from dataclasses import dataclass

@dataclass
class Person:
    name: str
    age: int

# Creating an instance of Person
person = Person("Alice", 25)

print(person.name)  # Output: Alice
print(person.age)   # Output: 25
```
In this example, we apply the **@dataclass** decorator to the **Person** class. The decorator automatically generates special methods like **__init__, __repr__, and __eq__** based on the class variables (name and age in this case).
The **dataclass** decorator simplifies the process of defining classes that are primarily used for holding data, reducing the amount of boilerplate code required.


7- cached_property 
The **cached_property** decorator is available in third-party libraries such as **django.utils.functional** and **cachetools** and provides a way to cache the result of a method as a property, improving performance when the method is called multiple times.

```angular2html
from django.utils.functional import cached_property

class Square:
    def __init__(self, side):
        self.side = side

    @cached_property
    def area(self):
        print("Calculating area...")
        return self.side**2

# Creating an instance of Square
my_square = Square(5)

print(my_square.area)  # Output: Calculating area... 25
print(my_square.area)  # Output: 25 (Cached result, no recalculation)
```
In this example, we apply the **@cached_property** decorator to the **area** method. The decorator caches the result of the method on the instance, so subsequent accesses to area return the cached value without recalculating it.




























































































## Django related topics:

### Django signals

Django signals can be used to automate tasks and update data in your application without having to manually perform
those tasks or update the data.
Let's say we have a Django application that allows users to place orders for products. We want to automatically update
the product quantity in the database whenever an order is placed. We can use Django signals to accomplish this.
Here are the steps to use Django signals for this example:

1. Create a new file called **signals.py** in the same directory as your **models.p**y file.
1. Import the **django.dispatch.Signal** class.
1. Define a new signal using the **Signal** class.
1. Define a function that will be called when the signal is triggered. This function should accept two arguments: **sender**
   and **instance**.
1. Connect the signal to the function using the receiver decorator.

Here's an example implementation:

```
from django.dispatch import Signal
from myapp.models import Order, Product

order_placed = Signal()

def update_product_quantity(sender, instance, **kwargs):
    # Get the product associated with the order
    product = instance.product

    # Calculate the new quantity
    new_quantity = product.quantity - instance.quantity

    # Update the product quantity in the database
    Product.objects.filter(pk=product.pk).update(quantity=new_quantity)

order_placed.connect(update_product_quantity, sender=Order)
```

In this example, we define a new signal called **order_placed** using the Signal class. We also define a function called
**update_product_quantity** that will be called when the signal is triggered. This function gets the Product object
associated with the Order object, calculates the new quantity, and updates the product quantity in the database.

Finally, we connect the **order_placed** signal to the update_product_quantity function using the **connect** method. We also
specify the sender argument to indicate that this signal should only be triggered when an Order object is saved.

To trigger the signal, we simply need to create a new Order object:

```
from myapp.models import Order, Product

product = Product.objects.get(pk=1)
order = Order(product=product, quantity=3)
order.save()  # This will trigger the order_placed signal
```

When the save method is called on the **Order** object, the **order_placed** signal will be triggered, and the
**update_product_quantity** function will be called, updating the product quantity in the database.

### Django middleware

Django middleware provides a way to process requests and responses globally in your application. Middleware can be used
to perform authentication, logging, modifying headers, and more.
Let's say we have a Django application that needs to add a custom header to every HTTP response. We can use Django
middleware to accomplish this.
Here are the steps to use Django middleware:

1. Create a new file called **middleware.py** in the same directory as your settings.py file.
1. Define a class that extends the **MiddlewareMixin** class.
   Implement the **process_response** method to modify the response object.
1. Add your middleware class to the **MIDDLEWARE** setting in your **settings.py** file.

Here's an example implementation:

```
class CustomHeaderMiddleware:
    def process_response(self, request, response):
        response['X-Custom-Header'] = 'Hello, World!'
        return response
```

In this example, we define a new middleware class called **CustomHeaderMiddleware** that extends the MiddlewareMixin class.
We implement the **process_response** method to modify the response object by adding a custom header.
Finally, we add our middleware class to the MIDDLEWARE setting in our **settings.py** file:

```
MIDDLEWARE = [
    # Other middleware classes...
    'myapp.middleware.CustomHeaderMiddleware',
]
```

Now, whenever an HTTP response is returned by our application, the **CustomHeaderMiddleware** class will modify the response
by adding a custom header.

### Django custom template tags

Custom template tags can be used to perform complex operations on data or to create reusable components for your
templates.
Here's a simple example of how to create a custom template tag in Django:

1. Create a new Python module in one of your Django app's templatetags directory. For example, if you have an app named
   **myapp**, you could create a new module named **myapp_tags.py** in the **myapp/templatetags** directory.

1. Define a function in the module that takes a template context and any arguments you want to pass to the tag. The
   function should return the value you want to output in the template. For example, here's a function that takes a list
   of strings and returns the first item in the list:

```
from django import template

register = template.Library()

@register.simple_tag
def first_item(my_list):
    if my_list:
        return my_list[0]
    return ''
```

In this example, we're using the **@register.simple_tag** decorator to register the function as a simple template tag.

1. In your template, load the custom tag library and use the new tag in your HTML code. To load the custom tag library,
   add **{% load myapp_tags %}** at the top of your template. Here's an example of how to use the first_item tag we
   defined earlier:

```
{% load myapp_tags %}

<ul>
  {% for item in my_list %}
    <li>{% first_item item %}</li>
  {% endfor %}
</ul>
```

In this example, we're using the **first_item** tag to output the first item in each list item in a loop.

### Django permissions

Django provides a built-in permissions system that allows you to control access to views and models in your application.
Permissions can be assigned to users or groups, and can be checked in your views or templates to determine whether a
user has the necessary permissions to perform certain actions.
Here's a simple example of how to use Django permissions:

1. First, you need to define the permissions for your models. You can do this by adding a permissions attribute to
   your **model's meta class**. For example, let's say you have a Book model and you want to define a permission called
   **can_edit_book**:

```
from django.db import models
from django.contrib.auth.models import User

class Book(models.Model):
    title = models.CharField(max_length=100)
    author = models.ForeignKey(User, on_delete=models.CASCADE)
    published_date = models.DateField()

    class Meta:
        permissions = [
            ("can_edit_book", "Can edit book"),
        ]
```

In this example, we've added a permissions attribute to the Book model's meta class, and defined a single permission
named **can_edit_book**.

5. Next, you need to assign the permissions to users or groups. You can do this using Django's built-in admin interface,
   or programmatically in your code. For example, let's say we want to assign the **can_edit_book** permission to a group
   called Editors:

```
from django.contrib.auth.models import Group

editors_group, created = Group.objects.get_or_create(name='Editors')
editors_group.permissions.add('myapp.can_edit_book')

```

In this example, we're using the Group model to get or create a group called Editors, and then adding the
**myapp.can_edit_book** permission to the group.

9. Finally, you can check the user's permissions in your views or templates to control access to certain actions. For
   example, let's say we have a view that allows users to edit a book:

```
from django.shortcuts import get_object_or_404, render
from django.contrib.auth.decorators import login_required, permission_required
from myapp.models import Book

@login_required
@permission_required('myapp.can_edit_book', raise_exception=True)
def edit_book(request, book_id):
    book = get_object_or_404(Book, id=book_id)
    # perform edit operation
    return render(request, 'book_edit.html', {'book': book})
```

In this example, we're using the **permission_required** decorator to check if the user has the myapp.can_edit_book
permission before allowing them to edit the book. If the user does not have the necessary permission, a **PermissionDenied**
exception will be raised.

### Django custom user models

Django's built-in **User** model provides a lot of functionality for authentication and authorization, but sometimes you may
need to customize the user model to include additional fields or functionality. In such cases, you can create a custom
user model that inherits from Django's **AbstractBaseUser** or **AbstractUser** classes.
Here's a simple example of how to create a custom user model in Django:

- Create a new app for your custom user model. For example, let's say you want to create a custom user model for a blog
  app. You could create a new app called **blog_auth**.

- Create a new model for your custom user model. For example, let's say you want to add a **bio field** to your user
  model:

```
from django.contrib.auth.models import AbstractBaseUser, BaseUserManager, PermissionsMixin
from django.db import models

class BlogUser(AbstractBaseUser, PermissionsMixin):
    email = models.EmailField(unique=True)
    first_name = models.CharField(max_length=30, blank=True)
    last_name = models.CharField(max_length=30, blank=True)
    bio = models.TextField(blank=True)

    is_staff = models.BooleanField(default=False)
    is_active = models.BooleanField(default=True)

    USERNAME_FIELD = 'email'
    EMAIL_FIELD = 'email'

    def __str__(self):
        return self.email
```

In this example, we've created a new model called **BlogUser** that inherits from **AbstractBaseUser** and **PermissionsMixin**.
We've also defined the necessary fields, including a custom bio field.

- Update your project settings to use the custom user model. In your project's **settings.py** file, update the \*
   **AUTH_USER_MODEL** setting to point to your new user model:

```
AUTH_USER_MODEL = 'blog_auth.BlogUser'
```

- Migrate your database to create the new user model table. Run the following commands in your terminal:

```
python manage.py makemigrations
python manage.py migrate
```

That's it! You now have a custom user model in Django that you can use for authentication and authorization in your blog
app.

### Django Custom Managers

Django provides a default manager for each model that allows you to interact with the database. However, sometimes you
may need to customize the default manager to add additional functionality or implement custom queries.
Here's a simple example of how to create a custom manager in Django:

- Let's say we have a model called **Book** in our app that represents books in a library. We want to create a custom
  manager that returns only the books that are currently available for borrowing.

```
from django.db import models

class AvailableBooksManager(models.Manager):
    def get_queryset(self):
        return super().get_queryset().filter(is_available=True)

class Book(models.Model):
    title = models.CharField(max_length=100)
    author = models.CharField(max_length=100)
    is_available = models.BooleanField(default=True)

    objects = models.Manager()  # default manager
    available_books = AvailableBooksManager()  # custom manager
```

In this example, we've created a custom manager called **AvailableBooksManager** that filters the books based on the
**is_available** field. We've also added a **available_books** attribute to the Book model that uses the custom manager.

- Now we can use the custom manager in our views or templates to get only the books that are currently available for
  borrowing. For example:

```
from django.shortcuts import render
from myapp.models import Book

def available_books(request):
    books = Book.available_books.all()
    return render(request, 'available_books.html', {'books': books})
```

In this example, we're using the **available_books** manager to get all the books that are currently available for
borrowing, and passing them to the **available_books.html** template.

### Django Custom validators

Django provides a set of built-in validators that can be used to validate form data and model fields. However, sometimes
you may need to create your own custom validators to validate data in a specific way. Here's a simple example of how to
create a custom validator in Django:

- Let's say we have a model called Book in our app that represents books in a library. We want to create a custom
  validator that checks whether the book's title starts with a capital letter.

```
from django.core.exceptions import ValidationError

def validate_title(value):
    if not value[0].isupper():
        raise ValidationError("Title must start with a capital letter.")

class Book(models.Model):
    title = models.CharField(max_length=100, validators=[validate_title])
    author = models.CharField(max_length=100)
```

In this example, we've created a custom validator called **validate_title** that checks whether the first character of the
title is a capital letter. If the validation fails, a ValidationError is raised. We've also added the validate_title
validator to the title field of the Book model.
Now when a user tries to create a book with a title that doesn't start with a capital letter, the validation will fail
and an error message will be displayed.

### Custom management commands

Custom management commands allow you to add your own functionality to the **manage.py** command, making it easy to automate
tasks and perform custom operations on your Django project.

Here is a simple example to demonstrate how to create and use custom management commands in Django:

- Create a new Django app:

```
python manage.py startapp myapp
```

- Create a new directory called **management** inside the app directory, and create another directory called **commands** inside the management directory:

```
mkdir myapp/management
mkdir myapp/management/commands
```

- Create a new Python file inside the commands directory, and name it **mycommand.py**. This will be the file that
  contains the code for your custom management command:

```
from django.core.management.base import BaseCommand

class Command(BaseCommand):
    help = 'My custom management command'

    def handle(self, *args, **options):
        print('Hello from my custom management command!')
```

Register the new command with Django by adding an empty** **__init__.py** file inside the management directory:

```
touch myapp/management/__init__.py
```

- Test the new command by running it from the command line:

```
python manage.py mycommand
```

You should see the message **"Hello from my custom management command!"** printed to the console.

### Django's Query API
Here are some examples of how to use Django's Query API:
- Retrieving all objects from a model:
```angular2html
from myapp.models import MyModel

all_objects = MyModel.objects.all()
```
This will retrieve all objects from the **MyModel** model and store them in the **all_objects** variable.

- Filtering objects based on a condition:
```angular2html
from myapp.models import MyModel

filtered_objects = MyModel.objects.filter(attribute=value)
```
This will retrieve all objects from the **MyModel** model where the attribute matches the value and store them in the filtered_objects variable.

- Chaining filters:
```angular2html
from myapp.models import MyModel

filtered_objects = MyModel.objects.filter(attribute1=value1).filter(attribute2=value2)
```
This will retrieve all objects from the **MyModel** model where attribute1 matches value1 and attribute2 matches value2 and store them in the **filtered_objects** variable.


- Querying related fields:
```angular2html
from myapp.models import MyModel

related_objects = MyModel.objects.filter(related_model__attribute=value)
```
This will retrieve all objects from the **MyModel** model where the related model's attribute matches value and store them in the **related_objects** variable.

- Ordering results:
```angular2html
from myapp.models import MyModel

ordered_objects = MyModel.objects.order_by('attribute')
```
This will retrieve all objects from the **MyModel** model and order them by the attribute field in ascending order. You can also use the - sign to order in descending order.

- Limiting results:
```angular2html
from myapp.models import MyModel

limited_objects = MyModel.objects.all()[:10]
```
This will retrieve the first 10 objects from the **MyModel** model and store them in the **limited_objects** variable.

- Using OR conditions:
```angular2html
from myapp.models import MyModel
from django.db.models import Q

objects = MyModel.objects.filter(Q(attribute1=value1) | Q(attribute2=value2))
```
This will retrieve all objects from the **MyModel** model where either attribute1 matches value1 or attribute2 matches value2 and store them in the objects variable.

- Using LIKE conditions:
```angular2html
from myapp.models import MyModel

objects = MyModel.objects.filter(attribute__contains=value)
```
This will retrieve all objects from the **MyModel** model where attribute contains value and store them in the objects variable.

- Using NOT conditions:
```angular2html
from myapp.models import MyModel

objects = MyModel.objects.exclude(attribute=value)
```
This will retrieve all objects from the **MyModel** model where attribute does not match value and store them in the objects variable.

- Retrieving a single object:
```angular2html
from myapp.models import MyModel

object = MyModel.objects.get(id=value)
```
This will retrieve a single object from the **MyModel** model where **id** matches value and store it in the object variable.

- Updating objects:
```angular2html
from myapp.models import MyModel

MyModel.objects.filter(attribute=value).update(attribute=new_value)
```
This will update all objects from the **MyModel** model where attribute matches value and set attribute to new_value.



### Custom query expressions or Custom Lookup

Custom query expressions are a way to extend the Django query API with your own custom SQL expressions. Custom query
expressions can be useful when you need to perform queries that are not easily expressible using the standard query API.

Suppose you have a model called Person that represents a **person** with a first name, last name, and age. You want to
perform a query that returns all people whose first name starts with a given letter. Here's how you can create a custom
query expression to perform this query:

```
from django.db.models import Lookup

class StartsWith(Lookup):
    lookup_name = 'startswith'

    def as_sql(self, compiler, connection):
        lhs, lhs_params = self.process_lhs(compiler, connection)
        rhs, rhs_params = self.process_rhs(compiler, connection)
        params = lhs_params + [rhs_params[0] + '%']
        return f"{lhs} LIKE %s", params

Person.objects.filter(first_name__startswith='A')
```

In this example, we define a custom lookup called **StartsWith** that extends the Lookup class. We set the lookup_name
attribute to **'startswith'** to define the name of the lookup. We then define the **as_sql** method to generate the SQL
expression for the lookup.

Here's another simple example of defining and using a custom lookup in Django: 

```angular2html
from django.db import models
from django.db.models import Lookup


class GreaterThanLookup(Lookup):
    lookup_name = 'gt'
    def as_sql(self, compiler, connection):
        lhs, lhs_params = self.process_lhs(compiler, connection)
        rhs, rhs_params = self.process_rhs(compiler, connection)
        params = lhs_params + rhs_params
        return f'{lhs} > {rhs}', params


models.IntegerField.register_lookup(GreaterThanLookup)
class Product(models.Model):
    name = models.CharField(max_length=100)
    price = models.DecimalField(max_digits=8, decimal_places=2)
```

Usage of the custom lookup

```angular2html
expensive_products = Product.objects.filter(price__gt=100.00)
```
In this example, we define a custom lookup called **GreaterThanLookup** that performs a greater-than comparison (>) for IntegerField fields. We subclass **django.db.models.Lookup** and override the **as_sql()** method to define the SQL representation of the lookup.
The usage of the custom lookup is demonstrated, where we filter the Product objects based on the price field using the gt lookup.

### Django Filterset
Django Filterset provides a simple and intuitive way to filter data in Django. It allows you to define filterset classes that specify the fields to filter on and provides a range of built-in filters that you can use to filter data. You can also define custom filters and combine filters to create more complex filtering logic.
Here are some simple examples of using Django Filterset:
- Basic filtering: 
To filter a queryset using Django Filterset, you first need to define a filterset class that specifies the fields to filter on. For example:

```angular2html
import django_filters
from .models import Product

class ProductFilter(django_filters.FilterSet):
    class Meta:
        model = Product
        fields = ['name', 'price']
```

This defines a filterset class that filters on the **name** and **price** fields of the Product model. You can then use this filterset class to filter a queryset:

```angular2html
from .filters import ProductFilter

def product_list(request):
    queryset = Product.objects.all()
    filterset = ProductFilter(request.GET, queryset=queryset)
    return render(request, 'product_list.html', {'filterset': filterset})
```

This filters the queryset based on the parameters provided in the GET request.

- Custom filtering: 
You can also define custom filters that perform more complex filtering logic. For example:

```angular2html
import django_filters
from .models import Product

class ProductFilter(django_filters.FilterSet):
    min_price = django_filters.NumberFilter(field_name='price', lookup_expr='gte')
    max_price = django_filters.NumberFilter(field_name='price', lookup_expr='lte')

    class Meta:
        model = Product
        fields = ['name', 'min_price', 'max_price']
```

This defines custom filters that filter on the **price** field of the Product model. The **min_price** filter filters on products with a price greater than or equal to the provided value, and the max_price filter filters on products with a price less than or equal to the provided value.
Instead of using FilterSets, you can directly use the Django ORM filters to perform filtering on your querysets. Django ORM provides a wide range of filter options such as exact match, case-insensitive match, range filters, and more. You can chain multiple filters together to create complex queries.




### Context managers
The context manager is responsible for setting up the context, running the block of code, and then cleaning up the context when the block is exited, regardless of whether the block raised an exception or not. In Django, context managers can be used to control signals, transactions, and caching.
Here are some simple examples of context managers in Django:
- **Database transactions**: 
In Django, context managers can be used to control database transactions. For example:
```angular2html
from django.db import transaction

with transaction.atomic():
    # code that requires a transaction
```

- **Caching**: 
Context managers can be used to control caching in Django. For example:
```angular2html
from django.core.cache import cache

class CacheContext:
    def __init__(self, key, value):
        self.key = key
        self.value = value

    def __enter__(self):
        cache.set(self.key, self.value)

    def __exit__(self, exc_type, exc_val, exc_tb):
        cache.delete(self.key)

with CacheContext('my_key', 'my_value'):
    # code that requires the cache to be set
```

In summary, context managers in Django provide a simple and intuitive API for a powerful construct. They allow you to allocate and release resources precisely when you want to, and they make it easier to write safe and readable code.
Overall, context managers provide a robust and efficient way to manage resources and ensure proper cleanup in Django applications. They contribute to cleaner code, improved error handling, and better resource utilization.

### Django Channels
Django Channels is a package that allows Django to handle WebSockets and other non-HTTP protocols. It extends the built-in capabilities of Django, allowing Django projects to handle not only HTTP but also protocols that require long-running connections, such as WebSockets, MQTT (IoT), chatbots, radios, and other real-time applications.
Here are some differences between Django Channels and Django's built-in HTTP capabilities:

Django Channels:

- Allows Django projects to handle protocols other than HTTP, such as WebSockets, MQTT, and chatbots
- Provides support for Django's core features like authentication and sessions
- Preserves the synchronous behavior of Django and adds a layer of asynchronous protocols allowing users to write views that are entirely synchronous, asynchronous, or a mixture of both
- Replaces Django's default WSGI with its ASGI (Asynchronous Server Gateway Interface) 

Django's built-in HTTP capabilities:
- Handle only HTTP requests
- Do not support protocols that require long-running connections, such as WebSockets and MQTT
- Do not provide support for asynchronous code execution

In summary, Django Channels extends Django's built-in capabilities to handle protocols other than HTTP and provides support for asynchronous code execution.

### HTTP methods in Django
Django provides built-in support for handling HTTP requests and responses using request and response objects Here are some examples of how to use HTTP methods in Django:
- **GET**: 
To handle a GET request in a class-based view, you can define a method called **get()** in your view class. For example:

```angular2html
from django.views import View
from django.http import HttpResponse

class HelloView(View):
    def get(self, request):
        return HttpResponse('Hello, World!')
```

- **POST**: 
To handle a POST request in a class-based view, you can define a method called **post()** in your view class. For example:

```angular2html
from django.views import View
from django.http import HttpResponse

class LoginView(View):
    def post(self, request):
        username = request.POST['username']
        password = request.POST['password']
        # Authenticate user
        return HttpResponse('Logged in successfully')
```

- **PUT** and **DELETE**: 
Django's class-based views do not have built-in support for handling PUT and DELETE requests. However, you can use mixins or third-party packages like Django REST framework to handle these requests. For example, using Django REST framework, you can define a class-based view that inherits from **APIView** and override the appropriate methods for PUT and DELETE requests:

```angular2html
from rest_framework.views import APIView
from rest_framework.response import Response

class UserDetailView(APIView):
    def put(self, request, pk):
        # Update user object with pk
        return Response({'message': 'User updated'})

    def delete(self, request, pk):
        # Delete user object with pk
        return Response({'message': 'User deleted'})
```

In Django, the difference between **PUT** and **PATCH** methods is similar to their difference in general HTTP terms.

- **PUT** is used to modify an entire resource on the server. When a client sends a PUT request in Django, it updates the entire resource with the new data provided. If the resource does not exist, PUT creates a new resource. PUT is idempotent, meaning that calling it once or multiple times successively has the same effect.
- PATCH is used to modify a part of a resource on the server. When a client sends a PATCH request in Django, it updates only the specified part of the resource with the new data provided. PATCH is not idempotent, meaning that successive identical PATCH requests may have additional effects. PATCH allows partial updates and side-effects on other resources.

Here's an example of how to handle PUT and PATCH requests in Django using Django REST Framework:

```angular2html
from rest_framework.views import APIView
from rest_framework.response import Response
from rest_framework import status

class MyResourceView(APIView):
    def put(self, request, pk):
        # Retrieve the resource with the given pk
        resource = MyResource.objects.get(pk=pk)

        # Update the entire resource with the new data
        resource.name = request.data.get('name')
        resource.age = request.data.get('age')
        resource.save()

        return Response(status=status.HTTP_200_OK)

    def patch(self, request, pk):
        # Retrieve the resource with the given pk
        resource = MyResource.objects.get(pk=pk)

        # Update only the specified part of the resource with the new data
        if 'name' in request.data:
            resource.name = request.data['name']
        if 'age' in request.data:
            resource.age = request.data['age']
        resource.save()

        return Response(status=status.HTTP_200_OK)
```

In the above example, the put method is used to handle PUT requests and update the entire resource with the new name and age. The patch method is used to handle PATCH requests and update only the specified part of the resource. The request.data attribute is used to access the data sent in the request body.

### annotate and aggregate in Django
**annotate()** is typically used when you want to add additional information or calculated fields to each object in the queryset. For example, you can annotate a queryset of books with the number of authors for each book
On the other hand, **aggregate()** is used when you want to perform calculations on the entire queryset, such as calculating the sum, average, or count of a specific field across all objects in the queryset.

The output of **annotate()** is a QuerySet, which means it returns a modified queryset with the annotated values. On the other hand, **aggregate()** returns a dictionary containing the calculated aggregate values

Here is a simple example of using annotate() and aggregate() in Django:

```angular2html
from django.db.models import Count
from myapp.models import Book, Author

# Count the number of books for each author
authors = Author.objects.annotate(num_books=Count('book'))

# Count the total number of books
total_books = Book.objects.aggregate(total=Count('id'))

```
In the above example, **annotate()** is used to count the number of books for each author. The **Count()** function is used to count the number of related books for each author. The resulting queryset will have an additional attribute num_books for each author object.
**aggregate()** is used to count the total number of books. The **Count()** function is used to count the number of books in the Book model. The resulting dictionary will have a single key total with the total number of books as its value.
It is important to note that **annotate()** returns a queryset, while **aggregate()** returns a dictionary.

### Mixin in Django
In Django, a **mixin** is a class that provides additional functionality to other classes through **inheritance**. Mixins are used to add common or reusable functionality to multiple classes without the need for duplicating code.
 Here's a simple example to demonstrate how mixins work in Django: 

```angular2html
# Define a mixin class
class TimestampMixin:
    created_at = models.DateTimeField(auto_now_add=True)
    updated_at = models.DateTimeField(auto_now=True)

    class Meta:
        abstract = True

# Use the mixin in a model
class MyModel(TimestampMixin, models.Model):
    name = models.CharField(max_length=100)
    # other fields

# Use the mixin in a view
class MyView(TimestampMixin, View):
    def get(self, request):
        # handle GET request
        pass

    def post(self, request):
        # handle POST request
        pass

```
 In this example, we have defined a mixin class called **TimestampMixin**. It adds two fields, **created_at** and **updated_at**, to any class that inherits from it. The Meta class with **abstract = True** ensures that the mixin itself is not treated as a model.
 By using mixins, you can easily add common functionality to multiple classes without duplicating code. This promotes code reuse, improves maintainability, and keeps your codebase organized.
 
### Cache in Django
 By using caching in Django, you can significantly improve the performance of your application by reducing the load on the database and serving cached results faster. It is an essential technique for optimizing web applications and improving user experience.
 Django provides built-in support for caching through its caching framework. The caching framework allows you to cache the results of views, template fragments, and even low-level database queries. It supports various cache backends and provides flexibility in configuring cache settings.
Here's a simple example to demonstrate how caching works in Django:

 1- Configure the cache backend in your Django settings:

```angular2html
CACHES = {
    'default': {
        'BACKEND': 'django.core.cache.backends.memcached.MemcachedCache',
        'LOCATION': '127.0.0.1:11211',
    }
}

```

2- Use the **cache_page** decorator to cache the result of a view:

```angular2html
from django.views.decorators.cache import cache_page

@cache_page(60 * 15)  # Cache the page for 15 minutes
def my_view(request):
    # Expensive computation or database query
    # ...
    return HttpResponse('Hello, World!')

```
We then use the **cache_page** decorator to cache the result of the **my_view** function for 15 minutes. This means that the first time the view is accessed, the result will be computed and stored in the cache. For subsequent requests within the next 15 minutes, the cached result will be returned directly without executing the view function again.

### Django constraint
In Django, a constraint refers to a rule or condition that can be applied to a database table to enforce data integrity. Constraints ensure that the data stored in the table follows certain rules and meets specific requirements.
Django provides a way to define constraints on model fields using the constraints attribute. This attribute allows you to specify one or more constraints for a model, such as unique constraints, check constraints, foreign key constraints, and more.
Here's a simple example of defining and using a constraint in Django: 

```angular2html
from django.db import models
class Person(models.Model):
    name = models.CharField(max_length=100)
    age = models.IntegerField()
    class Meta:
        constraints = [
            models.CheckConstraint(check=models.Q(age__gte=18), name='age_gte_18')
        ]
```
In this example, we define a **Person** model with two fields: **name** and **age**. We want to enforce a constraint that ensures the age field is greater than or equal to 18.
By defining this constraint, Django will automatically create the necessary SQL statements to enforce the constraint when creating or modifying the database table for the Person model. Constraints help maintain data integrity and ensure that the data stored in the database follows the defined rules. They can be particularly useful in scenarios where you want to enforce specific conditions or relationships between fields in your models.

#### Django constraints and model validators differences

Django constraints and model validators are two different mechanisms for ensuring data integrity in Django applications.
Constraints are used to enforce data integrity rules at the database level, while validators are used to enforce data integrity rules at the application leve.
During exceptions in Django Constraints raise database-level errors such as IntegrityError, while validators raise application-level errors such as ValidationError


### bulk creation in Django
In Django, bulk creation refers to the process of creating multiple model instances in a single database query, rather than creating them one by one. This can significantly improve the performance of creating large numbers of objects.  This method takes a list of model instances as an argument and inserts them into the database efficiently.
 Here's a simple example of using **bulk_create()** in Django: 

```angular2html
from django.db import models

class Book(models.Model):
    title = models.CharField(max_length=100)
    author = models.CharField(max_length=100)
    publication_year = models.IntegerField()


# Create a list of Book instances
books = [
    Book(title='Book 1', author='Author 1', publication_year=2020),
    Book(title='Book 2', author='Author 2', publication_year=2021),
    Book(title='Book 3', author='Author 3', publication_year=2022),
]

# Bulk create the books
Book.objects.bulk_create(books)
```

In this example, we define a **Book** model with three fields: title, author, and publication_year. We then create a list of Book instances with different values. To perform bulk creation, we use the **bulk_create()** method of the Book.objects manager. We pass the list of Book instances as an argument to **bulk_create()**, and Django will efficiently insert them into the database in a single query.
 Overall, **bulk_create()** is a useful feature in Django for efficiently creating multiple model instances in a single database query.

### prefetch_related and select_related in Django
In Django, **prefetch_related** and **select_related** are query optimization techniques that allow you to reduce the number of database queries when retrieving related objects.

1- **select_related**

It works for **ForeignKey** and **OneToOneField** relationships. By using **select_related**, you can avoid the overhead of multiple database queries when accessing related objects.
 Here's a simple example: 

```angular2html
from django.db import models

class Author(models.Model):
    name = models.CharField(max_length=100)

class Book(models.Model):
    title = models.CharField(max_length=100)
    author = models.ForeignKey(Author, on_delete=models.CASCADE)
```

 Suppose we have a **Book** model with a **ForeignKey** relationship to the **Author** model. If we want to retrieve all books and their corresponding authors, we can use **select_related** to fetch the related authors in a single query: 

```angular2html
books = Book.objects.select_related('author').all()

for book in books:
    print(f"Book: {book.title}, Author: {book.author.name}")
```

 In this example, **select_related('author')** is used to fetch the related Author objects along with the Book objects in a single query. This avoids the need for an additional query for each book's author.

2- **prefetch_related**

It works for **ManyToManyField** and **reverse ForeignKey** relationships. By using **prefetch_related**, you can reduce the number of queries when accessing related objects. Here's a simple example:

```angular2html
from django.db import models

class Category(models.Model):
    name = models.CharField(max_length=100)

class Product(models.Model):
    name = models.CharField(max_length=100)
    categories = models.ManyToManyField(Category)
```

 Suppose we have a **Product** model with a **ManyToManyField** relationship to the **Category** model. If we want to retrieve all products and their corresponding categories, we can use **prefetch_related** to fetch the related categories efficiently: 

```angular2html
products = Product.objects.prefetch_related('categories').all()

for product in products:
    print(f"Product: {product.name}")
    for category in product.categories.all():
        print(f"Category: {category.name}")
```
 To retrieve all authors along with their books efficiently, we can use **prefetch_related** as follows: 

```angular2html
authors = Author.objects.prefetch_related('books').all()
for author in authors:
    print(f"Author: {author.name}")
    for book in author.books.all():
        print(f"Book: {book.title}")
```

 In this example, **prefetch_related('books')** is used to fetch all the related Book objects efficiently for each author. It reduces the number of queries by fetching all the related books in a separate query, rather than fetching them individually for each author.

 In this example, **prefetch_related('categories')** is used to fetch the related Category objects efficiently. It reduces the number of queries by fetching all the related categories in a separate query, rather than fetching them individually for each product.
 Using **select_related** and **prefetch_related** can significantly improve the performance of your Django queries by reducing the number of database queries. It is especially useful when dealing with large datasets or complex relationships between models.

### Third-party packages in Django
There are several third-party packages that can greatly enhance your development experience and provide additional functionality. Here is a list of must-have third-party packages that are commonly used in Django projects:
- **Django REST framework**: A powerful and flexible toolkit for building Web APIs.
- **Django Crispy Forms**: Easily manage Django forms' layout using bootstrap styles.
- **Django Debug Toolbar**: Provides a set of panels displaying various debug information about the current request/response.
- **Django Celery**: Distributed task queue system for asynchronous processing.
- **Django allauth**: User registration, authentication, and account management.
- **Django Rest Auth**: Provides a set of REST API endpoints for user registration, authentication, and account management.
- **Django Filter**: Simplifies the process of filtering querysets dynamically.
- **Django Rest Framework Swagger**: Generates interactive API documentation using the OpenAPI standard.
- **Django Environ**: Allows you to define environment variables for your Django project.

### Property decorators
The @property decorator in Django is used to define a method that behaves like a model attribute. It allows you to call custom model methods as if they were normal model attributes. Here's a simple example to illustrate the concept:

```angular2html
from django.db import models

class Book(models.Model):
    title = models.CharField(max_length=100)
    author = models.CharField(max_length=50)
    price = models.DecimalField(max_digits=5, decimal_places=2)

    @property
    def price_in_euros(self):
        return f"{self.price} EUR"

```
In this example, we define a **Book** model with fields for **title**, **author**, and **price**. We then define a **price_in_euros** method with the **@property** decorator. This method returns the price of the book in euros as a string.

By using the **@property** decorator, we can access the **price_in_euros** method as if it were a model attribute. For example, we can retrieve the price of a book in euros as follows:

```angular2html
book = Book.objects.get(pk=1)
print(book.price_in_euros)  # Output: "19.99 EUR"

```

In Django models, a method with the @property decorator behaves like a model attribute, while a method without this decorator behaves like a normal method. 
Here's an example to illustrate the difference:

```angular2html
class Book(models.Model):
    title = models.CharField(max_length=100)
    author = models.CharField(max_length=50)
    price = models.DecimalField(max_digits=5, decimal_places=2)

    @property
    def price_in_euros(self):
        return f"{self.price} EUR"

    def calculate_discounted_price(self, discount):
        return self.price * (1 - discount)

```

When we access **my_book.price_in_euros**, it behaves like a model attribute and returns the price of the book in euros as a string. On the other hand, when we call **my_book.calculate_discounted_price(0.1)**, it behaves like a normal method and returns the discounted price of the book.

### WSGI and ASGI
The Web Server Gateway Interface (**WSGI**) and the Asynchronous Server Gateway Interface (**ASGI**) are two different specifications in Django for handling web requests and responses. Here's a brief explanation of each:

#### WSGI (Web Server Gateway Interface):
- WSGI is a synchronous interface that defines how web servers communicate with Python web applications.
- It provides a standard way for web servers to forward requests to Python web frameworks and applications.
- WSGI servers handle one request at a time and block until the response is generated, making it suitable for traditional synchronous web applications.
- WSGI is the older and more established interface, widely used by Python web frameworks and servers.
#### ASGI (Asynchronous Server Gateway Interface):
- ASGI is an asynchronous interface that extends the capabilities of WSGI to support asynchronous web applications.
- It allows multiple, concurrent requests to be handled asynchronously, making it suitable for real-time applications, long-polling, and WebSockets.
- ASGI servers can handle both synchronous and asynchronous applications, providing flexibility for developers.
- ASGI is designed to be a superset of WSGI, meaning that WSGI applications can be run inside ASGI servers.

In summary, **WSGI** is a synchronous interface for handling web requests and responses, while **ASGI** is an asynchronous interface that extends the capabilities of WSGI to support asynchronous applications. 
**ASGI** provides the ability to handle multiple concurrent requests and is suitable for real-time and long-polling applications.

### Advanced features in ORM
Django ORM (Object-Relational Mapping) provides several advanced features that allow for more complex and powerful database queries and data manipulation. Here are some of the advanced features of Django ORM:

#### Q objects:
Q objects allow for complex queries by combining multiple filters using logical operators like AND (&) and OR (|). They encapsulate keyword arguments for filtering and provide more flexibility in query construction

```angular2html
from django.db.models import Q

# Query to retrieve books with either 'fiction' or 'mystery' genre
books = Book.objects.filter(Q(genre='fiction') | Q(genre='mystery'))
```

#### F expressions: 
F expressions allow you to perform database operations using field values without pulling the values from the database. They enable calculations and comparisons directly within the database query, improving performance and reducing round trips to the database

```angular2html
from django.db.models import F

# Query to update the price of all books by increasing it by 10%
Book.objects.all().update(price=F('price') * 1.1)
```

#### QuerySet methods
Django provides a comprehensive set of QuerySet methods for retrieving, filtering, and manipulating data from the database. These methods include **annotate()**, **aggregate()**, **values()**, **distinct()**, **order_by()**, **reverse()**, and many more

```angular2html
# Query to retrieve the top 5 books with the highest ratings
top_books = Book.objects.order_by('-rating')[:5]

# Query to retrieve the distinct authors of all books
authors = Book.objects.values('author').distinct()

# Query to annotate the average price for each genre
genres = Book.objects.values('genre').annotate(avg_price=Avg('price'))
```

#### Model managers
Model managers allow you to customize the default QuerySet behavior by defining custom methods on the manager class. Managers provide a way to encapsulate common query logic and make it easily accessible across multiple models

```angular2html
class BookManager(models.Manager):
    def get_best_sellers(self):
        return self.filter(sales__gt=1000)

class Book(models.Model):
    title = models.CharField(max_length=100)
    author = models.CharField(max_length=50)
    price = models.DecimalField(max_digits=5, decimal_places=2)
    sales = models.IntegerField()

    objects = BookManager()

# Query to retrieve the best-selling books
best_sellers = Book.objects.get_best_sellers()

```
#### Model inheritance
Django supports model inheritance, allowing you to create more complex data models by building relationships between models. You can use abstract base classes, multi-table inheritance, and proxy models to implement different types of model inheritance

```angular2html
class Publication(models.Model):
    title = models.CharField(max_length=100)
    publisher = models.CharField(max_length=50)

class Book(Publication):
    author = models.CharField(max_length=50)
    price = models.DecimalField(max_digits=5, decimal_places=2)

class Magazine(Publication):
    issue_number = models.IntegerField()

# Query to retrieve all publications (books and magazines)
publications = Publication.objects.all()

```

These examples demonstrate the usage of advanced features in Django ORM, such as Q objects for complex queries, F expressions for database operations, QuerySet methods for data retrieval and manipulation, model managers for custom query logic, and model inheritance for creating relationships between models.

### Class-based views methods
Django class-based views provide a set of methods that can be overridden to customize the behavior of the view. Here are some of the commonly used methods in Django class-based views:

- **as_view()**: 
This method returns a callable view function that handles the request and generates the response. It is called when the URL pattern is matched to the view class.

- **dispatch()**: 
This method is called by the **as_view()** method to handle the request. It inspects the request method (GET, POST, etc.) and calls the appropriate method (get(), post(), etc.) to generate the response.


- **HTTP method handlers**:
The HTTP method handlers (get(), post(), etc.) are called by the **dispatch()** method to generate the response. They perform the necessary operations (querying the database, rendering templates, etc.) and return an **HttpResponse** object.


- **get_context_data()**: 
This method is called by the HTTP method handlers to retrieve the context data for the template. It returns a dictionary of context variables that are passed to the template.

- **get(), post(), put(), delete()**:
These methods are called by the **dispatch()** method to handle the corresponding HTTP methods. They perform the necessary operations (querying the database, rendering templates, etc.) and return an HttpResponse object.

- **get_queryset()**: 
This method is used to retrieve the queryset that the view will use to retrieve objects. It can be overridden to customize the queryset based on the request.

- **get_object()**: 
This method is used to retrieve a single object from the queryset. It can be overridden to customize the object retrieval based on the request.

- **form_valid(), form_invalid()**: 
These methods are called when a form is submitted and validated. They perform the necessary operations (saving the form data, redirecting to a new page, etc.) and return an HttpResponse object.


By understanding these methods, you can customize the behavior of Django class-based views to suit your specific requirements and optimize the performance of your Django applications.


### Django optimization
To optimize your Django application for scalability, there are several techniques you can implement:

#### **Database Optimization:**

Django's database layer provides various ways to improve performance, such as using database indexes, optimizing queries, and reducing database round trips
Suppose you have a Django model called **Book** with a field called **title**. To optimize the database query, you can add an index to the title field by adding **db_index=True** to the field definition in the model:

```angular2html
class Book(models.Model):
    title = models.CharField(max_length=100, db_index=True)
    author = models.CharField(max_length=50)
    
```
this index will speed up queries that filter or order by the title field, as the database can use the index to quickly find the relevant rows

#### **Caching:** 

Implementing caching can significantly improve the performance of your Django application. You can use tools like Django's built-in caching framework. For example, to cache the result of a query for 5 minutes, you can use the **cache_page** decorator:

```angular2html
from django.views.decorators.cache import cache_page

@cache_page(60 * 5)
def my_view(request):
    # perform database query
    books = Book.objects.all()
    
```

#### **Code Optimization:** 

Optimizing your code can help improve the overall performance of your application. This includes writing efficient algorithms, reducing unnecessary database queries, and optimizing resource-intensive operations.

Suppose you have a Django view that returns a list of all **Book** objects in the database. To optimize the code, you can use the **prefetch_related** method to fetch related objects in a single query:

code example:

```angular2html
def book_list(request):
    # perform database query for all books
    books = Book.objects.all()
    # perform database query for each author of each book
    for book in books:
        authors = book.author_set.all()
        ...
```

Optimized version: 

```angular2html
def book_list(request):
    # fetch related authors in a single query
    books = Book.objects.prefetch_related('author_set').all()
    for book in books:
        authors = book.author_set.all()
        ...
```

In the first example, the code performs a separate database query for each author of each book, resulting in a large number of queries. In the second example, the **prefetch_related** method fetches all related authors in a single query, reducing the number of queries and improving performance.

#### **Distributed Task Queues:** 

Using distributed task queues, such as **Celery**, can help offload time-consuming tasks to separate worker processes, allowing your application to handle more concurrent requests.
Suppose you have a view that performs a time-consuming task, such as sending an email. To offload the task to a separate worker process, you can use **Celery** such as below:

```angular2html
from celery import shared_task

@shared_task
def send_email_task(email):
    # send email
    ...

def my_view(request):
    # offload task to Celery worker
    send_email_task.delay(email)
    ...


```

#### **Scaling Horizontally:**

To handle increased traffic and user load, you can scale your Django application horizontally by splitting it into individual services (SOA) and scaling them independently. This approach allows you to distribute the load and optimize each service individually.
Suppose you have a Django application that handles both user authentication and payment processing. To scale the application horizontally, you can split it into two separate services:
1- Authentication service: Handles user authentication and authorization. 
2- Payment service: Handles payment processing and billing.


#### **Benchmarking:** 

Regularly benchmarking and profiling your application can help identify performance bottlenecks and areas for improvement. Tools like **Django Debug Toolbar** and **Django Silk** can assist in analyzing and optimizing your code.


### Generic Foreign Key in Django
In Django, a Generic Foreign Key is a feature that allows you to create a relationship between a model and any other model in the database without directly specifying the related model. This is useful when you have a model that needs to be related to multiple other models. Instead of creating separate foreign keys for each related model, you can use a generic foreign key to achieve this flexibility.

In this example, we will create a model called **Vote**, which can be used to represent votes on different types of content, such as **posts**, **comments**, or **images**.

1- Define the models in **models.py**:

```angular2html
from django.contrib.contenttypes.fields import GenericForeignKey
from django.contrib.contenttypes.models import ContentType
from django.db import models

class Vote(models.Model):
    content_type = models.ForeignKey(ContentType, on_delete=models.CASCADE)
    object_id = models.PositiveIntegerField()
    content_object = GenericForeignKey('content_type', 'object_id')

    voter_name = models.CharField(max_length=100)
    vote_type = models.CharField(max_length=10)  # e.g., 'upvote', 'downvote'

    def __str__(self):
        return f"{self.voter_name} voted on {self.content_object} ({self.vote_type})"

```

2- Create instances of the models:
Now, you can create instances of the **Vote** model and associate them with any other models in the database. For example:

```angular2html
from django.contrib.contenttypes.models import ContentType

# Create a post instance (just an example, you can have other models)
post = Post.objects.create(title="My Post", content="This is my post content")

# Create a comment instance (just an example, you can have other models)
comment = Comment.objects.create(text="Nice post!")

# Create a vote for the post
post_vote = Vote.objects.create(
    content_object=post,
    voter_name="John Doe",
    vote_type="upvote"
)

# Create a vote for the comment
comment_vote = Vote.objects.create(
    content_object=comment,
    voter_name="Alice",
    vote_type="downvote"
)
```
In this example, we have created a Vote model with a generic foreign key, allowing it to be associated with different types of content (posts, comments, etc.). 
You can now use the **Vote** model to track votes on various content types throughout your Django project.

### Django custom exceptions

In Django, you can create custom exceptions to handle specific error scenarios in your application. Custom exceptions allow you to define your own exception classes that inherit from Python's built-in **Exception** class or any other existing exception class. By doing so, you can raise and catch these custom exceptions in your code to handle different types of errors more effectively.
Here's a simple example of how to create and use custom exceptions in Django:

1- Define the custom exception in a **exceptions.py** file (you can create this file in your app directory):

```angular2html
class InvalidDataError(Exception):
    def __init__(self, message="Invalid data provided."):
        self.message = message
        super().__init__(self.message)

```

2- Raise the custom exception in your views or other parts of the code:

```angular2html
from django.shortcuts import render
from .exceptions import InvalidDataError

def custom_exception_view(request):
    try:
        # Some logic to validate data
        data = request.POST.get('data')
        if not data:
            raise InvalidDataError("Data is missing!")

        # Rest of the code for processing valid data
        return render(request, 'success.html', {'data': data})

    except InvalidDataError as e:
        # Handle the custom exception
        error_message = str(e)
        return render(request, 'error.html', {'error_message': error_message})


```

In this example, we create a view function called **custom_exception_view**. Inside the view, we perform some validation on the data received in the POST request. If the data is missing or invalid, we raise the **InvalidDataError** custom exception with a specific error message.

### select_for_update in Django
In Django, **select_for_update** is a method that allows you to lock database rows for update during a database query.  This is useful in scenarios where you want to prevent multiple transactions from simultaneously modifying the same rows, thus avoiding potential conflicts and ensuring data consistency.
When you use **select_for_update**, it places a "select for update" lock on the selected rows in the database. Other transactions attempting to modify the same rows will have to wait until the lock is released. This feature is particularly important in situations where concurrent updates could lead to incorrect results or data integrity issues.

Assume we have a model called **Book** that represents books in a library. We want to ensure that when a user borrows a book, the book's availability status is updated, and during this process, no other user can borrow the same book until the update is complete.

1- Define the model in **models.py**:

```angular2html
from django.db import models

class Book(models.Model):
    title = models.CharField(max_length=100)
    is_available = models.BooleanField(default=True)

    def __str__(self):
        return self.title

```

2- Borrow the book using **select_for_update**:
In your view or business logic, use **select_for_update** to borrow the book and update its availability status:

```angular2html
from django.db import transaction
from .models import Book

def borrow_book(book_id):
    try:
        with transaction.atomic():
            book = Book.objects.select_for_update().get(pk=book_id)
            if book.is_available:
                book.is_available = False
                book.save()
                return f"Successfully borrowed {book.title}."
            else:
                return f"Sorry, {book.title} is not available for borrowing."

    except Book.DoesNotExist:
        return "Book not found."


```

In this example, we use a context manager (**with transaction.atomic()**) to ensure that the update operation is atomic and handled within a single database transaction. The **select_for_update()** method is called on the **Book.objects** queryset to obtain a lock on the selected row for update.

This example demonstrates how to use **select_for_update** to lock a specific row in the database during an update operation to maintain data integrity and consistency in a concurrent environment.
