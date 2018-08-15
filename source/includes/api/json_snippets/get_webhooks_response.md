```text
HTTP/1.1 200 OK
Content-Type: application/vnd.api+json
ETag: W/"db50338caf58efd86513055a93bf1ebb"
Cache-Control: max-age=0, private, must-revalidate
```

```json
{
  "data": [
    {
      "id": "503678086298993748",
      "type": "webhooks",
      "links": {
        "self": "https://api.mwwondemand.com/api/webhooks/503678086298993748"
      },
      "attributes": {
        "created-at": "2016-04-09T22:38:50.426Z",
        "updated-at": "2016-04-09T23:35:18.364Z",
        "url": "https://your-server.com/mwwondemand-order-notifications",
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
  ],
  "meta": {
    "page": {
      "total": 1
    }
  },
  "links": {
    "first": "https://api.mwwondemand.com/api/webhooks?page%5Blimit%5D=10&page%5Boffset%5D=0",
    "last": "https://api.mwwondemand.com/api/webhooks?page%5Blimit%5D=10&page%5Boffset%5D=0"
  }
}
```
