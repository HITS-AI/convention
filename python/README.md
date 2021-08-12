# Python convention

## Style

- [PEP 8](https://www.python.org/dev/peps/pep-0008/)
- [Google docstring style](https://google.github.io/styleguide/pyguide.html#38-comments-and-docstrings)

## Installation

If you install `Python` extension on VScode, Vscode will ask if you want to install the program below. Press `yes`.

```shell
python3 -m pip install pylint black isort
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

- [Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python)
- [Pylance](https://marketplace.visualstudio.com/items?itemName=ms-python.vscode-pylance)
- [Jupyter](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter)
- [Python Docstring Generator](https://marketplace.visualstudio.com/items?itemName=njpwerner.autodocstring)
- [Bracket Pair Colorizer 2](https://marketplace.visualstudio.com/items?itemName=CoenraadS.bracket-pair-colorizer-2)
- [Git Graph](https://marketplace.visualstudio.com/items?itemName=mhutchie.git-graph)
- [GitLens — Git supercharged](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
- [indent-rainbow](https://marketplace.visualstudio.com/items?itemName=oderwat.indent-rainbow)
- [Material Icon Theme](https://marketplace.visualstudio.com/items?itemName=PKief.material-icon-theme)
- [Remote Development](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack)
- [Vim](https://marketplace.visualstudio.com/items?itemName=vscodevim.vim)

### settings.json

- Press Ctrl(Command) + Shift + P
- Find `>Preferences: Open Settings (JSON)` option and select it
- Add below configuration

```json
  ...

  "[python]": {
    "editor.codeActionsOnSave": {
      "source.organizeImports": true
    },
    "editor.defaultFormatter": "ms-python.python",
    "editor.insertSpaces": true,
    "editor.tabSize": 4
  },
  "python.analysis.autoImportCompletions": false,
  "python.analysis.typeCheckingMode": "basic",
  "python.formatting.blackArgs": ["--line-length", "80"],
  "python.formatting.provider": "black",
  "python.languageServer": "Pylance",
  "python.linting.pylintEnabled": true,
  "python.sortImports.args": ["--profile", "black"],

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
