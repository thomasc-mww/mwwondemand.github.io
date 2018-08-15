```python
# Install the Python Requests library:
# `pip install requests`

import requests


def send_request():
    # Get Line Item
    # GET https://api.mwwondemand.com/api/line_items/

    try:
        response = requests.get(
            url="https://api.mwwondemand.com/api/line_items/764805840312993036",
            headers={
                "Authorization": "auth-key=YOUR_API_KEY",
                "Accept": "application/vnd.api+json; version=1",
            },
        )
        print('Response HTTP Status Code: {status_code}'.format(
            status_code=response.status_code))
        print('Response HTTP Response Body: {content}'.format(
            content=response.content))
    except requests.exceptions.RequestException:
        print('HTTP Request failed')
```
