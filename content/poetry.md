---
title: "poetry"
---

Yet another package manager for Python the language.
`source $HOME/.poetry/env` to activate.

> [!warning]
> By default, poetry uses `~/.cache/pypoetry/virtualenvs` for storing virtual envs. Bad idea. Change it with `poetry config virtualenvs.path /your/new/path`. `$HOME/.local/share/poetry/virtualenvs` is suggested. See [this issue](https://github.com/python-poetry/poetry/issues/3346).

### How to use
- `poetry shell` - activate a virtual environment
- `poetry install` - install dependencies of existing project
