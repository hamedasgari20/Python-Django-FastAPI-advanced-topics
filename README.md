![](image1.png)

## Introduction

In this research, I have given a brief overview of advanced topics in Python and Django. This article does not provide
in-depth knowledge on various topics and the purpose of this research is to collect topics in one place to provide the
reader with a mental framework. In this article, I have used very simple examples to explain the topics easily.
Naturally, studying and examining more and more practical examples will help a lot to understand each topic. I hope
reading this article is useful for you. (**Hamid Asgari**)



<!-- TOC -->
  * [Introduction](#introduction)
  * [Python related topics:](#python-related-topics)
    * [object-oriented programming (OOP)](#object-oriented-programming-oop)
      * [Inheritance](#inheritance)
      * [Method Resolution Order (MRO)](#method-resolution-order-mro)
        * [1. Single Inheritance](#1-single-inheritance)
        * [2. Multiple Inheritance](#2-multiple-inheritance)
        * [3. The Diamond Inheritance Problem](#3-the-diamond-inheritance-problem)
        * [4. Using super() with MRO](#4-using-super-with-mro)
        * [5. Checking the MRO](#5-checking-the-mro)
      * [Polymorphism](#polymorphism)
      * [Encapsulation](#encapsulation)
      * [Abstraction](#abstraction)
    * [Decorators](#decorators)
    * [More decorators in Python](#more-decorators-in-python)
    * [Map function](#map-function)
    * [Itertools](#itertools)
    * [Lambda function](#lambda-function)
    * [Exception Handling](#exception-handling)
    * [SOLID principles](#solid-principles)
    * [Python collection](#python-collection)
    * [frozenset in Python](#frozenset-in-python)
    * [Generators and Iterators](#generators-and-iterators)
    * [Magic methods](#magic-methods)
    * [GIL](#gil)
    * [concurrency and parallelism](#concurrency-and-parallelism)
    * [Main types of methods in python classes](#main-types-of-methods-in-python-classes)
    * [Data serialization](#data-serialization)
    * [Data class in python](#data-class-in-python)
    * [Shallow copy and deep copy](#shallow-copy-and-deep-copy)
    * [Local and global variables](#local-and-global-variables)
    * [Comprehension](#comprehension)
    * [Pydantic](#pydantic)
    * [Args and Kwargs in Python](#args-and-kwargs-in-python)
    * [Operator overloading](#operator-overloading)
    * [Recursive function](#recursive-function)
    * [Context manager](#context-manager)
    * [Python 3.11 over previous versions](#python-311-over-previous-versions)
    * [Semaphores and Mutexes](#semaphores-and-mutexes)
    * [Python built-in functions](#python-built-in-functions)
    * [Type Hints and Type Checking](#type-hints-and-type-checking)
    * [Package Management](#package-management)
    * [Code Quality Tools](#code-quality-tools)
    * [Performance Profiling](#performance-profiling)
    * [Metaclasses](#metaclasses)
    * [Descriptors](#descriptors)
    * [functools Module](#functools-module)
    * [Advanced Collections](#advanced-collections)
    * [Enum and NamedTuple](#enum-and-namedtuple)
    * [asyncio (Advanced)](#asyncio-advanced)
    * [pathlib Module](#pathlib-module)
    * [Regular Expressions (re module)](#regular-expressions-re-module)
    * [datetime Module](#datetime-module)
    * [__slots__ and Memory Optimization](#__slots__-and-memory-optimization)
    * [__init__ vs __new__](#__init__-vs-__new__)
    * [Abstract Base Classes (ABC) Advanced](#abstract-base-classes-abc-advanced)
    * [Weak References](#weak-references)
    * [Monkey Patching and Metaprogramming](#monkey-patching-and-metaprogramming)
    * [__getattr__ vs __getattribute__](#__getattr__-vs-__getattribute__)
    * [Threading vs Multiprocessing (Detailed)](#threading-vs-multiprocessing-detailed)
    * [Memory Management and Garbage Collection](#memory-management-and-garbage-collection)
    * [JSON vs Pickle Comparison](#json-vs-pickle-comparison)
    * [Protocol and Structural Subtyping](#protocol-and-structural-subtyping)
    * [Composition vs Inheritance](#composition-vs-inheritance)
    * [Duck Typing](#duck-typing)
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
    * [bulk creation in Django](#bulk-creation-in-django)
    * [prefetch_related and select_related in Django](#prefetch_related-and-select_related-in-django)
    * [Third-party packages in Django](#third-party-packages-in-django)
    * [Property decorators](#property-decorators)
    * [WSGI and ASGI](#wsgi-and-asgi)
      * [WSGI (Web Server Gateway Interface):](#wsgi-web-server-gateway-interface)
      * [ASGI (Asynchronous Server Gateway Interface):](#asgi-asynchronous-server-gateway-interface)
    * [Advanced features in ORM](#advanced-features-in-orm)
    * [Class-based views methods](#class-based-views-methods)
    * [Django optimization](#django-optimization)
    * [Generic Foreign Key in Django](#generic-foreign-key-in-django)
    * [Django custom exceptions](#django-custom-exceptions)
    * [select_for_update in Django](#select_for_update-in-django)
    * [Django model methods](#django-model-methods)
    * [Parametric unit tests](#parametric-unit-tests)
    * [Database Migrations (Advanced)](#database-migrations-advanced)
    * [Database Indexing Strategies](#database-indexing-strategies)
    * [Testing in Django](#testing-in-django)
    * [Security Best Practices in Django](#security-best-practices-in-django)
    * [Logging and Monitoring in Django](#logging-and-monitoring-in-django)
  * [FastAPI related topics:](#fastapi-related-topics)
    * [Dependency Injection in FastAPI](#dependency-injection-in-fastapi)
      * [use cases](#use-cases)
    * [Dependency Ordering](#dependency-ordering)
    * [Pydantic methods in FastAPI](#pydantic-methods-in-fastapi)
    * [Decorators in FastAPI](#decorators-in-fastapi)
      * [Real-World Use Cases of decorators:](#real-world-use-cases-of-decorators)
    * [WebSockets in FastAPI](#websockets-in-fastapi)
      * [Real-World Use Cases of websocket:](#real-world-use-cases-of-websocket)
    * [Asynchronous File Uploads](#asynchronous-file-uploads)
      * [Real-World Use Cases of Asynchronous File Uploads:](#real-world-use-cases-of-asynchronous-file-uploads)
    * [Security Headers](#security-headers)
    * [Background Tasks](#background-tasks)
    * [Middleware in FastAPI](#middleware-in-fastapi)
      * [Real-World Use Cases of Middlewares:](#real-world-use-cases-of-middlewares)
    * [Permissions in FastAPI](#permissions-in-fastapi)
    * [Custom Validators in FastAPI](#custom-validators-in-fastapi)
      * [Use Cases in Real-World Applications](#use-cases-in-real-world-applications)
    * [FastAPI BaseSettings](#fastapi-basesettings)
      * [The use of **BaseSettings** in FastAPI has several real-world applications, including:](#the-use-of-basesettings-in-fastapi-has-several-real-world-applications-including)
    * [Dependency Caching](#dependency-caching)
      * [Use Cases in Real-World Applications](#use-cases-in-real-world-applications-1)
    * [Rate Limiting](#rate-limiting)
      * [Use Cases in Real-World Applications](#use-cases-in-real-world-applications-2)
    * [Cache in FastAPI](#cache-in-fastapi)
      * [Use Cases in Real-World Applications](#use-cases-in-real-world-applications-3)
    * [Custom Exceptions in FastAPI](#custom-exceptions-in-fastapi)
      * [Use Cases in Real-World Applications](#use-cases-in-real-world-applications-4)
    * [Optimization techniques in FastAPI](#optimization-techniques-in-fastapi)
    * [Concurrency and Parallelism In FastAPI](#concurrency-and-parallelism-in-fastapi)
    * [API Documentation Best Practices](#api-documentation-best-practices)
    * [Testing in FastAPI](#testing-in-fastapi)
    * [Security Best Practices in FastAPI](#security-best-practices-in-fastapi)
    * [Logging and Monitoring in FastAPI](#logging-and-monitoring-in-fastapi)
  * [General Topics:](#general-topics)
    * [REST API Design Principles](#rest-api-design-principles)
    * [Deployment and DevOps](#deployment-and-devops)
      * [Docker and Containerization](#docker-and-containerization)
      * [CI/CD Pipelines](#cicd-pipelines)
      * [Environment Management](#environment-management)
  * [Interview Preparation questions](#interview-preparation-questions)
    * [PostgreSQL Querying](#postgresql-querying)
    * [Algorithmic Problem Solving](#algorithmic-problem-solving)
      * [Common Data Structures Review](#common-data-structures-review)
      * [Problem-Solving Strategy](#problem-solving-strategy)
      * [Practice Problems & Solutions (Python)](#practice-problems--solutions-python)
  * [Interview Questions](#interview-questions)
    * [Problem 1: Database Transactions (Django & SQLAlchemy)](#problem-1-database-transactions-django--sqlalchemy)
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
from abc import ABC, abstractmethod

class Animal(ABC):
    def __init__(self, name):
        self.name = name

    @abstractmethod
    def speak(self):
        pass

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
print(cat.speak())  # Output: Meow!

```

In this example, Animal is the superclass, and Dog and Cat are subclasses that inherit from it. The speak method is an
abstract method in the Animal class that is implemented in the subclasses.
We import the **ABC** (Abstract Base Class) class from the **abc** module and use the **@abstractmethod** decorator to mark the **speak** method as an abstract method in the **Animal** class. This enforces that subclasses of **Animal** must provide an implementation for the speak method.

#### Method Resolution Order (MRO)

The method resolution order (MRO) defines the sequence in which base classes are searched when executing a method. Initially, the search starts within the class itself, and then proceeds according to the order specified during inheritance. This order is also known as the linearization of a class, and the set of rules governing it is referred to as MRO (Method Resolution Order).

To illustrate this concept more clearly, let's walk through some examples that cover different inheritance scenarios.

##### 1. Single Inheritance

In single inheritance, the MRO is very straightforward. When a derived class inherits from a single base class, Python searches the base class for the desired method or attribute if it’s not found in the derived class.

```
class A:
    def greet(self):
        print("Hello from A")

class B(A):
    pass

b = B()
b.greet()
```

Output:

```
Hello from A
```

##### 2. Multiple Inheritance

In multiple inheritance, the MRO determines the sequence in which parent classes are called. Python uses the C3 linearization algorithm to establish this order, ensuring that each class appears only once.

```
class A:
    def greet(self):
        print("Hello from A")

class B:
    def greet(self):
        print("Hello from B")

class C(A, B):
    pass

c = C()
c.greet()
```

Output:

```
Hello from A
```

##### 3. The Diamond Inheritance Problem

The diamond inheritance problem occurs when a class inherits from multiple classes that share a common ancestor. MRO ensures that the common ancestor is not invoked multiple times, preventing redundancy.

```
class A:
    def greet(self):
        print("Hello from A")

class B(A):
    def greet(self):
        print("Hello from B")

class C(A):
    def greet(self):
        print("Hello from C")

class D(B, C):
    pass

d = D()
d.greet()
```

Output:

```
Hello from B
```

##### 4. Using super() with MRO

Using the super() function in a multiple inheritance scenario ensures that the next class in the MRO sequence is called. This is particularly useful for maintaining a consistent flow through all classes in the hierarchy.

```
class A:
    def greet(self):
        print("Hello from A")

class B(A):
    def greet(self):
        print("Hello from B")
        super().greet()

class C(A):
    def greet(self):
        print("Hello from C")
        super().greet()

class D(B, C):
    def greet(self):
        print("Hello from D")
        super().greet()

d = D()
d.greet()
```

Explanation:

D calls B, B calls C, and C calls A according to the MRO (D -> B -> C -> A).

Using super() ensures that each class in the MRO chain is called in order.

Output:

```
Hello from D
Hello from B
Hello from C
Hello from A
```

##### 5. Checking the MRO

You can inspect the MRO of a class using the mro() method or the __mro__ attribute.

```
print(D.mro())
```

Output:

```
[<class '__main__.D'>, <class '__main__.B'>, <class '__main__.C'>, <class '__main__.A'>, <class 'object'>]
```

This output tells you the exact order in which classes are searched for methods or attributes when an instance of D is used.

#### Polymorphism

Polymorphism is the ability of objects to take on different forms or perform different actions depending on the context.
In Python, polymorphism is achieved through **method overriding** and **method overloading**.

```
from abc import ABC, abstractmethod
import math

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

class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return math.pi * self.radius ** 2

shapes = [Rectangle(5, 10), Circle(7)]
for shape in shapes:
    print(shape.area())

```

In this example, Shape is an abstract class that defines the area method as an abstract method. Rectangle and Circle are
concrete subclasses that implement the area method. The shapes list contains instances of both Rectangle and Circle, and
the area method is called on each instance, demonstrating polymorphism.

In this code, we use the **ABC** class and the **@abstractmethod** decorator to define **Shape** as an abstract base class with an abstract area method. This ensures that subclasses of **Shape** must implement the area method. The **math.pi** constant is used for more accurate calculations of the circle's area.

#### Encapsulation

Encapsulation is the practice of hiding the internal details of an object and providing a public interface for
interacting with it. In Python, encapsulation is achieved through the use of _public and private methods and attributes_.

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

In this example, **BankAccount** is a class that represents a bank account. The **_balance** attribute is marked as _private_
by convention (_using a single underscore_), and can only be accessed through public methods such as **deposit**, **withdraw**,
and **get_balance**.

#### Abstraction

Abstraction is the process of simplifying complex systems by breaking them down into smaller, more manageable parts. In
Python, abstraction is achieved through the use of _abstract classes_ and interfaces.

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

In this example, **Shape** is an abstract class that defines the **area** method as an **abstract** method. **Rectangle** is a concrete
subclass that implements the area method. The shapes list contains an instance of **Rectangle**, demonstrating abstraction.

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

In this example, the **DecoratorClass** is a class-based decorator that takes the original function as an argument in its constructor. The **__call__** method is used to define the behavior of the decorator when the decorated function is called.

### More decorators in Python

In Python, class decorators are functions or callable objects that are used to modify or enhance the behavior of a class. They are applied to the class definition itself and can add or modify class-level attributes, methods, or perform other operations on the class.
Here are a few examples of class decorators:

- classmethod

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

- staticmethod

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

- property

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

- abstractmethod

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

- dataclass

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

- cached_property

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

### SOLID principles

The SOLID principles are a set of design principles that help in creating maintainable, scalable, and flexible software
systems.

- **Single Responsibility Principle (SRP):**

This principle states that a class should have only one responsibility. Let's say we have a **User** class that handles both user authentication and user data management.
Instead, we can separate these responsibilities into two classes: **Authenticator** and **UserManager**. Here's a Python
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

- **Open/Closed Principle (OCP):**

  This principle states that software entities (classes, modules, functions) should be open for extension but closed for
  modification. In other words, you should be able to add new functionality without modifying existing code. Let's say
  we have a **Shape** class with different subclasses such as **Circle** and **Rectangle**. Instead of modifying the **Shape** class
  every time we want to add a new shape, we can use **inheritance** and **polymorphism** to extend the functionality:

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

- **Liskov Substitution Principle (LSP):**

  This principle states that objects of a superclass should be replaceable with objects of its subclasses without
  affecting the correctness of the program. Let's say we have a function that expects a **Shape** object. According to LSP,
  we should be able to pass any subclass of **Shape** without causing any issues. In simpler terms, it means that a subclass should be able to be used wherever its superclass is expected, without causing any issues or breaking the functionality of the program.

Here's a simple Python example to illustrate the _Liskov Substitution Principle_:

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

In this example, we have a superclass called **Shape** with a method **area()** that calculates the area of a shape. We then have two subclasses, **Rectangle** and **Square**, that inherit from the **Shape** class and override the **area()** method to calculate the area specific to each shape.
According to the _Liskov Substitution Principle_, we should be able to use objects of the **Rectangle** and **Square** classes interchangeably with objects of the Shape class. For example:

```angular2html
def print_area(shape):
    print(f"The area is: {shape.area()}")

rectangle = Rectangle(4, 5)
square = Square(4)

print_area(rectangle)  # Output: The area is: 20
print_area(square)  # Output: The area is: 16
```

In this example, we can see that both the **Rectangle** and **Square** objects can be passed to the **print_area()** function, which expects an object of the **Shape** class. This demonstrates the _Liskov Substitution Principle_, as the subclasses can be used in place of the superclass without any issues or breaking the functionality of the program.

- **Interface Segregation Principle (ISP):**

This principle states that clients should not be forced to depend on interfaces they do not use. It promotes the idea of
having smaller, focused interfaces rather than large, general-purpose ones. Let's say we have an **Animal** interface with
methods like **walk(), swim(), and fly()**. Instead of having a single interface **Animal**, we can split it into smaller interfaces
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

- **Dependency Inversion Principle (DIP):**

  This principle states that high-level modules should not depend on low-level modules. Both should depend on
  abstractions. It encourages the use of interfaces or abstract classes to decouple dependencies. . This helps to decouple the high-level and low-level modules, making it easier to change the low-level ones without affecting the high-level ones

### Python collection

Python provides several built-in collection types, such as **lists, tuples, sets, and dictionaries**. These collections can
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

  A dictionary is a collection that stores **key-value** pairs. It is defined using curly braces ({}) and colons (:). Here's
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

### frozenset in Python

In Python, a **frozenset** is an immutable (unchangeable) version of the built-in set type. It is an unordered collection of unique elements, just like a regular set, but it cannot be modified once created. This means you cannot add, remove, or modify elements in a frozenset after it is created.
Here's an example of creating and utilizing a frozenset:

```angular2html
# Create a frozenset
numbers = frozenset([1, 2, 3, 4, 5])

# Accessing elements
for number in numbers:
    print(number)

# Frozenset operations
other_numbers = frozenset([4, 5, 6, 7, 8])

# Union
union = numbers.union(other_numbers)
print(union)  # Output: frozenset({1, 2, 3, 4, 5, 6, 7, 8})

# Intersection
intersection = numbers.intersection(other_numbers)
print(intersection)  # Output: frozenset({4, 5})

# Difference
difference = numbers.difference(other_numbers)
print(difference)  # Output: frozenset({1, 2, 3})

# Subset check
is_subset = numbers.issubset(other_numbers)
print(is_subset)  # Output: False
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

`__new__(self)`: It is a static method that is called before the `__init__` method when creating an object. The primary purpose of **__new__** is to handle the object construction process and return an instance of the class.

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

In this example, we define a Person class that has a **name** and an **age** attribute. We define both __str__ and __repr__ methods for the class. The __str__ method returns a string that is intended to be readable by humans, while the __repr__ method returns a string that is intended to be unambiguous and can be used to recreate the object.
When we create a Person object and print it using the **str()** and **repr()** functions, we get different outputs. The **str()** function calls the __str__ method, which returns a user-friendly string representation of the object. The **repr()** function calls the __repr__ method, which returns a developer-friendly string representation of the object.

### GIL

The **_Global Interpreter Lock_** is a mechanism in _CPython_ (the most common implementation of Python) that serves to serialize access to Python objects, _preventing multiple threads from executing Python bytecodes at once_.
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

In summary, _local variables_ are declared inside a function or method and can only be accessed within that specific block, while _global variables_ are declared outside any function or method and can be accessed throughout the program and inside every function. To modify a global variable inside a function, we need to use the **global** keyword.
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

- Pydantic vs Data Classes:

In summary, Pydantic is more suitable when you need robust data validation, type conversion, and serialization capabilities. It's often used in scenarios where data integrity and consistency are critical, such as in web APIs or data validation pipelines. On the other hand, data classes are a simpler and more lightweight choice for defining basic data structures or DTOs (Data Transfer Objects) where validation and serialization are not primary concerns. Your choice between the two depends on your specific requirements and the complexity of your data handling needs.

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

### Python 3.11 over previous versions

Here are some simple examples of the advantages of using Python 3.11 over previous versions:

- Fine-grained error locations in tracebacks:
  When an error occurs, Python 3.11 will point to the exact expression that caused the error, instead of just the line. For example, if you have a syntax error in a long line of code, Python 3.11 will point to the exact part of the line that caused the error, making it easier to debug.
- Task and exception groups that simplify working with asynchronous code:
  Task groups provide a cleaner syntax for running and monitoring asynchronous tasks. For example, you can use task groups to run multiple tasks concurrently and wait for them to complete before continuing.
- Faster code execution:
  Python 3.11 is faster than previous versions, which means that your Python programs will run faster. For example, if you have a program that performs a lot of computations, you will notice a significant speed improvement in Python 3.11.
- A new built-in library for working with TOML files:
  Python 3.11 includes a new built-in library for working with TOML files, which is a popular configuration file format. For example, you can use the "toml" module to read and write TOML files in your Python programs.

These are just a few simple examples of the advantages of using Python 3.11 over previous versions

### Semaphores and Mutexes

Semaphores and Mutexes are synchronization mechanisms used in concurrent programming to control access to shared resources and avoid race conditions. Here, I'll explain the concepts of Semaphore and Mutex in Python

- Mutex (Mutual Exclusion):
  A Mutex is a synchronization primitive that allows only one thread to access a shared resource at a time. It ensures that only one thread can acquire the mutex and access the protected resource, while other threads must wait until the mutex is released.

Here's a simple Python example using the **threading** module:

```
import threading

# Create a mutex
mutex = threading.Lock()

shared_variable = 0

def increment_shared_variable():
    global shared_variable
    with mutex:
        shared_variable += 1

# Create multiple threads to increment the shared variable
threads = []
for _ in range(5):
    thread = threading.Thread(target=increment_shared_variable)
    threads.append(thread)
    thread.start()

for thread in threads:
    thread.join()

print("Shared variable:", shared_variable)

```

In this example, the **mutex** ensures that only one thread can execute the critical section (incrementing **shared_variable**) at a time, preventing **race conditions**.

- Semaphore:
  A Semaphore is a synchronization primitive that allows a fixed number of threads to access a resource simultaneously. It maintains a count, and threads can acquire or release the semaphore based on this count.

Here's a simple Python example using the **threading** module:

```angular2html
import threading

# Create a semaphore with a maximum of 2 permits
semaphore = threading.Semaphore(2)

def access_shared_resource(thread_id):
    semaphore.acquire()
    print(f"Thread {thread_id} is accessing the shared resource.")
    # Simulate some work
    threading.Event().wait()
    print(f"Thread {thread_id} is releasing the shared resource.")
    semaphore.release()

# Create multiple threads to access the shared resource
threads = []
for i in range(5):
    thread = threading.Thread(target=access_shared_resource, args=(i,))
    threads.append(thread)
    thread.start()

for thread in threads:
    thread.join()

```

In this example, the semaphore allows up to 2 threads to access the shared resource concurrently, while other threads will wait until a permit is released.

### Python built-in functions

Here are some advanced Python built-in functions with simple examples:

- `abs()` - returns the absolute value of a number

```angular2html
print(abs(-5)) # Output: 5
```

- `all()` - returns True if all elements in an iterable are true

```angular2html
print(all([True, True, False])) # Output: False
```

- `any()` - returns True if any element in an iterable is true

```angular2html
print(any([True, True, False])) # Output: True
```

- `bin()` - converts an integer to a binary string

```angular2html
print(bin(10)) # Output: 0b1010
```

- `enumerate()` - returns an iterator that generates tuples containing indices and values from an iterable

```angular2html
fruits = ['apple', 'banana', 'cherry']
for index, value in enumerate(fruits):
    print(index, value)
# Output:
# 0 apple
# 1 banana
# 2 cherry
```

- `map()` - returns an iterator that generates the results of applying a function to the elements of an iterable

```angular2html
def square(num):
    return num ** 2

numbers = [1, 2, 3, 4, 5]
squared_numbers = list(map(square, numbers))
print(squared_numbers) # Output: [1, 4, 9, 16, 25]
```

- `max()` - returns the largest element in an iterable or the largest of two or more arguments

```angular2html
print(max([1, 2, 3])) # Output: 3
```

- `pow()` - returns the result of raising a number to a power

```
print(pow(2, 3)) # Output: 8
```

- `reversed()` - returns an iterator that generates the elements of a sequence in reverse order

```
fruits = ['apple', 'banana', 'cherry']
for fruit in reversed(fruits):
    print(fruit)
# Output:
# cherry
# banana
# apple
```

- `round()` - rounds a number to a specified number of decimal places

```
print(round(3.14159, 2)) # Output: 3.14
```

- `zip()` - returns an iterator that generates tuples by aggregating the elements of several iterables

```
fruits = ['apple', 'banana', 'cherry']
prices = [1.0, 2.0, 3.0]
for fruit, price in zip(fruits, prices):
    print(fruit, price)
# Output:
# apple 1.0
# banana 2.0
# cherry 3.0
```

- `format()` - formats a string using replacement fields

```
name = 'Alice'
age = 30
print('My name is {0} and I am {1} years old.'.format(name, age))
# Output: My name is Alice and I am 30 years old.
```

- `frozenset()` - returns an immutable frozenset object initialized with elements from the given iterable

```angular2html
vowels = ('a', 'e', 'i', 'o', 'u')
f_set = frozenset(vowels)
print(f_set) # Output: frozenset({'a', 'e', 'i', 'o', 'u'})
```

- `getattr()` - returns the value of a named attribute of an object

```
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

person = Person('Alice', 30)
print(getattr(person, 'name')) # Output: 'Alice'
```

- `hash()` - returns the hash value of an object

```angular2html
print(hash('hello')) # Output: -3557965013271865832
```

- `isinstance()` - returns True if an object is an instance of a specified class

```angular2html
class Person:
    pass

person = Person()
print(isinstance(person, Person)) # Output: True
```

- `issubclass()` - returns True if a class is a subclass of a specified class

```angular2html
class Animal:
    pass

class Dog(Animal):
    pass

print(issubclass(Dog, Animal)) # Output: True
```

- `setattr()` - sets the value of a named attribute of an object

```
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

person = Person('Alice', 30)
setattr(person, 'age', 31)
print(person.age) # Output: 31
```

- `delattr()` - deletes a named attribute from an object

```
class Person:
    name = 'Alice'

person = Person()
delattr(person, 'name')
print(hasattr(person, 'name')) # Output: False
```

- `open()` - opens a file and returns a file object

```
file = open('example.txt', 'r')
print(file.read()) # Output: This is an example file.
file.close()
```

- `slice()` - returns a slice object

```
my_list = [1, 2, 3, 4, 5]
my_slice = slice(1, 4)
print(my_list[my_slice]) # Output: [2, 3, 4]
```

### Type Hints and Type Checking

Type hints in Python allow you to specify the expected types of variables, function parameters, and return values. This improves code readability, enables better IDE support, and allows static type checking with tools like `mypy`.

**Basic Type Hints:**

```python
from typing import List, Dict, Optional, Union, Tuple

# Function with type hints
def greet(name: str, age: int) -> str:
    return f"Hello, {name}. You are {age} years old."

# Variables with type hints
count: int = 10
name: str = "Alice"
is_active: bool = True

# Collections
numbers: List[int] = [1, 2, 3, 4, 5]
user_data: Dict[str, Union[str, int]] = {"name": "John", "age": 30}
```

**Optional and Union Types:**

```python
from typing import Optional, Union

def find_user(user_id: int) -> Optional[Dict[str, str]]:
    # Returns Dict or None
    if user_id > 0:
        return {"id": str(user_id), "name": "John"}
    return None

def process_data(data: Union[str, int, float]) -> str:
    return str(data)
```

**Generic Types and Type Variables:**

```python
from typing import TypeVar, Generic, List

T = TypeVar('T')

class Stack(Generic[T]):
    def __init__(self) -> None:
        self._items: List[T] = []
    
    def push(self, item: T) -> None:
        self._items.append(item)
    
    def pop(self) -> T:
        return self._items.pop()

# Usage
int_stack: Stack[int] = Stack()
int_stack.push(1)
int_stack.push(2)
```

**Type Checking with mypy:**

Install mypy: `pip install mypy`

Run type checking: `mypy your_file.py`

**Use Cases:**

1. **Code Documentation:** Type hints serve as inline documentation
2. **IDE Support:** Better autocomplete and error detection
3. **Refactoring:** Safer refactoring with type checking
4. **Team Collaboration:** Clearer code contracts between team members
5. **Catching Bugs:** Static type checking can catch type-related errors before runtime

### Package Management

Effective package management is crucial for Python projects. Here are the main tools and practices:

**pip and requirements.txt:**

```python
# requirements.txt
Django==4.2.0
requests==2.31.0
pytest==7.4.0

# Install packages
# pip install -r requirements.txt

# Generate requirements.txt
# pip freeze > requirements.txt
```

**Poetry (Modern Package Management):**

```bash
# Install Poetry
# curl -sSL https://install.python-poetry.org | python3 -

# Create a new project
poetry new myproject

# Add dependencies
poetry add django
poetry add pytest --dev

# Install dependencies
poetry install

# Update dependencies
poetry update
```

**pyproject.toml (Poetry configuration):**

```toml
[tool.poetry]
name = "myproject"
version = "0.1.0"
description = ""

[tool.poetry.dependencies]
python = "^3.9"
django = "^4.2.0"
requests = "^2.31.0"

[tool.poetry.dev-dependencies]
pytest = "^7.4.0"
black = "^23.0.0"

[build-system]
requires = ["poetry-core"]
build-backend = "poetry.core.masonry.api"
```

**Virtual Environments:**

```bash
# Create virtual environment
python -m venv venv

# Activate (Windows)
venv\Scripts\activate

# Activate (Linux/Mac)
source venv/bin/activate

# Deactivate
deactivate
```

**Best Practices:**

1. **Always use virtual environments** for project isolation
2. **Pin dependency versions** in production (use `==` instead of `>=`)
3. **Separate dev dependencies** from production dependencies
4. **Use poetry or pip-tools** for better dependency resolution
5. **Regularly update dependencies** to get security patches

### Code Quality Tools

Maintaining code quality is essential for long-term project success. Here are key tools:

**Black (Code Formatter):**

```bash
# Install
pip install black

# Format a file
black your_file.py

# Format entire project
black .

# Check without formatting
black --check .
```

**Flake8 (Linter):**

```bash
# Install
pip install flake8

# Run linter
flake8 your_file.py

# Configuration in .flake8 or setup.cfg
[flake8]
max-line-length = 88
exclude = .git,__pycache__,venv
```

**Pylint (Advanced Linting):**

```bash
# Install
pip install pylint

# Run pylint
pylint your_file.py

# Generate configuration
pylint --generate-rcfile > .pylintrc
```

**isort (Import Sorter):**

```bash
# Install
pip install isort

# Sort imports
isort your_file.py

# Check imports
isort --check-only .
```

**Pre-commit Hooks:**

```yaml
# .pre-commit-config.yaml
repos:
  - repo: https://github.com/psf/black
    rev: 23.3.0
    hooks:
      - id: black
  - repo: https://github.com/pycqa/flake8
    rev: 6.0.0
    hooks:
      - id: flake8
  - repo: https://github.com/pycqa/isort
    rev: 5.12.0
    hooks:
      - id: isort
```

**Use Cases:**

1. **Consistent Code Style:** Black ensures consistent formatting
2. **Error Detection:** Linters catch potential bugs and code smells
3. **Import Organization:** isort organizes imports consistently
4. **Automated Checks:** Pre-commit hooks enforce quality before commits
5. **Team Standards:** Shared configuration ensures team-wide consistency

### Performance Profiling

Profiling helps identify performance bottlenecks in your code:

**cProfile (Built-in Profiler):**

```python
import cProfile
import pstats

def slow_function():
    total = 0
    for i in range(1000000):
        total += i * 2
    return total

# Profile the function
profiler = cProfile.Profile()
profiler.enable()
slow_function()
profiler.disable()

# Print statistics
stats = pstats.Stats(profiler)
stats.sort_stats('cumulative')
stats.print_stats(10)  # Print top 10 functions
```

**line_profiler (Line-by-line Profiling):**

```python
# Install: pip install line_profiler

@profile
def my_function():
    result = []
    for i in range(1000):
        result.append(i * 2)
    return result

# Run: kernprof -l -v script.py
```

**memory_profiler (Memory Usage):**

```python
# Install: pip install memory-profiler

@profile
def my_function():
    data = [0] * 1000000
    return sum(data)

# Run: python -m memory_profiler script.py
```

**timeit (Quick Timing):**

```python
import timeit

# Time a function
time_taken = timeit.timeit(
    'sum(range(1000))',
    number=10000
)
print(f"Time taken: {time_taken} seconds")
```

**Use Cases:**

1. **Bottleneck Identification:** Find slow parts of your code
2. **Optimization Guidance:** Know what to optimize first
3. **Memory Leaks:** Detect memory issues
4. **Performance Regression:** Compare performance before/after changes
5. **Production Monitoring:** Profile in production environments

### Metaclasses

Metaclasses are the "classes of classes" - they define how classes are created. They are an advanced feature that allows you to customize class creation.

**Basic Metaclass:**

```python
class MyMeta(type):
    def __new__(cls, name, bases, attrs):
        # Add a class attribute to all classes using this metaclass
        attrs['created_by'] = 'MyMeta'
        return super().__new__(cls, name, bases, attrs)

class MyClass(metaclass=MyMeta):
    pass

print(MyClass.created_by)  # Output: MyMeta
```

**Metaclass for Automatic Registration:**

```python
class RegistryMeta(type):
    registry = {}
    
    def __new__(cls, name, bases, attrs):
        new_class = super().__new__(cls, name, bases, attrs)
        if hasattr(new_class, 'name'):
            cls.registry[new_class.name] = new_class
        return new_class

class Animal(metaclass=RegistryMeta):
    name = None

class Dog(Animal):
    name = 'dog'

class Cat(Animal):
    name = 'cat'

print(RegistryMeta.registry)  # Output: {'dog': <class '__main__.Dog'>, 'cat': <class '__main__.Cat'>}
```

**Use Cases:**

1. **Framework Development:** Django ORM uses metaclasses for model creation
2. **API Generation:** Automatically generate methods based on class attributes
3. **Validation:** Enforce rules during class definition
4. **Singleton Pattern:** Ensure only one instance of a class exists

### Descriptors

Descriptors are objects that define how attribute access works. They're used to implement properties, methods, and static methods.

**Property Descriptor:**

```python
class Temperature:
    def __init__(self):
        self._celsius = 0
    
    def get_celsius(self):
        return self._celsius
    
    def set_celsius(self, value):
        if value < -273.15:
            raise ValueError("Temperature below absolute zero")
        self._celsius = value
    
    celsius = property(get_celsius, set_celsius)

temp = Temperature()
temp.celsius = 25
print(temp.celsius)  # Output: 25
```

**Custom Descriptor:**

```python
class ValidatedAttribute:
    def __init__(self, validator):
        self.validator = validator
        self.name = None
    
    def __set_name__(self, owner, name):
        self.name = name
    
    def __get__(self, obj, objtype=None):
        if obj is None:
            return self
        return obj.__dict__.get(self.name)
    
    def __set__(self, obj, value):
        if not self.validator(value):
            raise ValueError(f"Invalid value for {self.name}")
        obj.__dict__[self.name] = value

def is_positive(value):
    return value > 0

class Product:
    price = ValidatedAttribute(is_positive)
    
    def __init__(self, price):
        self.price = price

# Usage
product = Product(100)  # OK
# product = Product(-10)  # Raises ValueError
```

**Use Cases:**

1. **Data Validation:** Validate attribute values before assignment
2. **Lazy Evaluation:** Compute values only when accessed
3. **Caching:** Cache expensive computations
4. **ORM Implementation:** Django ORM uses descriptors for field access

### functools Module

The `functools` module provides higher-order functions and operations on callable objects.

**lru_cache (Memoization):**

```python
from functools import lru_cache
import time

@lru_cache(maxsize=128)
def fibonacci(n):
    if n < 2:
        return n
    return fibonacci(n-1) + fibonacci(n-2)

# First call - computes
start = time.time()
result = fibonacci(30)
print(f"Time: {time.time() - start}")  # Slower

# Second call - uses cache
start = time.time()
result = fibonacci(30)
print(f"Time: {time.time() - start}")  # Much faster
```

**partial (Partial Application):**

```python
from functools import partial

def multiply(x, y, z):
    return x * y * z

# Create a new function with some arguments pre-filled
multiply_by_2 = partial(multiply, 2)
result = multiply_by_2(3, 4)  # Equivalent to multiply(2, 3, 4)
print(result)  # Output: 24
```

**wraps (Preserving Function Metadata):**

```python
from functools import wraps

def my_decorator(func):
    @wraps(func)  # Preserves function metadata
    def wrapper(*args, **kwargs):
        print(f"Calling {func.__name__}")
        return func(*args, **kwargs)
    return wrapper

@my_decorator
def say_hello(name):
    """Greets a person"""
    return f"Hello, {name}!"

print(say_hello.__name__)  # Output: say_hello (not wrapper)
print(say_hello.__doc__)    # Output: Greets a person
```

**reduce (Functional Reduction):**

```python
from functools import reduce

numbers = [1, 2, 3, 4, 5]
product = reduce(lambda x, y: x * y, numbers)
print(product)  # Output: 120

# Equivalent to:
result = 1
for num in numbers:
    result *= num
```

**Use Cases:**

1. **Performance Optimization:** Cache expensive function calls
2. **Function Composition:** Create specialized functions from general ones
3. **Decorator Development:** Preserve function metadata in decorators
4. **Functional Programming:** Apply functional patterns

### Advanced Collections

Python's `collections` module provides specialized container datatypes.

**defaultdict (Default Dictionary):**

```python
from collections import defaultdict

# Regular dict - raises KeyError for missing keys
regular_dict = {}
# regular_dict['missing']  # KeyError

# defaultdict - returns default value
dd = defaultdict(list)
dd['fruits'].append('apple')
dd['fruits'].append('banana')
print(dd['vegetables'])  # Output: [] (empty list, not KeyError)
```

**Counter (Counting Elements):**

```python
from collections import Counter

# Count occurrences
words = ['apple', 'banana', 'apple', 'cherry', 'banana', 'apple']
counter = Counter(words)
print(counter)  # Output: Counter({'apple': 3, 'banana': 2, 'cherry': 1})

# Most common
print(counter.most_common(2))  # Output: [('apple', 3), ('banana', 2)]
```

**OrderedDict (Remember Insertion Order):**

```python
from collections import OrderedDict

# In Python 3.7+, regular dicts maintain order, but OrderedDict has extra features
od = OrderedDict()
od['first'] = 1
od['second'] = 2
od['third'] = 3

# Move to end
od.move_to_end('first')
print(list(od.keys()))  # Output: ['second', 'third', 'first']
```

**deque (Double-Ended Queue):**

```python
from collections import deque

# Efficient append/pop from both ends
dq = deque([1, 2, 3])
dq.appendleft(0)  # Add to left
dq.append(4)       # Add to right
print(dq)  # Output: deque([0, 1, 2, 3, 4])

dq.popleft()  # Remove from left
dq.pop()      # Remove from right
```

**ChainMap (Multiple Dictionaries):**

```python
from collections import ChainMap

dict1 = {'a': 1, 'b': 2}
dict2 = {'c': 3, 'd': 4}
dict3 = {'b': 5, 'e': 6}

# Chain maps - searches in order
chain = ChainMap(dict1, dict2, dict3)
print(chain['b'])  # Output: 2 (from dict1, first match)
print(chain['c'])  # Output: 3 (from dict2)
```

**Use Cases:**

1. **Data Grouping:** defaultdict for grouping operations
2. **Frequency Analysis:** Counter for counting occurrences
3. **Queue Operations:** deque for efficient queue/stack operations
4. **Configuration Management:** ChainMap for layered configurations

### Enum and NamedTuple

**Enum (Enumerations):**

```python
from enum import Enum, auto

class Color(Enum):
    RED = 1
    GREEN = 2
    BLUE = 3

# Usage
print(Color.RED)        # Output: Color.RED
print(Color.RED.value)  # Output: 1
print(Color.RED.name)  # Output: RED

# Auto values
class Status(Enum):
    PENDING = auto()
    PROCESSING = auto()
    COMPLETED = auto()

# String enum
class HttpMethod(str, Enum):
    GET = "GET"
    POST = "POST"
    PUT = "PUT"
    DELETE = "DELETE"
```

**NamedTuple (Tuple with Named Fields):**

```python
from collections import namedtuple

# Define a named tuple
Point = namedtuple('Point', ['x', 'y'])

# Create instances
p1 = Point(1, 2)
p2 = Point(x=3, y=4)

print(p1.x, p1.y)  # Output: 1 2
print(p1[0])       # Output: 1 (still indexable)

# With type hints (Python 3.6+)
from typing import NamedTuple

class Point(NamedTuple):
    x: int
    y: int

p = Point(1, 2)
print(p.x, p.y)  # Output: 1 2
```

**Use Cases:**

1. **Constants:** Enum for fixed set of values
2. **Status Codes:** Represent states with enums
3. **Data Structures:** NamedTuple for simple data containers
4. **API Design:** Use enums for method types, status codes

### asyncio (Advanced)

Advanced asyncio patterns for complex asynchronous programming.

**Async Context Managers:**

```python
import asyncio

class AsyncContextManager:
    async def __aenter__(self):
        print("Entering async context")
        return self
    
    async def __aexit__(self, exc_type, exc_val, exc_tb):
        print("Exiting async context")
        return False

async def main():
    async with AsyncContextManager() as acm:
        print("Inside async context")
        await asyncio.sleep(1)

asyncio.run(main())
```

**Async Generators:**

```python
async def async_range(n):
    for i in range(n):
        await asyncio.sleep(0.1)
        yield i

async def main():
    async for value in async_range(5):
        print(value)

asyncio.run(main())
```

**Task Groups (Python 3.11+):**

```python
async def fetch_data(url):
    await asyncio.sleep(0.1)
    return f"Data from {url}"

async def main():
    async with asyncio.TaskGroup() as tg:
        task1 = tg.create_task(fetch_data("url1"))
        task2 = tg.create_task(fetch_data("url2"))
        task3 = tg.create_task(fetch_data("url3"))
    
    # All tasks completed
    print(task1.result(), task2.result(), task3.result())

asyncio.run(main())
```

**Use Cases:**

1. **Concurrent I/O:** Handle multiple network requests simultaneously
2. **Streaming Data:** Process data streams asynchronously
3. **Real-time Applications:** WebSockets, chat applications
4. **Resource Management:** Async context managers for resources

### pathlib Module

Modern path handling with `pathlib` (Python 3.4+).

**Basic Usage:**

```python
from pathlib import Path

# Create Path objects
p = Path('/home/user/documents/file.txt')

# Path operations
print(p.name)        # Output: file.txt
print(p.stem)        # Output: file
print(p.suffix)      # Output: .txt
print(p.parent)      # Output: /home/user/documents
print(p.parts)       # Output: ('/', 'home', 'user', 'documents', 'file.txt')

# Join paths
new_path = Path('/home/user') / 'documents' / 'file.txt'
```

**File Operations:**

```python
from pathlib import Path

# Read/write
path = Path('data.txt')
path.write_text('Hello, World!')
content = path.read_text()
print(content)

# Check existence
if path.exists():
    print("File exists")

# Create directory
dir_path = Path('new_directory')
dir_path.mkdir(exist_ok=True)

# Iterate over directory
for file in Path('.').iterdir():
    if file.is_file():
        print(file.name)
```

**Glob Patterns:**

```python
from pathlib import Path

# Find all Python files
for py_file in Path('.').glob('*.py'):
    print(py_file)

# Recursive search
for py_file in Path('.').rglob('*.py'):
    print(py_file)

# Pattern matching
for file in Path('.').glob('test_*.py'):
    print(file)
```

**Use Cases:**

1. **File Management:** Handle file paths cross-platform
2. **Directory Traversal:** Navigate directory structures
3. **Path Manipulation:** Join, split, and modify paths safely
4. **Configuration Files:** Locate config files reliably

### Regular Expressions (re module)

Powerful pattern matching with regular expressions.

**Basic Matching:**

```python
import re

# Search for pattern
text = "The price is $100.50"
match = re.search(r'\$(\d+\.\d+)', text)
if match:
    print(match.group(1))  # Output: 100.50

# Find all matches
text = "Contact: email@example.com or phone: 123-456-7890"
emails = re.findall(r'\b[\w.-]+@[\w.-]+\.\w+\b', text)
print(emails)  # Output: ['email@example.com']
```

**Compiled Patterns:**

```python
import re

# Compile pattern for reuse
pattern = re.compile(r'\d{3}-\d{3}-\d{4}')

text = "Call 123-456-7890 or 987-654-3210"
matches = pattern.findall(text)
print(matches)  # Output: ['123-456-7890', '987-654-3210']
```

**Groups and Capturing:**

```python
import re

text = "Date: 2024-01-15"
pattern = r'(\d{4})-(\d{2})-(\d{2})'
match = re.search(pattern, text)

if match:
    print(match.group(0))  # Output: 2024-01-15 (full match)
    print(match.group(1))  # Output: 2024 (year)
    print(match.group(2))  # Output: 01 (month)
    print(match.group(3))  # Output: 15 (day)
    print(match.groups())  # Output: ('2024', '01', '15')
```

**Substitution:**

```python
import re

text = "Hello, my name is John Doe"
# Replace name with [REDACTED]
result = re.sub(r'\b\w+\s+\w+\b', '[REDACTED]', text)
print(result)  # Output: Hello, my name is [REDACTED]

# With callback
def mask_email(match):
    email = match.group(0)
    return email.split('@')[0] + '@***'

text = "Contact: user@example.com"
result = re.sub(r'\b[\w.-]+@[\w.-]+\.\w+\b', mask_email, text)
print(result)  # Output: Contact: user@***
```

**Use Cases:**

1. **Data Validation:** Validate email, phone, URLs
2. **Text Processing:** Extract information from text
3. **Data Cleaning:** Remove or replace patterns
4. **Parsing:** Parse structured text data

### datetime Module

Comprehensive date and time handling.

**Basic Operations:**

```python
from datetime import datetime, date, time, timedelta

# Current date and time
now = datetime.now()
print(now)  # Output: 2024-01-15 10:30:45.123456

# Create specific date/time
dt = datetime(2024, 1, 15, 10, 30, 45)
print(dt.date())  # Output: 2024-01-15
print(dt.time())  # Output: 10:30:45

# Formatting
formatted = dt.strftime('%Y-%m-%d %H:%M:%S')
print(formatted)  # Output: 2024-01-15 10:30:45

# Parsing
parsed = datetime.strptime('2024-01-15', '%Y-%m-%d')
print(parsed)  # Output: 2024-01-15 00:00:00
```

**Time Arithmetic:**

```python
from datetime import datetime, timedelta

now = datetime.now()

# Add/subtract time
future = now + timedelta(days=7, hours=3)
past = now - timedelta(weeks=2)

# Difference
diff = future - past
print(diff.days)  # Output: 21

# Timezone aware
from datetime import timezone
utc_now = datetime.now(timezone.utc)
print(utc_now)  # Output: 2024-01-15 10:30:45.123456+00:00
```

**Use Cases:**

1. **Date Calculations:** Calculate deadlines, durations
2. **Logging:** Timestamp events
3. **Scheduling:** Schedule tasks and reminders
4. **Data Analysis:** Time series data processing

### __slots__ and Memory Optimization

`__slots__` restricts instance attributes and reduces memory usage.

**Basic Usage:**

```python
class RegularClass:
    def __init__(self, x, y):
        self.x = x
        self.y = y

class SlottedClass:
    __slots__ = ['x', 'y']
    
    def __init__(self, x, y):
        self.x = x
        self.y = y

# Regular class allows dynamic attributes
r = RegularClass(1, 2)
r.z = 3  # OK

# Slotted class doesn't
s = SlottedClass(1, 2)
# s.z = 3  # AttributeError: 'SlottedClass' object has no attribute 'z'
```

**Memory Comparison:**

```python
import sys

class Regular:
    pass

class Slotted:
    __slots__ = ['x', 'y']

r = Regular()
s = Slotted()

print(sys.getsizeof(r))  # Larger (typically 56+ bytes)
print(sys.getsizeof(s))  # Smaller (typically 48 bytes)

# With many instances, the difference is significant
regular_instances = [Regular() for _ in range(1000)]
slotted_instances = [Slotted() for _ in range(1000)]
```

**Use Cases:**

1. **Memory Optimization:** Reduce memory for many instances
2. **Performance:** Faster attribute access
3. **Preventing Errors:** Prevent typos in attribute names
4. **Framework Development:** ORMs use slots for models

### __init__ vs __new__

Understanding the difference between object creation and initialization.

**__new__ (Object Creation):**

```python
class Singleton:
    _instance = None
    
    def __new__(cls):
        if cls._instance is None:
            cls._instance = super().__new__(cls)
        return cls._instance
    
    def __init__(self):
        print("Initialized")

s1 = Singleton()  # Output: Initialized
s2 = Singleton()  # No output (same instance)
print(s1 is s2)   # Output: True
```

**Custom __new__ for Immutability:**

```python
class PositiveInt(int):
    def __new__(cls, value):
        if value < 0:
            raise ValueError("Value must be positive")
        return super().__new__(cls, value)

# Usage
pos = PositiveInt(5)
print(pos)  # Output: 5
# pos = PositiveInt(-5)  # ValueError
```

**Use Cases:**

1. **Singleton Pattern:** Ensure single instance
2. **Immutable Objects:** Control object creation
3. **Subclassing Built-ins:** Customize built-in types
4. **Object Pooling:** Reuse objects for performance

### Abstract Base Classes (ABC) Advanced

Advanced usage of ABCs for interface definition.

**Multiple Abstract Methods:**

```python
from abc import ABC, abstractmethod

class Shape(ABC):
    @abstractmethod
    def area(self):
        pass
    
    @abstractmethod
    def perimeter(self):
        pass
    
    def describe(self):
        return f"Shape with area {self.area()} and perimeter {self.perimeter()}"

class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height
    
    def area(self):
        return self.width * self.height
    
    def perimeter(self):
        return 2 * (self.width + self.height)

# Can't instantiate Shape directly
# shape = Shape()  # TypeError

rect = Rectangle(5, 3)
print(rect.describe())
```

**Abstract Properties:**

```python
from abc import ABC, abstractproperty

class Animal(ABC):
    @abstractproperty
    def sound(self):
        pass

class Dog(Animal):
    @property
    def sound(self):
        return "Woof!"

dog = Dog()
print(dog.sound)  # Output: Woof!
```

**Use Cases:**

1. **Interface Definition:** Define contracts for subclasses
2. **Framework Design:** Create extensible frameworks
3. **Type Checking:** Enable static type checking
4. **Documentation:** Document expected methods

### Weak References

Weak references allow objects to be garbage collected even if referenced.

**Basic Usage:**

```python
import weakref

class MyClass:
    def __init__(self, name):
        self.name = name
    
    def __repr__(self):
        return f"MyClass({self.name})"

# Regular reference
obj = MyClass("test")
ref = obj
del obj
print(ref)  # Still exists

# Weak reference
obj = MyClass("test")
weak_ref = weakref.ref(obj)
print(weak_ref())  # Output: MyClass(test)

del obj
print(weak_ref())  # Output: None (object was garbage collected)
```

**WeakValueDictionary:**

```python
import weakref

class Cache:
    def __init__(self):
        self._cache = weakref.WeakValueDictionary()
    
    def get(self, key):
        return self._cache.get(key)
    
    def set(self, key, value):
        self._cache[key] = value

cache = Cache()
obj = MyClass("cached")
cache.set("key1", obj)

print(cache.get("key1"))  # Output: MyClass(cached)

del obj
print(cache.get("key1"))  # Output: None (automatically removed)
```

**Use Cases:**

1. **Caching:** Cache that doesn't prevent garbage collection
2. **Circular References:** Break circular reference cycles
3. **Observer Pattern:** Weak references in observer patterns
4. **Resource Management:** Manage resources without strong references

### Monkey Patching and Metaprogramming

Dynamically modifying classes and objects at runtime.

**Monkey Patching:**

```python
class MyClass:
    def original_method(self):
        return "Original"

obj = MyClass()

# Add method at runtime
def new_method(self):
    return "New method"

MyClass.new_method = new_method
print(obj.new_method())  # Output: New method

# Replace existing method
def patched_method(self):
    return "Patched"

MyClass.original_method = patched_method
print(obj.original_method())  # Output: Patched
```

**Dynamic Attribute Access:**

```python
class DynamicClass:
    def __getattr__(self, name):
        if name.startswith('get_'):
            attr_name = name[4:]
            return lambda: getattr(self, attr_name, None)
        raise AttributeError(f"'{type(self).__name__}' has no attribute '{name}'")

obj = DynamicClass()
obj.value = 42
print(obj.get_value())  # Output: 42
```

**Use Cases:**

1. **Testing:** Mock methods in tests
2. **Extending Libraries:** Add functionality to third-party code
3. **Plugin Systems:** Dynamically add features
4. **Debugging:** Add logging to existing methods

### __getattr__ vs __getattribute__

Understanding attribute access hooks.

**__getattr__ (Called for Missing Attributes):**

```python
class DynamicAttributes:
    def __init__(self):
        self.existing = "I exist"
    
    def __getattr__(self, name):
        return f"Attribute '{name}' not found, but I'll return this"

obj = DynamicAttributes()
print(obj.existing)      # Output: I exist (normal access)
print(obj.missing)       # Output: Attribute 'missing' not found, but I'll return this
```

**__getattribute__ (Called for All Attributes):**

```python
class LoggingAttributes:
    def __init__(self):
        self.value = 42
    
    def __getattribute__(self, name):
        print(f"Accessing attribute: {name}")
        # Must use super() to avoid infinite recursion
        return super().__getattribute__(name)

obj = LoggingAttributes()
print(obj.value)  # Output: Accessing attribute: value\n42
```

**Use Cases:**

1. **Lazy Loading:** Load attributes on demand
2. **Proxy Objects:** Forward attribute access
3. **Validation:** Validate attribute access
4. **Logging:** Log all attribute accesses

### Threading vs Multiprocessing (Detailed)

Detailed comparison and when to use each.

**Threading (I/O-bound tasks):**

```python
import threading
import requests
import time

def fetch_url(url):
    response = requests.get(url)
    return response.status_code

urls = ['http://example.com'] * 10

# Sequential
start = time.time()
results = [fetch_url(url) for url in urls]
print(f"Sequential: {time.time() - start}")

# Threading
start = time.time()
threads = [threading.Thread(target=fetch_url, args=(url,)) for url in urls]
for t in threads:
    t.start()
for t in threads:
    t.join()
print(f"Threading: {time.time() - start}")  # Much faster for I/O
```

**Multiprocessing (CPU-bound tasks):**

```python
import multiprocessing
import time

def cpu_intensive(n):
    total = 0
    for i in range(n):
        total += i ** 2
    return total

numbers = [10000000] * 4

# Sequential
start = time.time()
results = [cpu_intensive(n) for n in numbers]
print(f"Sequential: {time.time() - start}")

# Multiprocessing
start = time.time()
with multiprocessing.Pool() as pool:
    results = pool.map(cpu_intensive, numbers)
print(f"Multiprocessing: {time.time() - start}")  # Much faster for CPU
```

**Use Cases:**

1. **Threading:** Network requests, file I/O, database queries
2. **Multiprocessing:** Mathematical computations, image processing
3. **Asyncio:** Modern alternative to threading for I/O-bound tasks
4. **Hybrid:** Combine multiprocessing with threading for complex workloads

### Memory Management and Garbage Collection

Understanding Python's memory management.

**Reference Counting:**

```python
import sys

obj = [1, 2, 3]
print(sys.getrefcount(obj))  # Reference count

# Increase references
ref1 = obj
ref2 = obj
print(sys.getrefcount(obj))  # Increased

# Decrease references
del ref1, ref2
print(sys.getrefcount(obj))  # Decreased
```

**Garbage Collection:**

```python
import gc

# Force garbage collection
gc.collect()

# Get GC statistics
stats = gc.get_stats()
print(stats)

# Check if object is tracked
obj = [1, 2, 3]
print(gc.is_tracked(obj))  # True for containers
```

**Circular References:**

```python
class Node:
    def __init__(self, value):
        self.value = value
        self.next = None

# Create circular reference
node1 = Node(1)
node2 = Node(2)
node1.next = node2
node2.next = node1  # Circular!

# Without GC, these would never be freed
del node1, node2
gc.collect()  # GC handles circular references
```

**Use Cases:**

1. **Memory Optimization:** Understand memory usage patterns
2. **Debugging:** Identify memory leaks
3. **Performance:** Optimize memory-intensive applications
4. **Resource Management:** Properly manage resources

### JSON vs Pickle Comparison

Understanding serialization options.

**JSON (Text-based, Portable):**

```python
import json

data = {'name': 'John', 'age': 30, 'scores': [85, 90, 95]}

# Serialize
json_str = json.dumps(data)
print(json_str)  # Output: {"name": "John", "age": 30, "scores": [85, 90, 95]}

# Deserialize
loaded = json.loads(json_str)
print(loaded)  # Output: {'name': 'John', 'age': 30, 'scores': [85, 90, 95]}

# File operations
with open('data.json', 'w') as f:
    json.dump(data, f)

with open('data.json', 'r') as f:
    loaded = json.load(f)
```

**Pickle (Binary, Python-specific):**

```python
import pickle

class CustomClass:
    def __init__(self, value):
        self.value = value

obj = CustomClass(42)

# Serialize
pickled = pickle.dumps(obj)

# Deserialize
unpickled = pickle.loads(pickled)
print(unpickled.value)  # Output: 42

# File operations
with open('data.pkl', 'wb') as f:
    pickle.dump(obj, f)

with open('data.pkl', 'rb') as f:
    loaded = pickle.load(f)
```

**Comparison:**

| Feature | JSON | Pickle |
|---------|------|--------|
| Format | Text | Binary |
| Python objects | Limited | All types |
| Security | Safe | Can execute code |
| Portability | Cross-language | Python only |
| Speed | Slower | Faster |
| File size | Larger | Smaller |

**Use Cases:**

1. **JSON:** API communication, configuration files, data exchange
2. **Pickle:** Python-specific data, complex objects, temporary storage
3. **Security:** Always prefer JSON for untrusted data
4. **Performance:** Pickle for internal Python applications

### Protocol and Structural Subtyping

Python's structural typing system (PEP 544).

**Protocol (Duck Typing with Type Checking):**

```python
from typing import Protocol

class Drawable(Protocol):
    def draw(self) -> None:
        ...

class Circle:
    def draw(self) -> None:
        print("Drawing circle")

class Rectangle:
    def draw(self) -> None:
        print("Drawing rectangle")

def render(item: Drawable) -> None:
    item.draw()

# Works with any object that has draw() method
render(Circle())      # OK
render(Rectangle())   # OK
```

**TypedDict (Dictionary with Type Hints):**

```python
from typing import TypedDict

class UserDict(TypedDict):
    name: str
    age: int
    email: str

# Type-checked dictionary
user: UserDict = {
    'name': 'John',
    'age': 30,
    'email': 'john@example.com'
}

# Type checker will catch errors
# user['invalid'] = 'value'  # Error
```

**Use Cases:**

1. **Type Safety:** Structural typing without inheritance
2. **API Contracts:** Define expected interfaces
3. **Duck Typing:** Formalize duck typing with types
4. **Data Validation:** TypedDict for structured data

### Composition vs Inheritance

Choosing between composition and inheritance.

**Inheritance:**

```python
class Animal:
    def make_sound(self):
        pass

class Dog(Animal):
    def make_sound(self):
        return "Woof!"

class Cat(Animal):
    def make_sound(self):
        return "Meow!"
```

**Composition:**

```python
class Engine:
    def start(self):
        return "Engine started"

class Car:
    def __init__(self):
        self.engine = Engine()  # Composition
    
    def start(self):
        return self.engine.start()

car = Car()
print(car.start())  # Output: Engine started
```

**When to Use:**

- **Inheritance:** "is-a" relationship, code reuse, polymorphism
- **Composition:** "has-a" relationship, flexibility, avoid deep hierarchies

**Use Cases:**

1. **Inheritance:** Model hierarchies, shared behavior
2. **Composition:** Flexible design, avoid coupling
3. **Mixins:** Combine both approaches
4. **Design Patterns:** Strategy, Decorator patterns use composition

### Duck Typing

"If it walks like a duck and quacks like a duck, it's a duck."

**Basic Concept:**

```python
class Duck:
    def quack(self):
        return "Quack!"

class Person:
    def quack(self):
        return "I'm quacking like a duck!"

def make_it_quack(thing):
    # Doesn't care about type, only behavior
    return thing.quack()

print(make_it_quack(Duck()))    # Output: Quack!
print(make_it_quack(Person()))  # Output: I'm quacking like a duck!
```

**Iterable Protocol:**

```python
class MyRange:
    def __init__(self, start, end):
        self.start = start
        self.end = end
    
    def __iter__(self):
        return self
    
    def __next__(self):
        if self.start >= self.end:
            raise StopIteration
        current = self.start
        self.start += 1
        return current

# Works with any iterable
for value in MyRange(1, 5):
    print(value)  # Output: 1, 2, 3, 4

# Works with built-in functions
print(list(MyRange(1, 5)))  # Output: [1, 2, 3, 4]
```

**Use Cases:**

1. **Flexibility:** Write code that works with multiple types
2. **Polymorphism:** Achieve polymorphism without inheritance
3. **Protocols:** Implement protocols implicitly
4. **Pythonic Code:** Write idiomatic Python code

## Django related topics:

### Django signals

Django signals can be used to automate tasks and update data in your application without having to manually perform
those tasks or update the data.
Let's say we have a Django application that allows users to place orders for products. We want to automatically update
the product quantity in the database whenever an order is placed. We can use Django signals to accomplish this.

Let's say you want to send an email notification whenever a new user is registered in your Django application. You can use Django's built-in signals for this purpose.

- **Import necessary modules:**

```angular2html
from django.db import models
from django.contrib.auth.models import User
from django.db.models.signals import post_save
from django.dispatch import receiver
from django.core.mail import send_mail

```

- **Create a signal handler function to send an email:**

```
@receiver(post_save, sender=User)
def send_registration_email(sender, instance, created, **kwargs):
    if created:
        subject = 'Welcome to My Website'
        message = 'Thank you for registering on our website.'
        from_email = 'noreply@example.com'
        recipient_list = [instance.email]

        send_mail(subject, message, from_email, recipient_list)

```

- **Connect the signal handler:**

You need to connect the signal handler to the **post_save** signal of the **User** model. You can do this in your Django app's **apps.py** or **models.py** file, or in a separate **signals.py** file:

```angular2html
from django.apps import AppConfig

class YourAppConfig(AppConfig):
    default_auto_field = 'django.db.models.BigAutoField'
    name = 'your_app'

    def ready(self):
        import your_app.signals  # Import the signals module where you defined your signal handler

```

Now, whenever a new user is registered in your Django application, the **send_registration_email** function will be triggered, sending a welcome email to the user.

**Use cases:**

1. [X]  **User Authentication:** Use signals to perform custom actions when a user is registered or when a user logs in. or Send a welcome email to a user upon registration.
2. [X]  **Database Changes:** Notify users or perform other actions when a certain condition is met, like a low stock alert for an e-commerce application.
3. [X]  **Signals for Models:** Trigger actions when a model is created, updated, or deleted.
4. [X]  **File Uploads:** Perform post-processing tasks on uploaded files. For example, generating thumbnails after an image is uploaded.
5. [X]  **Notification Systems:** Send notifications to users or administrators when certain events occur, such as a new comment on a post.
6. [X]  **Django Middleware:** For instance, you can create a signal that fires before or after middleware processes a request, allowing you to perform custom actions at different points in the request/response cycle.
7. [X]  **Internationalization (i18n) and Localization (l10n):** Use signals to switch the language or locale dynamically based on user preferences or specific events within your application

### Django middleware

Django middleware provides a way to process **requests** and **responses** globally in your application. Middleware can be used
to perform authentication, logging, modifying headers, and more.
Let's say we have a Django application that needs to add a custom header to every HTTP response. We can use Django
middleware to accomplish this.
Here are the steps to use Django middleware:

1. Create a new file called **middleware.py** in the same directory as your settings.py file.
2. Define a class that extends the **MiddlewareMixin** class.
   Implement the **process_response** method to modify the response object.
3. Add your middleware class to the **MIDDLEWARE** setting in your **settings.py** file.

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

**Use cases:**

1. [X]  **Authentication and Authorization:** Middleware can check if a user is authenticated and has the required permissions to access a particular view.
2. [X]  **Security Measures:** Implement security-related tasks such as preventing Cross-Site Request Forgery (CSRF) attacks by adding CSRF tokens to forms or setting security headers like HTTP Strict Transport Security (HSTS) headers.
3. [X]  **Request Transformation:** Modify the request data before it reaches the view. For example, parsing JSON data from the request body and making it available to the view as a Python dictionary.
4. [X]  **Throttling and Rate Limiting:** Implement rate limiting to prevent abuse or overuse of your API or services by limiting the number of requests a client can make within a certain time frame.
5. [X]  **CORS (Cross-Origin Resource Sharing):** Enforce security policies for allowing or denying cross-origin requests to your application's resources.
6. [X]  **Content Compression:** Compress responses to reduce bandwidth usage and improve page load times, especially for resources like HTML, CSS, and JavaScript files.

### Django custom template tags

Custom template tags can be used to perform complex operations on data or to create reusable components for your
templates.
Here's a simple example of how to create a custom template tag in Django:

1. Create a new Python module in one of your Django app's templatetags directory. For example, if you have an app named
   **myapp**, you could create a new module named **myapp_tags.py** in the **myapp/templatetags** directory.
2. Define a function in the module that takes a template context and any arguments you want to pass to the tag. The
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

Here are some common use cases for template tags in Django:

1. [ ]  **Displaying Data from the Database:** Template tags are often used to fetch and display data from the database. You can use **{% for %}** loops to iterate through querysets and display records, or use **{% if %}** tags to conditionally show content based on database values.
2. [ ]  **Including Other Templates:** You can use the **{% include %}** tag to include other templates within your template. This is useful for reusing common components across multiple pages.
3. [ ]  **Conditional Rendering:** Template tags like **{% if %}** and **{% else %}** are used for conditional rendering. You can show different content based on certain conditions.
4. [ ]  **Loading External Scripts and Styles:** You can use the **{% load %}** tag to load custom template tags or template libraries that provide additional functionality.
5. [ ]  **Extending Base Templates:** Template inheritance allows you to create a base template and extend it in other templates. This is useful for maintaining a consistent layout across your site.
6. [ ]  **Setting Variables:** The **{% with %}** tag allows you to set variables within a template, making it easier to reuse values.
7. [ ]  **Handling Forms:** Template tags like **{% csrf_token %}** are used for including CSRF tokens in forms to ensure security. Additionally, you can use tags like **{% forloop %}** to iterate through form fields.

These are just a few examples of how template tags can be used in Django templates to add dynamic behavior and logic to your web pages.

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

**Use cases:**

1. [X]  **Access Control for Views and URLs:** For example, allow only authenticated users to access their profile page, while allowing administrators to access an admin dashboard.
2. [X]  **Admin Panel Permissions:** Define who can create, modify, or delete records in the admin interface for specific models.
3. [X]  **API Access Control:** Implement role-based access control (RBAC) for APIs, allowing different levels of access for different user roles.

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

**Use cases:**

1. [X]  **Filtering and Query Optimization:** For example, you can create a manager that filters out inactive or deleted records by default.
2. [X]  **Data Validation and Preprocessing:** For instance, you can create a manager that ensures all data entered is in uppercase.
3. [X]  **Complex Query Construction:** For example, you can create a manager that fetches the top-rated products based on user reviews.
4. [X]  **Pagination and Result Limiting:** For example, Create a manager that retrieves a specified number of records per page.

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

**Use cases**

1. [X]  **Password Strength Validation:** Ensure that user passwords meet certain complexity requirements, such as a minimum length, the presence of uppercase and lowercase characters, and special characters.
2. [X]  **Age Verification:** Validate that a user's age is above a certain threshold for age-restricted content or actions.
3. [X]  **URL or Domain Validation:** Verify that a URL or domain meets specific criteria, such as being a valid domain name or belonging to an allowed list of domains.
4. [X]  **File Type Validation:** Ensure that uploaded files have valid file extensions or meet specific criteria.
5. [X]  **Consistency Checks:** Ensure consistency between related fields in a model. For example, checking that start dates are earlier than end dates.

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

**Use cases:**

1. [X]  **Data Import/Export:** Export data from your database to different formats for backup or analysis.
2. [X]  **Database Maintenance:** Implement commands for database maintenance tasks, such as creating database backups, purging old records, or optimizing database tables.
3. [X]  **User Management:** Create custom commands for managing users, such as creating user accounts in bulk, resetting passwords, or deactivating inactive users.
4. [X]  **Content Population:** Populate your database with sample or test data for development and testing purposes using custom commands.
5. [X]  **Cache Management:** Develop commands to clear or refresh your cache to keep your application's data cache up to date.
6. [X]  **API Data Fetching:** Create commands to fetch data from external APIs, update your database with the retrieved data, and perform any necessary data transformations.
7. [X]  **Report Generation:** Generate and distribute reports as PDFs, Excel sheets, or other formats using custom management commands.

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

- **Basic filtering:**

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

- **Custom filtering:**

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

This defines custom filters that filter on the **price** field of the Product model. The **min_price** filter filters on products with a price greater than or equal to the provided value, and the **max_price** filter filters on products with a price less than or equal to the provided value.
Instead of using FilterSets, you can directly use the Django ORM filters to perform filtering on your querysets. Django ORM provides a wide range of filter options such as exact **match, case-insensitive match, range filters**, and more. You can chain multiple filters together to create complex queries.

**Use cases:**

1. [X]  **Search Functionality:** Implement a search feature allowing users to search for records based on specific criteria, such as keywords or partial matches in various fields.
2. [X]  **Data Filtering:** Create filters to allow users to filter data based on multiple fields, such as date ranges, categories, or status.
3. [X]  **Exporting Filtered Data:** Enable users to export filtered data to CSV, Excel, or other formats for further analysis or reporting.
4. [X]  **Geolocation Filtering:** Build Filtersets for location-based queries, such as finding nearby places or events within a specific radius.
5. [X]  **Data Visualization:** Integrate Filtersets with data visualization libraries to enable users to filter and explore data interactively.

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

**Use Cases:**

1. [ ]  **Database Transactions:** Use context managers to manage database transactions. This ensures that database changes are committed if the code block executes without errors or rolled back in case of exceptions.
2. [ ]  **File Handling:** Open and close files safely using a context manager, ensuring that files are closed properly even if an exception occurs.
3. [ ]  **Resource Locking:** Implement resource locking to ensure exclusive access to a resource, preventing concurrent access by multiple threads or processes.
4. [ ]  **Database Connections:** Manage database connections and cursors safely, ensuring that connections are closed after use.

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

**Use Cases:**

1. [X]  **Real-Time Chat Applications:** Create real-time chat applications where users can send and receive messages instantly using WebSockets.
2. [X]  **Live Notifications:** Implement live notifications to inform users about new messages, friend requests, updates, or any other events that require immediate user attention.
3. [X]  **Multiplayer Online Games:** Develop real-time multiplayer games using WebSockets for game state synchronization, player interaction, and chat functionality.
4. [X]  **IoT Integration:** Integrate with Internet of Things (IoT) devices by handling real-time data streams, sensor data, and device control.
5. [X]  **Financial Trading Platforms:** Build financial trading applications that require real-time price updates, order execution, and live trading data.
6. [X]  **Geolocation and Mapping:** Develop applications that track and display the real-time location of vehicles, deliveries, or assets on a map.
7. [X]  **Live Video Streaming:** Build live video streaming platforms for webinars, conferences, or live events, where viewers can interact with the stream in real time.

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
- **PATCH** is used to modify a part of a resource on the server. When a client sends a PATCH request in Django, it updates only the specified part of the resource with the new data provided. PATCH is not idempotent, meaning that successive identical PATCH requests may have additional effects. PATCH allows partial updates and side-effects on other resources.

Here's an example of how to handle PUT and PATCH requests in Django using Django REST Framework:

```angular2html
from rest_framework.views import APIView
from rest_framework.response import Response
from rest_framework import status
from myapp_models import MyResource

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

**Use Cases:**

1. [X]  **Authentication Mixin:** Add authentication checks to views, ensuring that only authenticated users can access specific views.
2. [X]  **Permission Mixin:** Check user permissions or roles before allowing access to certain views, ensuring that users have the required privileges.
3. [X]  **Pagination Mixin:** Implement pagination for list views, allowing users to navigate through large datasets.
4. [X]  **Timestamp Mixin:** Add timestamp fields (created_at, updated_at) to models for automatic tracking of creation and modification times.
5. [X]  **Geolocation Mixin:** Add latitude and longitude fields to models, enabling geospatial queries and location-based services.
6. [X]  **Captcha Mixin:** Integrate CAPTCHA validation with forms to prevent spam submissions.
7. [X]  **File Upload Mixin:** Add file upload functionality to forms, allowing users to upload files like images or documents.
8. [X]  **User Tracking Mixin:** Implement middleware to track user activity, such as page views or interactions, and log them for analytics.

These are just a few examples of how mixins can enhance Django applications by promoting code reuse and modularity. They allow you to easily add and extend functionality across various components of your Django project, making your code more maintainable and efficient.

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

**Use Cases:**

1. [X]  **Page Caching:** Cache the rendered HTML of frequently accessed pages to reduce the load on the database and speed up page rendering.
2. [X]  **Queryset Caching:** Cache the results of database queries, especially for complex or frequently used queries. This reduces the need to hit the database repeatedly.
3. [X]  **Template Fragment Caching:** Cache specific portions of templates, such as navigation menus or sidebars, to minimize rendering time for frequently used components.
4. [X]  **Computed Values Caching:** Cache the results of expensive computations or data transformations to avoid recomputation for the same input.
5. [X]  **Third-Party API Responses:** Cache responses from third-party APIs to reduce the number of requests made to external services and improve the application's reliability.
6. [X]  **Rate Limiting:** Implement rate limiting by caching user request information to control the number of requests allowed within a specific time period.

Django provides a flexible caching framework that supports various caching backends, including in-memory caching, file-based caching, and distributed cache systems like Memcached and Redis. By strategically implementing caching in your Django application, you can significantly improve its performance and scalability.

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

- **Django constraints vs model validators differences**

Django constraints and model validators are two different mechanisms for ensuring data integrity in Django applications.
Constraints are used to enforce data integrity rules at the database level, while validators are used to enforce data integrity rules at the application leve.
During exceptions in Django Constraints raise database-level errors such as IntegrityError, while validators raise application-level errors such as ValidationError

**Use Cases:**

1. [X]  **Unique Constraints:** Ensure that a specific field or combination of fields contains unique values across records. Commonly used for unique usernames, email addresses, or product codes.
2. [X]  **Check Constraints:** Specify custom validation rules for data in one or more fields. For example, ensure that a price field is always positive, or that a date falls within a certain range.
3. [X]  **Unique Together Constraints:** Ensure that a combination of fields contains unique values. Useful when you want to enforce uniqueness based on multiple fields, such as a combination of username and email.
4. [X]  **Table-Level Constraints:** Enforce constraints that involve multiple fields or records at the table level. For instance, ensuring that the start date is always earlier than the end date for date ranges.

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

**Use Cases:**

1. [X]  **Data Import and Migration:** Importing data from external sources, such as CSV files or JSON files, into your Django application's database.
2. [X]  **Bulk Updates:** Updating multiple rows in a database table simultaneously when changes need to be made to many records at once.
3. [X]  **Historical Data:** Maintaining historical records, such as version history, snapshots, or backups, by inserting historical data into dedicated tables.

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

```python
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

- **Q objects:**

Q objects allow for complex queries by combining multiple filters using logical operators like AND (&) and OR (|). They encapsulate keyword arguments for filtering and provide more flexibility in query construction

```angular2html
from django.db.models import Q

# Query to retrieve books with either 'fiction' or 'mystery' genre
books = Book.objects.filter(Q(genre='fiction') | Q(genre='mystery'))
```

- **F expressions:**

F expressions allow you to perform database operations using field values without pulling the values from the database. They enable calculations and comparisons directly within the database query, improving performance and reducing round trips to the database

```angular2html
from django.db.models import F

# Query to update the price of all books by increasing it by 10%
Book.objects.all().update(price=F('price') * 1.1)
```

- **QuerySet methods**

Django provides a comprehensive set of QuerySet methods for retrieving, filtering, and manipulating data from the database. These methods include **annotate()**, **aggregate()**, **values()**, **distinct()**, **order_by()**, **reverse()**, and many more

```angular2html
# Query to retrieve the top 5 books with the highest ratings
top_books = Book.objects.order_by('-rating')[:5]

# Query to retrieve the distinct authors of all books
authors = Book.objects.values('author').distinct()

# Query to annotate the average price for each genre
genres = Book.objects.values('genre').annotate(avg_price=Avg('price'))
```

- **Model managers**

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

- **Model inheritance**

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

- **Database Optimization:**

Django's database layer provides various ways to improve performance, such as using database indexes, optimizing queries, and reducing database round trips
Suppose you have a Django model called **Book** with a field called **title**. To optimize the database query, you can add an index to the title field by adding **db_index=True** to the field definition in the model:

```angular2html
class Book(models.Model):
    title = models.CharField(max_length=100, db_index=True)
    author = models.CharField(max_length=50)
  
```

this index will speed up queries that filter or order by the title field, as the database can use the index to quickly find the relevant rows

- **Caching:**

Implementing caching can significantly improve the performance of your Django application. You can use tools like Django's built-in caching framework. For example, to cache the result of a query for 5 minutes, you can use the **cache_page** decorator:

```angular2html
from django.views.decorators.cache import cache_page

@cache_page(60 * 5)
def my_view(request):
    # perform database query
    books = Book.objects.all()
  
```

- **Code Optimization:**

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

- **Distributed Task Queues:**

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

- **Scaling Horizontally:**

To handle increased traffic and user load, you can scale your Django application horizontally by splitting it into individual services (SOA) and scaling them independently. This approach allows you to distribute the load and optimize each service individually.
Suppose you have a Django application that handles both user authentication and payment processing. To scale the application horizontally, you can split it into two separate services:
1- Authentication service: Handles user authentication and authorization.
2- Payment service: Handles payment processing and billing.

- **Benchmarking:**

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

### Django model methods

To list all the methods available for models in Django, we can refer to the methods provided by the base Model class and other related classes.
Here are some common methods available for models in Django:

- ```save():``` :
  Saves the model instance to the database.
- ```delete():```
  Deletes the model instance from the database.
- ```full_clean():```
  Performs model validation, including field validation, and raises any validation errors.
- ```clean_fields(): ```
  Performs field validation and raises any validation errors.
- ```clean():```
  Performs model-specific validation and raises any validation errors.
- ```validate_unique():```
  Validates the uniqueness of fields and raises any validation errors.
- ```refresh_from_db():```
  Reloads the model instance's fields from the database.
- ```get_FOO_display(): ```
  Returns the display value of a choices field, where FOO is the name of the field.
- ```get_absolute_url():```
  Returns the URL for displaying the model instance.
- ```get_field_name():```
  Returns the name of the field associated with a given database column name.
- ```get_next_by_FOO():```
  Returns the next model instance by a specified field, where FOO is the name of the field.
- ```get_previous_by_FOO():```
  Returns the previous model instance by a specified field, where FOO is the name of the field.
- ```serializable_value():```
  Returns the value of a field as a serializable object.
- ```to_json():```
  Returns a JSON representation of the model instance.
- ```to_dict():```
  Returns a dictionary representation of the model instance.
- ```queryset():```
  Is used to customize the initial queryset used in a model's manager
- ```pre_save()``` and ```post_save()```:
  Are signals that are emitted before and after saving a model instance
- ```all()```:
  Returns a QuerySet containing all objects of the model from the database
- ```filter()```:
  Is used to retrieve a subset of objects from the database based on specified criteria

### Parametric unit tests

In Django, parametric unit tests refer to the practice of executing the same test logic with different input parameters or test data. This allows you to write more concise and reusable tests by avoiding code duplication.
Here's a simple example of a parametric unit test in Django:

```angular2html
from django.test import TestCase

def multiply_numbers(a, b):
    return a * b

class MathTestCase(TestCase):
    def test_multiply_numbers(self):
        test_cases = [
            (2, 3, 6),  # (a, b, expected_result)
            (0, 5, 0),
            (-4, 2, -8),
            (10, -3, -30),
        ]

        for a, b, expected_result in test_cases:
            result = multiply_numbers(a, b)
            self.assertEqual(result, expected_result)
```

When running the test, Django's test runner will execute the **test_multiply_numbers** method for each test case, providing detailed feedback for each iteration.

Using parametric unit tests like this helps to reduce code duplication and makes it easier to add, modify, or remove test cases. It also provides a clear overview of which test cases pass or fail and enables you to test your code against a variety of scenarios.

### Database Migrations (Advanced)

Django migrations are a powerful way to manage database schema changes. Understanding advanced migration techniques is crucial for complex projects.

**Custom Migrations:**

```python
# myapp/migrations/0002_custom_migration.py
from django.db import migrations, models

def populate_initial_data(apps, schema_editor):
    # Get the historical model
    MyModel = apps.get_model('myapp', 'MyModel')
    # Create initial data
    MyModel.objects.create(name='Initial Item')

def reverse_populate(apps, schema_editor):
    MyModel = apps.get_model('myapp', 'MyModel')
    MyModel.objects.filter(name='Initial Item').delete()

class Migration(migrations.Migration):
    dependencies = [
        ('myapp', '0001_initial'),
    ]

    operations = [
        migrations.RunPython(populate_initial_data, reverse_populate),
    ]
```

**Data Migrations:**

```python
from django.db import migrations

def update_user_status(apps, schema_editor):
    User = apps.get_model('auth', 'User')
    User.objects.filter(is_active=False).update(status='inactive')

class Migration(migrations.Migration):
    dependencies = [
        ('myapp', '0001_initial'),
    ]

    operations = [
        migrations.RunPython(update_user_status),
    ]
```

**Squashing Migrations:**

```bash
# Squash migrations 0001 to 0005
python manage.py squashmigrations myapp 0001 0005
```

**Use Cases:**

1. **Data Transformation:** Migrate data during schema changes
2. **Backward Compatibility:** Handle migrations that need to work with old data
3. **Performance:** Optimize migration performance for large datasets
4. **Complex Changes:** Handle multi-step schema changes safely

### Database Indexing Strategies

Proper indexing is crucial for database performance. Here are advanced indexing strategies:

**Basic Indexing:**

```python
from django.db import models

class Book(models.Model):
    title = models.CharField(max_length=200, db_index=True)
    author = models.ForeignKey(Author, on_delete=models.CASCADE)
    published_date = models.DateField()
    
    class Meta:
        indexes = [
            models.Index(fields=['title', 'author']),
            models.Index(fields=['-published_date']),  # Descending order
        ]
```

**Composite Indexes:**

```python
class Meta:
    indexes = [
        models.Index(fields=['author', 'published_date'], name='author_date_idx'),
    ]
```

**Partial Indexes (PostgreSQL):**

```python
from django.contrib.postgres.indexes import GinIndex, BTreeIndex

class Article(models.Model):
    title = models.CharField(max_length=200)
    content = models.TextField()
    is_published = models.BooleanField(default=False)
    
    class Meta:
        indexes = [
            models.Index(
                fields=['title'],
                condition=models.Q(is_published=True),
                name='published_title_idx'
            ),
        ]
```

**Full-Text Search Indexes:**

```python
from django.contrib.postgres.indexes import GinIndex
from django.contrib.postgres.search import SearchVectorField

class Article(models.Model):
    title = models.CharField(max_length=200)
    content = models.TextField()
    search_vector = SearchVectorField(null=True)
    
    class Meta:
        indexes = [
            GinIndex(fields=['search_vector']),
        ]
```

**Use Cases:**

1. **Query Optimization:** Speed up frequently used queries
2. **Foreign Key Indexing:** Automatically indexed, but composite indexes can help
3. **Full-Text Search:** Enable fast text search capabilities
4. **Unique Constraints:** Ensure data integrity while maintaining performance

### Testing in Django

Comprehensive testing is essential for Django applications:

**Test Client:**

```python
from django.test import TestCase, Client
from django.urls import reverse

class ViewTestCase(TestCase):
    def setUp(self):
        self.client = Client()
        self.user = User.objects.create_user(
            username='testuser',
            password='testpass123'
        )
    
    def test_home_page(self):
        response = self.client.get(reverse('home'))
        self.assertEqual(response.status_code, 200)
    
    def test_login_required(self):
        response = self.client.get(reverse('protected'))
        self.assertRedirects(response, '/login/')
```

**Mocking External Services:**

```python
from unittest.mock import patch, Mock
from django.test import TestCase

class EmailTestCase(TestCase):
    @patch('myapp.views.send_email')
    def test_send_notification(self, mock_send_email):
        mock_send_email.return_value = True
        response = self.client.post('/send-notification/')
        self.assertTrue(mock_send_email.called)
```

**Factory Boy (Test Data Generation):**

```python
# Install: pip install factory_boy
import factory
from django.contrib.auth.models import User

class UserFactory(factory.django.DjangoModelFactory):
    class Meta:
        model = User
    
    username = factory.Sequence(lambda n: f"user{n}")
    email = factory.LazyAttribute(lambda obj: f"{obj.username}@example.com")

# Usage in tests
user = UserFactory()
```

**Fixtures:**

```python
# fixtures/initial_data.json
[
    {
        "model": "myapp.book",
        "pk": 1,
        "fields": {
            "title": "Test Book",
            "author": 1
        }
    }
]

# In tests
class BookTestCase(TestCase):
    fixtures = ['initial_data.json']
```

**Use Cases:**

1. **Unit Testing:** Test individual components in isolation
2. **Integration Testing:** Test component interactions
3. **API Testing:** Test REST API endpoints
4. **Performance Testing:** Test query performance and optimization

### Security Best Practices in Django

Security is paramount in web applications. Here are essential security practices:

**CSRF Protection:**

```python
from django.views.decorators.csrf import csrf_exempt, csrf_protect

# CSRF is enabled by default
# To exempt (use carefully):
@csrf_exempt
def my_view(request):
    pass
```

**SQL Injection Prevention:**

```python
# BAD - Vulnerable to SQL injection
User.objects.extra(where=["username = '%s'" % username])

# GOOD - Use parameterized queries
User.objects.filter(username=username)
```

**XSS Prevention:**

```python
# In templates, always use:
{{ user_input|escape }}
# or
{% autoescape on %}
    {{ user_input }}
{% endautoescape %}
```

**Password Hashing:**

```python
from django.contrib.auth.hashers import make_password, check_password

# Hash password
hashed = make_password('mypassword')

# Check password
is_valid = check_password('mypassword', hashed)
```

**Security Settings:**

```python
# settings.py
SECURE_SSL_REDIRECT = True
SESSION_COOKIE_SECURE = True
CSRF_COOKIE_SECURE = True
SECURE_BROWSER_XSS_FILTER = True
SECURE_CONTENT_TYPE_NOSNIFF = True
X_FRAME_OPTIONS = 'DENY'
```

**Use Cases:**

1. **Authentication:** Secure user authentication and authorization
2. **Data Protection:** Protect sensitive data from unauthorized access
3. **Input Validation:** Prevent injection attacks
4. **HTTPS Enforcement:** Ensure secure communication

### Logging and Monitoring in Django

Effective logging and monitoring help track application behavior:

**Logging Configuration:**

```python
# settings.py
LOGGING = {
    'version': 1,
    'disable_existing_loggers': False,
    'formatters': {
        'verbose': {
            'format': '{levelname} {asctime} {module} {message}',
            'style': '{',
        },
    },
    'handlers': {
        'file': {
            'level': 'INFO',
            'class': 'logging.FileHandler',
            'filename': 'django.log',
            'formatter': 'verbose',
        },
        'console': {
            'level': 'DEBUG',
            'class': 'logging.StreamHandler',
            'formatter': 'verbose',
        },
    },
    'loggers': {
        'django': {
            'handlers': ['file', 'console'],
            'level': 'INFO',
            'propagate': True,
        },
        'myapp': {
            'handlers': ['file', 'console'],
            'level': 'DEBUG',
        },
    },
}
```

**Using Loggers:**

```python
import logging

logger = logging.getLogger(__name__)

def my_view(request):
    logger.info('Processing request')
    try:
        # Your code
        logger.debug('Debug information')
    except Exception as e:
        logger.error(f'Error occurred: {e}', exc_info=True)
```

**Sentry Integration:**

```python
# Install: pip install sentry-sdk
import sentry_sdk
from sentry_sdk.integrations.django import DjangoIntegration

sentry_sdk.init(
    dsn="your-sentry-dsn",
    integrations=[DjangoIntegration()],
    traces_sample_rate=1.0,
    send_default_pii=True
)
```

**Use Cases:**

1. **Error Tracking:** Monitor and debug production errors
2. **Performance Monitoring:** Track slow queries and operations
3. **Audit Logging:** Log important user actions
4. **Debugging:** Detailed logs for troubleshooting

## FastAPI related topics:

### Dependency Injection in FastAPI

In FastAPI, dependency injection is a powerful feature that allows you to declare dependencies for your route handlers, making your code modular, testable, and reusable. Dependencies can be functions or classes that provide the necessary data or services required by a route. FastAPI automatically manages the injection of these dependencies when a request is processed.
Here's a simple example of dependency injection in FastAPI:

```
from fastapi import FastAPI, Depends

app = FastAPI()

# Dependency function
def get_query_parameter(q: str = None):
    return q or "No query parameter provided."

# Route using the dependency
@app.get("/items/")
async def read_item(commons: str = Depends(get_query_parameter)):
    return {"message": commons}

```

**get_query_parameter** is a dependency function that takes a query parameter **q** and returns its value or a default message if no parameter is provided. **Depends** is used to declare the dependency in the route handler (read_item). FastAPI will automatically execute the **get_query_parameter** function and inject its result into the commons parameter of the route handler. The route handler then uses the value provided by the dependency.

#### use cases

1. **Authentication:** You can use dependency injection to handle authentication. For example, a dependency function could verify an API key, OAuth token, or JWT token and provide user information to the route handler.
2. **Database Connections:** Dependency injection is useful for managing database connections. You can create a dependency that establishes a database connection and injects it into route handlers that require database access.
3. **Configuration Settings:** Injecting configuration settings (e.g., API keys, environment variables) into your route handlers allows for easy configuration changes without modifying the route functions.
4. **Logging:** Use dependency injection to inject a logging service into route handlers, enabling consistent logging across your application.
5. **Caching:** Dependencies can be employed for caching mechanisms. For instance, a dependency can check if the requested data is already cached and return it without hitting the actual data source.
6. **Request Validation:** You can create a dependency function to handle request validation, checking headers, parameters, and request bodies before the route handler is executed.
7. **Authorization:** Dependency injection can be used to handle authorization logic. A dependency function could check whether the authenticated user has the required permissions for a specific operation.
8. **Rate Limiting:** Implementing rate limiting is another use case. A dependency can check the rate limit for a user and prevent excessive requests.

### Dependency Ordering

**Dependency ordering** in FastAPI refers to the order in which dependencies are executed. FastAPI executes dependencies in a top-down order, meaning that dependencies listed first are executed before those listed later. Understanding dependency ordering is crucial when you have dependencies that depend on the results of other dependencies.

Here's an example to illustrate dependency ordering in FastAPI:

```
from fastapi import FastAPI, Depends

app = FastAPI()

# First dependency
async def common_parameters(q: str = None, skip: int = 0, limit: int = 10):
    return {"q": q, "skip": skip, "limit": limit}

# Second dependency that depends on the result of the first one
async def query_processing(params: dict = Depends(common_parameters)):
    # Some processing using the result of the first dependency
    processed_query = f"Processed query: {params['q']}, Skip: {params['skip']}, Limit: {params['limit']}"
    return {"processed_query": processed_query}

# Route using the dependencies
@app.get("/items/")
async def read_item(query_result: dict = Depends(query_processing)):
    return query_result

```

**common_parameters** is the first dependency that provides common parameters like q, skip, and limit. **query_processing** is the second dependency that depends on the result of common_parameters. It performs some processing based on the parameters obtained from the first dependency. The route handler **read_item** depends on the result of **query_processing**. It uses the processed query result in the route response.

### Pydantic methods in FastAPI

In FastAPI, models are typically defined using Pydantic, a data validation and parsing library. Pydantic models in FastAPI can utilize various methods to customize their behavior. These methods help in validating, parsing, and processing the data before it is used in your application. Let's explore some of these methods with examples and discuss their use cases in real-world applications.

- @validator Decorator:
  You can use the @validator decorator to define custom validation logic for a specific field.

```
from typing import List
from pydantic import BaseModel, validator

class Item(BaseModel):
    name: str
    price: float

    @validator("price")
    def validate_price(cls, value):
        if value < 0:
            raise ValueError("Price must be non-negative")
        return round(value, 2)

```

- @root_validator Decorator:
  Use Case: Use the @root_validator decorator to perform validation that involves multiple fields.

```
from pydantic import BaseModel, root_validator

class Item(BaseModel):
    name: str
    price: float
    quantity: int

    @root_validator
    def validate_total_price(cls, values):
        total_price = values['price'] * values['quantity']
        if total_price > 100:
            raise ValueError("Total price cannot exceed 100")
        return values

```

### Decorators in FastAPI

In FastAPI, decorators are used to modify the behavior of functions or class methods. They are functions that take another function as an argument and extend or modify the behavior of that function. Decorators in FastAPI are often used for creating reusable components, handling dependencies, and adding extra functionality to route handlers or other parts of your application.
Let's start with a simple example of using decorators in FastAPI:

```
from fastapi import FastAPI, Depends

app = FastAPI()

# Decorator to log information before and after handling a request
def log_request(func):
    async def wrapper(*args, **kwargs):
        print("Request received")
        response = await func(*args, **kwargs)
        print("Request handled")
        return response
    return wrapper

# Using the decorator for a route
@app.get("/items/", dependencies=[Depends(log_request)])
async def read_items():
    return {"message": "Items retrieved"}

```

#### Real-World Use Cases of decorators:

- **Authentication and Authorization**: To check if a user is authenticated before allowing access to certain routes.
- **Rate Limiting**: To limit the rate of requests to a specific route.
- **Logging and Monitoring**: To log information about incoming requests and responses.
- **Validation and Transformation**: To validate input data before processing it.

### WebSockets in FastAPI

WebSocket is a communication protocol that provides full-duplex communication channels over a single, long-lived connection. FastAPI supports WebSocket communication, allowing you to build real-time applications, such as chat applications, live updates, notifications, or collaborative editing. Let's go through a simple example of using WebSocket in FastAPI and then discuss potential use cases.

Now, let's create a simple WebSocket application:
```
from fastapi import FastAPI, WebSocket

app = FastAPI()

# WebSocket endpoint
@app.websocket("/ws")
async def websocket_endpoint(websocket: WebSocket):
    await websocket.accept()
    while True:
        data = await websocket.receive_text()
        await websocket.send_text(f"Message text was: {data}")

```
The **/ws** route is designated as a WebSocket endpoint. The **websocket_endpoint** function is called when a WebSocket connection is established. It accepts the WebSocket connection and enters a loop to continuously receive and send messages.

The **await websocket.receive_text()** line waits for incoming messages, and **await websocket.send_text()** sends a response back to the client.

#### Real-World Use Cases of websocket:
- **Real-Time Chat Applications:** Implementing real-time chat applications where users can send and receive messages instantly.
- **Live Updates and Notifications:** Providing live updates and notifications to users, such as news updates, sports scores, or social media notifications.
- **Real-Time Monitoring and Dashboards:** Building real-time monitoring dashboards that display live data, such as system metrics, financial data, or IoT sensor readings.
- **Financial Trading Platforms:** Developing financial trading platforms where real-time updates of stock prices, trades, and market data are crucial.
- **Job Processing and Notifications:** Providing real-time updates on the progress of long-running tasks or job processing.

### Asynchronous File Uploads
FastAPI supports asynchronous file uploads, allowing you to handle large file uploads efficiently. This is especially beneficial when dealing with web applications that need to process file uploads without blocking the server for other requests. 

Now, let's create a FastAPI application with an asynchronous file upload endpoint:

```angular2html
from fastapi import FastAPI, File, UploadFile

app = FastAPI()

# Asynchronous file upload endpoint
@app.post("/uploadfile/")
async def create_upload_file(file: UploadFile = File(...)):
    return {"filename": file.filename}

```
The **/uploadfile/** route is designated as an asynchronous file upload endpoint.
The **create_upload_file** function is called when a POST request is made to **/uploadfile/** with a file attached.
The **UploadFile** class from FastAPI's **File** module is used to handle file uploads asynchronously.

#### Real-World Use Cases of Asynchronous File Uploads:
- **Large File Uploads:** Allowing users to upload large files, such as images, videos, or documents, without causing timeouts or blocking other requests.
- **Image and Video Processing:** Processing images or videos uploaded by users asynchronously, such as generating thumbnails, applying filters, or transcoding videos.
- **Document Processing:** Handling document uploads, such as PDFs or text files, and processing them asynchronously, such as extracting text, generating previews, or converting formats.
- **Audio File Processing:** Uploading audio files for processing, such as extracting metadata, analyzing content, or converting formats.

### Security Headers

Security headers play a crucial role in web applications to enhance security by preventing certain types of attacks. FastAPI allows you to set security headers easily, providing protection against common web vulnerabilities.
Now, let's create a FastAPI application with custom security headers:

```
from fastapi import FastAPI
from fastapi.middleware.trustedhost import TrustedHostMiddleware

app = FastAPI()

# Middleware for trusted hosts
app.add_middleware(TrustedHostMiddleware, allowed_hosts=["example.com", "sub.example.com"])

# Middleware for security headers
@app.middleware("http")
async def add_security_headers(request, call_next):
    response = await call_next(request)

    # Set security headers
    response.headers["Strict-Transport-Security"] = "max-age=31536000; includeSubDomains"
    response.headers["Content-Security-Policy"] = "default-src 'self'"
    response.headers["X-Content-Type-Options"] = "nosniff"
    response.headers["X-Frame-Options"] = "DENY"
    response.headers["X-XSS-Protection"] = "1; mode=block"
    response.headers["Referrer-Policy"] = "no-referrer"

    return response

# Route to demonstrate security headers
@app.get("/")
async def read_root():
    return {"message": "Welcome to the secure endpoint!"}

```
The **TrustedHostMiddleware** is used to enforce a list of allowed hostnames for better protection against HTTP Host header attacks.
The **add_security_headers** function is a middleware that sets various security headers in the HTTP response.

The security headers set include:

- **Strict-Transport-Security (HSTS):** Enforces the use of HTTPS for a specified duration.
- **Content-Security-Policy (CSP):** Defines content security policies to mitigate XSS attacks.
- **X-Content-Type-Options:** Prevents browsers from MIME-sniffing a response.
- **X-Frame-Options:** Prevents the browser from rendering a page in a frame.
- **X-XSS-Protection:** Enables a browser's built-in XSS protection.
- **Referrer-Policy:** Controls how much information is included in the Referer header.

Implementing these security headers is an essential part of securing web applications and protecting against a wide range of common web vulnerabilities. They contribute to creating a robust and secure environment for your users and help in maintaining compliance with security standards and best practices.

### Background Tasks
Background tasks in FastAPI allow you to execute functions asynchronously in the background, separate from the main request-response cycle. This is particularly useful for tasks that do not need an immediate response but can be performed in the background to improve the overall responsiveness of your application. 
Now, let's create a FastAPI application with a background task:

```angular2html
from fastapi import FastAPI, BackgroundTasks
import time

app = FastAPI()

# Background task
def process_data(background_tasks: BackgroundTasks, data: str):
    # Simulate a time-consuming task
    time.sleep(5)
    print(f"Processing data: {data}")

# Route using the background task
@app.post("/process_data/")
async def create_process_data(data: str, background_tasks: BackgroundTasks):
    background_tasks.add_task(process_data, data)
    return {"message": "Data processing started in the background"}

```
The **process_data** function is a background task that simulates a time-consuming operation. In a real-world scenario, this could be a task like sending emails, processing images, updating records in a database, etc.

The **create_process_data** route uses the **BackgroundTasks** dependency to add the **process_data** background task. The route returns a response immediately, and the background task runs asynchronously.

### Middleware in FastAPI
Middleware in FastAPI is a function that works with every request before it is processed by any specific path operation and with every response before returning it. 
You can add middleware to FastAPI applications using the **@app.middleware("http")** decorator on top of a function. The middleware function receives the request and a **call_next** function that will receive the request as a parameter. It then passes the request to be processed by the rest of the application and takes the response generated by the application, allowing you to modify it further before returning it

Here's a simple example of a middleware that adds a custom header to the response to measure the processing time:

```
from fastapi import FastAPI, Request
import time

app = FastAPI()

@app.middleware("http")
async def add_process_time_header(request: Request, call_next):
    start_time = time.time()
    response = await call_next(request)
    process_time = time.time() - start_time
    response.headers["X-Process-Time"] = str(process_time)
    return response
    
```
#### Real-World Use Cases of Middlewares:

- Adding custom functionality to the request-response cycle without disrupting the core framework
- Separating concerns and keeping API endpoints focused on their core tasks while handling shared operations through middleware components
- Enabling the addition of authentication, error handling, data transformation, and more by extending the functionality of APIs in unique ways

In addition to built-in middleware, FastAPI allows the creation of custom middleware to extend its capabilities beyond the built-in options, offering a powerful way to enhance the functionality of APIs


### Permissions in FastAPI
In FastAPI, permissions are used to control access to different parts of an application based on the user's role or other factors.

Here's a simple example of using **permissions** in FastAPI to restrict access to a specific route based on the user's role:

```

from fastapi import FastAPI, Depends, HTTPException
from fastapi.security import OAuth2PasswordBearer
from typing import Optional

app = FastAPI()

oauth2_scheme = OAuth2PasswordBearer(tokenUrl="token")

async def get_current_user(token: str = Depends(oauth2_scheme)):
    # Implement logic to get user details from the token
    # Example: decode the token and fetch user details from the database
    # Return the user object if the token is valid, else raise an HTTPException
    return {"username": "user1", "role": "admin"}

def has_permission(user: dict = Depends(get_current_user), required_role: Optional[str] = None):
    if required_role and user["role"] != required_role:
        raise HTTPException(status_code=403, detail="Permission denied")
    return user

@app.get("/admin")
async def admin_route(current_user: dict = Depends(has_permission)):
    return {"message": "Welcome admin!"}

```

**Permissions** in FastAPI are crucial for implementing role-based access control (RBAC) and ensuring that users can only access the resources they are authorized to. Some real-world use cases include:

- **Role-Based Access Control (RBAC):** Restricting access to certain routes or data based on the user's role, such as admin, user, or manager

- **Row-Level Security:** Implementing fine-grained permissions based on the state or attributes of specific resources, such as allowing users to view, edit, or retract scientific papers based on the submission process state

- **Custom Business Logic:** Enforcing custom business rules and access restrictions based on specific application requirements, such as allowing users to modify only their own items

By using permissions, FastAPI applications can ensure that sensitive data and functionality are protected, and that users are granted appropriate access based on their roles and other contextual factors.


### Custom Validators in FastAPI

Custom validators in FastAPI can be implemented using **Pydantic**, which is used for data validation in FastAPI. Pydantic allows you to define custom validation rules for request data. Here's a simple example of using custom validators in FastAPI with Pydantic:

```
from fastapi import FastAPI
from pydantic import BaseModel, Field, ValidationError

app = FastAPI()

class Item(BaseModel):
    name: str
    price: float

    @property
    def price_must_be_positive(cls):
        if cls.price <= 0:
            raise ValueError('price must be positive')

@app.post("/items/")
async def create_item(item: Item):
    try:
        item.price_must_be_positive
    except ValueError as e:
        return {"error": str(e)}
    return {"item_name": item.name, "item_price": item.price}
    
```
In this example, a custom validator **price_must_be_positive** is defined within the **Item** class to ensure that the price of an item is positive. If the validation fails, a **ValueError** is raised, and an appropriate error message is returned.

#### Use Cases in Real-World Applications

Custom validators in FastAPI can be used in various real-world scenarios, such as:

- **Data Integrity Checks:** Ensuring that the incoming data meets specific business rules or constraints, such as validating the format of user input, ensuring the correctness of submitted data, or enforcing specific conditions on the input data
- **Complex Data Validation:** Implementing custom validation logic for complex data structures or interdependent fields, such as validating relationships between different fields or performing custom checks based on multiple input parameters
- **Integration with External Services:** Validating data against external services or APIs, such as verifying the correctness of input data before making requests to external systems or services

By using custom validators, FastAPI applications can enforce specific data validation rules tailored to their business requirements, ensuring the integrity and correctness of incoming data.


### FastAPI BaseSettings
In FastAPI, **BaseSettings** is a class provided by **Pydantic** for managing application settings and environment variables. It allows you to define a settings model with default values and data types, and then load and use these settings throughout your application. Here's a simple example of using **BaseSettings** in FastAPI:

```
from fastapi import FastAPI
from pydantic import BaseSettings

class Settings(BaseSettings):
    app_name: str = "Awesome API"
    admin_email: str
    items_per_user: int = 50

settings = Settings()

app = FastAPI()

@app.get("/info")
async def info():
    return {
        "app_name": settings.app_name,
        "admin_email": settings.admin_email,
        "items_per_user": settings.items_per_user
    }
```
In this example, the **Settings** class inherits from **BaseSettings** and defines the application settings, including default values and data types. These settings can then be used throughout the FastAPI application.

#### The use of **BaseSettings** in FastAPI has several real-world applications, including:

- **Centralized Settings Management:** Providing a centralized and structured way to manage application settings, including environment-specific configurations, database credentials, API keys, and other parameters
- **Environment Variable Handling:** Facilitating the loading and management of environment variables, allowing for easy configuration of application behavior across different deployment environments such as development, testing, and production

By using **BaseSettings**, FastAPI applications can maintain a clear and consistent approach to managing settings and configurations, ensuring that the application behaves predictably across different environments and deployment scenarios.



### Dependency Caching
In FastAPI, dependency caching refers to the ability to cache the result of a dependency function so that it is not re-evaluated for each request. This can be useful for improving performance and reducing redundant computations. Here's a simple example of using dependency caching in FastAPI:

```
from fastapi import FastAPI, Depends
from functools import lru_cache

app = FastAPI()

@lru_cache
def expensive_operation():
    # Simulate an expensive operation
    return "result"

async def get_cached_result(result: str = Depends(expensive_operation)):
    return {"cached_result": result}

@app.get("/cached")
async def cached_endpoint(response: dict = Depends(get_cached_result)):
    return response
```

In this example, the **@lru_cache** decorator is used to cache the result of the **expensive_operation** function. The **get_cached_result** function then depends on the cached result of **expensive_operation**, and the cached result is used in the **/cached** endpoint.

#### Use Cases in Real-World Applications
Dependency caching in FastAPI has several real-world applications, including:

- **Performance Optimization:** Caching the result of computationally expensive operations, such as database queries, external API calls, or complex calculations, to improve response times and reduce server load
- **Rate Limiting:** Using caching to enforce rate limits on certain operations or endpoints by storing and checking the frequency of requests within a specific time frame
- **External Service Integration:** Caching the results of requests to external services or APIs to reduce latency and minimize the impact of service outages or slowdowns

By leveraging dependency caching, FastAPI applications can efficiently manage the results of dependencies, reduce redundant computations, and enhance overall system performance.


### Rate Limiting
**Rate limiting** in FastAPI allows you to restrict the number of requests a client can make to an API within a given time frame. This can be achieved using third-party packages such as **fastapi-limiter**. Here's a simple example of using rate limiting in FastAPI with fastapi-limiter:

```
from fastapi import FastAPI
from fastapi_limiter import FastAPILimiter
from fastapi_limiter.depends import RateLimiter

app = FastAPI()

# Initialize the rate limiter
FastAPILimiter.init()

@app.get("/limited")
@RateLimiter(times=5, seconds=60)
async def limited_endpoint():
    return {"message": "This endpoint is rate-limited"}
    
```

In this example, the **fastapi-limiter** package is used to apply rate limiting to the **/limited** endpoint, allowing a maximum of 5 requests per 60 seconds.

#### Use Cases in Real-World Applications

Rate limiting in FastAPI has several real-world applications, including:
- **Protection Against Abuse:** Preventing abuse and misuse of APIs by limiting the number of requests from a single client within a specific time period, safeguarding the API from excessive traffic and potential denial-of-service attacks
- **Throttling:** Managing the flow of requests to ensure that the API server is not overwhelmed by a large number of requests, maintaining system stability and preventing performance degradation during peak usage periods

By implementing rate limiting, FastAPI applications can effectively manage and control the volume of incoming requests, ensuring the stability, security, and fair usage of the API.


### Cache in FastAPI
FastAPI provides various options for caching responses and function results, including third-party packages such as **fastapi-cache**. This tool allows you to cache FastAPI responses and function results, with support for backends like Redis, Memcached, and Amazon DynamoDB
Here's a simple example of using **fastapi-cache** to cache a FastAPI response:

```
from fastapi import FastAPI
from fastapi_cache import FastAPICache
from fastapi_cache.backends.redis import RedisBackend
from fastapi_cache.decorator import cache
import aioredis

app = FastAPI()

# Initialize the cache with Redis as the backend
@app.on_event("startup")
async def startup():
    redis = await aioredis.create_redis_pool('redis://localhost')
    FastAPICache.init(RedisBackend(redis), prefix="fastapi-cache")

# Cache the response of the endpoint
@app.get("/")
@cache()
async def cached_endpoint():
    return {"message": "This response is cached"}

```

#### Use Cases in Real-World Applications
Caching in FastAPI has several real-world applications, including:
- **Performance Optimization:** Caching responses to reduce the computational load and improve the response time of frequently accessed endpoints, enhancing the overall performance of the API
- **Database Query Results:** Caching the results of database queries to minimize the load on the database and improve the responsiveness of data retrieval operations
- **External API Responses:** Caching responses from external APIs to reduce latency and minimize the impact of external service outages or slowdowns, ensuring a more reliable and responsive API

By leveraging caching in FastAPI, applications can efficiently manage and optimize the handling of responses and data, leading to improved performance and a better user experience.


### Custom Exceptions in FastAPI

Custom exceptions in FastAPI allow you to define and handle application-specific errors in a structured manner. You can create custom exception classes and handle them using FastAPI's exception handling mechanisms. Here's a simple example of using custom exceptions in FastAPI:

```angular2html
from fastapi import FastAPI, HTTPException

app = FastAPI()

class CustomException(Exception):
    def __init__(self, detail: str):
        self.detail = detail

@app.get("/custom_exception")
async def custom_exception_endpoint():
    raise CustomException(detail="Custom exception message")

```
In this example, a custom exception class **CustomException** is defined, and it is raised within the **/custom_exception** endpoint. You can then handle this custom exception using FastAPI's exception handling mechanisms.

#### Use Cases in Real-World Applications
Custom exceptions in FastAPI have several real-world applications, including:

- **Application-Specific Errors:** Defining custom exceptions to represent specific error conditions or business logic failures within the application, providing a structured way to handle and communicate these errors to clients

- **Error Abstraction:** Abstracting and encapsulating complex error handling logic into custom exception classes, promoting code modularity and maintainability by centralizing error management

- **Consistent Error Responses:** Standardizing error responses by using custom exceptions to represent different error scenarios, ensuring a consistent and predictable API behavior for clients

By utilizing custom exceptions, FastAPI applications can effectively manage and communicate application-specific errors, enhancing the robustness and reliability of the API.


### Optimization techniques in FastAPI
FastAPI is a high-performance web framework for building REST APIs in Python. It provides various optimization techniques to enhance the performance of applications.

Some of the Optimization Techniques

- **Asynchronous Programming:** Utilize asynchronous functions to handle heavy request payloads and I/O bound operations

- **Use of Pydantic for Data Validation:** Leverage Pydantic models for data validation and conversion

- **Dependency Caching:** Reuse dependencies and cache their results within a request's scope to avoid recalculating them

- **BackgroundTasks:** Use BackgroundTasks for handling tasks that can be run in the background to improve response times

- **Optimizing CPU Intensive Tasks:** Send CPU intensive tasks to workers in another process for optimization

- **Caching Responses:** Implement response caching to store the results of expensive computations and serve them directly for subsequent identical requests

- **Optimizing JSON Responses:** Utilize FastAPI's JSON response classes for efficient serialization and deserialization of JSON data

- **Asynchronous Database Operations:** Use asynchronous database drivers and queries to optimize database interactions and improve overall request handling

- **Project Structure:** Organize the project structure following best practices to enhance maintainability and performance

- **Use of APIRouter:** Utilize APIRouter to modularize and organize route handling, especially for larger applications with multiple files

- **Observability Tools:** Employ observability tools like New Relic to gain insights into performance issues and optimize FastAPI applications

- **Custom Base Model:** Implement a custom base model from the beginning to ensure consistency and efficiency in data handling

- **Use of Pydantic's BaseSettings for Configs:** Leverage Pydantic's BaseSettings for efficient management of application configurations

- **Optimizing File Handling:** Save files in chunks to optimize file handling and improve overall performance

- **Avoid Unnecessary Asynchronous Operations:** Do not make routes async if there are only blocking I/O operations, as unnecessary async operations can impact performance

- **Careful Usage of Dynamic Pydantic Fields:** Exercise caution when using dynamic Pydantic fields to avoid potential performance impacts

- **Dependency Calls Caching:** Cache dependency calls to improve performance by reusing previously calculated results

- **Documentation:** Ensure comprehensive documentation to facilitate understanding and usage, contributing to efficient development and performance


### Concurrency and Parallelism In FastAPI
Concurrency and parallelism are essential concepts in FastAPI for handling multiple tasks simultaneously and improving performance. Concurrency refers to the ability to execute multiple tasks in overlapping time periods, while parallelism involves executing multiple tasks simultaneously. 
Real-world use cases of concurrency and parallelism in FastAPI include:

- **Handling Multiple Requests:** Concurrency allows the server to handle multiple incoming requests simultaneously, improving the responsiveness of the application.
- **Asynchronous I/O Operations:** Concurrency is beneficial for I/O-bound operations such as reading from databases, making API calls, or accessing files, as it allows the server to perform other tasks while waiting for I/O operations to complete.
- **Parallel Processing:** For CPU-bound tasks like data processing or machine learning computations, parallelism can be used to execute multiple tasks concurrently, leveraging multi-core processors for improved performance.
- **Real-time Data Streaming:** Concurrency enables the server to handle real-time data streaming, such as sending continuous updates to clients while simultaneously processing other tasks.
- **Background Tasks:** Asynchronous operations are useful for executing background tasks, such as sending emails, processing notifications, or performing periodic maintenance tasks without blocking the main application flow

### API Documentation Best Practices

FastAPI automatically generates interactive API documentation, but following best practices enhances its usefulness:

**Customizing OpenAPI Schema:**

```python
from fastapi import FastAPI
from fastapi.openapi.utils import get_openapi

app = FastAPI(
    title="My API",
    description="A comprehensive API for managing resources",
    version="1.0.0",
)

def custom_openapi():
    if app.openapi_schema:
        return app.openapi_schema
    openapi_schema = get_openapi(
        title="My API",
        version="1.0.0",
        description="Custom API documentation",
        routes=app.routes,
    )
    app.openapi_schema = openapi_schema
    return app.openapi_schema

app.openapi = custom_openapi
```

**Adding Examples and Descriptions:**

```python
from pydantic import BaseModel, Field

class Item(BaseModel):
    name: str = Field(..., description="Item name", example="Widget")
    price: float = Field(..., gt=0, description="Item price in USD", example=29.99)
    description: str = Field(None, description="Item description", example="A useful widget")

@app.post("/items/", response_model=Item, summary="Create an item", 
          description="Create a new item in the system",
          response_description="The created item")
async def create_item(item: Item):
    """Create a new item.
    
    - **name**: The name of the item
    - **price**: The price must be greater than 0
    - **description**: Optional description
    """
    return item
```

**Tagging and Grouping:**

```python
@app.post("/users/", tags=["users"], summary="Create user")
async def create_user(user: User):
    pass

@app.get("/users/", tags=["users"], summary="List users")
async def list_users():
    pass

@app.post("/items/", tags=["items"], summary="Create item")
async def create_item(item: Item):
    pass
```

**Use Cases:**

1. **API Discovery:** Help developers understand available endpoints
2. **Testing:** Interactive docs allow testing endpoints directly
3. **Documentation:** Automatic documentation reduces maintenance
4. **Client Generation:** OpenAPI schema can generate client libraries

### Testing in FastAPI

Comprehensive testing ensures FastAPI applications work correctly:

**Test Client:**

```python
from fastapi.testclient import TestClient
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def read_root():
    return {"message": "Hello World"}

# Tests
def test_read_root():
    client = TestClient(app)
    response = client.get("/")
    assert response.status_code == 200
    assert response.json() == {"message": "Hello World"}
```

**Testing with Dependencies:**

```python
from fastapi import Depends
from unittest.mock import Mock

def get_db():
    # Mock database dependency
    return Mock()

@app.get("/items/")
def read_items(db=Depends(get_db)):
    return db.query_items()

def test_read_items():
    client = TestClient(app)
    response = client.get("/items/")
    assert response.status_code == 200
```

**Async Testing:**

```python
import pytest
from httpx import AsyncClient

@pytest.mark.asyncio
async def test_async_endpoint():
    async with AsyncClient(app=app, base_url="http://test") as ac:
        response = await ac.get("/async-endpoint/")
        assert response.status_code == 200
```

**Use Cases:**

1. **Unit Testing:** Test individual endpoints and functions
2. **Integration Testing:** Test complete request/response cycles
3. **API Contract Testing:** Ensure API contracts are maintained
4. **Performance Testing:** Test endpoint performance under load

### Security Best Practices in FastAPI

Security is critical for API applications:

**Authentication with JWT:**

```python
from fastapi import Depends, HTTPException, status
from fastapi.security import OAuth2PasswordBearer
from jose import JWTError, jwt

oauth2_scheme = OAuth2PasswordBearer(tokenUrl="token")

SECRET_KEY = "your-secret-key"
ALGORITHM = "HS256"

async def get_current_user(token: str = Depends(oauth2_scheme)):
    credentials_exception = HTTPException(
        status_code=status.HTTP_401_UNAUTHORIZED,
        detail="Could not validate credentials",
        headers={"WWW-Authenticate": "Bearer"},
    )
    try:
        payload = jwt.decode(token, SECRET_KEY, algorithms=[ALGORITHM])
        username: str = payload.get("sub")
        if username is None:
            raise credentials_exception
    except JWTError:
        raise credentials_exception
    return username

@app.get("/protected/")
async def protected_route(current_user: str = Depends(get_current_user)):
    return {"user": current_user}
```

**Input Validation:**

```python
from pydantic import BaseModel, validator, EmailStr

class UserCreate(BaseModel):
    email: EmailStr
    password: str
    
    @validator('password')
    def validate_password(cls, v):
        if len(v) < 8:
            raise ValueError('Password must be at least 8 characters')
        return v
```

**Rate Limiting:**

```python
from slowapi import Limiter, _rate_limit_exceeded_handler
from slowapi.util import get_remote_address
from slowapi.errors import RateLimitExceeded

limiter = Limiter(key_func=get_remote_address)
app.state.limiter = limiter
app.add_exception_handler(RateLimitExceeded, _rate_limit_exceeded_handler)

@app.get("/api/")
@limiter.limit("5/minute")
async def limited_endpoint(request: Request):
    return {"message": "This is rate limited"}
```

**CORS Configuration:**

```python
from fastapi.middleware.cors import CORSMiddleware

app.add_middleware(
    CORSMiddleware,
    allow_origins=["https://example.com"],
    allow_credentials=True,
    allow_methods=["*"],
    allow_headers=["*"],
)
```

**Use Cases:**

1. **Authentication:** Secure API access with tokens
2. **Authorization:** Control access to resources
3. **Input Sanitization:** Prevent injection attacks
4. **Rate Limiting:** Prevent abuse and ensure fair usage

### Logging and Monitoring in FastAPI

Effective logging and monitoring help track API behavior:

**Structured Logging:**

```python
import logging
import sys
from pythonjsonlogger import jsonlogger

# Configure JSON logger
logHandler = logging.StreamHandler(sys.stdout)
formatter = jsonlogger.JsonFormatter()
logHandler.setFormatter(formatter)
rootLogger = logging.getLogger()
rootLogger.addHandler(logHandler)
rootLogger.setLevel(logging.INFO)

logger = logging.getLogger(__name__)

@app.get("/items/")
async def get_items():
    logger.info("Fetching items", extra={"endpoint": "/items/"})
    return {"items": []}
```

**Request Logging Middleware:**

```python
import time
from fastapi import Request

@app.middleware("http")
async def log_requests(request: Request, call_next):
    start_time = time.time()
    response = await call_next(request)
    process_time = time.time() - start_time
    logger.info(
        "Request processed",
        extra={
            "method": request.method,
            "url": str(request.url),
            "status_code": response.status_code,
            "process_time": process_time,
        }
    )
    return response
```

**Prometheus Metrics:**

```python
# Install: pip install prometheus-fastapi-instrumentator
from prometheus_fastapi_instrumentator import Instrumentator

Instrumentator().instrument(app).expose(app)
```

**Use Cases:**

1. **Error Tracking:** Monitor and debug production errors
2. **Performance Monitoring:** Track response times and throughput
3. **Audit Logging:** Log important API operations
4. **Analytics:** Understand API usage patterns

## General Topics:

### REST API Design Principles

Following REST principles ensures APIs are intuitive and maintainable:

**Resource-Based URLs:**

```python
# Good
GET    /api/users/          # List users
POST   /api/users/          # Create user
GET    /api/users/123/      # Get user
PUT    /api/users/123/      # Update user
DELETE /api/users/123/      # Delete user

# Bad
GET    /api/getUser/123
POST   /api/createUser
```

**HTTP Status Codes:**

```python
from fastapi import status

@app.post("/users/", status_code=status.HTTP_201_CREATED)
async def create_user(user: User):
    return user

@app.get("/users/", status_code=status.HTTP_200_OK)
async def list_users():
    return []

@app.get("/users/999/", status_code=status.HTTP_404_NOT_FOUND)
async def get_user(user_id: int):
    raise HTTPException(status_code=404, detail="User not found")
```

**Versioning:**

```python
# URL versioning
@app.get("/v1/users/")
async def list_users_v1():
    pass

@app.get("/v2/users/")
async def list_users_v2():
    pass

# Header versioning
@app.get("/users/", headers={"API-Version": "v1"})
async def list_users():
    pass
```

**Pagination:**

```python
from fastapi import Query

@app.get("/items/")
async def list_items(
    skip: int = Query(0, ge=0),
    limit: int = Query(10, ge=1, le=100)
):
    return {"items": [], "skip": skip, "limit": limit}
```

**Use Cases:**

1. **API Consistency:** Standard patterns make APIs easier to use
2. **Scalability:** RESTful design supports growth
3. **Maintainability:** Clear structure simplifies updates
4. **Developer Experience:** Intuitive APIs reduce learning curve

### Deployment and DevOps

#### Docker and Containerization

Containerization ensures consistent deployment across environments:

**Dockerfile for FastAPI:**

```dockerfile
FROM python:3.11-slim

WORKDIR /app

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]
```

**Dockerfile for Django:**

```dockerfile
FROM python:3.11-slim

WORKDIR /app

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

RUN python manage.py collectstatic --noinput

CMD ["gunicorn", "myproject.wsgi:application", "--bind", "0.0.0.0:8000"]
```

**Docker Compose:**

```yaml
version: '3.8'

services:
  web:
    build: .
    ports:
      - "8000:8000"
    environment:
      - DATABASE_URL=postgresql://user:pass@db:5432/mydb
    depends_on:
      - db
  
  db:
    image: postgres:15
    environment:
      - POSTGRES_DB=mydb
      - POSTGRES_USER=user
      - POSTGRES_PASSWORD=pass
    volumes:
      - postgres_data:/var/lib/postgresql/data

volumes:
  postgres_data:
```

**Use Cases:**

1. **Environment Consistency:** Same environment in dev, staging, production
2. **Isolation:** Applications don't interfere with each other
3. **Scalability:** Easy to scale containers horizontally
4. **CI/CD Integration:** Containers work seamlessly with CI/CD pipelines

#### CI/CD Pipelines

Automated testing and deployment improve development workflow:

**GitHub Actions Example:**

```yaml
# .github/workflows/ci.yml
name: CI

on: [push, pull_request]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Set up Python
        uses: actions/setup-python@v4
        with:
          python-version: '3.11'
      - name: Install dependencies
        run: |
          pip install -r requirements.txt
          pip install pytest
      - name: Run tests
        run: pytest
      - name: Run linter
        run: |
          pip install black flake8
          black --check .
          flake8 .
  
  deploy:
    needs: test
    runs-on: ubuntu-latest
    if: github.ref == 'refs/heads/main'
    steps:
      - uses: actions/checkout@v3
      - name: Deploy to production
        run: |
          # Deployment commands
```

**GitLab CI Example:**

```yaml
# .gitlab-ci.yml
stages:
  - test
  - deploy

test:
  stage: test
  image: python:3.11
  script:
    - pip install -r requirements.txt
    - pytest
    - black --check .
    - flake8 .

deploy:
  stage: deploy
  script:
    - echo "Deploying to production"
  only:
    - main
```

**Use Cases:**

1. **Automated Testing:** Run tests on every commit
2. **Code Quality:** Enforce code standards automatically
3. **Deployment Automation:** Deploy to production automatically
4. **Rollback Capability:** Easy to revert to previous versions

#### Environment Management

Managing different environments (dev, staging, production) effectively:

**Environment Variables:**

```python
# .env
DATABASE_URL=postgresql://user:pass@localhost/db
SECRET_KEY=your-secret-key
DEBUG=True

# settings.py
import os
from dotenv import load_dotenv

load_dotenv()

DATABASE_URL = os.getenv("DATABASE_URL")
SECRET_KEY = os.getenv("SECRET_KEY")
DEBUG = os.getenv("DEBUG", "False") == "True"
```

**Configuration Management:**

```python
# config.py
from pydantic_settings import BaseSettings

class Settings(BaseSettings):
    database_url: str
    secret_key: str
    debug: bool = False
    
    class Config:
        env_file = ".env"
        env_file_encoding = "utf-8"

settings = Settings()
```

**Use Cases:**

1. **Security:** Keep secrets out of code
2. **Flexibility:** Different configs for different environments
3. **Maintainability:** Centralized configuration management
4. **Compliance:** Meet security and compliance requirements

## Interview Preparation questions

This guide provides explanations, practical examples, questions, answers, and Python code snippets to solidify your understanding. Let's dive in!

### PostgreSQL Querying

- **Why Raw SQL?**

While ORMs (like SQLAlchemy or Django ORM) are incredibly useful for rapid development and abstraction, understanding raw SQL is crucial for:

*   **Performance Tuning:** Writing highly optimized queries that an ORM might not generate.
*   **Complex Reporting:** Crafting intricate queries involving multiple joins, subqueries, window functions, or CTEs.
*   **Debugging:** Understanding the exact SQL being executed by an ORM or identifying database-level issues.
*   **Database Features:** Leveraging specific PostgreSQL features not directly exposed by all ORMs (e.g., specific index types, extensions).
*   **Legacy Systems:** Working with systems that may not use an ORM.


- **Core SQL Concepts Review**

Before diving into questions, let's quickly recap essential SQL commands:

*   `SELECT`: Retrieves data from one or more tables.
*   `FROM`: Specifies the table(s) to query.
*   `WHERE`: Filters rows based on specified conditions.
*   `JOIN` (`INNER`, `LEFT`, `RIGHT`, `FULL OUTER`): Combines rows from two or more tables based on a related column.
*   `GROUP BY`: Groups rows that have the same values in specified columns into a summary row. Often used with aggregate functions (`COUNT`, `MAX`, `MIN`, `SUM`, `AVG`).
*   `HAVING`: Filters groups based on a specified condition (used *after* `GROUP BY`).
*   `ORDER BY`: Sorts the result set based on specified columns (`ASC`, `DESC`).
*   `LIMIT`: Restricts the number of rows returned.
*   `OFFSET`: Skips a specified number of rows before starting to return rows (often used with `LIMIT` for pagination).
*   `INSERT INTO`: Adds new rows to a table.
*   `UPDATE`: Modifies existing rows in a table.
*   `DELETE FROM`: Removes rows from a table.
*   **Transactions:** (`BEGIN`, `COMMIT`, `ROLLBACK`) Ensuring atomicity of operations.
*   **Indexes:** Data structures that improve the speed of data retrieval operations. Common types: B-tree (default), Hash, GiST, GIN.
*   **Subqueries:** Queries nested inside another query.
*   **Common Table Expressions (CTEs):** (`WITH ... AS ...`) Temporary, named result sets you can reference within a single statement. Improves readability for complex queries.
*   **Window Functions:** Perform calculations across a set of table rows that are somehow related to the current row (e.g., ranking, running totals).

- **Example Schema**

We'll use the following simple schema for our practice questions:

```sql
-- Departments Table
CREATE TABLE departments (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100) NOT NULL UNIQUE,
    location VARCHAR(100)
);

-- Employees Table
CREATE TABLE employees (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE,
    salary DECIMAL(10, 2) CHECK (salary > 0),
    hire_date DATE DEFAULT CURRENT_DATE,
    department_id INTEGER REFERENCES departments(id) ON DELETE SET NULL -- Foreign key
);

-- Projects Table
CREATE TABLE projects (
    id SERIAL PRIMARY KEY,
    name VARCHAR(150) NOT NULL UNIQUE,
    start_date DATE,
    deadline DATE
);

-- Employee-Project Junction Table (Many-to-Many)
CREATE TABLE employee_projects (
    employee_id INTEGER REFERENCES employees(id) ON DELETE CASCADE,
    project_id INTEGER REFERENCES projects(id) ON DELETE CASCADE,
    role VARCHAR(50),
    PRIMARY KEY (employee_id, project_id) -- Composite primary key
);

-- Sample Data (Conceptual)
INSERT INTO departments (name, location) VALUES
('Engineering', 'Building A'), ('Sales', 'Building B'), ('HR', 'Building A'), ('Marketing', 'Building B');

INSERT INTO employees (name, email, salary, department_id) VALUES
('Alice', 'alice@company.com', 90000, 1),
('Bob', 'bob@company.com', 85000, 1),
('Charlie', 'charlie@company.com', 70000, 2),
('David', 'david@company.com', 72000, 2),
('Eve', 'eve@company.com', 110000, 1),
('Frank', 'frank@company.com', 60000, 3),
('Grace', 'grace@company.com', 95000, NULL); -- No department assigned yet

INSERT INTO projects (name, start_date, deadline) VALUES
('Project Alpha', '2023-01-15', '2023-12-31'),
('Project Beta', '2023-03-01', '2024-06-30'),
('Project Gamma', '2023-07-01', NULL);

INSERT INTO employee_projects (employee_id, project_id, role) VALUES
(1, 1, 'Developer'), (1, 2, 'Lead Developer'),
(2, 1, 'Developer'),
(3, 2, 'Sales Lead'),
(5, 2, 'Tech Lead'),
(5, 3, 'Architect');
```

- **Practice Questions & Answers (SQL)**

**Q1: Basic Retrieval**

*   **Question:** Find the names and salaries of all employees earning more than $80,000.
*   **Answer (SQL):**
    ```sql
    SELECT name, salary
    FROM employees
    WHERE salary > 80000;
    ```
    
**Q2: `ORDER BY` and `LIMIT`**

*   **Question:** Find the names and hire dates of the 3 most recently hired employees.
*   **Answer (SQL):**
    ```sql
    SELECT name, hire_date
    FROM employees
    ORDER BY hire_date DESC
    LIMIT 3;
    ```

**Q3: `JOIN`**

*   **Question:** List the names of all employees and their corresponding department names. Only include employees who are assigned to a department.
*   **Answer (SQL):**
    ```sql
    SELECT e.name AS employee_name, d.name AS department_name
    FROM employees e
    INNER JOIN departments d ON e.department_id = d.id;
    ```



**Q4: `LEFT JOIN`**

*   **Question:** List all employee names and their department names. Include employees even if they are not currently assigned to a department.
*   **Answer (SQL):**
    ```sql
    SELECT e.name AS employee_name, d.name AS department_name
    FROM employees e
    LEFT JOIN departments d ON e.department_id = d.id;
    ```
*   **Explanation:** `LEFT JOIN` ensures all rows from the *left* table (`employees`) are included. If there's no match in the *right* table (`departments`), the columns from the right table will be `NULL`.



**Q5: `GROUP BY` and Aggregate Functions**

*   **Question:** Find the number of employees in each department. Display the department name and the count.
*   **Answer (SQL):**
    ```sql
    SELECT d.name AS department_name, COUNT(e.id) AS employee_count
    FROM departments d
    LEFT JOIN employees e ON d.id = e.department_id
    GROUP BY d.name
    ORDER BY employee_count DESC;
    ```
*   **Note:** Using `LEFT JOIN` here ensures departments with zero employees are also listed (with a count of 0). Using `COUNT(e.id)` correctly counts employees, ignoring `NULL`s from the `LEFT JOIN`.


**Q6: `GROUP BY` and `HAVING`**

*   **Question:** Find the departments with an average employee salary greater than $85,000. Display the department name and the average salary.
*   **Answer (SQL):**
    ```sql
    SELECT d.name AS department_name, AVG(e.salary) AS average_salary
    FROM employees e
    JOIN departments d ON e.department_id = d.id
    GROUP BY d.name
    HAVING AVG(e.salary) > 85000;
    ```
*   **Explanation:** `WHERE` filters rows *before* aggregation, while `HAVING` filters groups *after* aggregation.


**Q7: Subquery in `WHERE` Clause**

*   **Question:** Find the names of employees who earn more than the overall average salary of all employees.
*   **Answer (SQL):**
    ```sql
    SELECT name, salary
    FROM employees
    WHERE salary > (SELECT AVG(salary) FROM employees);
    ```

**Q8: Subquery in `SELECT` Clause (Correlated Subquery)**

*   **Question:** For each employee, show their name, salary, and the average salary of their department.
*   **Answer (SQL):**
    ```sql
    SELECT
        e.name AS employee_name,
        e.salary,
        (SELECT AVG(salary) FROM employees e2 WHERE e2.department_id = e.department_id) AS department_avg_salary
    FROM employees e;
    ```
*   **Note:** Correlated subqueries can sometimes be less performant than joins or window functions for this type of task, especially on large tables.


**Q9: Many-to-Many Join**

*   **Question:** List all employees working on 'Project Beta'. Show employee name and their role on the project.
*   **Answer (SQL):**
    ```sql
    SELECT e.name AS employee_name, ep.role
    FROM employees e
    JOIN employee_projects ep ON e.id = ep.employee_id
    JOIN projects p ON ep.project_id = p.id
    WHERE p.name = 'Project Beta';
    ```
**Q10: Common Table Expression (CTE)**

*   **Question:** Find departments where the maximum salary is greater than $100,000. Use a CTE to first find the maximum salary per department.
*   **Answer (SQL):**
    ```sql
    WITH DepartmentMaxSalary AS (
        SELECT
            department_id,
            MAX(salary) AS max_salary
        FROM employees
        WHERE department_id IS NOT NULL
        GROUP BY department_id
    )
    SELECT d.name AS department_name, dms.max_salary
    FROM departments d
    JOIN DepartmentMaxSalary dms ON d.id = dms.department_id
    WHERE dms.max_salary > 100000;
    ```

**Q11: Window Function (`RANK`)**

*   **Question:** Rank employees within each department based on their salary (highest salary gets rank 1). Display department name, employee name, salary, and rank.
*   **Answer (SQL):**
    ```sql
    SELECT
        d.name AS department_name,
        e.name AS employee_name,
        e.salary,
        RANK() OVER (PARTITION BY e.department_id ORDER BY e.salary DESC) AS salary_rank
    FROM employees e
    JOIN departments d ON e.department_id = d.id
    ORDER BY d.name, salary_rank;
    ```
*   **Explanation:** `PARTITION BY e.department_id` divides the rows into partitions (one for each department). `ORDER BY e.salary DESC` sorts rows within each partition. `RANK()` assigns the rank based on this order. `DENSE_RANK()` is similar but doesn't leave gaps for ties. `ROW_NUMBER()` assigns unique numbers regardless of ties.

**Q12: Data Modification (`INSERT`, `UPDATE`, `DELETE`)**

*   **Question:**
    1.  Add a new department 'Finance' in 'Building C'.
    2.  Update 'Charlie's salary to $75,000.
    3.  Remove the employee named 'Frank'.
*   **Answer (SQL):**
    ```sql
    -- 1. Insert new department
    INSERT INTO departments (name, location)
    VALUES ('Finance', 'Building C');

    -- 2. Update Charlie's salary (assuming email is unique identifier if name isn't)
    UPDATE employees
    SET salary = 75000
    WHERE email = 'charlie@company.com'; -- Use a unique identifier like id or email

    -- 3. Delete Frank (use a unique identifier)
    DELETE FROM employees
    WHERE name = 'Frank' AND email = 'frank@company.com'; -- Be specific
    ```
*   **Caution:** `DELETE` operations are permanent. Always be careful and use specific `WHERE` clauses, preferably targeting primary keys or unique constraints. Transactions (`BEGIN`, `COMMIT`, `ROLLBACK`) are essential for safety.

**Q13: Indexing Concept**

*   **Question:** When would you add an index to the `employees` table? Explain your reasoning for choosing a specific column(s).
*   **Answer (Conceptual):**
    *   You would add an index to columns frequently used in `WHERE` clauses, `JOIN` conditions, or `ORDER BY` clauses to speed up data retrieval.
    *   **`id` (Primary Key):** PostgreSQL automatically creates a unique B-tree index on primary keys. This is essential for fast lookups and enforcing uniqueness.
    *   **`department_id` (Foreign Key):** Definitely index this column. It's used in `JOIN` operations with the `departments` table and potentially in `WHERE` clauses (e.g., `WHERE department_id = X`). A B-tree index is suitable here.
    *   **`email` (Unique Constraint):** PostgreSQL often automatically creates an index for unique constraints (typically B-tree) to efficiently check for duplicates during inserts/updates and speed up lookups based on email.
    *   **`name`:** If you frequently search or sort employees by name (`WHERE name = '...'` or `ORDER BY name`), an index on this column could be beneficial. A B-tree index works well for range queries and exact matches.
    *   **`salary`:** If you often filter or sort by salary (`WHERE salary > X`, `ORDER BY salary`), indexing this column can improve performance. A B-tree index is appropriate.
    *   **`hire_date`:** Similar to `salary`, if filtering or sorting by `hire_date` is common, an index helps.
    *   **Composite Index:** If you frequently filter by `department_id` AND `salary` together (e.g., `WHERE department_id = X AND salary > Y`), a composite index on `(department_id, salary)` might be more efficient than two separate indexes. The order matters.
    *   **Trade-offs:** Indexes speed up reads (`SELECT`) but slow down writes (`INSERT`, `UPDATE`, `DELETE`) because the index also needs to be updated. They also consume disk space. Only index columns where the performance benefit outweighs the cost.


**Q14: Transaction Concept**

*   **Question:** Imagine you need to transfer an employee ('Alice') from 'Engineering' to 'Sales' and simultaneously update her role on 'Project Alpha' to 'Consultant'. Why is it important to use a transaction for these operations?
*   **Answer (Conceptual):**
    *   A transaction groups multiple SQL statements into a single, atomic unit of work. It guarantees **ACID** properties (Atomicity, Consistency, Isolation, Durability).
    *   **Atomicity:** In this scenario, both updating the employee's `department_id` and updating their role in `employee_projects` must succeed together, or neither should happen. If the first update succeeds but the second fails (e.g., due to a constraint violation or connection drop), a transaction ensures the first update is rolled back, leaving the database in its original consistent state. Without a transaction, you could end up with inconsistent data (Alice in Sales but still listed as 'Developer' on the project, or vice-versa depending on the order and failure point).
    *   **Consistency:** The transaction ensures the database transitions from one valid state to another, respecting all constraints.
    *   **Isolation:** If other users are querying the data concurrently, a transaction ensures they see the data either *before* the changes or *after* both changes are committed, preventing them from seeing intermediate, inconsistent states (e.g., Alice listed in Sales but still having her old Engineering role on the project).
    *   **Durability:** Once a transaction is committed, the changes are permanent and will survive system crashes.
    *   **Syntax Example:**
        ```sql
        BEGIN; -- Start transaction

        UPDATE employees
        SET department_id = (SELECT id FROM departments WHERE name = 'Sales')
        WHERE email = 'alice@company.com';

        UPDATE employee_projects
        SET role = 'Consultant'
        WHERE employee_id = (SELECT id FROM employees WHERE email = 'alice@company.com')
          AND project_id = (SELECT id FROM projects WHERE name = 'Project Alpha');

        -- Add more related operations if needed...

        COMMIT; -- Apply changes permanently if all succeed
        -- Or ROLLBACK; if an error occurs or check fails
        ```









### Algorithmic Problem Solving

Senior Python roles often require solving algorithmic problems efficiently. This involves understanding data structures, common algorithms, and complexity analysis (Big O notation).

#### Common Data Structures Review

Be comfortable using and knowing the trade-offs of:

*   **Lists:** Ordered, mutable sequences. O(1) append, O(n) insertion/deletion/search.
*   **Tuples:** Ordered, immutable sequences. Used for fixed collections.
*   **Dictionaries (Hash Maps):** Key-value pairs. Average O(1) insertion/deletion/lookup. Crucial for many algorithms.
*   **Sets:** Unordered collections of unique elements. Average O(1) add/remove/contains check. Useful for uniqueness and membership testing.
*   **Strings:** Immutable sequences of characters.
*   **(Conceptual) Stacks (LIFO):** Use `list.append()` for push, `list.pop()` for pop.
*   **(Conceptual) Queues (FIFO):** Use `collections.deque` for efficient O(1) appends and pops from both ends.
*   **(Conceptual) Heaps (Priority Queues):** Use `heapq` module. O(log n) push/pop smallest element.
*   **(Conceptual) Trees (Binary Search Trees, Tries):** Know their properties and traversal methods (in-order, pre-order, post-order, level-order/BFS).
*   **(Conceptual) Graphs:** Know representations (adjacency list, adjacency matrix) and traversal algorithms (BFS, DFS).

#### Problem-Solving Strategy

1.  **Understand:** Clarify the problem, inputs, outputs, constraints, and edge cases. Ask questions!
2.  **Plan:** Think about different approaches. Consider data structures. Whiteboard or sketch ideas. Analyze potential time/space complexity.
3.  **Code:** Write clean, readable Python code. Use meaningful variable names.
4.  **Test:** Test with examples, edge cases (empty input, large input, specific values), and constraints.
5.  **Optimize:** If necessary, revisit your plan to improve time or space complexity.

---

#### Practice Problems & Solutions (Python)

**Problem 1: Two Sum**

**Statement:** Given an array of integers `nums` and an integer `target`, return *indices* of the two numbers such that they add up to `target`. Assume that each input would have *exactly one solution*, and you may not use the same element twice.

**Example:** `nums = [2, 7, 11, 15]`, `target = 9` -> Output: `[0, 1]` (because `nums[0] + nums[1] == 9`)

**Approach:** Iterate through the array. For each number `n`, check if `target - n` exists in a hash map (dictionary) that stores numbers encountered so far and their indices. If it exists, we found the pair. If not, add the current number `n` and its index to the map.

**Python Code:**

    ```python
    def two_sum(nums: list[int], target: int) -> list[int]:
        """Finds indices of two numbers that sum to target."""
        num_map = {} # Stores {number: index}
        for index, num in enumerate(nums):
            complement = target - num
            if complement in num_map:
                return [num_map[complement], index]
            num_map[num] = index
        return [] # Should not be reached based on problem statement
    ```
**Complexity:**

*   Time: O(n) - We iterate through the list once. Dictionary lookups/insertions are O(1) on average.
*   Space: O(n) - In the worst case, the dictionary stores all numbers.


**Problem 2: Valid Parentheses**

**Statement:** Given a string `s` containing just the characters `(`, `)`, `{`, `}`, `[` and `]`, determine if the input string is valid. An input string is valid if:
    1.  Open brackets must be closed by the same type of brackets.
    2.  Open brackets must be closed in the correct order.
    3.  Every close bracket has a corresponding open bracket of the same type.

**Example:** `s = "()[]{}"` -> `True`; `s = "(]"` -> `False`; `s = "{[]}"` -> `True`

**Approach:** Use a stack. Iterate through the string. If an opening bracket (`(`, `{`, `[`) is encountered, push it onto the stack. If a closing bracket (`)`, `}`, `]`) is encountered, check if the stack is empty or if the top of the stack is the corresponding opening bracket. If not, return `False`. If it matches, pop the stack. After iterating through the string, the stack should be empty for the string to be valid.

**Python Code:**

```python
    def is_valid_parentheses(s: str) -> bool:
        """Checks if a string of parentheses is valid."""
        stack = []
        mapping = {")": "(", "}": "{", "]": "["}

        for char in s:
            if char in mapping: # It's a closing bracket
                # Pop from stack if not empty, otherwise use a dummy value
                top_element = stack.pop() if stack else '#'
                if mapping[char] != top_element:
                    return False
            else: # It's an opening bracket
                stack.append(char)

        return not stack # Stack should be empty at the end
```
    
*   **Complexity:**
    *   Time: O(n) - We iterate through the string once. Stack operations are O(1).
    *   Space: O(n) - In the worst case (e.g., `((((...))))`), the stack stores all opening brackets.



**Problem 3: Longest Substring Without Repeating Characters**

*   **Statement:** Given a string `s`, find the length of the longest substring without repeating characters.
*   **Example:** `s = "abcabcbb"` -> `3` ("abc"); `s = "bbbbb"` -> `1` ("b"); `s = "pwwkew"` -> `3` ("wke")
*   **Approach:** Use a sliding window technique. Maintain a window `[left, right]` and a set (or dictionary) to keep track of characters currently in the window. Expand the window by moving `right`. If `s[right]` is already in the set, shrink the window from the left by moving `left` and removing `s[left]` from the set until `s[right]` is no longer a duplicate. Add `s[right]` to the set. Update the maximum length found so far (`right - left + 1`).
*   **Python Code:**
    ```python
    def length_of_longest_substring(s: str) -> int:
        """Finds the length of the longest substring without repeating chars."""
        char_set = set()
        left = 0
        max_length = 0

        for right in range(len(s)):
            # If char already in window, shrink from left until it's removed
            while s[right] in char_set:
                char_set.remove(s[left])
                left += 1
            # Add the new character to the set and update max length
            char_set.add(s[right])
            max_length = max(max_length, right - left + 1)

        return max_length
    ```
*   **Complexity:**
    *   Time: O(n) - Although there's a nested `while` loop, each character is added and removed from the set at most once. Both `left` and `right` pointers traverse the string linearly.
    *   Space: O(min(m, n)) - Where `n` is the length of the string and `m` is the size of the character set (e.g., 26 for lowercase English letters, or up to `n`). The space is used by the `char_set`.


**Problem 4: Kth Largest Element in an Array**

*   **Statement:** Given an integer array `nums` and an integer `k`, return the `k`th largest element in the array. Note that it is the `k`th largest element in the sorted order, not the `k`th distinct element.
*   **Example:** `nums = [3, 2, 1, 5, 6, 4]`, `k = 2` -> `5`; `nums = [3, 2, 3, 1, 2, 4, 5, 5, 6]`, `k = 4` -> `4`
*   **Approach (Heap):** Use a min-heap. Iterate through the numbers. Push each number onto the heap. If the heap size exceeds `k`, pop the smallest element (the root of the min-heap). After iterating through all numbers, the root of the heap will be the `k`th largest element.
*   **Python Code:**
    ```python
    import heapq

    def find_kth_largest(nums: list[int], k: int) -> int:
        """Finds the Kth largest element using a min-heap."""
        # Create a min-heap
        min_heap = []
        for num in nums:
            heapq.heappush(min_heap, num)
            # If heap size exceeds k, remove the smallest element
            if len(min_heap) > k:
                heapq.heappop(min_heap)
        # The root of the heap is the Kth largest element
        return min_heap[0]

    # Alternative concise version using heapify:
    # def find_kth_largest_concise(nums: list[int], k: int) -> int:
    #     return heapq.nlargest(k, nums)[-1]
    ```
*   **Complexity:**
    *   Time: O(n log k) - We process `n` elements. Heap push/pop operations take O(log k) time since the heap size is capped at `k`. (`heapq.nlargest` is often O(n log k) as well). A Quickselect approach offers average O(n) but worst-case O(n^2).
    *   Space: O(k) - To store the elements in the heap.


**Problem 5: Coin Change**

*   **Statement:** You are given an integer array `coins` representing coins of different denominations and an integer `amount` representing a total amount of money. Return the *fewest* number of coins that you need to make up that amount. If that amount of money cannot be made up by any combination of the coins, return `-1`. Assume you have an infinite number of each kind of coin.
*   **Example:** `coins = [1, 2, 5]`, `amount = 11` -> `3` (11 = 5 + 5 + 1); `coins = [2]`, `amount = 3` -> `-1`
*   **Approach (Dynamic Programming):** Create a DP array `dp` of size `amount + 1`, initialized with a value indicating infinity (e.g., `amount + 1`) except `dp[0] = 0` (0 coins needed for amount 0). Iterate from `1` to `amount`. For each amount `i`, iterate through the `coins`. If a coin `c` is less than or equal to `i`, check if using this coin can lead to a smaller number of coins needed: `dp[i] = min(dp[i], 1 + dp[i - c])`. After the loops, if `dp[amount]` is still the infinity value, it means the amount is unreachable; otherwise, `dp[amount]` holds the minimum number of coins.
*   **Python Code:**
    ```python
    def coin_change(coins: list[int], amount: int) -> int:
        """Finds the minimum number of coins to make a given amount (DP)."""
        # dp[i] will store the minimum coins needed for amount i
        # Initialize with a value larger than any possible result (amount + 1)
        dp = [amount + 1] * (amount + 1)
        dp[0] = 0 # Base case: 0 coins for amount 0

        for i in range(1, amount + 1):
            for coin in coins:
                if coin <= i:
                    # If we use 'coin', we need 1 + dp[i - coin] coins
                    dp[i] = min(dp[i], 1 + dp[i - coin])

        # If dp[amount] is still amount + 1, it means amount is unreachable
        return dp[amount] if dp[amount] <= amount else -1
    ```

*   **Complexity:**
    *   Time: O(amount * num_coins) - We have nested loops iterating up to `amount` and through the `coins`.
    *   Space: O(amount) - We use a DP array of size `amount + 1`.

    
Here is another solution:

*   **Python Code:**
    ```python
    def coin_change(coins, amount):
        map_dict = {}
        fewest = 1000
        for element in coins:
            remainder = amount % element
            qu = amount // element
            if remainder == 0 or remainder in coins:
                fewest = min(qu + remainder, fewest)
    
        return -1 if fewest == 1000 else fewest
    ```


**Problem 6: Merge Intervals**

**Statement:** Given an array of intervals where intervals`[i] = [start_i, end_i]`, merge all overlapping intervals, and return an array of the non-overlapping intervals that cover all the intervals in the input.

**Example:** `intervals = [[1,3],[2,6],[8,10],[15,18]] -> [[1,6],[8,10],[15,18]]` (because `[1,3]` and [2,6] overlap and merge into `[1,6]`). `intervals = [[1,4],[4,5]] -> [[1,5]]` (overlap at the boundary).

**Approach:** First, sort the intervals based on their start times. Initialize a list merged_intervals with the first interval. Iterate through the sorted intervals starting from the second one. If the current interval overlaps with the last interval in merged_intervals (i.e., current_interval.start <= last_merged_interval.end), merge them by updating the end time of the last interval in merged_intervals to the maximum of the two end times. Otherwise, if they don't overlap, add the current interval to merged_intervals.

**Python Code:**

```python
def merge_intervals(intervals: list[list[int]]) -> list[list[int]]:
    if not intervals:
        return []

    # Sort intervals based on the start time
    intervals.sort(key=lambda x: x[0])

    merged_intervals = [intervals[0]]

    for i in range(1, len(intervals)):
        current_start, current_end = intervals[i]
        last_merged_start, last_merged_end = merged_intervals[-1]

        # Check for overlap
        if current_start <= last_merged_end:
            # Merge: update the end of the last merged interval
            merged_intervals[-1][1] = max(last_merged_end, current_end)
        else:
            # No overlap, add the current interval
            merged_intervals.append([current_start, current_end])

    return merged_intervals
```

Complexity:

Time: O(n log n) - Dominated by the sorting step. The merging process is O(n).

Space: O(n) or O(log n) - O(n) for the merged_intervals list. The space complexity of sorting depends on the implementation (Timsort in Python is O(n), but sometimes considered O(log n) for recursion stack if not in-place).





**Problem 7: Number of Islands**

**Statement:** Given an **m x n** 2D binary grid grid which represents a map of '1's (land) and '0's (water), return the number of islands. An island is surrounded by water and is formed by connecting adjacent lands horizontally or vertically. You may assume all four edges of the grid are surrounded by water.

**Example:**

`
grid = [
  ["1","1","1","1","0"],
  ["1","1","0","1","0"],
  ["1","1","0","0","0"],
  ["0","0","0","0","0"]
] -> 1
`

`
grid = [
  ["1","1","0","0","0"],
  ["1","1","0","0","0"],
  ["0","0","1","0","0"],
  ["0","0","0","1","1"]
] -> 3
`

**Approach (DFS or BFS):** Iterate through each cell of the grid. If a cell contains '1' (land) and hasn't been visited yet (or is part of a found island), increment the island count. Then, start a traversal (DFS or BFS) from this cell to find all connected land cells belonging to this island. Mark these visited cells (e.g., change '1' to '0' or use a separate visited set) to avoid recounting them. Continue iterating through the grid.

**Python Code (DFS):**

```python
def num_islands(grid: list[list[str]]) -> int:
    """Counts the number of islands in a grid using DFS."""
    if not grid or not grid[0]:
        return 0

    rows, cols = len(grid), len(grid[0])
    num_islands = 0

    def dfs(r, c):
        # Check boundaries and if it's water or already visited (marked as '0')
        if r < 0 or c < 0 or r >= rows or c >= cols or grid[r][c] == '0':
            return
        # Mark the current cell as visited (by changing it to water)
        grid[r][c] = '0' 
        # Explore neighbors
        dfs(r + 1, c)
        dfs(r - 1, c)
        dfs(r, c + 1)
        dfs(r, c - 1)

    for r in range(rows):
        for c in range(cols):
            if grid[r][c] == '1':
                num_islands += 1
                dfs(r, c) # Explore and mark the entire island

    return num_islands
```


**Complexity:**

Time: `O(m * n)` - Each cell is visited at most a constant number of times.

Space: `O(m * n)` - In the worst case (grid full of land), the recursion depth for DFS could go up to mn. If using BFS, the queue could also store up to `O(mn)` cells. Also `O(m*n)` if using a separate visited set instead of modifying the grid.


**Problem 8: Maximum Subarray**

**Statement:** Given an integer array nums, find the contiguous subarray (containing at least one number) which has the largest sum and return its sum.

**Example:** `nums = [-2,1,-3,4,-1,2,1,-5,4] -> 6` (subarray `[4,-1,2,1]`). `nums = [1] -> 1`. `nums = [5,4,-1,7,8] -> 23` (subarray `[5,4,-1,7,8]`).

**Approach (Kadane's Algorithm):** Iterate through the array, keeping track of the maximum sum ending at the current position (current_max) and the overall maximum sum found so far (global_max). For each number, update current_max to be the maximum of the number itself OR the number plus the current_max from the previous position. This effectively decides whether to extend the previous subarray or start a new one. Update global_max whenever current_max is greater.

**Python Code:**

```python
def max_subarray(nums: list[int]) -> int:
    """Finds the maximum sum of a contiguous subarray using Kadane's Algo."""
    if not nums:
        return 0 # Or raise error, depends on constraints

    current_max = nums[0]
    global_max = nums[0]

    for i in range(1, len(nums)):
        # Decide whether to extend the current subarray or start a new one
        current_max = max(nums[i], current_max + nums[i])
        # Update the overall maximum sum found so far
        global_max = max(global_max, current_max)
        
    return global_max

```


**Complexity:**

Time: O(n) - Single pass through the array.

Space: O(1) - Only a few variables are used.







## Interview Questions

### Problem 1: Database Transactions (Django & SQLAlchemy)

**Statement:** Explain the concept of database transactions, why they are important, and demonstrate how to use them when performing multiple operations involving related models in both Django and SQLAlchemy.

**Concept:**

A database transaction is a sequence of one or more database operations treated as a single logical unit of work. This unit is governed by the ACID properties, primarily **Atomicity**. Atomicity ensures that either all operations within the transaction are successfully completed and the changes are committed to the database, or if any operation fails, the entire transaction is aborted, and all changes are rolled back to their state before the transaction began. This prevents partial updates and maintains data consistency, especially when dealing with interrelated data or multiple steps that must collectively succeed or fail.

1.  You need to perform multiple write operations that depend on each other (e.g., debiting one account and crediting another – both must happen).
2.  An operation involves modifying data based on the current state, and you want to prevent other processes from changing that state in between.
3.  You want a set of operations to be retryable or easily undone if something goes wrong.

**Example Models (Author and Book):**

We'll use simple `Author` and `Book` models where a `Book` has a foreign key relationship to an `Author`. Creating an author and several books for them is a common scenario where a transaction is useful – you want either the author *and* all specified books to be created, or none of them if any step fails (e.g., a validation error on a book title).

**Django ORM:**

Django manages transactions automatically for individual `save()` or `create()` calls (usually implicit), but for a block of multiple operations, you typically use `django.db.transaction.atomic()`. This context manager guarantees atomicity for the operations performed within the `with` block.

```python

# Assume these models are defined in your Django app's models.py
# from django.db import models

# class Author(models.Model):
#     name = models.CharField(max_length=100)

# class Book(models.Model):
#     title = models.CharField(max_length=200)
#     author = models.ForeignKey(Author, on_delete=models.CASCADE)

from django.db import transaction, IntegrityError

def create_author_and_books_django(author_name, book_titles):
    """
    Creates an author and multiple books within a single transaction.
    If any step fails, the entire operation is rolled back.
    """
    try:
        # Use the 'atomic' block to ensure the operations are transactional
        with transaction.atomic():
            print(f"Starting transaction to create {author_name} and {len(book_titles)} books...")

            # Operation 1: Create the Author
            author = Author.objects.create(name=author_name)
            print(f"Created Author: {author.name} (ID: {author.id})")

            # Operation 2+: Create Books linked to the Author
            for i, title in enumerate(book_titles):
                # Simulate a potential error for demonstration (e.g., validation fails)
                if "Invalid" in title:
                     print(f"Simulating error for book '{title}'. This will trigger rollback.")
                     raise ValueError(f"Invalid book title encountered: {title}")

                Book.objects.create(title=title, author=author)
                print(f"Created Book: '{title}' for {author.name}")

            # If the block finishes without exceptions, the transaction is committed
            print("Transaction successful! Changes committed.")

    except (ValueError, IntegrityError) as e:
        # If an exception occurs within the 'atomic' block, the transaction is rolled back
        print(f"An error occurred: {e}. Transaction rolled back.")
        # Note: Any partial creations within the block are undone.


# --- Example Usage (Requires Django setup) ---
# Assume you have run 'manage.py migrate' and can import your models
from myapp.models import Author, Book # Adjust import based on your app name

# Example 1: Success
print("\n--- Running successful scenario ---")
create_author_and_books_django("Jane Austen", ["Pride and Prejudice", "Sense and Sensibility"])
print("\n--- Database State After Success ---")
print("Authors:", list(Author.objects.values_list('name', flat=True)))
print("Books:", list(Book.objects.values_list('title', flat=True)))


```

**SQLAlchemy**:

In SQLAlchemy, sessions manage transactions. The recommended way to handle transactions is using the session as a context manager (with session). This automatically handles the commit if the block completes successfully and performs a rollback if an exception occurs.

```python

# Assume these models are defined using SQLAlchemy Declarative Base
from sqlalchemy import create_engine, Column, Integer, String, ForeignKey
from sqlalchemy.orm import sessionmaker, relationship
from sqlalchemy.ext.declarative import declarative_base

Base = declarative_base()

class Author(Base):
    __tablename__ = 'authors_sqla' # Use different table names if mixing ORMs in one DB
    id = Column(Integer, primary_key=True)
    name = Column(String)
    books = relationship("Book", back_populates="author")

class Book(Base):
    __tablename__ = 'books_sqla'
    id = Column(Integer, primary_key=True)
    title = Column(String)
    author_id = Column(Integer, ForeignKey('authors_sqla.id'))
    author = relationship("Author", back_populates="books")

# --- Example Setup (needed to run SQLAlchemy code) ---
engine = create_engine('sqlite:///:memory:') # Or your actual database URL
Base.metadata.create_all(engine) # Create tables based on models
SessionLocal = sessionmaker(bind=engine) # Configure a session factory

from sqlalchemy.exc import SQLAlchemyError # Import specific exceptions as needed

def create_author_and_books_sqla(session, author_name, book_titles):
    """
    Creates an author and multiple books within a SQLAlchemy transaction
    managed by the session context.
    """
    try:
        # The 'with session:' context manager handles the transaction:
        # It calls session.begin(), session.commit() on success,
        # and session.rollback() on exception.
        with session: # Start a transaction
            print(f"Starting SQLAlchemy session/transaction to create {author_name} and {len(book_titles)} books...")

            # Operation 1: Create the Author
            author = Author(name=author_name)
            session.add(author)
            # You might need session.flush() here if subsequent operations
            # immediately need the author.id before commit, but for relationship
            # assignment like book.author = author, it's often handled by SA.
            session.flush() # Get the author's ID assigned if needed

            print(f"Added Author: {author.name} (ID will be assigned on commit or flush)")

            # Operation 2+: Create Books linked to the Author
            for i, title in enumerate(book_titles):
                 # Simulate a potential error
                if "Invalid" in title:
                     print(f"Simulating error for book '{title}'. This will trigger rollback.")
                     raise ValueError(f"Invalid book title encountered: {title}")

                book = Book(title=title, author=author) # Link using the Author object
                session.add(book)
                print(f"Added Book: '{title}' for {author.name}")


            # If the block finishes without exceptions, session.commit() is called automatically
            print("Transaction successful! Changes committed.")

    except (ValueError, SQLAlchemyError) as e:
        # If an exception occurs, session.rollback() is called automatically by the 'with' block
        print(f"An error occurred: {e}. Transaction rolled back.")
        # Note: The session might be in an invalid state after rollback;
        # it's often best to close and get a new one for subsequent operations.

# --- Example Usage (Requires SQLAlchemy setup above) ---
from your_models_file import Author, Book, SessionLocal # Adjust import
session = SessionLocal() # Get a new session instance

Example 1: Success
print("\n--- Running successful scenario (SQLA) ---")
create_author_and_books_sqla(session, "J.R.R. Tolkien", ["The Hobbit", "The Fellowship of the Ring"])
session.close() # Always close the session

```