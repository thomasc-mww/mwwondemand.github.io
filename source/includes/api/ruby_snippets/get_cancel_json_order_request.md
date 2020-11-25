```ruby
require 'net/http'

# Create Order (POST )
def send_request
  uri = URI('https://api.mwwondemand.com/api/orders')

  # Create client
  http = Net::HTTP.new(uri.host, uri.port)

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
  req.body = '{
  "data": {
     "type": "orders",
     "attributes": {
       "vendor-po": "14679881309",
       "shipping-method": "SAMPLE",
       "shipping-account-number": "1234",
       "test-order": "test"
     }
   }
  }'

  # Fetch Request
  res = http.request(req)
  puts "Response HTTP Status Code: #{res.code}"
  puts "Response HTTP Response Body: #{res.body}"
rescue StandardError => e
  puts "HTTP Request failed (#{e.message})"
end
```
