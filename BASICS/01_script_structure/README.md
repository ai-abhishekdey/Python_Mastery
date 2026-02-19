## Basic Order of a Python Script

A standard Python script usually follows this order:

1. Imports

2. Global constants / variables

3. Function definitions

4. Class definitions (if any)

5. Main execution block

## Best Practice

- Keep imports at the top

- Define functions and classes before using them

- Place execution logic inside the main block

---

1. Imports

All required libraries should be imported at the top of the file.

```
import math
import os
```

2. Global Constants / Variables

Constants are usually written in uppercase.

```
PI = 3.14159
```

3. Function Definitions

Functions contain reusable logic and should be defined before they are used.

```
def area_of_circle(radius):
    return PI * radius * radius
```

4. Class Definitions (Optional)

Classes define object structure and behavior.

```
class Person:
    def __init__(self, name):
        self.name = name
```

5. Main Execution Block

The main execution block controls what runs when the file is executed directly.

```
if __name__ == "__main__":
    print(area_of_circle(5))
```