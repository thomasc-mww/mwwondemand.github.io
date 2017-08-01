```php
<?php

// Get cURL resource
$ch = curl_init();

// Set url
curl_setopt($ch, CURLOPT_URL, 'http://localhost:3000/api/orders');

// Set method
curl_setopt($ch, CURLOPT_CUSTOMREQUEST, 'POST');

// Set options
curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);

// Set headers
curl_setopt($ch, CURLOPT_HTTPHEADER, [
  "Content-Type: application/vnd.api+json",
  "Authorization: auth-key=S@mpl3!",
  "Accept: application/vnd.api+json; version=1",
 ]
);
// Create body
$body = "{
 'data': {
    'type': 'orders',
    'attributes': {
      'vendor-po': '1480697743',
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
}";

// Set body
curl_setopt($ch, CURLOPT_POST, 1);
curl_setopt($ch, CURLOPT_POSTFIELDS, $body);

// Send the request & save response to $resp
$resp = curl_exec($ch);

if(!$resp) {
  die('Error: "' . curl_error($ch) . '" - Code: ' . curl_errno($ch));
} else {
  echo "Response HTTP Status Code : " . curl_getinfo($ch, CURLINFO_HTTP_CODE);
  echo "\nResponse HTTP Body : " . $resp;
}

// Close request to clear up some resources
curl_close($ch);
```
