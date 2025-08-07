---
title: Using Python Tools
teaching: 10 # teaching time in minutes
exercises: 2 # exercise time in minutes
---

## What is a Python tool?

A Python tool is just a Python package that provides a command line interface (CLI). These tools can be run directly with uv or installed globally just like any other command line application.

## Run a Python Tool with uv

The pycowsay package provides a command line interface for a talking cow based on text provided by the user. The uv command shown below will run the pycowsay tool with the provided text:

```
uv tool run pycowsay hello there!
```

The output from running this command is shown below:

```text
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

```
uvx pycowsay hello there!
```

```text
  ------------
< hello there! >
  ------------
   \   ^__^
    \  (oo)\_______
       (__)\       )\/\
           ||----w |
           ||     ||
```

## Install a Python Tool with uv

Use the uv install command to globally install a Python tool on your system. To demonstrate this, the command shown below installs the genja tool which is a static website generator built with Python.

```
uv tool install genja
```

The genja tool can now be directly run from the command line without invoking uv such as:

```
genja --version
```

This will output the following:

```text
25.3
```

Use the list command to show all the tools installed by uv:

```
$ uv tool list

genja v25.3.1
- genja 
```

## Demo

Time for a demo of uv tool.

<script src="https://asciinema.org/a/GjafY19S5PktSmK365hPkOLG1.js" id="asciicast-GjafY19S5PktSmK365hPkOLG1" async="true"></script>

