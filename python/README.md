# Python convention

## Style

- [PEP 8](https://www.python.org/dev/peps/pep-0008/)
- [Google docstring style](https://google.github.io/styleguide/pyguide.html#38-comments-and-docstrings)

## Installation

```shell
python3 -m pip install pylint black
```

Download [python/.pylintrc](https://github.com/HITS-AI/HITS-convention/blob/main/python/.pylintrc) and save it to a project root path.

ex)

```shell
<project>
├── ...
├── .pylintrc
└── ...
```

## VS Code

### Extension

- [https://marketplace.visualstudio.com/items?itemName=ms-python.python](https://marketplace.visualstudio.com/items?itemName=ms-python.python)
- [https://marketplace.visualstudio.com/items?itemName=njpwerner.autodocstring](https://marketplace.visualstudio.com/items?itemName=njpwerner.autodocstring)
- [https://marketplace.visualstudio.com/items?itemName=ms-python.vscode-pylance](https://marketplace.visualstudio.com/items?itemName=ms-python.vscode-pylance)

### settings.json

- Press Ctrl(Command) + Shift + P
- Find `>Preferences: Open Settings (JSON)` option and select it

```json
  ...

  "[python]": {
    "editor.defaultFormatter": "ms-python.python"
  },
  "python.formatting.blackArgs": ["--line-length", "80"],
  "python.formatting.provider": "black",
  "python.linting.pylintEnabled": true,
  "python.languageServer": "Pylance",
  "python.analysis.typeCheckingMode": "basic",
  "python.analysis.autoImportCompletions": false,

...
```

## Manually check and format

### Style check

```shell
pylint **/*.py
```

### Auto formmat

```shell
black -l 80 .
```
