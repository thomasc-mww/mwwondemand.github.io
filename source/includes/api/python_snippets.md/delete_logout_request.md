```python
# Install the Python Requests library:
# `pip install requests`

import requests


def send_request():
    # Request (11)
    # DELETE https://api.mwwondemand.com/api/logout

    try:
        response = requests.delete(
            url="https://api.mwwondemand.com/api/logout",
            headers={
                "Content-Type": "application/vnd.api+json",
                "Authorization": "auth-key=S@mpl3!",
                "Accept": "application/vnd.api+json;version=1",
            },
        )
        print('Response HTTP Status Code: {status_code}'.format(
            status_code=response.status_code))
        print('Response HTTP Response Body: {content}'.format(
            content=response.content))
    except requests.exceptions.RequestException:
        print('HTTP Request failed')
```
