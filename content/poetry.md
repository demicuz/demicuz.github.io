---
title: "poetry"
date: "2022-10-05"
lastmod: "2022-10-05"
---

Yet another package manager for Python the language.
`source $HOME/.poetry/env` to activate.

> [!warning]
> By default, poetry uses `~/.cache/pypoetry/virtualenvs` for storing virtual envs. Bad idea. Change it with `poetry config virtualenvs.path /your/new/path`. `$HOME/.local/share/poetry/virtualenvs` is suggested. See [this issue](https://github.com/python-poetry/poetry/issues/3346).

### How to use
- `poetry new` - create a project at current path
- `poetry shell` - activate a virtual environment
- `poetry add` - install packages
	- `poetry add --dev` - install dev dependencies
- `poetry show` - show all packages 
- `poetry init` - initialize an existing project with `pyproject.toml`
- `poetry install` - install dependencies of an existing project
---
- `poetry list` - list **all commands**. Not packages.