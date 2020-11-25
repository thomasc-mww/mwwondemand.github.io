```text
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8
```
```json
{
  "data": {
    "id": "568129875827754040",
    "type": "orders",
    "links": {
      "self": "https://api.mwwondemand.com/api/orders/568129875827754040"
    },
    "attributes": {
      "created-at": "2016-07-07T20:53:02.578Z",
      "updated-at": "2016-07-07T20:53:02.578Z",
      "state": "received",
      "shipping-method": "SAMPLE",
      "shipping-account-number": "1234",
      "vendor-po": "1467924781"
    },
    "relationships": {
      "line-items": {
        "links": {
          "self": "https://api.mwwondemand.com/api/orders/568129875827754040/relationships/line-items",
          "related": "https://api.mwwondemand.com/api/orders/568129875827754040/line-items"
        }
      },
      "line-item-views": {
        "links": {
          "self": "https://api.mwwondemand.com/api/orders/568129875827754040/relationships/line-item-views",
          "related": "https://api.mwwondemand.com/api/orders/568129875827754040/line-item-views"
        }
      },
      "user": {
        "links": {
          "self": "https://api.mwwondemand.com/api/orders/568129875827754040/relationships/user",
          "related": "https://api.mwwondemand.com/api/orders/568129875827754040/user"
        }
      },
      "packing-list": {
        "links": {
          "self": "https://api.mwwondemand.com/api/orders/568129875827754040/relationships/packing-list",
          "related": "https://api.mwwondemand.com/api/orders/568129875827754040/packing-list"
        }
      },
      "shipping-label": {
        "links": {
          "self": "https://api.mwwondemand.com/api/orders/568129875827754040/relationships/shipping-label",
          "related": "https://api.mwwondemand.com/api/orders/568129875827754040/shipping-label"
        }
      },
      "billing-address": {
        "links": {
          "self": "https://api.mwwondemand.com/api/orders/568129875827754040/relationships/billing-address",
          "related": "https://api.mwwondemand.com/api/orders/568129875827754040/billing-address"
        }
      },
      "shipping-address": {
        "links": {
          "self": "https://api.mwwondemand.com/api/orders/568129875827754040/relationships/shipping-address",
          "related": "https://api.mwwondemand.com/api/orders/568129875827754040/shipping-address"
        }
      }
    }
  }
}
```
