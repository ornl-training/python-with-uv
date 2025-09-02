---
title: Anaconda and Pixi
teaching: 5 # teaching time in minutes
exercises: 2 # exercise time in minutes
---

:::::: questions
- What is Anaconda?
- What is pixi?
::::::

:::::: objectives
- Recognize the use cases for Python programming with Anaconda.
- When to use Pixi for Python projects.
::::::

## What is Anaconda?

[Anaconda](https://www.anaconda.com/) is a popular package and dependency management platform used primarily for Python programming in data science and scientific computing. It is bundled with a wide range of pre-built packages and includes the Conda package manager. Anaconda/Conda offer package management support for C and C++ libraries and other programming languages but it is mostly used for Python.

It should be noted that Anaconda's license agreement requires organizations of more than 200 employees to purchase a business license. This may be cost prohibitive for some companies and institutions. Contrast this with uv which does not have such license restrictions.

## What is Pixi?

[Pixi](https://pixi.sh/latest/) is a package manager that supports multiple programming languages including Python; although, its Python support is provided through uv. Pixi is a good alternative to Anaconda if you need to use libraries or packages that are only available through Conda.

:::::: keypoints
- Anaconda offers easy installation and package management for multi-language projects but its license restrictions can be cost prohibitive.
- Pixi is a good alternative to Anaconda/Conda but it still relies on uv for Python package management.
- For Python projects, uv offers better dependency management and faster installation compared to Anaconda/Conda and Pixi.
::::::
