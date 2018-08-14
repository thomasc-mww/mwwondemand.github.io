```text
HTTPS/1.1 201 Created
Content-Type: application/vnd.api+json
ETag: W/"a3c86d6fc9e44e75887b996cafc57b37"
Cache-Control: max-age=0, private, must-revalidate
```

```json
{
  "data": {
    "id": "503678086298993748",
    "type": "webhooks",
    "links": {
      "self": "https://api.mwwondemand.com/api/webhooks/503678086298993748"
    },
    "attributes": {
      "created-at": "2016-04-09T22:38:50.426Z",
      "updated-at": "2016-04-09T22:38:50.426Z",
      "url": "https://your-server.com/order-notifications",
      "enabled": false,
      "received": false,
      "shipped": false
    },
    "relationships": {
      "user": {
        "links": {
          "self": "https://api.mwwondemand.com/api/webhooks/503678086298993748/relationships/user",
          "related": "https://api.mwwondemand.com/api/webhooks/503678086298993748/user"
        }
      }
    }
  }
}
```
