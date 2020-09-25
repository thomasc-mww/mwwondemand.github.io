```ruby
require 'net/http'

# Update Shipping Address (PATCH)
def send_request
  shipping_address_id = "1674068325472142392"
  uri = URI("https://api.mwwondemand.com/api/shipping-addresses/#{shipping_address_id}")

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
     "id": "1674068325472142392",
     "type": "shipping-addresses",
     "attributes": {
       "name": "Test User",
       "address1": "5757 Howard Gap Rd.",
       "address2": "",
       "city": "Hendersonville",
       "state": "NC",
       "postal-code": 28792,
       "country": "US",
       "phone": "555-555-5555",
       "email": "user@mwwwondemand.com"
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
