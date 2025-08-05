---
title: Running Python Scripts
teaching: 5 # teaching time in minutes
exercises: 2 # exercise time in minutes
---

## What is a Python script?

A Python script is just a Python file like `example.py`. A Python file is also referred to as a module in the context of a Python package but for this lesson we will use the script definition.

## Running a script with uv

Below is the contents of a Python script named `example.py`. This script does not have any external dependencies. It only uses features available in the Python standard library.

```python
# example.py

import random


def main():
    print("Script using standard Python")
    print("Random number is", random.random())


if __name__ == "__main__":
    main()
```

Use the following command to run the script with uv:

```
uv run example.py
```

## Running a script that has dependencies with uv

Below is the contents of another Python script named `example2.py`. This script imports the NumPy package which is an external dependency (not included in Python).

```python
# example2.py

import numpy as np


def main():
    print("Hello from NumPy!")

    a = np.array([1, 2, 3, 4, 5])
    print("a is", a)


if __name__ == "__main__":
    main()
```

To run this code, uv must install the NumPy package so it can be imported by the script. The command shown below will add a script section that provides the Python version and list of dependencies.

```
uv add —-script example2.py numpy
```

```python
# /// script
# requires-python = ">=3.13"
# dependencies = [
#     "numpy",
# ]
# ///

import numpy as np


def main():
    print("Hello from NumPy!")

    a = np.array([1, 2, 3, 4, 5])
    print("a is", a)


if __name__ == "__main__":
    main()
```

Now you can run the script using the same run command used in the previous example:

```
uv run example2.py
```

By including the `/// script` section in a Python script, anyone can run a Python file using uv.
