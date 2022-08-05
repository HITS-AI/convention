# Python convention

## Style

- [PEP 8](https://www.python.org/dev/peps/pep-0008/)
- [Google docstring style](https://google.github.io/styleguide/pyguide.html#38-comments-and-docstrings)

## Version scheme

- [Semantic Versioning 2.0.0](https://semver.org/)
- [PEP 440](https://www.python.org/dev/peps/pep-0440/)

## Installation

If you install `Python` extension on VScode, Vscode will ask if you want to install the program below. Press `yes`.

```shell
python3 -m pip install pylint black isort
```

```shell
pylint --generate-toml-config >> pyproject.toml
```

## VS Code

### Extension

- [Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python)
- [Pylance](https://marketplace.visualstudio.com/items?itemName=ms-python.vscode-pylance)
- [Black Formatter](https://marketplace.visualstudio.com/items?itemName=ms-python.black-formatter)
- [isort](https://marketplace.visualstudio.com/items?itemName=ms-python.isort)
- [Jupyter](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter)
- [Python Docstring Generator](https://marketplace.visualstudio.com/items?itemName=njpwerner.autodocstring)
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
  "editor.bracketPairColorization.enabled": true,
  "editor.formatOnSave": true,
  "editor.guides.bracketPairs": true,
  "git-graph.repository.fetchAndPrune": true,
  "git.pruneOnFetch": true,
  "[python]": {
    "editor.codeActionsOnSave": {
      "source.organizeImports": true
    },
    "editor.defaultFormatter": "ms-python.black-formatter",
    "editor.insertSpaces": true,
    "editor.tabSize": 4
  },
  "python.analysis.autoImportCompletions": false,
  "python.analysis.typeCheckingMode": "basic",
  "python.formatting.provider": "black",
  "python.languageServer": "Pylance",
  "python.linting.pylintEnabled": true,
  "isort.args": ["--profile", "black"],
  "vim.useSystemClipboard": true,
```

## Manually check and format

### Style check

```shell
pylint **/*.py
```

### Auto formmat

```shell
black .
```
