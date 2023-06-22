# Python and Django advanced topics with simple examples

## Introduction

In this research, I have given a brief overview of advanced topics in Python and Django. This article does not provide
in-depth knowledge on various topics and the purpose of this research is to collect topics in one place to provide the
reader with a mental framework. In this article, I have used very simple examples to explain the topics easily.
Naturally, studying and examining more and more practical examples will help a lot to understand each topic. I hope
reading this article is useful for you. (**Hamid Asgari**)

<!-- TOC -->

* [Python and Django advanced topics with simple examples](#python-and-django-advanced-topics-with-simple-examples)
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
        * [concurrency and parallelism](#concurrency-and-parallelism)
        * [Main types of methods in python classes](#main-types-of-methods-in-python-classes)
    * [Django related topics:](#django-related-topics-2)
        * [Django signals](#django-signals-2)
        * [Django middleware](#django-middleware-2)
        * [Django custom template tags](#django-custom-template-tags-2)
        * [Django permissions](#django-permissions-2)
        * [Django custom user models](#django-custom-user-models)
        * [Django Custom Managers](#django-custom-managers)
        * [Django Custom validators](#django-custom-validators)
        * [Custom management commands](#custom-management-commands)
        * [Custom query expressions](#custom-query-expressions)

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
print(cat.speak())  # Output: Meow!
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

In this example, BankAccount is a class that represents a bank account. The** _balance** attribute is marked as private
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

Here are a few examples of decorators commonly used in Django:

-     @login_required
-     @permission_required
-     @csrf_exempt
-     @cache_page
-     @transaction.atomic

### Map function

The map() function in Python is a built-in function that applies a given function to each item in an iterable (such as a
list, tuple, or string) and returns an iterator with the results. It takes two or more arguments: the function to apply
and one or more iterables. The basic syntax of the map() function is as follows:

```
map(function, iterable1, iterable2, ...)
```

Here's an example that demonstrates the usage of the map() function:

```
# Example 1: Squaring numbers using map()
numbers = [1, 2, 3, 4, 5]
squared = map(lambda x: x**2, numbers)
print(list(squared))
# Output: [1, 4, 9, 16, 25]
```

The map() function can be useful in various scenarios when working with Django. In the following gives an example of
mapping a function to a query set:

```
from django.contrib.auth.models import User
 
# Get a queryset of all users
users = User.objects.all()
 
# Get a list of usernames using map() and a lambda function
usernames = list(map(lambda user: user.username, users))
 
# Output: ['user1', 'user2', 'user3', ...]
```

### Itertools

Itertools is a Python module that provides a collection of functions for creating and manipulating iterators, which are
objects that can be iterated (looped) over. Here are some commonly used functions provided by the itertools module

- count(): Generates an infinite sequence of numbers starting from a specified value.
- chain(): Combines multiple iterators into a single iterator.
- groupby(): Groups consecutive elements in an iterable based on a common key

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

In Python, a lambda function is a small anonymous function that can be defined without a name. It is also known as an
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

Lambda functions are often used with built-in functions like map(), filter(), and reduce(). These functions take another
function as a parameter, and lambda functions provide a convenient way to define these functions on the fly without
explicitly defining a separate function. Here's an example using the map() function with a lambda function to square a
list of numbers:

```
numbers = [1, 2, 3, 4, 5]
squared_numbers = list(map(lambda x: x ** 2, numbers))
print(squared_numbers)  # Output: [1, 4, 9, 16, 25]
```

For more complex or reusable functions, it's often better to define a regular named function using the def keyword. Here
are a few examples of how you can use lambda functions in Django:

- Filtering objects in a queryset:
  You can use a lambda function as a condition for filtering objects in a Django queryset. For instance:

```
filtered_queryset = MyModel.objects.filter(lambda obj: obj.field_name == 'some_value')
```

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
  This principle states that a class should have only one reason to change, meaning it should have only one
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
  we should be able to pass any subclass of Shape without causing any issues:

```
def print_area(shape):
    print(f"Area: {shape.area()}")
 
shape = Circle(5)
print_area(shape)  # Output: Area: 78.5
 
shape = Rectangle(3, 4)
print_area(shape)  # Output: Area: 12
```

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
  abstractions. It encourages the use of interfaces or abstract classes to decouple dependencies.

I have not found yet good example to show this principle.

### Python collection

Python provides several built-in collection types, such as lists, tuples, sets, and dictionaries. These collections can
be used to store and organize data efficiently.

- lists
  A list is a mutable collection that can store an ordered sequence of elements. It is defined using square
  brackets ([]). Here's an example:

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

- Tuples
  A tuple is an immutable collection that can store an ordered sequence of elements. It is defined using
  parentheses (()). Here's an example:

```
# Creating a tuple
point = (3, 4)

# Accessing elements
print(point[0])  # Output: 3

# Unpacking tuple
x, y = point
print(x, y)  # Output: 3 4

```

- Sets
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

- Dictionaries
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

Here, the read_lines() function returns a generator that yields one line at a time. This approach is memory-efficient
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

`__init__(self, ...)` : This method is called when an object is created and initialized. It takes arguments that are
used to initialize the object's attributes.

`__str__(self)` : This method is called when the object is printed as a string. It returns a string representation of
the object.

`__len__(self)` : This method is called when the built-in len() function is called on the object. It returns the length
of the object.

`__add__(self, other)` : This method is called when the + operator is used on the object. It takes another object as an
argument and returns the result of the addition.

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

### concurrency and parallelism

Concurrency involves allowing multiple tasks to take turns accessing the same shared resources, like disk, network, or a
single CPU core. Parallelism, on the other hand, is about maximizing the use of hardware resources, such as multiple CPU
cores, to execute multiple tasks simultaneously. Threading is a way to achieve concurrency by running multiple threads
within a single process, while asyncio is a way to achieve concurrency by running a single thread that can switch
between multiple tasks.

- Threading:
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

- Asyncio:
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

- Multiprocessing:
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

In general, concurrency is preferred for IO-bound tasks, as it allows you to do something else while the IO resources
are being fetched. Parallelism, on the other hand, is preferred for CPU-bound tasks, as it allows you to take advantage
of multiple CPU cores to execute multiple tasks simultaneously.

### Main types of methods in python classes

In Python, there are three main types of methods that can be defined in a class:

1. Instance Methods
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

2. Class Methods
   Class methods are methods that are bound to the class and not the instance of the class. They are defined using the *
   *@classmethod** decorator, and they take the class itself as their first argument, typically named **cls**. Class
   methods can be called on the class itself, rather than on an instance of the class.

```
class MyClass:
    class_attribute = 0
    
    @classmethod
    def my_class_method(cls, x, y):
        cls.class_attribute += 1
        return cls.class_attribute + x + y

result1 = MyClass.my_class_method(3, 4)
print(result1)  # Output: 2 + 3 + 4 = 9

result2 = MyClass.my_class_method(1, 2)
print(result2)  # Output: 3 + 1 + 2 = 6
```

3. Static Methods
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

## Django related topics:

### Django signals

Django signals can be used to automate tasks and update data in your application without having to manually perform
those tasks or update the data.
Let's say we have a Django application that allows users to place orders for products. We want to automatically update
the product quantity in the database whenever an order is placed. We can use Django signals to accomplish this.
Here are the steps to use Django signals for this example:

1. Create a new file called **signals.py** in the same directory as your **models.p**y file.
1. Import the** django.dispatch.Signal** class.
1. Define a new signal using the Signal class.
1. Define a function that will be called when the signal is triggered. This function should accept two arguments: sender
   and instance.
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

In this example, we define a new signal called order_placed using the Signal class. We also define a function called
update_product_quantity that will be called when the signal is triggered. This function gets the Product object
associated with the Order object, calculates the new quantity, and updates the product quantity in the database.

Finally, we connect the order_placed signal to the update_product_quantity function using the connect method. We also
specify the sender argument to indicate that this signal should only be triggered when an Order object is saved.

To trigger the signal, we simply need to create a new Order object:

```
from myapp.models import Order, Product

product = Product.objects.get(pk=1)
order = Order(product=product, quantity=3)
order.save()  # This will trigger the order_placed signal
```

When the save method is called on the Order object, the order_placed signal will be triggered, and the
update_product_quantity function will be called, updating the product quantity in the database.

### Django middleware

Django middleware provides a way to process requests and responses globally in your application. Middleware can be used
to perform authentication, logging, modifying headers, and more.
Let's say we have a Django application that needs to add a custom header to every HTTP response. We can use Django
middleware to accomplish this.
Here are the steps to use Django middleware:

1. Create a new file called **middleware.py** in the same directory as your settings.py file.
1. Define a class that extends the **MiddlewareMixin** class.
   Implement the process_response method to modify the response object.
1. Add your middleware class to the MIDDLEWARE setting in your **settings.py** file.

Here's an example implementation:

```
class CustomHeaderMiddleware:
    def process_response(self, request, response):
        response['X-Custom-Header'] = 'Hello, World!'
        return response
```

In this example, we define a new middleware class called CustomHeaderMiddleware that extends the MiddlewareMixin class.
We implement the process_response method to modify the response object by adding a custom header.
Finally, we add our middleware class to the MIDDLEWARE setting in our **settings.py** file:

```
MIDDLEWARE = [
    # Other middleware classes...
    'myapp.middleware.CustomHeaderMiddleware',
]
```

Now, whenever an HTTP response is returned by our application, the CustomHeaderMiddleware class will modify the response
by adding a custom header.

### Django custom template tags

Custom template tags can be used to perform complex operations on data or to create reusable components for your
templates.
Here's a simple example of how to create a custom template tag in Django:

1. Create a new Python module in one of your Django app's templatetags directory. For example, if you have an app named
   myapp, you could create a new module named **myapp_tags.py** in the **myapp/templatetags** directory.

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

In this example, we're using the @register.simple_tag decorator to register the function as a simple template tag.

1. In your template, load the custom tag library and use the new tag in your HTML code. To load the custom tag library,
   add** {% load myapp_tags %}** at the top of your template. Here's an example of how to use the first_item tag we
   defined earlier:

```
{% load myapp_tags %}

<ul>
  {% for item in my_list %}
    <li>{% first_item item %}</li>
  {% endfor %}
</ul>
```

In this example, we're using the first_item tag to output the first item in each list item in a loop.

### Django permissions

Django provides a built-in permissions system that allows you to control access to views and models in your application.
Permissions can be assigned to users or groups, and can be checked in your views or templates to determine whether a
user has the necessary permissions to perform certain actions.
Here's a simple example of how to use Django permissions:

1. First, you need to define the permissions for your models. You can do this by adding a permissions attribute to
   your** model's meta class**. For example, let's say you have a Book model and you want to define a permission called
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
named can_edit_book.

2. Next, you need to assign the permissions to users or groups. You can do this using Django's built-in admin interface,
   or programmatically in your code. For example, let's say we want to assign the can_edit_book permission to a group
   called Editors:

```
from django.contrib.auth.models import Group

editors_group, created = Group.objects.get_or_create(name='Editors')
editors_group.permissions.add('myapp.can_edit_book')

```

In this example, we're using the Group model to get or create a group called Editors, and then adding the
myapp.can_edit_book permission to the group.

3. Finally, you can check the user's permissions in your views or templates to control access to certain actions. For
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

In this example, we're using the permission_required decorator to check if the user has the myapp.can_edit_book
permission before allowing them to edit the book. If the user does not have the necessary permission, a PermissionDenied
exception will be raised.

# Python and Django advanced topics with simple examples

## Introduction

In this research, I have given a brief overview of advanced topics in Python and Django. This article does not provide
in-depth knowledge on various topics and the purpose of this research is to collect topics in one place to provide the
reader with a mental framework. In this article, I have used very simple examples to explain the topics easily.
Naturally, studying and examining more and more practical examples will help a lot to understand each topic. I hope
reading this article is useful for you. (**Hamid Asgari**)

## Python related topics:

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

Here are a few examples of decorators commonly used in Django:

-     @login_required
-     @permission_required
-     @csrf_exempt
-     @cache_page
-     @transaction.atomic

### Map function

The map() function in Python is a built-in function that applies a given function to each item in an iterable (such as a
list, tuple, or string) and returns an iterator with the results. It takes two or more arguments: the function to apply
and one or more iterables. The basic syntax of the map() function is as follows:

```
map(function, iterable1, iterable2, ...)
```

Here's an example that demonstrates the usage of the map() function:

```
# Example 1: Squaring numbers using map()
numbers = [1, 2, 3, 4, 5]
squared = map(lambda x: x**2, numbers)
print(list(squared))
# Output: [1, 4, 9, 16, 25]
```

The map() function can be useful in various scenarios when working with Django. In the following gives an example of
mapping a function to a query set:

```
from django.contrib.auth.models import User
 
# Get a queryset of all users
users = User.objects.all()
 
# Get a list of usernames using map() and a lambda function
usernames = list(map(lambda user: user.username, users))
 
# Output: ['user1', 'user2', 'user3', ...]
```

### Itertools

Itertools is a Python module that provides a collection of functions for creating and manipulating iterators, which are
objects that can be iterated (looped) over. Here are some commonly used functions provided by the itertools module

- count(): Generates an infinite sequence of numbers starting from a specified value.
- chain(): Combines multiple iterators into a single iterator.
- groupby(): Groups consecutive elements in an iterable based on a common key

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

In Python, a lambda function is a small anonymous function that can be defined without a name. It is also known as an
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

Lambda functions are often used with built-in functions like map(), filter(), and reduce(). These functions take another
function as a parameter, and lambda functions provide a convenient way to define these functions on the fly without
explicitly defining a separate function. Here's an example using the map() function with a lambda function to square a
list of numbers:

```
numbers = [1, 2, 3, 4, 5]
squared_numbers = list(map(lambda x: x ** 2, numbers))
print(squared_numbers)  # Output: [1, 4, 9, 16, 25]
```

For more complex or reusable functions, it's often better to define a regular named function using the def keyword. Here
are a few examples of how you can use lambda functions in Django:

- Filtering objects in a queryset:
  You can use a lambda function as a condition for filtering objects in a Django queryset. For instance:

```
filtered_queryset = MyModel.objects.filter(lambda obj: obj.field_name == 'some_value')
```

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
  This principle states that a class should have only one reason to change, meaning it should have only one
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
  we should be able to pass any subclass of Shape without causing any issues:

```
def print_area(shape):
    print(f"Area: {shape.area()}")
 
shape = Circle(5)
print_area(shape)  # Output: Area: 78.5
 
shape = Rectangle(3, 4)
print_area(shape)  # Output: Area: 12
```

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
  abstractions. It encourages the use of interfaces or abstract classes to decouple dependencies.

I have not found yet good example to show this principle.

### Python collection

Python provides several built-in collection types, such as lists, tuples, sets, and dictionaries. These collections can
be used to store and organize data efficiently.

- lists
  A list is a mutable collection that can store an ordered sequence of elements. It is defined using square
  brackets ([]). Here's an example:

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

- Tuples
  A tuple is an immutable collection that can store an ordered sequence of elements. It is defined using
  parentheses (()). Here's an example:

```
# Creating a tuple
point = (3, 4)

# Accessing elements
print(point[0])  # Output: 3

# Unpacking tuple
x, y = point
print(x, y)  # Output: 3 4

```

- Sets
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

- Dictionaries
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

Here, the read_lines() function returns a generator that yields one line at a time. This approach is memory-efficient
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

`__init__(self, ...)` : This method is called when an object is created and initialized. It takes arguments that are
used to initialize the object's attributes.

`__str__(self)` : This method is called when the object is printed as a string. It returns a string representation of
the object.

`__len__(self)` : This method is called when the built-in len() function is called on the object. It returns the length
of the object.

`__add__(self, other)` : This method is called when the + operator is used on the object. It takes another object as an
argument and returns the result of the addition.

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

### concurrency and parallelism

Concurrency involves allowing multiple tasks to take turns accessing the same shared resources, like disk, network, or a
single CPU core. Parallelism, on the other hand, is about maximizing the use of hardware resources, such as multiple CPU
cores, to execute multiple tasks simultaneously. Threading is a way to achieve concurrency by running multiple threads
within a single process, while asyncio is a way to achieve concurrency by running a single thread that can switch
between multiple tasks.

- Threading:
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

- Asyncio:
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

- Multiprocessing:
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

In general, concurrency is preferred for IO-bound tasks, as it allows you to do something else while the IO resources
are being fetched. Parallelism, on the other hand, is preferred for CPU-bound tasks, as it allows you to take advantage
of multiple CPU cores to execute multiple tasks simultaneously.

### Main types of methods in python classes

In Python, there are three main types of methods that can be defined in a class:

1. Instance Methods
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

2. Class Methods
   Class methods are methods that are bound to the class and not the instance of the class. They are defined using the *
   *@classmethod** decorator, and they take the class itself as their first argument, typically named **cls**. Class
   methods can be called on the class itself, rather than on an instance of the class.

```
class MyClass:
    class_attribute = 0
    
    @classmethod
    def my_class_method(cls, x, y):
        cls.class_attribute += 1
        return cls.class_attribute + x + y

result1 = MyClass.my_class_method(3, 4)
print(result1)  # Output: 2 + 3 + 4 = 9

result2 = MyClass.my_class_method(1, 2)
print(result2)  # Output: 3 + 1 + 2 = 6
```

3. Static Methods
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

## Django related topics:

### Django signals

Django signals can be used to automate tasks and update data in your application without having to manually perform
those tasks or update the data.
Let's say we have a Django application that allows users to place orders for products. We want to automatically update
the product quantity in the database whenever an order is placed. We can use Django signals to accomplish this.
Here are the steps to use Django signals for this example:

1. Create a new file called **signals.py** in the same directory as your **models.p**y file.
1. Import the** django.dispatch.Signal** class.
1. Define a new signal using the Signal class.
1. Define a function that will be called when the signal is triggered. This function should accept two arguments: sender
   and instance.
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

In this example, we define a new signal called order_placed using the Signal class. We also define a function called
update_product_quantity that will be called when the signal is triggered. This function gets the Product object
associated with the Order object, calculates the new quantity, and updates the product quantity in the database.

Finally, we connect the order_placed signal to the update_product_quantity function using the connect method. We also
specify the sender argument to indicate that this signal should only be triggered when an Order object is saved.

To trigger the signal, we simply need to create a new Order object:

```
from myapp.models import Order, Product

product = Product.objects.get(pk=1)
order = Order(product=product, quantity=3)
order.save()  # This will trigger the order_placed signal
```

When the save method is called on the Order object, the order_placed signal will be triggered, and the
update_product_quantity function will be called, updating the product quantity in the database.

### Django middleware

Django middleware provides a way to process requests and responses globally in your application. Middleware can be used
to perform authentication, logging, modifying headers, and more.
Let's say we have a Django application that needs to add a custom header to every HTTP response. We can use Django
middleware to accomplish this.
Here are the steps to use Django middleware:

1. Create a new file called **middleware.py** in the same directory as your settings.py file.
1. Define a class that extends the **MiddlewareMixin** class.
   Implement the process_response method to modify the response object.
1. Add your middleware class to the MIDDLEWARE setting in your **settings.py** file.

Here's an example implementation:

```
class CustomHeaderMiddleware:
    def process_response(self, request, response):
        response['X-Custom-Header'] = 'Hello, World!'
        return response
```

In this example, we define a new middleware class called CustomHeaderMiddleware that extends the MiddlewareMixin class.
We implement the process_response method to modify the response object by adding a custom header.
Finally, we add our middleware class to the MIDDLEWARE setting in our **settings.py** file:

```
MIDDLEWARE = [
    # Other middleware classes...
    'myapp.middleware.CustomHeaderMiddleware',
]
```

Now, whenever an HTTP response is returned by our application, the CustomHeaderMiddleware class will modify the response
by adding a custom header.

### Django custom template tags

Custom template tags can be used to perform complex operations on data or to create reusable components for your
templates.
Here's a simple example of how to create a custom template tag in Django:

1. Create a new Python module in one of your Django app's templatetags directory. For example, if you have an app named
   myapp, you could create a new module named **myapp_tags.py** in the **myapp/templatetags** directory.

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

In this example, we're using the @register.simple_tag decorator to register the function as a simple template tag.

1. In your template, load the custom tag library and use the new tag in your HTML code. To load the custom tag library,
   add** {% load myapp_tags %}** at the top of your template. Here's an example of how to use the first_item tag we
   defined earlier:

```
{% load myapp_tags %}

<ul>
  {% for item in my_list %}
    <li>{% first_item item %}</li>
  {% endfor %}
</ul>
```

In this example, we're using the first_item tag to output the first item in each list item in a loop.

### Django permissions

Django provides a built-in permissions system that allows you to control access to views and models in your application.
Permissions can be assigned to users or groups, and can be checked in your views or templates to determine whether a
user has the necessary permissions to perform certain actions.
Here's a simple example of how to use Django permissions:

1. First, you need to define the permissions for your models. You can do this by adding a permissions attribute to
   your** model's meta class**. For example, let's say you have a Book model and you want to define a permission called
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
named can_edit_book.

5. Next, you need to assign the permissions to users or groups. You can do this using Django's built-in admin interface,
   or programmatically in your code. For example, let's say we want to assign the can_edit_book permission to a group
   called Editors:

```
from django.contrib.auth.models import Group

editors_group, created = Group.objects.get_or_create(name='Editors')
editors_group.permissions.add('myapp.can_edit_book')

```

In this example, we're using the Group model to get or create a group called Editors, and then adding the
myapp.can_edit_book permission to the group.

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

In this example, we're using the permission_required decorator to check if the user has the myapp.can_edit_book
permission before allowing them to edit the book. If the user does not have the necessary permission, a PermissionDenied
exception will be raised.

# Python and Django advanced topics with simple examples

## Introduction

In this research, I have given a brief overview of advanced topics in Python and Django. This article does not provide
in-depth knowledge on various topics and the purpose of this research is to collect topics in one place to provide the
reader with a mental framework. In this article, I have used very simple examples to explain the topics easily.
Naturally, studying and examining more and more practical examples will help a lot to understand each topic. I hope
reading this article is useful for you. (**Hamid Asgari**)

## Python related topics:

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

Here are a few examples of decorators commonly used in Django:

-     @login_required
-     @permission_required
-     @csrf_exempt
-     @cache_page
-     @transaction.atomic

### Map function

The map() function in Python is a built-in function that applies a given function to each item in an iterable (such as a
list, tuple, or string) and returns an iterator with the results. It takes two or more arguments: the function to apply
and one or more iterables. The basic syntax of the map() function is as follows:

```
map(function, iterable1, iterable2, ...)
```

Here's an example that demonstrates the usage of the map() function:

```
# Example 1: Squaring numbers using map()
numbers = [1, 2, 3, 4, 5]
squared = map(lambda x: x**2, numbers)
print(list(squared))
# Output: [1, 4, 9, 16, 25]
```

The map() function can be useful in various scenarios when working with Django. In the following gives an example of
mapping a function to a query set:

```
from django.contrib.auth.models import User
 
# Get a queryset of all users
users = User.objects.all()
 
# Get a list of usernames using map() and a lambda function
usernames = list(map(lambda user: user.username, users))
 
# Output: ['user1', 'user2', 'user3', ...]
```

### Itertools

Itertools is a Python module that provides a collection of functions for creating and manipulating iterators, which are
objects that can be iterated (looped) over. Here are some commonly used functions provided by the itertools module

- count(): Generates an infinite sequence of numbers starting from a specified value.
- chain(): Combines multiple iterators into a single iterator.
- groupby(): Groups consecutive elements in an iterable based on a common key

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

In Python, a lambda function is a small anonymous function that can be defined without a name. It is also known as an
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

Lambda functions are often used with built-in functions like map(), filter(), and reduce(). These functions take another
function as a parameter, and lambda functions provide a convenient way to define these functions on the fly without
explicitly defining a separate function. Here's an example using the map() function with a lambda function to square a
list of numbers:

```
numbers = [1, 2, 3, 4, 5]
squared_numbers = list(map(lambda x: x ** 2, numbers))
print(squared_numbers)  # Output: [1, 4, 9, 16, 25]
```

For more complex or reusable functions, it's often better to define a regular named function using the def keyword. Here
are a few examples of how you can use lambda functions in Django:

- Filtering objects in a queryset:
  You can use a lambda function as a condition for filtering objects in a Django queryset. For instance:

```
filtered_queryset = MyModel.objects.filter(lambda obj: obj.field_name == 'some_value')
```

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
  This principle states that a class should have only one reason to change, meaning it should have only one
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
  we should be able to pass any subclass of Shape without causing any issues:

```
def print_area(shape):
    print(f"Area: {shape.area()}")
 
shape = Circle(5)
print_area(shape)  # Output: Area: 78.5
 
shape = Rectangle(3, 4)
print_area(shape)  # Output: Area: 12
```

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
  abstractions. It encourages the use of interfaces or abstract classes to decouple dependencies.

I have not found yet good example to show this principle.

### Python collection

Python provides several built-in collection types, such as lists, tuples, sets, and dictionaries. These collections can
be used to store and organize data efficiently.

- lists
  A list is a mutable collection that can store an ordered sequence of elements. It is defined using square
  brackets ([]). Here's an example:

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

- Tuples
  A tuple is an immutable collection that can store an ordered sequence of elements. It is defined using
  parentheses (()). Here's an example:

```
# Creating a tuple
point = (3, 4)

# Accessing elements
print(point[0])  # Output: 3

# Unpacking tuple
x, y = point
print(x, y)  # Output: 3 4

```

- Sets
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

- Dictionaries
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

Here, the read_lines() function returns a generator that yields one line at a time. This approach is memory-efficient
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

`__init__(self, ...)` : This method is called when an object is created and initialized. It takes arguments that are
used to initialize the object's attributes.

`__str__(self)` : This method is called when the object is printed as a string. It returns a string representation of
the object.

`__len__(self)` : This method is called when the built-in len() function is called on the object. It returns the length
of the object.

`__add__(self, other)` : This method is called when the + operator is used on the object. It takes another object as an
argument and returns the result of the addition.

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

### concurrency and parallelism

Concurrency involves allowing multiple tasks to take turns accessing the same shared resources, like disk, network, or a
single CPU core. Parallelism, on the other hand, is about maximizing the use of hardware resources, such as multiple CPU
cores, to execute multiple tasks simultaneously. Threading is a way to achieve concurrency by running multiple threads
within a single process, while asyncio is a way to achieve concurrency by running a single thread that can switch
between multiple tasks.

- Threading:
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

- Asyncio:
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

- Multiprocessing:
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

In general, concurrency is preferred for IO-bound tasks, as it allows you to do something else while the IO resources
are being fetched. Parallelism, on the other hand, is preferred for CPU-bound tasks, as it allows you to take advantage
of multiple CPU cores to execute multiple tasks simultaneously.

### Main types of methods in python classes

In Python, there are three main types of methods that can be defined in a class:

1. Instance Methods
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

2. Class Methods
   Class methods are methods that are bound to the class and not the instance of the class. They are defined using the *
   *@classmethod** decorator, and they take the class itself as their first argument, typically named **cls**. Class
   methods can be called on the class itself, rather than on an instance of the class.

```
class MyClass:
    class_attribute = 0
    
    @classmethod
    def my_class_method(cls, x, y):
        cls.class_attribute += 1
        return cls.class_attribute + x + y

result1 = MyClass.my_class_method(3, 4)
print(result1)  # Output: 2 + 3 + 4 = 9

result2 = MyClass.my_class_method(1, 2)
print(result2)  # Output: 3 + 1 + 2 = 6
```

3. Static Methods
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

## Django related topics:

### Django signals

Django signals can be used to automate tasks and update data in your application without having to manually perform
those tasks or update the data.
Let's say we have a Django application that allows users to place orders for products. We want to automatically update
the product quantity in the database whenever an order is placed. We can use Django signals to accomplish this.
Here are the steps to use Django signals for this example:

1. Create a new file called **signals.py** in the same directory as your **models.p**y file.
1. Import the** django.dispatch.Signal** class.
1. Define a new signal using the Signal class.
1. Define a function that will be called when the signal is triggered. This function should accept two arguments: sender
   and instance.
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

In this example, we define a new signal called order_placed using the Signal class. We also define a function called
update_product_quantity that will be called when the signal is triggered. This function gets the Product object
associated with the Order object, calculates the new quantity, and updates the product quantity in the database.

Finally, we connect the order_placed signal to the update_product_quantity function using the connect method. We also
specify the sender argument to indicate that this signal should only be triggered when an Order object is saved.

To trigger the signal, we simply need to create a new Order object:

```
from myapp.models import Order, Product

product = Product.objects.get(pk=1)
order = Order(product=product, quantity=3)
order.save()  # This will trigger the order_placed signal
```

When the save method is called on the Order object, the order_placed signal will be triggered, and the
update_product_quantity function will be called, updating the product quantity in the database.

### Django middleware

Django middleware provides a way to process requests and responses globally in your application. Middleware can be used
to perform authentication, logging, modifying headers, and more.
Let's say we have a Django application that needs to add a custom header to every HTTP response. We can use Django
middleware to accomplish this.
Here are the steps to use Django middleware:

1. Create a new file called **middleware.py** in the same directory as your settings.py file.
1. Define a class that extends the **MiddlewareMixin** class.
   Implement the process_response method to modify the response object.
1. Add your middleware class to the MIDDLEWARE setting in your **settings.py** file.

Here's an example implementation:

```
class CustomHeaderMiddleware:
    def process_response(self, request, response):
        response['X-Custom-Header'] = 'Hello, World!'
        return response
```

In this example, we define a new middleware class called CustomHeaderMiddleware that extends the MiddlewareMixin class.
We implement the process_response method to modify the response object by adding a custom header.
Finally, we add our middleware class to the MIDDLEWARE setting in our **settings.py** file:

```
MIDDLEWARE = [
    # Other middleware classes...
    'myapp.middleware.CustomHeaderMiddleware',
]
```

Now, whenever an HTTP response is returned by our application, the CustomHeaderMiddleware class will modify the response
by adding a custom header.

### Django custom template tags

Custom template tags can be used to perform complex operations on data or to create reusable components for your
templates.
Here's a simple example of how to create a custom template tag in Django:

1. Create a new Python module in one of your Django app's templatetags directory. For example, if you have an app named
   myapp, you could create a new module named **myapp_tags.py** in the **myapp/templatetags** directory.

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

In this example, we're using the @register.simple_tag decorator to register the function as a simple template tag.

1. In your template, load the custom tag library and use the new tag in your HTML code. To load the custom tag library,
   add** {% load myapp_tags %}** at the top of your template. Here's an example of how to use the first_item tag we
   defined earlier:

```
{% load myapp_tags %}

<ul>
  {% for item in my_list %}
    <li>{% first_item item %}</li>
  {% endfor %}
</ul>
```

In this example, we're using the first_item tag to output the first item in each list item in a loop.

### Django permissions

Django provides a built-in permissions system that allows you to control access to views and models in your application.
Permissions can be assigned to users or groups, and can be checked in your views or templates to determine whether a
user has the necessary permissions to perform certain actions.
Here's a simple example of how to use Django permissions:

1. First, you need to define the permissions for your models. You can do this by adding a permissions attribute to
   your** model's meta class**. For example, let's say you have a Book model and you want to define a permission called
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
named can_edit_book.

5. Next, you need to assign the permissions to users or groups. You can do this using Django's built-in admin interface,
   or programmatically in your code. For example, let's say we want to assign the can_edit_book permission to a group
   called Editors:

```
from django.contrib.auth.models import Group

editors_group, created = Group.objects.get_or_create(name='Editors')
editors_group.permissions.add('myapp.can_edit_book')

```

In this example, we're using the Group model to get or create a group called Editors, and then adding the
myapp.can_edit_book permission to the group.

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

In this example, we're using the permission_required decorator to check if the user has the myapp.can_edit_book
permission before allowing them to edit the book. If the user does not have the necessary permission, a PermissionDenied
exception will be raised.

### Django custom user models

Django's built-in User model provides a lot of functionality for authentication and authorization, but sometimes you may
need to customize the user model to include additional fields or functionality. In such cases, you can create a custom
user model that inherits from Django's AbstractBaseUser or AbstractUser classes.
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

In this example, we've created a new model called BlogUser that inherits from AbstractBaseUser and PermissionsMixin.
We've also defined the necessary fields, including a custom bio field.

- Update your project settings to use the custom user model. In your project's **settings.py** file, update the *
  *AUTH_USER_MODEL** setting to point to your new user model:

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

- Let's say we have a model called Book in our app that represents books in a library. We want to create a custom
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

In this example, we've created a custom manager called AvailableBooksManager that filters the books based on the
is_available field. We've also added a available_books attribute to the Book model that uses the custom manager.

- Now we can use the custom manager in our views or templates to get only the books that are currently available for
  borrowing. For example:

```
from django.shortcuts import render
from myapp.models import Book

def available_books(request):
    books = Book.available_books.all()
    return render(request, 'available_books.html', {'books': books})
```

In this example, we're using the available_books manager to get all the books that are currently available for
borrowing, and passing them to the available_books.html template.

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

In this example, we've created a custom validator called validate_title that checks whether the first character of the
title is a capital letter. If the validation fails, a ValidationError is raised. We've also added the validate_title
validator to the title field of the Book model.
Now when a user tries to create a book with a title that doesn't start with a capital letter, the validation will fail
and an error message will be displayed.

### Custom management commands

Custom management commands allow you to add your own functionality to the manage.py command, making it easy to automate
tasks and perform custom operations on your Django project.

Here is a simple example to demonstrate how to create and use custom management commands in Django:

- Create a new Django app:

```
python manage.py startapp myapp
```

- Create a new directory called **management** inside the app directory, and create another directory called **commands
  ** inside the management directory:

```
mkdir myapp/management
mkdir myapp/management/commands
```

- Create a new Python file inside the commands directory, and name it** mycommand.py**. This will be the file that
  contains the code for your custom management command:

```
from django.core.management.base import BaseCommand

class Command(BaseCommand):
    help = 'My custom management command'

    def handle(self, *args, **options):
        print('Hello from my custom management command!')
```

Register the new command with Django by adding an empty** __init__.py** file inside the management directory:

```
touch myapp/management/__init__.py
```

- Test the new command by running it from the command line:

```
python manage.py mycommand
```

You should see the message** "Hello from my custom management command!" **printed to the console.

### Custom query expressions

Custom query expressions are a way to extend the Django query API with your own custom SQL expressions. Custom query
expressions can be useful when you need to perform queries that are not easily expressible using the standard query API.

Suppose you have a model called Person that represents a person with a first name, last name, and age. You want to
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

In this example, we define a custom lookup called StartsWith that extends the Lookup class. We set the lookup_name
attribute to 'startswith' to define the name of the lookup. We then define the as_sql method to generate the SQL
expression for the lookup.
