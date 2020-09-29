```python
# Install the Python Requests library:
# `pip install requests`

import requests


def send_request():
    # Get Webhooks
    # GET https://api.mwwondemand.com/api/webhooks

    try:
        response = requests.get(
            url="https://api.mwwondemand.com/api/webhooks",
            headers={
                "Content-Type": "application/vnd.api+json",
                "Authorization": "<BEARER_TOKEN>",
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
