```shell
curl -X PATCH https://api.mwwondemand.com/api/webhooks/503678086298993748 \
  -H "Content-Type: application/vnd.api+json" \
  -H "Accept: application/vnd.api+json; version=1" \
  -H "Authorization: auth-key=YOUR_API_KEY"
  -d $'{
    "data": {
      "id": "503678086298993748",
      "type": "webhooks",
      "attributes": {
        "url": "https://your-server.com/mwwondemand-order-notifications",
        "enabled": true,
        "shipped": true
      }
    }
  }'

```
