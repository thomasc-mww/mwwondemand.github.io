```ruby
require 'net/http'

# Get Validate token (GET )
def send_request
  uri = URI('https://api.mwwondemand.com/api/validate_token')

  # Create client
  http = Net::HTTP.new(uri.host, uri.port)

  # Create Request
  req =  Net::HTTP::Get.new(uri)
  # Add headers
  req.add_field "Content-Type", "application/vnd.api+json"
  # Add headers
  req.add_field "Authorization", "application/vnd.api+json; version=1"
  # Add headers
  req.add_field "Accept", "application/vnd.api+json; version=1"

  # Fetch Request
  res = http.request(req)
  puts "Response HTTP Status Code: #{res.code}"
  puts "Response HTTP Response Body: #{res.body}"
rescue StandardError => e
  puts "HTTP Request failed (#{e.message})"
end
```
