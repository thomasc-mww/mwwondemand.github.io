```ruby
require 'net/http'

# Create Order (POST )
def send_request
  uri = URI('http://localhost:3000/api/orders')

  # Create client
  http = Net::HTTP.new(uri.host, uri.port)
  body = "{
 'data': {
    'type': 'orders',
    'attributes': {
      'vendor-po': '1480697676',
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
      'type': 'billing-address'
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

  # Create Request
  req =  Net::HTTP::Post.new(uri)
  # Add headers
  req.add_field "Content-Type", "application/vnd.api+json"
  # Add headers
  req.add_field "Authorization", "auth-key=S@mpl3!"
  # Add headers
  req.add_field "Accept", "application/vnd.api+json; version=1"
  # Set body
  req.body = body

  # Fetch Request
  res = http.request(req)
  puts "Response HTTP Status Code: #{res.code}"
  puts "Response HTTP Response Body: #{res.body}"
rescue StandardError => e
  puts "HTTP Request failed (#{e.message})"
end
```
