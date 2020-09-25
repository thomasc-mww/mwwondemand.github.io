```python
# Install the Python Requests library:
# `pip install requests`

import requests


def send_request():
    # Update Shipping Address
    # PATCH https://api.mwwondemand.com/api/shipping-addresses/:id

    try:
        response = requests.post(
            url="https://api.mwwondemand.com/api/shipping-addresses/1674068325472142392",
            headers={
                "Content-Type": "application/vnd.api+json",
                "Authorization": "auth-key=YOUR_API_KEY",
                "Accept": "application/vnd.api+json; version=1",
            },
            data=
            """{
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
          },
        }"""
        )
        print('Response HTTP Status Code: {status_code}'.format(
            status_code=response.status_code))
        print('Response HTTP Response Body: {content}'.format(
            content=response.content))
    except requests.exceptions.RequestException as e:
        print(e)
```
