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

## Installing uv

The only requirement for this workshop is the uv tool. Detailed installation instructions are given in the [uv documentation](https://docs.astral.sh/uv/getting-started/installation/) but the main macOS, Linux, and Windows installation commands are presented below.

Install uv on macOS and Linux with:

```
curl -LsSf https://astral.sh/uv/install.sh | sh
```

Install uv on Windows with:

```
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

That's it! You are now ready to run Python code.
