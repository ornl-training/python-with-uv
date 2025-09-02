---
title: Using Python Tools
teaching: 5 # teaching time in minutes
exercises: 5 # exercise time in minutes
---

:::::: questions
- What is a Python tool?
- How can I install, run, and manage a Python tool?
::::::

:::::: objectives
- Install and run a Python tool with uv.
::::::

## What is a Python tool?

A Python tool is just a Python package that provides a command line interface (CLI). These tools can be run directly with uv or installed globally just like any other command line application.

## Run a Python tool with uv

The pycowsay package provides a command line interface for a talking cow based on text provided by the user. The uv command shown below will run the pycowsay package with the provided text. Notice there is no need to install Python, create a virtual environment, activate the virtual environment, and install the pycowsay package into the environment. You just use uv to directly run the pycowsay package; uv will handle installation and virtual environment creation automatically.

```bash
$ uv tool run pycowsay hello there!
```

```output
  ------------
< hello there! >
  ------------
   \   ^__^
    \  (oo)\_______
       (__)\       )\/\
           ||----w |
           ||     ||
```

An equivalent command to `uv tool run` is `uvx` which is demonstrated below.

```bash
$ uvx pycowsay hello there!
```

```output
  ------------
< hello there! >
  ------------
   \   ^__^
    \  (oo)\_______
       (__)\       )\/\
           ||----w |
           ||     ||
```

Here is a demo of using uvx to run the pycowsay tool:

<script src="https://asciinema.org/a/GjafY19S5PktSmK365hPkOLG1.js" id="asciicast-GjafY19S5PktSmK365hPkOLG1" async="true"></script>

## Install, upgrade, and remove a Python tool

Use the uv install command to globally install a Python tool on your system. To demonstrate this, the command shown below installs the Genja tool which is a static website generator built with Python.

```bash
$ uv tool install genja
```

The genja tool can now be run directly from the command line without invoking uv such as:

```bash
$ genja --version
```

```output
25.3
```

Use the list command to show all the tools installed by uv:

```bash
$ uv tool list
```

```output
genja v25.3.1
- genja 
```

Use the upgrade command to upgrade a single Python tool or all of the installed tools:

```bash
# Upgrade a single tool
$ uv tool upgrade genja

# Upgrade all installed tools
$ uv tool upgrade --all
```

To remove a tool, use the uninstall command:

```bash
$ uv tool uninstall genja
```

:::::: challenge

What happens if you run `uvx jupyter notebook` in your terminal?

::: solution

You should see a Jupyter notebook running in your web browser. The file browser for the notebook shows the contents of the directory where the uvx command was run. This is the easiest way to run a Jupyter notebook to explore Python code.

:::
::::::

:::::: keypoints
- A Python package with a command-line interface is a Python tool.
- A Python tool can be installed, run, and managed with the `uv tool` command.
- With uv, Python tools can be easily installed on any operating system.
::::::
