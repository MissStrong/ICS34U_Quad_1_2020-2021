Note: IO Using Text Files

### I/O

**Input/output** (commonly referred to as **I/O** or **IO**, not to be confused with the top-level domain name *.io*) in computer science refers to the interactions between a program and an external source (e.g. a file, a device, a graphic user interface, etc.).


### Reading Text Files

In Python, you can open a plaintext file using `open()` and read its contents using `.readlines()`.  It's important that we also close the file using `.close()` to prevent strange behaviours from happening.

Plaintext file extensions include *.txt*, *.csv*, *.tsv,* as well as files that are used for programming (*.py*, *.java*, *.c*, etc.).

We can open, read, and close a file like this:

```python
file = open("document.txt", "r")  # Replace "document.txt" with the actual name of the file
file_contents = file.readlines()
file.close()
```

The first parameter in the `open()` function is the file name as a string. The second parameter is the **mode** we want the file to open in.

The `r`  indicates that the file will be opened in **read mode**.

* `w` for **write mode** with the cursor at the top of the file.
* `r+` or `w+` for both read mode and write mode.
* `a` for **append mode**, which is like write mode but the the cursor starts at the end of the file. 
* `a+` for both read mode and append mode.

The contents of the file get stored in a list, with each item being one line in the file. 

If we have a file called document.txt and it contains the following:

```
testing testing
1 2 3
```

...then the following program will print `["testing testing\n", "1 2 3"]`.

```python
file = open("document.txt", "r")
file_contents = file.readlines()
print(file_contents)
file.close()
```

If we want to get rid of the newline characters that appear at the end of a line, we can use `.rstrip()` (which stands for *right strip*, as in: strip the whitespace on the right side of the string).

A **token** is a string of characters that is surrounded by whitespace characters on both ends. Tokens are often words, but sometimes they are numbers, symbols, punctuation marks, or some combination.

If we want to read one "word" in the file at a time, we can do the following:

```python
file = open("document.txt", "r")
file_contents = file.readlines()

for line in file_contents:
  tokens = line.split()  # creates a list of tokens from the line
  for token in tokens:
    print(token)
  
print(file_contents)
file.close()
```

... This would print the following:

```
testing
testing
1
2
3
```

### Writing Text Files

We can create new files as well as modify ones that already exist.

```python
file = open("document.txt", "w")  # Lets us write to document.txt
file.write("Hello World!")
file.close()
```

This would give us the following for document.txt:

```
Hello World!
```

When we are writing multiple line to the file, we can put `\n` after each line.

```python
file = open("document.txt", "w")  # lets us write to document.txt
file.write("Hello\n")
file.write("World!")
file.close()
```

This would give us the following for document.txt:

```
Hello
World!
```

If we didn't have the `\n` at the end of `"Hello\n"`, we would get this instead:

```
HelloWorld!
```

**Important: When you write to a file that was opened in write mode, its original contents get deleted!** 

If you want to simply add something to the bottom of an existing file, open it using `"a"` instead of `"w"`.