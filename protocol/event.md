## Event & Command

### V1

```json
{
  "specversion": "1.0",
  "type": "aidocking.submit.v1",
  "source": "https://api.oneplatform.hits.ai/ai-docking/<project-id>/submit",
  "id": "2c04c116-19c2-4b59-857e-2f0396ad0e98",
  "time": "2022-07-02T21:59:07.975Z",
  "user_id": "1",
  "request_id": "8570baa3-666b-4b6b-9158-6643208354a6",
  "datacontenttype": "application/json",
  "data": {
    "key1": "value1",
    "key2": "value2"
  }
}
```

https://github.com/cloudevents/spec/blob/v1.0.2/cloudevents/spec.md 의 형식을 따르되 추적을 위해 `user_id`와 `request_id`가 추가되었습니다.

- `specversion`: `"1.0"`, CloudEvents spec version
- `type`: `string`, 이벤트를 구분할 수 있는 태그를 `.`으로 연결하여 표현한 값입니다.
- `source`: `URI`, 이벤트가 발생한 위치
- `id`: `UUID`, 이벤트 고유 번호로 이벤트를 생성할 때 같이 생성해주면 됩니다.
- `time`: `RFC3339, ISO8601`, 이벤트 생성 시간
- `user_id`: `string`, 요청한 유저 ID
- `request_id`: `UUID`, 요청의 흐름을 파악하기 위한 값
- `datacontenttype`: `data`를 해석하는 방법
- `data`: 이벤트를 처리하기위한 도메인 정보

CloudEvents 스펙에서는 일반적으로 이벤트 크기가 64KB 이하로 제한되었을 때, 안전하게 전달될 수 있다고 명시하고 있습니다.

### V1.1

protobuf로 정의된 스키마를 사용합니다.

- https://github.com/HITS-AI/schema/blob/main/proto/hschema/event/event_v1.proto

기존 JSON과 호환성을 위해 Consumer는 protobuf 스키마를 사용하고, Producer는 JSON 스키마를 사용합니다.
관련 Consumer가 protobuf를 사용하게 되면 Producer도 protobuf를 사용하는 방식으로 변경합니다.

#### Golang

```shell
go env -w GOPRIVATE=github.com/HITS-AI
```

```shell
export VERSION=<version>
```

```shell
go get github.com/HITS-AI/schema/gen/go@$VERSION
```

#### Python

```shell
export VERSION=<version>
```

```shell
poetry add git+ssh://github.com/HITS-AI/schema.git@gen/python/$VERSION#subdirectory=gen/python
```