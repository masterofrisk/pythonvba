# VBA-like Functions in Python

This module provides a set of VBA-like functions that you can use directly in your Python projects. Save the `cC.py` file to your project folder and import the functions using the following import statement:

```python
from cC import *
```
---
Alternatively, you can also install the **morvba** package with `pip`.

```python
pip install -U morvba
```

After your package has been installed, you can import the class **top-level functions** from the package as follows:

```python
from morvba.cC import *
```

Or if you prefer, you can import the **C** class from the package **morvba** as follows:

```python
from morvba.cC import C

# Now you can create an instance of the C class and use its methods
c = C()
c.trim('  This is a string   ')  # Returns 'This is a string'
```
---
# Functions

## savesetting(a='', b='', c='', d='')
Save a setting to an INI file.

**Arguments:**

- `a`: Group name
- `b`: Subgroup name
- `c`: Item name
- `d`: Value

**Example:**

```python
savesetting("app", "window", "width", "1024")
```

---
## getsetting(a='', b='', c='', d='')
If you pass a value to the d parameter, the savesetting function will be invoked to save the value before retrieving it from the INI file. This behavior can be useful in development mode to save settings the first time you run your code without needing to change the code structure or create additional code to set the values. If the d parameter is empty, the function will only retrieve the setting from the INI file. If the variable does not have a value, an empty string will be returned.

**Arguments:**

- `a`: Group name
- `b`: Subgroup name
- `c`: Item name
- `d`: Default value (optional)

**Example:**

```python
window_width = getsetting("app", "window", "width", "")
```

---
## left(str_text='', int_len=1)
Return the left part of a string.

**Arguments:**

- `str_text`: Input string
- `int_len`: Number of characters to return (default is 1)

**Example:**

```python
result = left("Hello, world!", 5)
```

---
## right(str_text='', int_len=1)
Return the right part of a string.

**Arguments:**

- `str_text`: Input string
- `int_len`: Number of characters to return (default is 1)

**Example:**

```python
result = right("Hello, world!", 6)
```

---
## mid(str_text='', int_start=1, int_len=1)
Return a substring from the middle of a string.

**Arguments:**

- `str_text`: Input string
- `int_start`: Starting position
- `int_len`: Number of characters to return

**Example:**

```python
result = mid("Hello, world!", 8, 5)
```

---
## pricap(str_text='')
Capitalize the first letter of each word in a string.

**Arguments:**

- `str_text`: Input string

**Example:**

```python
result = pricap("hello, world!")
```

---
## instr(int_start=1, str_text='', str_what='')
Return the position of a substring in a string.

**Arguments:**

- `int_start`: Starting position
- `str_text`: Input string
- `str_what`: Substring to search for

**Example:**

```python
position = instr(1, "Hello, world!", "world")
```

---
## trim(str_text='', str_char=' ')
Trim spaces or a specific character from a string.

**Arguments:**

- `str_text`: Input string
- `str_char`: Character to trim (default is space)

**Example:**

```python
result = trim("   Hello, world!   ")
```

---
## pkey(str_text='', str_ini='', str_end='', boo_trim=True)
Extract a string between two delimiters.

**Arguments:**

- `str_text`: Input string
- `str_ini`: Starting delimiter
- `str_end`: Ending delimiter
- `boo_trim`: Whether to trim spaces (default is True)

**Example:**

```python
result = pkey("Example: [Hello, world!]", "[", "]")
```
---
If you import these functions as top-level functions in your Python code, you can use them without referencing the class name, just like you would in VBA.
