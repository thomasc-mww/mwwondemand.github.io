```python
# Install the Python Requests library:
# `pip install requests`

import requests

def send_request():
  # api_user Login API KEY
  # POST https://api.mwwondemand.com/api/login

    try:
        response = requests.post(
            url="https://api.mwwondemand.com/api/login",
            headers={
                "Content-Type": "application/vnd.api+json",
                "Authorization": "auth-key=S@mpl3!",
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
