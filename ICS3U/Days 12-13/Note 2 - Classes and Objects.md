## Classes and Objects

### Classes 

In order to understand what an **object** is, it's first necessary to know what a **class** is. Classes are used to define the properties and functions for non-primitive data types. For example, there is a built-in class called `str` that has the defintions for `.count()`, `.lower()`, `.join()` and other functions used with strings. We can see all the built-in properties and functions of a class using the `dir()` function. For example, `print(dir(str))` prints the full list of the publicly accesible properties and functions defined within the `str` class.

Functions that are defined inside of a class are called **methods**. Variables that are defined inside of a class are called **fields**.

### Objects

An **object** is an instance of class.  Whenever we create a string, a list, a dictionary, or any data type (including custom ones), we are creating an object.

```python
my_list = [1, 2, 3] # The variable my_list stores the object [1, 2, 3]
my_string = "123" # The variable my_string stores the object "123"
```

All objects are stored in a particular location in memory and the variable name simply points to this location. To see the address in hexadecimal, we can use `hex(id())`.

```python
my_list = [1, 2, 3] 
my_string = "123"

print(hex(id(my_list)) # Prints the address of [1, 2, 3] in hexadecimal
print(hex(id(my_sting))  # Prints the address of 123" in hexadecimal
```

