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
            data="{
 'data': {
    'type': 'orders',
    'attributes': {
      'vendor-po': '1480697715',
      'shipping-method': 'SAMPLE',
      'shipping-account-number': '1234'
    }
  },
  'included': [
    {
      'type': 'shipping-address',
      'attributes': {
	'name': 'Phillip J. Fry',
     	'address': '123 Green St.\\nSuite 321',
      	'city': 'New New York',
      	'state': 'NY',
      	'postal-code': '10012'
      }
    },
    {
      'type': 'billing-address',
      'attributes': {
	'name': 'Hubert Farnsworth',
     	'address': '123 Green St.\\nSuite 321',
      	'city': 'New New York',
      	'state': 'NY',
      	'postal-code': '10012'
      }
    },
    {
      'type': 'return-address',
      'attributes': {
	'name': 'Bender B. Rodriguez',
     	'address': '123 Green St.\\nSuite 321',
      	'city': 'New New York',
      	'state': 'NY',
      	'postal-code': '10012'
      }
    },
    {
      'type': 'line-items',
      'attributes': {
        'line-number': 1,
        'quantity': 2,
        'description': 'It's not sò fluffy!',
        'product-code': '3PF-PSY-SQPGZ2C',
        'item-properties': {
          'thread-color': 'white',
          'blah': 'blah-2'
        },
        'designs': [
          {
            'image_remote_url': 'http://images.apple.com/v/home/cj/images/promos/ipad_pro_large.jpg',
            'position': 'centered',
            'crop': 'left'
          }
        ]
      }
    },
    {
      'type': 'line-items',
      'attributes': {
        'line-number': 2,
        'quantity': 5,
        'description': 'It's sò fluffy!',
        'product-code': '3PF-PJT-SLPG4CW',
        'item-properties': {
          'thread-color': 'white',
          'blah': 'blah-2'
        },
        'designs': [
          {
            'image_remote_url': 'http://images.apple.com/v/home/cj/images/heros/iphone-6s-change_xlarge.jpg'
          }
        ]
      }
    },
    {
      'type': 'packing-list',
       'attributes': {
	'url': 'http://www.akapparel.com/assets/production-pdf/110-160511-050-2.pdf'
       }
      },
      {
         'type': 'shipping-label',
   	  'attributes': {
	     'url': 'https://hellofabric.com/assets/mww/orders/86667297/56d712af0897d-86667297-MWWA1411.png'
	  }

      }
  ]
}"
        )
        print('Response HTTP Status Code: {status_code}'.format(
            status_code=response.status_code))
        print('Response HTTP Response Body: {content}'.format(
            content=response.content))
    except requests.exceptions.RequestException:
        print('HTTP Request failed')
```
