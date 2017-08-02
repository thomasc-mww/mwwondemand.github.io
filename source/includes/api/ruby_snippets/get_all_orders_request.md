```ruby
require 'net/http'

# Get All Orders (GET )
def send_request
  uri = URI('https://api.mwwondemand.com/api/orders')

  # Create client
  http = Net::HTTP.new(uri.host, uri.port)

  # Create Request
  req =  Net::HTTP::Get.new(uri)
  # Add headers
  req.add_field "Accept", "application/vnd.api+json; version=1"
  # Add headers
  req.add_field "Authorization", "auth-key=YOUR_API_KEY"
  # Add headers
  req.add_field "Content-Type", "application/vnd.api+json"

  # Fetch Request
  res = http.request(req)
  puts "Response HTTP Status Code: #{res.code}"
  puts "Response HTTP Response Body: #{res.body}"
rescue StandardError => e
  puts "HTTP Request failed (#{e.message})"
end
```
