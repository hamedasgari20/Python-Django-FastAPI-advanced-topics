# Python and Django advanced topics with simple examples

## Introduction
In this research, I have given a brief overview of advanced topics in Python and Django. This article does not provide in-depth knowledge on various topics and the purpose of this research is to collect topics in one place to provide the reader with a mental framework. In this article, I have used very simple examples to explain the topics easily. Naturally, studying and examining more and more practical examples will help a lot to understand each topic. I hope reading this article is useful for you. (**Hamid Asgari**)


## Python related topics:

### Decorators
In Python, decorators are a way to modify the behavior of functions or classes by wrapping them with other functions. Here's a simple example to demonstrate the basic concept of decorators:
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
The map() function in Python is a built-in function that applies a given function to each item in an iterable (such as a list, tuple, or string) and returns an iterator with the results. It takes two or more arguments: the function to apply and one or more iterables. The basic syntax of the map() function is as follows:
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
The map() function can be useful in various scenarios when working with Django. In the following gives an example of mapping a function to a query set:
```
from django.contrib.auth.models import User
 
# Get a queryset of all users
users = User.objects.all()
 
# Get a list of usernames using map() and a lambda function
usernames = list(map(lambda user: user.username, users))
 
# Output: ['user1', 'user2', 'user3', ...]
```
### Itertools
Itertools is a Python module that provides a collection of functions for creating and manipulating iterators, which are objects that can be iterated (looped) over. Here are some commonly used functions provided by the itertools module
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
Here are a few examples of how you can utilize itertools in the context of Django. In the following example, we use itertools.chain() to combine the querysets of posts and comments into a single iterable. We then sort the combined results based on the creation date, using sorted().
```
import itertools
from myapp.models import Post, Comment
 
posts = Post.objects.filter(published=True)
comments = Comment.objects.filter(approved=True)
 
combined_results = itertools.chain(posts, comments)
sorted_results = sorted(combined_results, key=lambda item: item.created_at, reverse=True)
```
### Lambda function
In Python, a lambda function is a small anonymous function that can be defined without a name. It is also known as an inline function or a lambda expression. Lambda functions are typically used when you need a simple function that will be used only once or as a parameter to another function. The general syntax of a lambda function in Python is:
```
lambda arguments: expression
```
For example, let's say we want to create a lambda function that takes two arguments and returns their sum:
```
add = lambda x, y: x + y
result = add(3, 5)
print(result)  # Output: 8
```
Lambda functions are often used with built-in functions like map(), filter(), and reduce(). These functions take another function as a parameter, and lambda functions provide a convenient way to define these functions on the fly without explicitly defining a separate function. Here's an example using the map() function with a lambda function to square a list of numbers:
```
numbers = [1, 2, 3, 4, 5]
squared_numbers = list(map(lambda x: x ** 2, numbers))
print(squared_numbers)  # Output: [1, 4, 9, 16, 25]
```
For more complex or reusable functions, it's often better to define a regular named function using the def keyword. Here are a few examples of how you can use lambda functions in Django:
- Filtering objects in a queryset:
You can use a lambda function as a condition for filtering objects in a Django queryset. For instance:
```
filtered_queryset = MyModel.objects.filter(lambda obj: obj.field_name == 'some_value')
```

### Exception Handling
Exception handling in Python allows you to gracefully handle and recover from runtime errors or exceptional conditions that may occur during the execution of your program. Here's an example that demonstrates the usage of exception handling:
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
In this example, if SomeException is raised within the try block, the corresponding except block will be executed. It returns an HTTP 500 response with a custom error message.

- Handling database-related exceptions:

When working with Django's ORM (Object-Relational Mapping) and database operations, you may encounter exceptions related to database errors. 

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

In this example, if a DatabaseError occurs during database operations, you can render an error template with the exception message.

### SOLID principles
The SOLID principles are a set of design principles that help in creating maintainable, scalable, and flexible software systems.
- Single Responsibility Principle (SRP)
This principle states that a class should have only one reason to change, meaning it should have only one responsibility. Let's say we have a User class that handles both user authentication and user data management. Instead, we can separate these responsibilities into two classes: Authenticator and UserManager. Here's a Python example:

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
This principle states that software entities (classes, modules, functions) should be open for extension but closed for modification. In other words, you should be able to add new functionality without modifying existing code. Let's say we have a Shape class with different subclasses such as Circle and Rectangle. Instead of modifying the Shape class every time we want to add a new shape, we can use inheritance and polymorphism to extend the functionality:

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
This principle states that objects of a superclass should be replaceable with objects of its subclasses without affecting the correctness of the program. Let's say we have a function that expects a Shape object. According to LSP, we should be able to pass any subclass of Shape without causing any issues:

```
def print_area(shape):
    print(f"Area: {shape.area()}")
 
shape = Circle(5)
print_area(shape)  # Output: Area: 78.5
 
shape = Rectangle(3, 4)
print_area(shape)  # Output: Area: 12
```

- Interface Segregation Principle (ISP)

This principle states that clients should not be forced to depend on interfaces they do not use. It promotes the idea of having smaller, focused interfaces rather than large, general-purpose ones. Let's say we have an Animal interface with methods like walk(), swim(), and fly(). Instead of having a single interface, we can split it into smaller interfaces based on functionality:

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
This principle states that high-level modules should not depend on low-level modules. Both should depend on abstractions. It encourages the use of interfaces or abstract classes to decouple dependencies.

I have not found yet good example to show this principle.

### Python collection
Python provides several built-in collection types, such as lists, tuples, sets, and dictionaries. These collections can be used to store and organize data efficiently.

 - lists
