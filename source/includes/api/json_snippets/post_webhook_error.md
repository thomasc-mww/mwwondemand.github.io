```text
HTTP/1.1 422 Unprocessable Entity
Content-Type: application/vnd.api+json
```

```json
{
  "errors": [
    {
      "title": "has already been taken",
      "detail": "user-id - has already been taken",
      "code": 100,
      "source": {
        "pointer": "/data/attributes/user-id"
      },
      "status": "422"
    }
  ]
}
```
