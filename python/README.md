## Python convention

### Python 빌드 의존성

```shell
sudo apt install -y build-essential libssl-dev zlib1g-dev \
    libbz2-dev libreadline-dev libsqlite3-dev curl \
    libncursesw5-dev xz-utils tk-dev libxml2-dev libxmlsec1-dev libffi-dev liblzma-dev
```

```shell
brew install openssl readline sqlite3 xz zlib tcl-tk
```

### Python 버전 관리

```shell
asdf plugin add python
```

```shell
asdf list all python | grep ^3\.
```

```shell
asdf install python <version>
```

### Poetry 가상환경 관리

#### 설치

- https://python-poetry.org/docs/#installing-with-the-official-installer

```shell
asdf shell python system
```

```shell
curl -sSL https://install.python-poetry.org | python3 -
```

`.bashrc`, `.zshrc` 등에 아래 내용 추가합니다.

```shell
export PATH=$HOME/.local/bin:$PATH
```

Poetry는 가상환경을 프로젝트 내부에 생성하도록 설정을 변경합니다.

```shell
poetry config virtualenvs.in-project true
```

#### 가상환경 생성

```shell
asdf local python <version>
```

```shell
poetry init
```

#### 가상환경 활성화

```shell
poetry env use `asdf which python`
```

```shell
poetry shell
```

#### 의존성 추가

- https://python-poetry.org/docs/managing-dependencies/

```shell
poetry add <package>
```

#### 의존성 동기화

```shell
poetry install --sync
```
