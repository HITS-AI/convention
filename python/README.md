# Python convention

## Installation

```shell
python3 -m pip install pylint black
```

Download `python/.pylintrc` and save it to a project root path.

ex)

```shell
<project>
├── ...
├── .pylintrc
└── ...
```

## VS Code

- Press Ctrl(Command) + Shift + P
- Find `>Preferences: Open Settings (JSON)` option and select it

```json
  ...

  "python.formatting.blackArgs": ["--line-length", "80"],
  "python.formatting.provider": "black",
  "python.linting.pylintEnabled": true,

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
