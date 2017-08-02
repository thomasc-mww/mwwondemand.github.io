```python
# Install the Python Requests library:
# `pip install requests`

import requests


def send_request():
    # Get Validate token
    # GET https://api.mwwondemand.com/api/validate_token

    try:
        response = requests.get(
            url="https://api.mwwondemand.com/api/validate_token",
            headers={
                "Content-Type": "application/vnd.api+json",
                "Authorization": "application/vnd.api+json; version=1",
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
