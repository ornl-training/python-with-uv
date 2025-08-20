---
site: sandpaper::sandpaper_site
---

This workshop introduces [uv](https://docs.astral.sh/uv/) which is a universal tool for installing Python and managing dependencies for Python projects. Without uv it can be cumbersome to install Python especially if different Python versions are needed. Also, managing Python packages can be a nightmare for large projects where it is essential that everyone has the same development environment. This workshop is for scientists, engineers, and programmers of all skill levels who want to learn about modern Python installation, dependency management, and reproducible environments for Python projects.

## Learning Objectives

After attending this workshop, participants will be able to:

- Easily install Python on macOS, Linux, and Windows operating systems.
- Create Python scripts with dependencies that can run on any operating system.
- Manage dependencies for a Python project without worrying about version conflicts.
- Install Python packages as command line tools.
- Create a reproducible and maintainable Python environment for collaborative project development.

## What is uv?

The [uv](https://docs.astral.sh/uv/) tool is a fast Python package and project manager written in Rust. It is developed by [Astral](https://astral.sh/) who also created [ruff](https://docs.astral.sh/ruff/) (linting and formatting) and [ty](https://docs.astral.sh/ty/) (type checker). It replaces tools like pip, tox, conda, pipenv, poetry, pdm, pipx, and more. Different versions of Python can easily be managed with uv. A global cache is utilized for dependencies to prevent excessive package downloads and disk usage. It is the most simple and easiest way to install Python and run Python code and tools.

:::::: prereq
The only prerequisite for this workshop is a basic understanding of the command line interface (CLI) in the terminal. All operating systems include a terminal application so please make sure you know how to use your terminal before attending this workshop. On macOS the included terminal app is just called Terminal. On Linux desktop environments the terminal app may be called konsole, console, terminal, or some variant of the word "terminal". On Windows the included terminal application is called Windows Terminal.
::::::
