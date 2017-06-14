```json
{
  "data": [
    {
      "id": "536862475937646298",
      "type": "orders",
      "links": {
        "self": "https://api.mwwondemand.com/api/orders/536862475937646298"
      },
      "attributes": {
        "created-at": "2016-04-26T20:53:19.530Z",
        "updated-at": "2016-05-25T17:30:17.855Z",
        "state": "received",
        "shipping-method": "SAMPLE",
        "shipping-account-number": "1234",
        "vendor-po": "1467924781"
      },
           "relationships": {
        "line-items": {
          "links": {
            "self": "https://api.mwwondemand.com/api/orders/536862475937646298/relationships/line-items",
            "related": "https://api.mwwondemand.com/api/orders/536862475937646298/line-items"
          }
        },
        "line-item-views": {
          "links": {
            "self": "https://api.mwwondemand.com/api/orders/536862475937646298/relationships/line-item-views",
            "related": "https://api.mwwondemand.com/api/orders/536862475937646298/line-item-views"
          }
        },
        "user": {
          "links": {
            "self": "https://api.mwwondemand.com/api/orders/536862475937646298/relationships/user",
            "related": "https://api.mwwondemand.com/api/orders/536862475937646298/user"
          }
        },
        "packing-list": {
          "links": {
            "self": "https://api.mwwondemand.com/api/orders/536862475937646298/relationships/packing-list",
            "related": "https://api.mwwondemand.com/api/orders/536862475937646298/packing-list"
          }
        },
        "shipping-label": {
          "links": {
            "self": "https://api.mwwondemand.com/api/orders/536862475937646298/relationships/shipping-label",
            "related": "https://api.mwwondemand.com/api/orders/536862475937646298/shipping-label"
          }
        },
        "billing-address": {
          "links": {
            "self": "https://api.mwwondemand.com/api/orders/536862475937646298/relationships/billing-address",
            "related": "https://api.mwwondemand.com/api/orders/536862475937646298/billing-address"
          }
        },
        "shipping-address": {
          "links": {
            "self": "https://api.mwwondemand.com/api/orders/536862475937646298/relationships/shipping-address",
            "related": "https://api.mwwondemand.com/api/orders/536862475937646298/shipping-address"
          }
        },
        "return-address": {
          "links": {
            "self": "https://api.mwwondemand.com/api/orders/536862475937646298/relationships/return-address",
            "related": "https://api.mwwondemand.com/api/orders/536862475937646298/return-address"
          }
        }
      }
    }
  ],
  "meta": {
    "page": {
      "total": 34
    }
  },
  "links": {
    "first": "https://api.mwwondemand.com/api/orders?page%5Blimit%5D=1&page%5Boffset%5D=0",
    "next": "https://api.mwwondemand.com/api/orders?page%5Blimit%5D=1&page%5Boffset%5D=1",
    "last": "https://api.mwwondemand.com/api/orders?page%5Blimit%5D=1&page%5Boffset%5D=33"
  }
}
```
