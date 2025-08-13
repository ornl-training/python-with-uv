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
uv init my-project
```

The contents of the directory is shown below. Notice that uv automatically sets up the directory as a Git repository and includes an ignore file to prevent unnecessary files from being committed to version control.

```bash
cd my-project
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

You can also use uv to add dependencies to the project. Here we add the NumPy package to the project which will automatically create a virtual environment and install the NumPy package into the virtual environment.

```bash
uv add numpy
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

Lastly, to run a script in the project, just use the uv run command:

```bash
uv run main.py
```

```output
Hello from my-project!
a is [1 2 3 4 5]
```

## Collaborate on Python Projects with uv

Collaborating on a Python project can be a daunting task because everyone needs to use the same version of Python and have the same dependencies (and versions of dependencies) installed in their virtual environment. However, uv makes collaboration very simple because it handles all of the installation steps for you. The basic steps for collaborating on a Python project with uv are:

1. Download and install uv
2. Download the Python project
3. Run the Python code in the project with uv

That's it! There is no need to install Python on your computer, or create and activate a virtual environment, or install dependencies for running code in the Python project. This is all handled by uv when you run the code.

:::::: keypoints
- A Python project is just a directory of Python files with a `pyproject.toml` file for configuration.
- Use uv to easily add dependencies to a Python project and collaborate with other developers.
::::::
