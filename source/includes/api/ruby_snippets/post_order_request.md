```ruby
require 'net/http'

# Create Order (POST )
def send_request
  uri = URI('https://api.mwwondemand.com/api/orders')

  # Create client
  http = Net::HTTP.new(uri.host, uri.port)
  body = '{
  "data": {
     "type": "orders",
     "attributes": {
       "vendor-po": "14679881309",
       "shipping-method": "SAMPLE",
       "shipping-account-number": "1234"
     }
   },
   "included": [
     {
       "type": "shipping-address",
       "attributes": {
       "name": "Phillip J. Fry",
       "address": "123 Green St.\nSuite 321",
         "city": "New New York",
         "state": "NY",
         "postal-code": "10012"
       }
     },
     {
       "type": "billing-address",
       "attributes": {
       "name": "Hubert Farnsworth",
       "address": "123 Green St.\nSuite 321",
         "city": "New New York",
         "state": "NY",
         "postal-code": "10012"
       }
     },
     {
       "type": "return-address",
       "attributes": {
       "name": "Bender B. Rodriguez",
       "address": "123 Green St.\nSuite 321",
         "city": "New New York",
         "state": "NY",
         "postal-code": "10012"
       }
     },
     {
       "type": "line-items",
       "attributes": {
         "line-number": 1,
         "quantity": 2,
         "description": "It\'s not sò fluffy!",
         "product-code": "3PF-SC6-SPFPI",
         "customer-product-code": "YOUR_UPC/SKU_NUMBER",
         "item-properties": {
           "thread-color": "white"
         },
         "designs": [
           {
             "image-remote-url": "http://images.apple.com/v/home/cj/images/promos/ipad_pro_large.jpg"
           }
         ]
       }
     },
     {
       "type": "line-items",
       "attributes": {
         "line-number": 2,
         "quantity": 5,
         "description": "Velour Vest",
         "product-code": "3PF-SC6-SPFPI",
         "customer-product-code": "YOUR_UPC/SKU_NUMBER",
         "item-properties": {
           "thread-color": "white"
         },
         "designs": [
           {
             "image-remote-url": "http://images.apple.com/v/home/cj/images/heros/iphone-6s-change_xlarge.jpg"
           }
         ]
       }
     },
     {
       "type": "packing-list",
       "attributes": {
         "url": "http://www.akapparel.com/assets/production-pdf/110-160511-050-2.pdf"
        }
       },
       {
       "type": "shipping-label",
       "attributes": {
        "url": "https://hellofabric.com/assets/mww/orders/86667297/56d712af0897d-86667297-MWWA1411.png"
       }
     }
   ]

}'

  # Create Request
  #http.use_ssl = true
  req =  Net::HTTP::Post.new(uri)
  # Add headers
  req["Accept"] = "application/vnd.api+json; version=1"
  # Add headers
  req.add_field "Authorization", "auth-key=YOUR_API_KEY"
  # Add headers
  req["Content-Type"] = "application/vnd.api+json"
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
