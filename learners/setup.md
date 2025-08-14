---
title: Setup
---

## Installing uv

The only requirement for this workshop is the uv tool. Detailed installation instructions are given in the [uv documentation](https://docs.astral.sh/uv/getting-started/installation/) but the main macOS, Linux, and Windows installation commands are presented below.

Install uv on macOS and Linux with:

```bash
$ curl -LsSf https://astral.sh/uv/install.sh | sh
```

Install uv on Windows with:

```bash
$ powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

You may need to restart your terminal to ensure that uv was installed. Check the installation by displaying the version number using the `--version` option as shown below. If the command displays the uv version number then the installation was successful.

```bash
$ uv --version
```

```output
uv 0.8.4 (e176e1714 2025-07-30)
```

That's it! You are now ready to run Python code. With uv you do not need to worry about installing Python or activating virtual environments, uv handles all of this for you.

