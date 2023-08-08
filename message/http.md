## HTTP Response

### V1

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

### V2

HTTP Status는 아래 5가지만 사용하며, 401, 403, 404, 429로 나타낼 수 없는 에러는 400으로 처리합니다.

- 400 Bad Request
- 401 Unauthorized: 인증(Authentication) 실패
- 403 Forbidden: 인가(Authorization) 실패
- 404 Not Found: 리소스를 찾을 수 없음
- 429 Too Many Requests

```json
{
  "status": 400,
  "errors": [
    {
      "code": 1,
      "message": "validation error"
    }
  ]
}
```

- `code`: `int`, 사전 정의된 에러 코드
- `message`: `string`, 사람이 식별할 수 있는 에러 메시지