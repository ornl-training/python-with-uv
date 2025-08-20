---
title: Working with Python Projects
teaching: 10 # teaching time in minutes
exercises: 2 # exercise time in minutes
---

:::::: questions
- What is a Python project?
- How do I create a Python project and run it?
::::::

:::::: objectives
- Create a Python project with uv.
- Add dependencies to a Python project and run code.
- Collaborate on a Python project with other developers.
::::::

## What is a Python project?

A Python project is a directory containing multiple Python files. The metadata for the Python project is contained in a `pyproject.toml` file which contains information about the Python version required for the project as well as dependencies required by the project.

## Create a Python Project with uv

Use the init command in uv to create a directory for a Python project. The command shown below creates a directory called my-project that represents a Python project.

```bash
$ uv init my-project
```

The contents of the directory are shown below. Notice that uv automatically sets up the directory as a Git repository (`.git/`) and includes an ignore file (`.gitignore`) to prevent unnecessary files from being committed to version control. The `.python-version` file contains the project's default Python version.

```bash
$ cd my-project
```

```output
my-project/
├── .git/
├── .gitignore
├── .python-version
├── main.py
├── pyproject.toml
└── README.md
```

You can also use uv to add dependencies to the project. Here we add the NumPy package to the project which will automatically create a virtual environment (`.venv/`) and install the NumPy package into the virtual environment. A `uv.lock` file is also created to ensure that developers working on the project are using a consistent set of package versions.

```bash
$ uv add numpy
```

```output
my-project/
├── .git/
├── .gitignore
├── .python-version
├── .venv/
├── main.py
├── pyproject.toml
├── README.md
└── uv.lock
```

Notice that uv automatically added the NumPy package as a dependency of the project to the `pyproject.toml` file:

```toml
# pyproject.toml

[project]
name = "my-project"
version = "0.1.0"
description = "Add your description here"
readme = "README.md"
requires-python = ">=3.13"
dependencies = [
    "numpy>=2.3.0",
]
```

Lastly, to run a script such as `main.py` in the project, just use the uv run command as shown below:

```python
# main.py

import numpy as np


def main():
    print("Hello from my-project!")

    a = np.array([1, 2, 3, 4, 5])
    print("a is", a)


if __name__ == "__main__":
    main()
```

```bash
$ uv run main.py
```

```output
Hello from my-project!
a is [1 2 3 4 5]
```

## Collaborate on Python Projects with uv

Collaborating on a Python project can be a daunting task because everyone needs to use the same version of Python and have the same dependencies (and versions of dependencies) installed in their virtual environment. For projects that contain a `pyproject.toml` file, uv makes collaboration very simple because it handles all of the installation steps for you. The basic steps for collaborating on a Python project with uv are:

1. Download and install uv
2. Download the Python project
3. Run the Python code in the project with the `uv run` command

That's it! There is no need to install Python on your computer, or create and activate a virtual environment, or install dependencies for running code in the Python project. This is all handled by uv when you run the code.

For projects that don't provide a `pyproject.toml` file, you may need to manually create the virtual environment with uv then install dependencies with pip as summarized below. Unfortunately, there are many ways to setup a Python project, so the steps needed to install and run such a project may vary if there is no `pyproject.toml` file.

1. Download and install uv
2. Download the Python project
3. Create the virtual environment for a specific Python version with `uv venv --python 3.12`
4. Install dependencies in the environment with the `uv pip install` command
5. Activate the virtual environment and run code with the `python` command

:::::: keypoints
- A Python project is just a directory of Python files with a `pyproject.toml` file for configuration.
- Use uv to easily add dependencies to a Python project and collaborate with other developers.
::::::
