## Workflow(Action)

### Name

```yaml
name: <workflowName>
```

`<workflowName>`은 사람이 식별할 수 있는 이름과 bot이 식별하기 위한 태그로 구성됩니다. 태그는 `[<tag>]`형식으로 추가하면 됩니다. 예를 들어 `Backend Auth CD [hits.ai/cd][hits.ai/dev]`와 같이 작성할 수 있습니다.

- `<tag>`
  - `hits.ai/cd`
  - `hits.ai/dev`
  - `hits.ai/stag`
  - `hits.ai/prod`