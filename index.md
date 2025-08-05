---
site: sandpaper::sandpaper_site
---

This lesson introduces [uv](https://docs.astral.sh/uv/) which is a universal tool for installing Python and managing dependencies for Python projects.

## Learning Objectives

After attending this workshop, participants will be able to:

- Easily install Python on macOS, Linux, and Windows operating systems.
- Manage package dependencies for a Python project without worrying about version conflicts.
- Install Python packages as command line tools.
- Create a reproducible and maintainable Python environment for collaborative project development.

## What is uv?

The uv tool is a fast Python package and project manager tool written in Rust. It is developed by Astral who also created ruff (linting and formatting) and ty (type checker). It replaces tools like pip, tox, conda, pipenv, poetry, pdm, pipx, and more. Different versions of Python can easily be managed with uv. A global cache is utilized for dependencies to prevent excessive package downloads and disk usage. It is the most simple and easiest way to install Python and run Python code and tools.

