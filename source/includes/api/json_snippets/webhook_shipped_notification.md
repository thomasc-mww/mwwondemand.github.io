



```ruby
# Notification for shipped order

{
  "data": {
    "id": "501323962228147713",
    "type": "mwwondemand-order-notifications",
    "attributes": {
      "event": "Shipped",
      "title": "Order Shipped",
      "description": "You have a webhook notice",
      "timestamp": "2016-04-06T16:41:36.895Z"
    },
    "relationships": {
      "mwwondemand-order": {
        "data": {
          "id": "501323961548670462",
          "type": "mwwondemand-orders"
        }
      },
      "mwwondemand-order-items": {
        "data": [
          {
            "id": "501323961934546431",
            "type": "mwwondemand-order-items"
          }
        ]
      }
    }
  },
  "included": {
    "mwwondemand-orders": [
      {
        "id": "501323961548670462",
        "type": "mwwondemand-orders",
        "attributes": {
          "vendor-po": "501323961548670462",
          "state": "received"
        }
      }
    ],
    "mwwondemand-order-items": [
      {
        "id": "501323961934546431",
        "type": "mwwondemand-order-items",
        "attributes": {
          "state": "received",
          "product-code": "254",
          "line-number": 1,
          "quantity": 1
        },
        "meta": {
          "received": 1,
          "not-valid": 0,
          "shipped": 0,
          "cancelled": 0,
          "printed": 0,
          "pressed": 0,
          "cut": 0,
          "sewn": 0,
          "turned": 0,
          "packed": 0
        }
      }
    ]
  },
  "links": {
    "callback": "https://api.mwwondemand.com/mwwondemand-orders",
    "mwwondemand-api": "https://api.mwwondemand.com",
    "webhook": "https://api.mwwondemand.com/webhooks/501323961246680573"
  },
  "meta": {
    "mwwondemand-api": {
      "version": 1
    }
  },
  "jsonapi": {
    "version": "1.0"
  }
}
```
