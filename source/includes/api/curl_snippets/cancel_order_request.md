```shell
curl -X "PATCH" "https://api.mwwondemand.com/api/orders/:id/" \
  -H "Accept: application/vnd.api+json;version=1" \
  -H "Authorization: auth-key=YOUR_API_KEY" \
  -H "Content-Type: application/vnd.api+json"
  -d $'{
    "data": {
      "type": "orders",
      "id": <YOUR_VENDOR_PO/ORDER_ID>
      "attributes": {
        "request": "cancel"
        }
      }
    }'
```
