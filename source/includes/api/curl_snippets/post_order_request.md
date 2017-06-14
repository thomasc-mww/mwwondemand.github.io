```shell
curl -X "POST" "http://api.mwwondemand.com/api/orders" \
  -H "Accept: application/vnd.api+json; version=1" \
  -H "Authorization: auth-key=YOUR_API_KEY" \
  -H "Content-Type: application/vnd.api+json" \
  -d $'{
 "data": {
    "type": "orders",
    "attributes": {
      "vendor-po": "1467988109",
      "shipping-method": "SAMPLE",
      "shipping-account-number": "1234"
    }
  },
  "included": [
    {
      "type": "shipping-address",
      "attributes": {
      "name": "Phillip J. Fry",
      "address": "123 Green St.\nSuite 321",
        "city": "New New York",
        "state": "NY",
        "postal-code": "10012"
      }
    },
    {
      "type": "billing-address",
      "attributes": {
      "name": "Hubert Farnsworth",
      "address": "123 Green St.\nSuite 321",
        "city": "New New York",
        "state": "NY",
        "postal-code": "10012"
      }
    },
    {
      "type": "return-address",
      "attributes": {
      "name": "Bender B. Rodriguez",
      "address": "123 Green St.\nSuite 321",
        "city": "New New York",
        "state": "NY",
        "postal-code": "10012"
      }
    },
    {
      "type": "line-items",
      "attributes": {
        "line-number": 1,
        "quantity": 2,
        "description": "It\'s not sò fluffy!",
        "product-code": "PRT-GEN-ZOH99",
        "item-properties": {
          "thread-color": "white"
        },
        "designs": [
          {
            "image-remote-url": "http://images.apple.com/v/home/cj/images/promos/ipad_pro_large.jpg"
          }
        ]
      }
    },
    {
      "type": "line-items",
      "attributes": {
        "line-number": 2,
        "quantity": 5,
        "description": "Velour Vest",
        "product-code": "PRT-GEN-XOH99",
        "item-properties": {
          "thread-color": "white"
        },
        "designs": [
          {
            "image-remote-url": "http://images.apple.com/v/home/cj/images/heros/iphone-6s-change_xlarge.jpg"
          }
        ]
      }
    },
    {
      "type": "packing-list",
      "attributes": {
        "url": "http://www.akapparel.com/assets/production-pdf/110-160511-050-2.pdf"
       }
      },
      {
      "type": "shipping-label",
      "attributes": {
       "url": "https://hellofabric.com/assets/mww/orders/86667297/56d712af0897d-86667297-MWWA1411.png"
      }
    }
  ]
}'
```