A list is a mutable collection that can store an ordered sequence of elements. It is defined using square brackets ([]). Here's an example:

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
A tuple is an immutable collection that can store an ordered sequence of elements. It is defined using parentheses (()). Here's an example:

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
A set is an unordered collection that stores unique elements. It is defined using curly braces ({}) or the set() function. Here's an example:

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
A dictionary is a collection that stores key-value pairs. It is defined using curly braces ({}) and colons (:). Here's an example:

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
Generators and iterators are powerful constructs in Python used for efficient iteration and lazy evaluation. They provide a way to generate or yield values on the fly, enabling you to work with large or infinite sequences without loading everything into memory at once. 
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
Here, the read_lines() function returns a generator that yields one line at a time. This approach is memory-efficient and allows you to process large files without loading the entire contents into memory.
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
The main advantage of the generator approach is its simplicity and conciseness. The generator function hides most of the implementation details required for iterators, resulting in cleaner code. On the other hand, the iterator approach provides more control and flexibility, allowing for more complex iterator implementations beyond what generators can offer.

Ultimately, the choice between generators and iterators depends on the specific requirements of your program. Generators are often the preferred choice for simpler iterations and lazy evaluation, while iterators offer more customization and control when dealing with complex iteration scenarios.

### Magic methods
Magic methods, also known as dunder methods, are special methods in Python that start and end with double underscores. They are not meant to be invoked directly by the user, but are called internally by the class on certain actions. 
 Here are some examples of commonly used magic methods in Python: 

`__init__(self, ...)` : This method is called when an object is created and initialized. It takes arguments that are used to initialize the object's attributes.

`__str__(self)` : This method is called when the object is printed as a string. It returns a string representation of the object.

`__len__(self)` : This method is called when the built-in len() function is called on the object. It returns the length of the object.

`__add__(self, other)` : This method is called when the + operator is used on the object. It takes another object as an argument and returns the result of the addition.

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
Concurrency involves allowing multiple tasks to take turns accessing the same shared resources, like disk, network, or a single CPU core. Parallelism, on the other hand, is about maximizing the use of hardware resources, such as multiple CPU cores, to execute multiple tasks simultaneously. Threading is a way to achieve concurrency by running multiple threads within a single process, while asyncio is a way to achieve concurrency by running a single thread that can switch between multiple tasks.
- Threading:
The following code snippet demonstrates how to use threading to execute multiple tasks concurrently within a single process.

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
The following code snippet demonstrates how to use asyncio to execute multiple tasks concurrently within a single thread:

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
The following code snippet demonstrates how to use multiprocessing to execute multiple tasks in parallel across multiple processes:

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
In general, concurrency is preferred for IO-bound tasks, as it allows you to do something else while the IO resources are being fetched. Parallelism, on the other hand, is preferred for CPU-bound tasks, as it allows you to take advantage of multiple CPU cores to execute multiple tasks simultaneously.

### Main types of methods in python classes
In Python, there are three main types of methods that can be defined in a class:
1. Instance Methods
Instance methods are the most common type of methods used in Python classes. They are defined using the **self** parameter as the first argument. Instance methods can access and modify the instance attributes of the class.

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
Class methods are methods that are bound to the class and not the instance of the class. They are defined using the **@classmethod** decorator, and they take the class itself as their first argument, typically named **cls**. Class methods can be called on the class itself, rather than on an instance of the class. 

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
Static methods are methods that don't depend on the class or instance. They are defined using the **@staticmethod** decorator and take no special first argument. Static methods are typically used for utility functions that don't require access to the class or instance. 

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
Django signals can be used to automate tasks and update data in your application without having to manually perform those tasks or update the data.
Let's say we have a Django application that allows users to place orders for products. We want to automatically update the product quantity in the database whenever an order is placed. We can use Django signals to accomplish this.
Here are the steps to use Django signals for this example:

1. Create a new file called **signals.py** in the same directory as your **models.p**y file.
1. Import the** django.dispatch.Signal** class.
1. Define a new signal using the Signal class.
1. Define a function that will be called when the signal is triggered. This function should accept two arguments: sender and instance.
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
In this example, we define a new signal called order_placed using the Signal class. We also define a function called update_product_quantity that will be called when the signal is triggered. This function gets the Product object associated with the Order object, calculates the new quantity, and updates the product quantity in the database.

Finally, we connect the order_placed signal to the update_product_quantity function using the connect method. We also specify the sender argument to indicate that this signal should only be triggered when an Order object is saved.

To trigger the signal, we simply need to create a new Order object:

```
from myapp.models import Order, Product

product = Product.objects.get(pk=1)
order = Order(product=product, quantity=3)
order.save()  # This will trigger the order_placed signal
```
When the save method is called on the Order object, the order_placed signal will be triggered, and the update_product_quantity function will be called, updating the product quantity in the database.

### Django middleware
Django middleware provides a way to process requests and responses globally in your application. Middleware can be used to perform authentication, logging, modifying headers, and more.
Let's say we have a Django application that needs to add a custom header to every HTTP response. We can use Django middleware to accomplish this.
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

In this example, we define a new middleware class called CustomHeaderMiddleware that extends the MiddlewareMixin class. We implement the process_response method to modify the response object by adding a custom header.
Finally, we add our middleware class to the MIDDLEWARE setting in our **settings.py** file:

```
MIDDLEWARE = [
    # Other middleware classes...
    'myapp.middleware.CustomHeaderMiddleware',
]
```
Now, whenever an HTTP response is returned by our application, the CustomHeaderMiddleware class will modify the response by adding a custom header.
