```python
# Install the Python Requests library:
# `pip install requests`

import requests
import json


def send_request():
    # api_user Login JWT
    # POST https://api.mwwondemand.com/api/login

    try:
        response = requests.post(
            url="https://api.mwwondemand.com/api/login",
            headers={
                "Content-Type": "application/vnd.api+json",
                "Authorization": "Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyX2lkIjo2NDgzODcyODM1Njg4MjE1MjYsImV4cCI6MTQ4MDUxNzcyOX0.SijY04z68CwqQ6AV2N3cWSng6fQAl06zodWicym_uuY",
                "Accept": "application/vnd.api+json; version=1",
            },
            data=json.dumps({

            })
        )
        print('Response HTTP Status Code: {status_code}'.format(
            status_code=response.status_code))
        print('Response HTTP Response Body: {content}'.format(
            content=response.content))
    except requests.exceptions.RequestException:
        print('HTTP Request failed')
```
