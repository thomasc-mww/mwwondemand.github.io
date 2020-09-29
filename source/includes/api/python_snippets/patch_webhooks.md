```python
# Install the Python Requests library:
# `pip install requests`

import requests


def send_request():
    # Patch Webhook
    # PATCH https://api.mwwondemand.com/api/webhooks/

    try:
        response = requests.patch(
            url="https://api.mwwondemand.com/api/webhooks/",
            headers={
                "Content-Type": "application/vnd.api+json",
                "Authorization": "<BEARER_TOKEN>",
                "Accept": "application/vnd.api+json; version=1",
            },
            data="{
  \"data\": {
    \"id\": \"\",
    \"type\": \"webhooks\",
    \"attributes\": {
      \"url\": \"http://localhost:3001/mwwondemand-order-notifications\",
      \"printed\": true,
      \"pressed\": true,
      \"cut\": true,
      \"sewn\": true,
      \"turned\": true,
      \"packed\": true
    }
  }
}"
        )
        print('Response HTTP Status Code: {status_code}'.format(
            status_code=response.status_code))
        print('Response HTTP Response Body: {content}'.format(
            content=response.content))
    except requests.exceptions.RequestException:
        print('HTTP Request failed')
```
