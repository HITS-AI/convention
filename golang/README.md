## Golang convension

### Golang 버전 관리

```shell
asdf plugin add golang
```

```shell
asdf list all golang
```

```shell
asdf install golang <version>
```

### Golang 프로젝트 관리

#### 프로젝트 생성

```shell
asdf local golang <version>
```

```shell
go mod init github.com/HITS-AI/<repository>[/<subdirectory>]
```

- `<subdirectory>`를 사용하는 경우 github tag를 `<subdirectory>/<sematicVersion>` 형식으로 생성해야 다른 프로젝트에서 설치할 수 있습니다.

`.gitignore`는 [생성 링크](https://www.toptal.com/developers/gitignore?templates=go,linux,macos,windows) 로  생성합니다.

#### 의존성 동기화

```shell
go mod tidy
```
