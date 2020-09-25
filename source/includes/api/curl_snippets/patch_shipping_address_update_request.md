```shell
curl -X PATCH https://api.mwwondemand.com/api/shipping-addresses/1674068325472142392 \
  -d '{
    "data": {
      "id": "1674068325472142392",
      "type": "shipping-addresses",
      "attributes": {
        "name": "Test User",
        "address1": "5757 Howard Gap Rd.",
        "address2": "",
        "city": "Hendersonville",
        "state": "NC",
        "postal-code": 28792,
        "country": "US",
        "phone": "555-555-5555",
        "email": "user@mwwwondemand.com"
      }
    }
  }' \
  -H "Content-Type: application/vnd.api+json" \
  -H "Accept: application/vnd.api+json; version=1" \
  -H "Authorization: auth-key=YOUR_API_KEY"
```
