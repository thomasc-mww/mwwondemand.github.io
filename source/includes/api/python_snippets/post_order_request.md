```python
# Install the Python Requests library:
# `pip install requests`

import requests


def send_request():
    # Create Order
    # POST https://api.mwwondemand.com/api/orders

    try:
        response = requests.post(
            url="https://api.mwwondemand.com/api/orders",
            headers={
                "Content-Type": "application/vnd.api+json",
                "Authorization": "auth-key=YOUR_API_KEY",
                "Accept": "application/vnd.api+json; version=1",
            },
            data=
            """{
         "data": {
            "type": "orders",
            "attributes": {
              "vendor-po": "14679881092",
              "shipping-method": "SAMPLE",
              "shipping-account-number": "1234",
              "test-order": "test"
            }
          },
          "included": [
            {
              "type": "shipping-address",
              "attributes": {
                "name": "Phillip J. Fry",
                "address1": "123 Green St.",
                "address2": "Suite 321",
                "city": "New New York",
                "state": "NY",
                "country": "US",
                "postal-code": "10012",
                "email": "bob@dobalina.net",
                "phone": "8288888888"
              }
            },
            {
              "type": "billing-address",
              "attributes": {
                "name": "Hubert Farnsworth",
                "address1": "123 Green St.",
                "address2": "Suite 321",
                "city": "New New York",
                "state": "NY",
                "country": "US",
                "postal-code": "10012",
                "email": "bob@dobalina.net",
                "phone": "8288888888"
              }
            },
            {
              "type": "line-items",
              "attributes": {
                "line-number": 1,
                "quantity": 2,
                "description": "It\'s not so fluffy!",
                "product-code": "3PF-SC6-SPFPI",
                "customer-product-code": "YOUR_UPC/SKU_NUMBER",
                "item-properties": {
                  "thread-color": "white",
                  "hs-code": "1234.56.789"
                },
                "designs": [
                  {
                    "image-remote-url": "https://static.pexels.com/photos/39803/pexels-photo-39803.jpeg"
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
                "product-code": "3PF-SC6-SPFPI",
                "customer-product-code": "YOUR_UPC/SKU_NUMBER",
                "item-properties": {
                  "thread-color": "white"
                },
                "designs": [
                  {
                    "image-remote-url": "http://www.publicdomainpictures.net/pictures/10000/velka/orange-871282749123hSB3.jpg"
                  }
                ]
              }
            },
            {
              "type": "packing-list",
              "attributes": {
                "url": "https://dllc.appstate.edu/sites/dllc.appstate.edu/files/SearchCCimages.pdf"
               }
              },
              {
              "type": "shipping-label",
              "attributes": {
               "url": "https://upload.wikimedia.org/wikipedia/commons/0/04/Einschreiben-Label_Deutsche_Post_2011.jpg"
              }
            }
          ]
        }"""
        )
        print('Response HTTP Status Code: {status_code}'.format(
            status_code=response.status_code))
        print('Response HTTP Response Body: {content}'.format(
            content=response.content))
    except requests.exceptions.RequestException as e:
        print(e)
```
