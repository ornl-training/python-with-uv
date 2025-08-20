---
title: Running Python Scripts
teaching: 5 # teaching time in minutes
exercises: 2 # exercise time in minutes
---

:::::: questions
- What is a Python script?
- How can I run a Python script?
::::::

:::::: objectives
- Learn about Python scripts and how to run them.
- Add dependencies to a Python script.
::::::

## What is a Python script?

A Python script is just a Python file like `example.py`. A Python file is also referred to as a module in the context of a Python package but for this lesson we will refer to a Python file as a script.

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

```bash
$ uv run example.py
```

```output
Script using standard Python
Random number is 0.8227936022620481
```

Without uv, you would typically run this Python script using the `$ python example.py` command in the terminal.

## Running a script with dependencies

Below is the contents of another Python script named `example2.py`. This script imports the NumPy package which is an external dependency (not included in the Python standard library).

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

```bash
$ uv add numpy --script example2.py
```

This is the script section that was added at the top of the Python file:

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

Now you can execute the script using the same run command used in the previous example:

```bash
$ uv run example2.py
```

```output
Hello from NumPy!
a is [1 2 3 4 5]
```

By including the script section in a Python script, anyone can run that Python file with uv. You don't have to worry about installing Python or creating a virtual environment and downloading dependencies. You just use uv to run the file and it will automatically install Python if it isn't available on your computer and it will automatically install any dependencies needed to run the script.

Below is a demo of using uv to run a Python script that imports the NumPy package. This recording is animated text (not video); consequently, the text in the demo is selectable and can be copied and pasted into your own terminal.

<script src="https://asciinema.org/a/WAai54d95xSKIHCfTOQFpS6YX.js" id="asciicast-WAai54d95xSKIHCfTOQFpS6YX" async="true"></script>

:::::: keypoints
- A Python script is just a single Python file.
- Dependencies can be added to a script to make it self contained.
- Scripts can easily be run with uv which handles Python installation and dependency management.
::::::
