## Note – Exception Handling


Whenever you run a program that has errors, you may have noticed that repl.it attempts to tells you what kind of error it is. 

For example, if you try to divide by zero, you get a message in the console saying that there was an error called `ZeroDivisionError`.

![](../../Images/Zero_Division_Error.png)

An **exception** is a problem that occurs while a program is running. When an exception occurs, it is **thrown**. When this happens and your program doesn't **catch** it (i.e. it doesn't handle it), the program terminates abruptly. 


In order to avoid a program from terminating abruptly, you should consider possible exceptions that could occur in your program.

Here is an example of a method that handles a division by zero error.

```python
def divide_three_ints(a, b, c):
  try:
    return a/b/c
  except:
    if (b == 0):
      print("Error. B cannot be zero.")
    if (c == 0):
      print("Error. C cannot be zero.")
```

The content in the `try` block is run first. It tries to run the lines in the block; if an exception occurs, the exception is "thrown" and the rest of the block does not run. 

The content in the `except` block runs only when an exception such as `ZeroDivisionError` has been thrown. It "catches" the exception and prevents the program from abruptly terminating and giving you a red error message.
