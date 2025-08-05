---
title: Operating System Python
teaching: 5 # teaching time in minutes
exercises: 2 # exercise time in minutes
---

## Why not use the operating system's Python?

Operating systems such as the various flavors of Linux include Python as part of their installation. So why not use this Python instead of installing a separate version? There are many reasons to not use the system Python:

- **Risk of breaking the system tools**. Many operating systems use their system Python installation to run essential tools. Installing or upgrading Python packages globally can break these tools or even destabilize the operating system.
- **Permission issues**. Modifying the system Python usually requires administrator or root privileges, which is a security risk and an inconvenience.
- **Version conflicts**. The system Python version is often outdated and may not match the requirements of your project. Different projects may require different Python or package versions, which system Python cannot flexibly support.
- **Reproducibility problems**. Sharing code or deploying to other machines becomes unreliable because system Python versions and installed packages can vary widely across platforms.
- **Lack of flexibility and control**. You have little control over the version of Python installed with your operating system, and you might not be able to use newer features unless the OS itself updates to a new version.

Using uv eliminates all of these issues.

:::::: challenge

## Check your system Python

What version of Python is your operating system running? You can check this by running `python --version` or `python3 --version` in your terminal which should display the Python version. If the command is not found, then Python is not installed on your system, which is fine because we will be using uv for Python installation.

::::::
