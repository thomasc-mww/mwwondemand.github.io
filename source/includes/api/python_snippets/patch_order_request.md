```python
# Install the Python Requests library:
# `pip install requests`

import requests


def send_request():
    # Cancel Order
    # PATCH https://api.mwwondemand.com/api/orders/:id

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
            "id": <YOUR_PO_HERE>,
            "attributes": {
              "shipping-method": <YOUR_NEW_SHIP_METHOD>
            }
          }
        }"""
        print('Response HTTP Status Code: {status_code}'.format(
            status_code=response.status_code))
        print('Response HTTP Response Body: {content}'.format(
            content=response.content))
    except requests.exceptions.RequestException as e:
        print(e)
```
