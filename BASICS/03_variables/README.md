
## Python Variables

- A variable is a name used to store a value.

- Think of a variable like a container with a label.

Example

```
x = 10
name = "Roger"
```
Here

- x stores 10

- name stores "Roger"

## Rules for Naming Variables:

- Can contain letters, numbers, underscores

- Cannot start with a number

- Case-sensitive (age and Age are different)

- Cannot use reserved keywords (if, for, class, etc.)

**Valid**

```
age = 25
user_name = "John"
_marks = 90
```

**Invalid**

```
1name = "John"   # ❌ starts with number
class = 10       # ❌ keyword
```

## Variable Scope:

### Local Variable

- Defined inside a function

```
def func():
    x = 10
```
### Global Variable

- Defined outside a function

```
x = 10

def func():
    print(x)
```    

### Using global keyword

```
x = 10

def func():
    global x
    x = 20

```

## Normal v/s Public / Protected / Private variables:

### Normal Variables (Outside Class)

```
x = 10
name = "Roger"

```

- These are just variables.

- There is No public/protected/private concept outside class

### Public / Protected / Private → Only Inside Classes

These concepts are used to control access to attributes of a class

```
class Student:
    def __init__(self):
        self.name = "Roger"        # Public variable
        self._age = 20             # Protected variable (single underscore)
        self.__marks = 95          # Private   variable (doube underscore)

```

## Deleting Variables

- To delete a variable use **del** keyword
```
x = 10

del x

```

## Variable Assignment and Equality in Python

### Variable Assignment

- Assignment means: Giving a value to a variable using **= operator**

```
x = 10

name = "Roger"
```
Here:

- x is assigned 10

- name is assigned "Roger"

### Variable Reassignment:

Reassignment means: We can change the value later:

```
x = 10
x = 20
```
Now x stores 20

### Multiple Assignment:

```
a = b = 5

```

Both a and b get the value 5

### Unpacking Assignment:

```
x, y, z = 1, 2, 3

```
## Equality in Python:

There are two ways to compare values:

-  "==" → Equality Operator

-  "="  → Identity Operator