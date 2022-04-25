## Git 브랜치 전략

### Branch name convention

- `feat/<feature-name>`: 새로운 기능
- `fix/<fix-name>`: 버그 수정
- `chore/<chore-name>`: 기타
- `hotfix/<hotfix-name>`: main에 바로 적용해야 하는 버그 수정
- `release/<version>`: staging

### Version

v로 시작하는 시맨틱 버저닝 2.0 사용 ex) `v1.0.0-beta.1`

### dev

```shell
git remote update --prune
```

```shell
git checkout -b <branch> origin/dev
```

작업 진행 -> PR to `origin/dev` -> merge 방식은 각 repo 규칙에 따름 
- Squash and merge (title: `<type>: <name> (#<PR-number>)`)
- Merge pull request (title: `<type>: <name> (#<PR-number>)`)
- Rebase and merge (title: `<type>: <name> (#<PR-number>)`)

### release(stag)

```shell
git remote update --prune
```

```shell
git checkout -b release/<version> origin/dev
```

```shell
git commit --allow-empty -m "release: <version>-rc.1"
```

- rc: Release Candidates, rc.1 -> rc.2 순으로 진행합니다.

```shell
git push -u origin release/<version>
```

### main

PR from `origin/release/<version>` to `origin/main` -> Merge pull request(title: `release: <version> (#<PR-number>)`)

```shell
git remote update --prune
```

```shell
git checkout origin/main
```

```shell
git tag <version>
```

```shell
git push --tags
```

Github 사이트 해당 Repo -> Releases -> Tags -> Create release -> Auto-generate release notes -> Publish release

### hotfix

```shell
git remote update --prune
```

```shell
git checkout -b hotfix/<hotfix-name> origin/main
```

작업 진행 -> PR to `origin/main` -> merge 방식은 각 repo 규칙에 따름 
- Squash and merge (title: `<type>: <name> (#<PR-number>)`)
- Merge pull request (title: `<type>: <name> (#<PR-number>)`)
- Rebase and merge (title: `<type>: <name> (#<PR-number>)`)

```shell
git remote update --prune
```

```shell
git checkout origin/main
```

```shell
git tag <version>
```

```shell
git push --tags
```

PR `origin/main` to `origin/dev` -> Merge pull request(title: `hotfix: <name> (#<PR-number>)`)

Github 사이트 해당 Repo -> Releases -> Tags -> Create release -> Auto-generate release notes -> Publish release
