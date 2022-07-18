## HTTP Response

4XX를 표현할 때, 상태 코드만으로 표현하기 어려운 정보가 있습니다. 400, 401, 403 등과 같이 최대한 표현 가능한 상태 코드를 고르고, 본문에 아래와 같이 사전 정의된 에러 코드를 통해 클라이언트가 에러를 올바르게 처리할 수 있도록 협의하는 것이 좋습니다.

```json
{
  "error": {
    "code": 1,
    "message": "Invalid Argument"
  }
}
```

- `code`: `int`, 사전 정의된 에러 코드
- `message`: `string`, 사람이 식별할 수 있는 에러 메시지
- 기타 필요한 정보는 Optional

## Event & Command

```json
{
  "specversion": "1.0",
  "type": "aidocking.submit.v1",
  "source": "https://api.oneplatform.hits.ai/ai-docking/<project-id>/submit",
  "id": "2c04c116-19c2-4b59-857e-2f0396ad0e98",
  "time": "2022-07-02T21:59:07.975+0900",
  "user_id": 1,
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
- `user_id`: `int`, 요청한 유저 ID
- `request_id`: `UUID`, 요청의 흐름을 파악하기 위한 값
- `datacontenttype`: `data`를 해석하는 방법
- `data`: 이벤트를 처리하기위한 도메인 정보

CloudEvents 스펙에서는 일반적으로 이벤트 크기가 64KB 이하로 제한되었을 때, 안전하게 전달될 수 있다고 명시하고 있습니다.
