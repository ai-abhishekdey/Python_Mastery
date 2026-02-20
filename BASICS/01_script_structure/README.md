# Python Script Structure:

## Best Practice

- Keep imports at the top

- Define functions and classes before using them

- Place execution logic inside the main block

---

## Basic Order of a Python Script

A standard Python script usually follows this order:

1. Imports

2. Global constants / variables

3. Function definitions

4. Class definitions (if any)

5. Main execution block
---


### 1. Imports

All required libraries should be imported at the top of the file.

```
import math
import os
```

### 2. Global Constants / Variables

Constants are usually written in uppercase.

```
PI = 3.14159
```

### 3. Function Definitions

Functions contain reusable logic and should be defined before they are used.

```
def area_of_circle(radius):
    return PI * radius * radius
```

### 4. Class Definitions (Optional)

Classes define object structure and behavior.

```
class Person:
    def __init__(self, name):
        self.name = name
```

### 5. Main Execution Block

The main execution block controls what runs when the file is executed directly.

```
if __name__ == "__main__":
    print(area_of_circle(5))
```

## Dunder Names

- **Dunder** -> **Double Underscore** in short

- There are two types of Dunder Names:

    - **Dunder Variables** 

    ```
    __name__
    __dict__
    __class__
    ```

    - **Dunder Methods** 

    ```
    __init__
    __str__
    __len__
    __add__
    ```

### Dunder Variables:

Dunder variables are special built-in identifiers in Python that start and end with double underscores:

```
__variable__
```

- They are defined by Python itself and are used to store internal information

- They are also called:

    - **Special variables**

    - **Magic variables**

    - **System-defined identifiers**

## Dunder Methods:

Dunder methods are special methods that also start and end with double underscores:

```
__method__()
```

- They are also called:

    - **Special methods**

    - **Magic methods**

- They define how objects behave

When we use operators like +, Python actually calls a dunder method behind the scenes

```
Example:

a = 5
b = 3
print(a + b)
```

Internally, Python is doing:

```
print(a.__add__(b))
```

- They are automatically called by Python

When we use operators like +, we just write:

```
a + b
```

Python automatically calls:

```
a.__add__(b)

```

# To add next:

1. __init__ and __main__



## Modules and Packages

📄 **module** : A single python (.py) file

📁 **package** : A folder containing multiple python (.py) files 

Understanding modules and packages is essential for writing modular Python code.

Consider the following project structure:

```
app/
├── main.py
└── src/
    ├── __init__.py
    ├── test.py
    └── train.py
```

### What is a Module?

- A module is simply a Python file (.py file).

- In the above structure:

    - `main.py` → Module

    - `test.py` → Module

    - `train.py` → Module

    - `__init__.py` → Also a module (special one)

- Every .py file is treated as a module in Python.

- Modules help us organize code into separate files so that functionality can be reused and maintained easily.

### What is a Package?

- A package is a folder that contains multiple modules.

- In the above structure:

    - src/ → Package

    - `test.py` → Module inside the src package

    - `train.py` → Module inside the src package

### What `__init__.py` Does Inside a Package ?

- `__init__.py` tells Python: "This folder is a package."

- It runs initialization code when the package is imported.

- In older Python versions (before 3.3), if a folder did NOT contain `__init__.py`, Python would NOT treat it as a package.

- However in modern Python versions (after 3.3), Python supports something called **namespace packages**. Now A folder can act like a package even without `__init__.py`

## Importing Modules vs Importing Specific Functions

- Consider the following structure:

```
app/
├── main.py
└── src/
    ├── __init__.py
    └── train.py
```

- From `main.py`, we can import in two ways:

```
from src import train
```

or

```
from src.train import some_function
```

- Let us consider `train.py` has two functions

```
def add(a, b):
    return a + b

def multiply(a, b):
    return a * b
```

### Scenario 1: Importing the Entire Module

`main.py`

```
from src import train

result1 = train.add(5, 3)
result2 = train.multiply(4, 2)

print(result1)
print(result2)

```

- Imports the entire train module

- We must use `train.` before calling functions

- All functions inside train.py are accessible through the module

### Scenario 2: Importing Specific Functions

`main.py`

```
from src.train import add

result1 = add(5, 3)

print(result1)

```

- Imports only the specific function `add`

- We can call it directly without using `train.`

- Other functions like multiply are not directly available